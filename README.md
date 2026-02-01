<!DOCTYPE html>
<html lang="fr">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>ABB Crêpes – App</title>

<style>
/* ================= RESET ================= */
*{margin:0;padding:0;box-sizing:border-box}
body{font-family:Arial,Helvetica,sans-serif;background:#0b0b12;color:#f1f5f9}

/* ================= COLORS ================= */
:root{
 --bg:#0b0b12;
 --card:#141225;
 --accent:#8b5cf6;
 --accent2:#6d28d9;
 --green:#10b981;
 --orange:#f59e0b;
 --red:#ef4444;
 --text2:#94a3b8;
}

/* ================= LOGIN ================= */
#login{
 position:fixed;inset:0;
 display:flex;align-items:center;justify-content:center;
 background:#000;
}
.login-box{
 background:var(--card);
 padding:30px;
 border-radius:14px;
 width:320px;
 text-align:center;
}
.login-box h1{margin-bottom:10px}
.login-box input,select,button{
 width:100%;
 padding:12px;
 margin-top:10px;
 border-radius:8px;
 border:none;
}
.login-box button{
 background:linear-gradient(135deg,var(--accent),var(--accent2));
 color:#fff;font-weight:bold;cursor:pointer;
}
.error{color:var(--red);margin-top:10px}

/* ================= APP ================= */
#app{display:none;min-height:100vh}
header{
 background:var(--card);
 padding:12px 16px;
 display:flex;
 justify-content:space-between;
 align-items:center;
}
nav{
 background:#0f0d1c;
 padding:10px;
 display:flex;
 gap:10px;
}
nav button{
 flex:1;
 padding:10px;
 background:var(--card);
 color:#fff;
 border:none;
 border-radius:8px;
 cursor:pointer;
}
nav button.active{background:var(--accent)}

main{padding:15px}

/* ================= CARDS ================= */
.card{
 background:var(--card);
 padding:15px;
 border-radius:12px;
 margin-bottom:15px;
}
.card h3{margin-bottom:10px}

/* ================= LIST ================= */
.item{
 background:#0f0d1c;
 padding:10px;
 border-radius:8px;
 margin-bottom:8px;
 display:flex;
 justify-content:space-between;
 align-items:center;
}
.badge{
 padding:4px 10px;
 border-radius:20px;
 font-size:12px;
}
.pending{background:var(--orange)}
.progress{background:var(--accent)}
.completed{background:var(--green)}
.offline{background:#475569}

/* ================= MOBILE ================= */
@media(max-width:768px){
 nav{flex-direction:column}
}
</style>
</head>

<body>

<!-- ================= LOGIN ================= -->
<div id="login">
 <div class="login-box">
  <h1>🥞 ABB Crêpes</h1>
  <select id="role">
   <option value="admin">Admin</option>
   <option value="livreur">Livreur</option>
  </select>
  <select id="livreurSelect" style="display:none"></select>
  <input type="password" id="password" placeholder="Mot de passe">
  <button onclick="login()">Connexion</button>
  <div class="error" id="error"></div>
 </div>
</div>

<!-- ================= APP ================= -->
<div id="app">
<header>
 <strong id="userTitle">Admin</strong>
 <button onclick="logout()">Déconnexion</button>
</header>

<nav>
 <button onclick="view('dashboard')" class="active">Dashboard</button>
 <button onclick="view('livreurs')">Livreurs</button>
 <button onclick="view('commandes')">Commandes</button>
</nav>

<main id="content"></main>
</div>

<script>
/* ================= DATA ================= */
const ADMIN_PASS="admin";
const LIVREUR_PASS="livreur";

let user=null;

let data={
 livreurs:[],
 commandes:[]
};

/* ================= LOGIN ================= */
document.getElementById("role").onchange=()=>{
 document.getElementById("livreurSelect").style.display=
  role.value==="livreur"?"block":"none";
 refreshLivreurSelect();
};

function refreshLivreurSelect(){
 livreurSelect.innerHTML=data.livreurs.map(l=>
  `<option value="${l.id}">${l.name}</option>`
 ).join("");
}

function login(){
 error.textContent="";
 if(role.value==="admin"){
  if(password.value!==ADMIN_PASS){
   error.textContent="Mot de passe incorrect";
   return;
  }
  user={type:"admin"};
 }
 else{
  if(data.livreurs.length===0){
   error.textContent="Aucun livreur créé";
   return;
  }
  if(password.value!==LIVREUR_PASS){
   error.textContent="Mot de passe incorrect";
   return;
  }
  const id=+livreurSelect.value;
  user={type:"livreur",id};
 }
 login.style.display="none";
 app.style.display="block";
 document.getElementById("userTitle").textContent=user.type.toUpperCase();
 renderDashboard();
}

/* ================= NAV ================= */
function view(v){
 document.querySelectorAll("nav button").forEach(b=>b.classList.remove("active"));
 event.target.classList.add("active");
 if(v==="dashboard")renderDashboard();
 if(v==="livreurs")renderLivreurs();
 if(v==="commandes")renderCommandes();
}

/* ================= DASHBOARD ================= */
function renderDashboard(){
 content.innerHTML=`
 <div class="card">
  <h3>📊 Résumé</h3>
  <p>Livreurs : ${data.livreurs.length}</p>
  <p>Commandes : ${data.commandes.length}</p>
 </div>
 `;
}

/* ================= LIVREURS ================= */
function renderLivreurs(){
 if(user.type!=="admin"){renderDashboard();return;}
 content.innerHTML=`
 <div class="card">
  <h3>🚴 Livreurs</h3>
  <input id="lname" placeholder="Nom livreur">
  <button onclick="addLivreur()">Ajouter</button>
 </div>
 ${data.livreurs.map(l=>`
 <div class="item">
  ${l.name}
  <span class="badge ${l.status}">${l.status}</span>
 </div>`).join("")}
 `;
}

function addLivreur(){
 const name=lname.value.trim();
 if(!name)return;
 data.livreurs.push({id:Date.now(),name,status:"offline"});
 lname.value="";
 refreshLivreurSelect();
 renderLivreurs();
}

/* ================= COMMANDES ================= */
function renderCommandes(){
 content.innerHTML=`
 <div class="card">
  <h3>📦 Commandes</h3>
  ${user.type==="admin"?`
   <input id="cname" placeholder="Client">
   <button onclick="addCommande()">Ajouter</button>
  `:""}
 </div>
 ${data.commandes.map(c=>`
 <div class="item">
  ${c.client}
  <span class="badge ${c.status}">${c.status}</span>
 </div>`).join("")}
 `;
}

function addCommande(){
 const client=cname.value.trim();
 if(!client)return;
 data.commandes.push({id:Date.now(),client,status:"pending"});
 cname.value="";
 renderCommandes();
}

/* ================= LOGOUT ================= */
function logout(){
 location.reload();
}
</script>

</body>
</html>
