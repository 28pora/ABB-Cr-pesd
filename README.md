<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Avis Clients - ABB Crêpes</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #1a0033 0%, #2d1b4e 50%, #1a0033 100%);
            color: #e0e0e0;
            min-height: 100vh;
            padding: 20px;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
        }

        .header {
            text-align: center;
            margin-bottom: 40px;
            padding: 30px 20px;
            background: rgba(138, 43, 226, 0.1);
            border-radius: 20px;
            border: 2px solid rgba(138, 43, 226, 0.3);
        }

        .header h1 {
            font-size: 2.5em;
            color: #9d4edd;
            margin-bottom: 10px;
            text-shadow: 0 0 20px rgba(157, 78, 221, 0.5);
        }

        .header p {
            color: #b8b8b8;
            font-size: 1.1em;
        }

        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
            margin-bottom: 40px;
        }

        .stat-card {
            background: rgba(30, 30, 50, 0.8);
            padding: 25px;
            border-radius: 15px;
            border: 2px solid rgba(138, 43, 226, 0.3);
            text-align: center;
            transition: all 0.3s ease;
        }

        .stat-card:hover {
            transform: translateY(-5px);
            border-color: rgba(138, 43, 226, 0.6);
            box-shadow: 0 10px 30px rgba(138, 43, 226, 0.3);
        }

        .stat-number {
            font-size: 3em;
            color: #9d4edd;
            font-weight: bold;
            margin-bottom: 10px;
        }

        .stat-label {
            color: #b8b8b8;
            font-size: 1.1em;
        }

        .stars {
            color: #ffd700;
            font-size: 1.5em;
            margin: 10px 0;
        }

        .review-form {
            background: rgba(30, 30, 50, 0.8);
            padding: 30px;
            border-radius: 15px;
            border: 2px solid rgba(138, 43, 226, 0.3);
            margin-bottom: 40px;
        }

        .review-form h3 {
            color: #9d4edd;
            margin-bottom: 20px;
            font-size: 1.5em;
        }

        .form-group {
            margin-bottom: 20px;
        }

        .form-group label {
            display: block;
            margin-bottom: 8px;
            color: #b8b8b8;
            font-weight: 500;
        }

        .form-group input,
        .form-group textarea {
            width: 100%;
            padding: 12px;
            background: rgba(50, 50, 70, 0.5);
            border: 2px solid rgba(138, 43, 226, 0.3);
            border-radius: 10px;
            color: #e0e0e0;
            font-size: 1em;
            font-family: inherit;
        }

        .form-group textarea {
            min-height: 120px;
            resize: vertical;
        }

        .form-group input:focus,
        .form-group textarea:focus {
            outline: none;
            border-color: #9d4edd;
            box-shadow: 0 0 15px rgba(157, 78, 221, 0.3);
        }

        .rating-input {
            display: flex;
            gap: 10px;
            flex-direction: row-reverse;
            justify-content: flex-end;
            font-size: 2em;
        }

        .rating-input input {
            display: none;
        }

        .rating-input label {
            cursor: pointer;
            color: #555;
            transition: all 0.2s;
        }

        .rating-input label:hover,
        .rating-input label:hover ~ label,
        .rating-input input:checked ~ label {
            color: #ffd700;
        }

        .radio-group,
        .checkbox-group {
            display: flex;
            flex-wrap: wrap;
            gap: 15px;
            margin-top: 10px;
        }

        .radio-option,
        .checkbox-option {
            display: flex;
            align-items: center;
            padding: 12px 20px;
            background: rgba(50, 50, 70, 0.5);
            border: 2px solid rgba(138, 43, 226, 0.3);
            border-radius: 10px;
            cursor: pointer;
            transition: all 0.3s ease;
            min-width: 120px;
        }

        .radio-option:hover,
        .checkbox-option:hover {
            border-color: #9d4edd;
            background: rgba(138, 43, 226, 0.2);
        }

        .radio-option input,
        .checkbox-option input {
            margin-right: 10px;
            width: 18px;
            height: 18px;
            cursor: pointer;
            accent-color: #9d4edd;
        }

        .radio-option span,
        .checkbox-option span {
            color: #e0e0e0;
            font-size: 1em;
        }

        .scale-rating {
            display: flex;
            justify-content: space-between;
            gap: 10px;
            margin: 15px 0 10px 0;
        }

        .scale-option {
            flex: 1;
            text-align: center;
            cursor: pointer;
        }

        .scale-option input {
            display: none;
        }

        .scale-number {
            display: block;
            padding: 15px;
            background: rgba(50, 50, 70, 0.5);
            border: 2px solid rgba(138, 43, 226, 0.3);
            border-radius: 10px;
            color: #e0e0e0;
            font-size: 1.2em;
            font-weight: bold;
            transition: all 0.3s ease;
        }

        .scale-option:hover .scale-number {
            border-color: #9d4edd;
            background: rgba(138, 43, 226, 0.2);
            transform: translateY(-3px);
        }

        .scale-option input:checked ~ .scale-number {
            background: linear-gradient(135deg, #9d4edd, #7b2cbf);
            border-color: #9d4edd;
            box-shadow: 0 5px 15px rgba(157, 78, 221, 0.4);
            transform: scale(1.1);
        }

        .scale-labels {
            display: flex;
            justify-content: space-between;
            color: #888;
            font-size: 0.9em;
            margin-top: 5px;
        }

        .submit-btn {
            width: 100%;
            padding: 15px;
            background: linear-gradient(135deg, #9d4edd, #7b2cbf);
            border: none;
            border-radius: 10px;
            color: white;
            font-size: 1.1em;
            font-weight: bold;
            cursor: pointer;
            transition: all 0.3s ease;
        }

        .submit-btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 10px 25px rgba(157, 78, 221, 0.4);
        }

        .reviews-list {
            display: grid;
            gap: 20px;
        }

        .review-card {
            background: rgba(30, 30, 50, 0.8);
            padding: 25px;
            border-radius: 15px;
            border: 2px solid rgba(138, 43, 226, 0.3);
            transition: all 0.3s ease;
        }

        .review-card:hover {
            border-color: rgba(138, 43, 226, 0.6);
            box-shadow: 0 5px 20px rgba(138, 43, 226, 0.2);
        }

        .review-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 15px;
            flex-wrap: wrap;
            gap: 10px;
        }

        .review-author {
            font-weight: bold;
            color: #9d4edd;
            font-size: 1.1em;
        }

        .review-date {
            color: #888;
            font-size: 0.9em;
        }

        .review-rating {
            color: #ffd700;
            font-size: 1.2em;
        }

        .review-text {
            color: #d0d0d0;
            line-height: 1.6;
        }

        @media (max-width: 768px) {
            .header h1 {
                font-size: 2em;
            }

            .stat-number {
                font-size: 2.5em;
            }

            .review-header {
                flex-direction: column;
                align-items: flex-start;
            }

            .radio-group,
            .checkbox-group {
                flex-direction: column;
            }

            .radio-option,
            .checkbox-option {
                width: 100%;
            }

            .scale-rating {
                gap: 5px;
            }

            .scale-number {
                padding: 10px;
                font-size: 1em;
            }
        }

        .no-reviews {
            text-align: center;
            padding: 60px 20px;
            color: #888;
            font-size: 1.2em;
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="header">
            <h1>🥞 ABB Crêpes - Avis Clients</h1>
            <p>Découvrez ce que nos clients pensent de nos délicieuses crêpes</p>
        </div>

        <div class="stats-grid">
            <div class="stat-card">
                <div class="stat-number" id="avgRating">4.7</div>
                <div class="stars">★★★★★</div>
                <div class="stat-label">Note Moyenne</div>
            </div>

            <div class="stat-card">
                <div class="stat-number" id="totalReviews">3</div>
                <div class="stat-label">Avis Total</div>
            </div>

            <div class="stat-card">
                <div class="stat-number" id="satisfied">100%</div>
                <div class="stat-label">Clients Satisfaits</div>
            </div>
        </div>

        <div class="review-form">
            <h3>Donnez votre avis sur ABB Crêpes</h3>
            <form id="reviewForm">
                <div class="form-group">
                    <label>Seriez-vous intéressé(e) par commander des crêpes en livraison ?</label>
                    <div class="radio-group">
                        <label class="radio-option">
                            <input type="radio" name="delivery_interest" value="Oui" required>
                            <span>Oui</span>
                        </label>
                        <label class="radio-option">
                            <input type="radio" name="delivery_interest" value="Non">
                            <span>Non</span>
                        </label>
                    </div>
                </div>

                <div class="form-group">
                    <label>À quel moment préféreriez-vous commander ?</label>
                    <div class="checkbox-group">
                        <label class="checkbox-option">
                            <input type="checkbox" name="moment" value="Goûter">
                            <span>Goûter</span>
                        </label>
                        <label class="checkbox-option">
                            <input type="checkbox" name="moment" value="Soirée">
                            <span>Soirée</span>
                        </label>
                        <label class="checkbox-option">
                            <input type="checkbox" name="moment" value="Week-end">
                            <span>Week-end</span>
                        </label>
                        <label class="checkbox-option">
                            <input type="checkbox" name="moment" value="Occasion spéciale">
                            <span>Occasion spéciale</span>
                        </label>
                    </div>
                </div>

                <div class="form-group">
                    <label>Quel type de crêpes préférez-vous ?</label>
                    <div class="radio-group">
                        <label class="radio-option">
                            <input type="radio" name="type_crepe" value="Sucrées" required>
                            <span>Sucrées</span>
                        </label>
                        <label class="radio-option">
                            <input type="radio" name="type_crepe" value="Salées">
                            <span>Salées</span>
                        </label>
                        <label class="radio-option">
                            <input type="radio" name="type_crepe" value="Les deux">
                            <span>Les deux</span>
                        </label>
                    </div>
                </div>

                <div class="form-group">
                    <label>Comment évaluez-vous le goût des crêpes ?</label>
                    <div class="scale-rating">
                        <label class="scale-option">
                            <input type="radio" name="gout" value="1" required>
                            <span class="scale-number">1</span>
                        </label>
                        <label class="scale-option">
                            <input type="radio" name="gout" value="2">
                            <span class="scale-number">2</span>
                        </label>
                        <label class="scale-option">
                            <input type="radio" name="gout" value="3">
                            <span class="scale-number">3</span>
                        </label>
                        <label class="scale-option">
                            <input type="radio" name="gout" value="4">
                            <span class="scale-number">4</span>
                        </label>
                        <label class="scale-option">
                            <input type="radio" name="gout" value="5">
                            <span class="scale-number">5</span>
                        </label>
                    </div>
                    <div class="scale-labels">
                        <span>Pas satisfait</span>
                        <span>Très satisfait</span>
                    </div>
                </div>

                <div class="form-group">
                    <label>Comment évaluez-vous la qualité des ingrédients ?</label>
                    <div class="scale-rating">
                        <label class="scale-option">
                            <input type="radio" name="qualite" value="1" required>
                            <span class="scale-number">1</span>
                        </label>
                        <label class="scale-option">
                            <input type="radio" name="qualite" value="2">
                            <span class="scale-number">2</span>
                        </label>
                        <label class="scale-option">
                            <input type="radio" name="qualite" value="3">
                            <span class="scale-number">3</span>
                        </label>
                        <label class="scale-option">
                            <input type="radio" name="qualite" value="4">
                            <span class="scale-number">4</span>
                        </label>
                        <label class="scale-option">
                            <input type="radio" name="qualite" value="5">
                            <span class="scale-number">5</span>
                        </label>
                    </div>
                    <div class="scale-labels">
                        <span>Pas satisfait</span>
                        <span>Très satisfait</span>
                    </div>
                </div>

                <div class="form-group">
                    <label>Recommanderiez-vous ABB Crêpes à vos proches ?</label>
                    <div class="scale-rating">
                        <label class="scale-option">
                            <input type="radio" name="recommandation" value="1" required>
                            <span class="scale-number">1</span>
                        </label>
                        <label class="scale-option">
                            <input type="radio" name="recommandation" value="2">
                            <span class="scale-number">2</span>
                        </label>
                        <label class="scale-option">
                            <input type="radio" name="recommandation" value="3">
                            <span class="scale-number">3</span>
                        </label>
                        <label class="scale-option">
                            <input type="radio" name="recommandation" value="4">
                            <span class="scale-number">4</span>
                        </label>
                        <label class="scale-option">
                            <input type="radio" name="recommandation" value="5">
                            <span class="scale-number">5</span>
                        </label>
                    </div>
                    <div class="scale-labels">
                        <span>Peu probable</span>
                        <span>Très probable</span>
                    </div>
                </div>

                <div class="form-group">
                    <label>Votre note globale</label>
                    <div class="rating-input">
                        <input type="radio" name="rating" id="star5" value="5" required>
                        <label for="star5">★</label>
                        <input type="radio" name="rating" id="star4" value="4">
                        <label for="star4">★</label>
                        <input type="radio" name="rating" id="star3" value="3">
                        <label for="star3">★</label>
                        <input type="radio" name="rating" id="star2" value="2">
                        <label for="star2">★</label>
                        <input type="radio" name="rating" id="star1" value="1">
                        <label for="star1">★</label>
                    </div>
                </div>

                <div class="form-group">
                    <label for="name">Votre prénom</label>
                    <input type="text" id="name" required placeholder="Marie">
                </div>

                <div class="form-group">
                    <label for="comment">Votre commentaire (optionnel)</label>
                    <textarea id="comment" placeholder="Partagez votre expérience avec ABB Crêpes..."></textarea>
                </div>

                <button type="submit" class="submit-btn">Envoyer mon avis</button>
            </form>
        </div>

        <div class="reviews-list" id="reviewsList"></div>
    </div>

    <script>
        // Initialiser avec des avis d'exemple si localStorage est vide
        function initializeReviews() {
            const existing = localStorage.getItem('abb_crepes_reviews');
            if (!existing) {
                const defaultReviews = [
                    {
                        id: 1,
                        author: "Julie",
                        rating: 5,
                        text: "Première commande hier soir, j'ai testé la crêpe Nutella. Livrée en 20 minutes, encore chaude ! Le livreur était souriant et poli. Bonne surprise pour une ouverture 😊",
                        date: "2026-02-06",
                        heure: "19:15",
                        questionnaire: {
                            deliveryInterest: "Oui",
                            moments: "Soirée",
                            typeCrepesPreferees: "Sucrées",
                            noteGout: "5",
                            noteQualite: "5",
                            noteRecommandation: "5"
                        }
                    },
                    {
                        id: 2,
                        author: "Maxime",
                        rating: 5,
                        text: "Commandé vers 19h30 hier. Service rapide, crêpe complète bien garnie. Franchement pour une première soirée c'était nickel. Je retesterai !",
                        date: "2026-02-06",
                        heure: "19:45",
                        questionnaire: {
                            deliveryInterest: "Oui",
                            moments: "Soirée, Week-end",
                            typeCrepesPreferees: "Les deux",
                            noteGout: "5",
                            noteQualite: "4",
                            noteRecommandation: "5"
                        }
                    },
                    {
                        id: 3,
                        author: "Sarah",
                        rating: 4,
                        text: "Testé hier soir, les crêpes sont bonnes ! La livraison a pris 25 min environ mais c'était l'ouverture donc normal. Contente qu'il y ait enfin ça au Mans",
                        date: "2026-02-06",
                        heure: "20:10",
                        questionnaire: {
                            deliveryInterest: "Oui",
                            moments: "Goûter, Week-end",
                            typeCrepesPreferees: "Sucrées",
                            noteGout: "4",
                            noteQualite: "4",
                            noteRecommandation: "4"
                        }
                    }
                ];
                localStorage.setItem('abb_crepes_reviews', JSON.stringify(defaultReviews));
            }
        }

        function loadReviews() {
            const saved = localStorage.getItem('abb_crepes_reviews');
            return saved ? JSON.parse(saved) : [];
        }

        function renderReviews() {
            const reviews = loadReviews();
            const reviewsList = document.getElementById('reviewsList');

            if (reviews.length === 0) {
                reviewsList.innerHTML = '<div class="no-reviews">Aucun avis disponible pour le moment.</div>';
                return;
            }

            reviewsList.innerHTML = reviews.map(review => `
                <div class="review-card">
                    <div class="review-header">
                        <div>
                            <div class="review-author">${review.author}</div>
                            <div class="review-rating">${'★'.repeat(review.rating)}${'☆'.repeat(5-review.rating)}</div>
                        </div>
                        <div class="review-date">${formatDate(review.date)} à ${review.heure}</div>
                    </div>
                    <div class="review-text">${review.text}</div>
                </div>
            `).join('');
        }

        function formatDate(dateStr) {
            const date = new Date(dateStr);
            const options = { year: 'numeric', month: 'long', day: 'numeric' };
            return date.toLocaleDateString('fr-FR', options);
        }

        function updateStats() {
            const reviews = loadReviews();
            if (reviews.length === 0) {
                document.getElementById('totalReviews').textContent = '0';
                document.getElementById('avgRating').textContent = '-';
                document.getElementById('satisfied').textContent = '-';
                return;
            }

            const total = reviews.length;
            const avgRating = (reviews.reduce((sum, r) => sum + r.rating, 0) / total).toFixed(1);
            const satisfied = Math.round((reviews.filter(r => r.rating >= 4).length / total) * 100);
            
            document.getElementById('totalReviews').textContent = total;
            document.getElementById('avgRating').textContent = avgRating;
            document.getElementById('satisfied').textContent = satisfied + '%';
        }

        document.getElementById('reviewForm').addEventListener('submit', function(e) {
            e.preventDefault();
            
            const name = document.getElementById('name').value;
            const comment = document.getElementById('comment').value || "Aucun commentaire supplémentaire";
            const rating = parseInt(document.querySelector('input[name="rating"]:checked').value);

            const deliveryInterest = document.querySelector('input[name="delivery_interest"]:checked')?.value || "";
            const typeCrepesPreferees = document.querySelector('input[name="type_crepe"]:checked')?.value || "";
            
            const moments = Array.from(document.querySelectorAll('input[name="moment"]:checked'))
                .map(cb => cb.value).join(', ') || "";
            
            const noteGout = document.querySelector('input[name="gout"]:checked')?.value || "";
            const noteQualite = document.querySelector('input[name="qualite"]:checked')?.value || "";
            const noteRecommandation = document.querySelector('input[name="recommandation"]:checked')?.value || "";

            const now = new Date();
            const reviews = loadReviews();
            
            const newReview = {
                id: reviews.length + 1,
                author: name,
                rating: rating,
                text: comment,
                date: now.toISOString().split('T')[0],
                heure: now.toLocaleTimeString('fr-FR', { hour: '2-digit', minute: '2-digit' }),
                questionnaire: {
                    deliveryInterest,
                    moments,
                    typeCrepesPreferees,
                    noteGout,
                    noteQualite,
                    noteRecommandation
                }
            };

            reviews.unshift(newReview);
            localStorage.setItem('abb_crepes_reviews', JSON.stringify(reviews));
            
            updateStats();
            renderReviews();

            this.reset();
            document.getElementById('reviewsList').scrollIntoView({ behavior: 'smooth' });
            alert('Merci pour votre avis détaillé ! Il a été enregistré avec succès. 🥞');
        });

        // Initialiser au chargement
        initializeReviews();
        renderReviews();
        updateStats();
    </script>
</body>
</html>
