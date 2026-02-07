<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ABB Crêpes - Avis Clients</title>
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
            max-width: 1400px;
            margin: 0 auto;
            position: relative;
        }

        /* Menu hamburger */
        .hamburger {
            position: fixed;
            top: 30px;
            right: 30px;
            width: 50px;
            height: 50px;
            background: linear-gradient(135deg, #9d4edd, #7b2cbf);
            border-radius: 50%;
            cursor: pointer;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            gap: 5px;
            z-index: 1000;
            box-shadow: 0 5px 20px rgba(157, 78, 221, 0.4);
            transition: all 0.3s ease;
        }

        .hamburger:hover {
            transform: scale(1.1);
            box-shadow: 0 8px 30px rgba(157, 78, 221, 0.6);
        }

        .hamburger span {
            width: 25px;
            height: 3px;
            background: white;
            border-radius: 2px;
            transition: all 0.3s ease;
        }

        .hamburger.active span:nth-child(1) {
            transform: rotate(45deg) translate(5px, 5px);
        }

        .hamburger.active span:nth-child(2) {
            opacity: 0;
        }

        .hamburger.active span:nth-child(3) {
            transform: rotate(-45deg) translate(7px, -7px);
        }

        /* Menu déroulant */
        .dropdown-menu {
            position: fixed;
            top: 90px;
            right: 30px;
            background: rgba(30, 30, 50, 0.98);
            border: 2px solid rgba(138, 43, 226, 0.5);
            border-radius: 15px;
            padding: 15px;
            min-width: 200px;
            opacity: 0;
            visibility: hidden;
            transform: translateY(-10px);
            transition: all 0.3s ease;
            z-index: 999;
            box-shadow: 0 10px 40px rgba(0, 0, 0, 0.5);
        }

        .dropdown-menu.show {
            opacity: 1;
            visibility: visible;
            transform: translateY(0);
        }

        .dropdown-item {
            padding: 15px 20px;
            color: #e0e0e0;
            text-decoration: none;
            display: flex;
            align-items: center;
            gap: 10px;
            border-radius: 10px;
            cursor: pointer;
            transition: all 0.3s ease;
            font-size: 1.1em;
        }

        .dropdown-item:hover {
            background: rgba(138, 43, 226, 0.3);
            color: #9d4edd;
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

        .admin-badge {
            display: inline-block;
            background: linear-gradient(135deg, #9d4edd, #7b2cbf);
            padding: 8px 20px;
            border-radius: 20px;
            color: white;
            font-weight: bold;
            font-size: 0.9em;
            margin-top: 10px;
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

        .admin-controls {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 15px;
            margin-bottom: 30px;
        }

        .admin-btn {
            padding: 15px 25px;
            background: linear-gradient(135deg, #9d4edd, #7b2cbf);
            border: none;
            border-radius: 10px;
            color: white;
            font-size: 1em;
            font-weight: bold;
            cursor: pointer;
            transition: all 0.3s ease;
        }

        .admin-btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 10px 25px rgba(157, 78, 221, 0.4);
        }

        .admin-btn.danger {
            background: linear-gradient(135deg, #dc2626, #991b1b);
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
            margin-bottom: 15px;
        }

        .review-details {
            background: rgba(50, 50, 70, 0.3);
            padding: 15px;
            border-radius: 10px;
            margin-bottom: 15px;
            font-size: 0.9em;
        }

        .review-details div {
            margin-bottom: 8px;
            color: #b8b8b8;
        }

        .review-details strong {
            color: #9d4edd;
        }

        .review-actions {
            display: flex;
            gap: 10px;
            padding-top: 15px;
            border-top: 1px solid rgba(138, 43, 226, 0.2);
            flex-wrap: wrap;
        }

        .action-btn {
            padding: 10px 20px;
            border: none;
            border-radius: 8px;
            cursor: pointer;
            font-size: 0.9em;
            font-weight: bold;
            transition: all 0.3s ease;
        }

        .action-btn.edit {
            background: rgba(59, 130, 246, 0.3);
            border: 2px solid rgba(59, 130, 246, 0.5);
            color: #60a5fa;
        }

        .action-btn.edit:hover {
            background: rgba(59, 130, 246, 0.5);
        }

        .action-btn.delete {
            background: rgba(220, 38, 38, 0.3);
            border: 2px solid rgba(220, 38, 38, 0.5);
            color: #f87171;
        }

        .action-btn.delete:hover {
            background: rgba(220, 38, 38, 0.5);
        }

        .modal {
            display: none;
            position: fixed;
            z-index: 2000;
            left: 0;
            top: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.8);
            overflow-y: auto;
        }

        .modal-content {
            background: linear-gradient(135deg, #1a0033 0%, #2d1b4e 100%);
            margin: 50px auto;
            padding: 40px;
            border: 2px solid rgba(138, 43, 226, 0.5);
            border-radius: 20px;
            width: 90%;
            max-width: 600px;
        }

        .modal-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 30px;
        }

        .modal-header h2 {
            color: #9d4edd;
            font-size: 1.8em;
        }

        .close {
            color: #aaa;
            font-size: 2em;
            font-weight: bold;
            cursor: pointer;
        }

        .close:hover {
            color: #9d4edd;
        }

        .form-actions {
            display: flex;
            gap: 15px;
            justify-content: flex-end;
            margin-top: 30px;
        }

        .btn-save {
            padding: 12px 30px;
            background: linear-gradient(135deg, #9d4edd, #7b2cbf);
            border: none;
            border-radius: 10px;
            color: white;
            font-size: 1em;
            font-weight: bold;
            cursor: pointer;
        }

        .btn-cancel {
            padding: 12px 30px;
            background: rgba(100, 100, 120, 0.3);
            border: 2px solid rgba(100, 100, 120, 0.5);
            border-radius: 10px;
            color: #e0e0e0;
            font-size: 1em;
            font-weight: bold;
            cursor: pointer;
        }

        .no-reviews {
            text-align: center;
            padding: 60px 20px;
            color: #888;
            font-size: 1.2em;
        }

        .hidden {
            display: none !important;
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

            .admin-controls {
                grid-template-columns: 1fr;
            }

            .hamburger {
                top: 20px;
                right: 20px;
            }

            .dropdown-menu {
                right: 20px;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <!-- Menu hamburger -->
        <div class="hamburger" id="hamburger">
            <span></span>
            <span></span>
            <span></span>
        </div>

        <!-- Menu déroulant -->
        <div class="dropdown-menu" id="dropdownMenu">
            <div class="dropdown-item" onclick="openAdminPanel()">
                🔒 Admin
            </div>
        </div>

        <div class="header">
            <h1 id="headerTitle">🥞 ABB Crêpes - Avis Clients</h1>
            <p id="headerSubtitle">Découvrez ce que nos clients pensent de nos délicieuses crêpes</p>
            <div id="adminBadge" class="admin-badge hidden">👤 MODE ADMINISTRATEUR</div>
        </div>

        <!-- Contrôles admin (cachés par défaut) -->
        <div id="adminControls" class="admin-controls hidden">
            <button class="admin-btn" onclick="exportToExcel()">📊 Télécharger Excel</button>
            <button class="admin-btn" onclick="refreshData()">🔄 Actualiser</button>
            <button class="admin-btn" onclick="exitAdminMode()">👁️ Mode Client</button>
            <button class="admin-btn danger" onclick="clearAllData()">🗑️ Tout supprimer</button>
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

        <div class="review-form" id="reviewForm">
            <h3>Donnez votre avis sur ABB Crêpes</h3>
            <form id="clientForm">
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

    <!-- Modal d'édition -->
    <div id="editModal" class="modal">
        <div class="modal-content">
            <div class="modal-header">
                <h2>✏️ Modifier l'avis</h2>
                <span class="close" onclick="closeModal()">&times;</span>
            </div>
            <form id="editForm">
                <input type="hidden" id="editId">
                
                <div class="form-group">
                    <label for="editAuthor">Prénom</label>
                    <input type="text" id="editAuthor" required>
                </div>

                <div class="form-group">
                    <label for="editRating">Note (1-5)</label>
                    <input type="number" id="editRating" min="1" max="5" required>
                </div>

                <div class="form-group">
                    <label for="editText">Commentaire</label>
                    <textarea id="editText" required></textarea>
                </div>

                <div class="form-group">
                    <label for="editDate">Date</label>
                    <input type="date" id="editDate" required>
                </div>

                <div class="form-group">
                    <label for="editTime">Heure</label>
                    <input type="time" id="editTime" required>
                </div>

                <div class="form-actions">
                    <button type="button" class="btn-cancel" onclick="closeModal()">Annuler</button>
                    <button type="submit" class="btn-save">💾 Sauvegarder</button>
                </div>
            </form>
        </div>
    </div>

    <script src="https://cdnjs.cloudflare.com/ajax/libs/xlsx/0.18.5/xlsx.full.min.js"></script>
    <script>
        let isAdminMode = false;
        const ADMIN_PASSWORD = "PiedSec72";

        // Initialiser avec des avis d'exemple
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

        // Menu hamburger
        document.getElementById('hamburger').addEventListener('click', function() {
            this.classList.toggle('active');
            document.getElementById('dropdownMenu').classList.toggle('show');
        });

        // Fermer le menu si on clique ailleurs
        document.addEventListener('click', function(event) {
            const hamburger = document.getElementById('hamburger');
            const menu = document.getElementById('dropdownMenu');
            if (!hamburger.contains(event.target) && !menu.contains(event.target)) {
                hamburger.classList.remove('active');
                menu.classList.remove('show');
            }
        });

        function openAdminPanel() {
            const password = prompt('🔒 Mot de passe administrateur :');
            if (password === ADMIN_PASSWORD) {
                isAdminMode = true;
                document.getElementById('adminControls').classList.remove('hidden');
                document.getElementById('adminBadge').classList.remove('hidden');
                document.getElementById('reviewForm').classList.add('hidden');
                document.getElementById('headerSubtitle').textContent = 'Panel de gestion des avis clients';
                document.getElementById('hamburger').classList.remove('active');
                document.getElementById('dropdownMenu').classList.remove('show');
                renderReviews();
            } else if (password !== null) {
                alert('❌ Mot de passe incorrect !');
            }
        }

        function exitAdminMode() {
            isAdminMode = false;
            document.getElementById('adminControls').classList.add('hidden');
            document.getElementById('adminBadge').classList.add('hidden');
            document.getElementById('reviewForm').classList.remove('hidden');
            document.getElementById('headerSubtitle').textContent = 'Découvrez ce que nos clients pensent de nos délicieuses crêpes';
            renderReviews();
        }

        function loadReviews() {
            const saved = localStorage.getItem('abb_crepes_reviews');
            return saved ? JSON.parse(saved) : [];
        }

        function saveReviews(reviews) {
            localStorage.setItem('abb_crepes_reviews', JSON.stringify(reviews));
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
                            <div class="review-author">${review.author}${isAdminMode ? ' (ID: ' + review.id + ')' : ''}</div>
                            <div class="review-rating">${'★'.repeat(review.rating)}${'☆'.repeat(5-review.rating)}</div>
                        </div>
                        <div class="review-date">${formatDate(review.date)} à ${review.heure}</div>
                    </div>
                    <div class="review-text">${review.text}</div>
                    
                    ${isAdminMode && review.questionnaire ? `
                    <div class="review-details">
                        <div><strong>Intéressé livraison:</strong> ${review.questionnaire.deliveryInterest || 'N/A'}</div>
                        <div><strong>Moments:</strong> ${review.questionnaire.moments || 'N/A'}</div>
                        <div><strong>Type crêpes:</strong> ${review.questionnaire.typeCrepesPreferees || 'N/A'}</div>
                        <div><strong>Note goût:</strong> ${review.questionnaire.noteGout || 'N/A'}/5 | 
                             <strong>Qualité:</strong> ${review.questionnaire.noteQualite || 'N/A'}/5 | 
                             <strong>Recommandation:</strong> ${review.questionnaire.noteRecommandation || 'N/A'}/5</div>
                    </div>
                    ` : ''}

                    ${isAdminMode ? `
                    <div class="review-actions">
                        <button class="action-btn edit" onclick="editReview(${review.id})">✏️ Modifier</button>
                        <button class="action-btn delete" onclick="deleteReview(${review.id})">🗑️ Supprimer</button>
                    </div>
                    ` : ''}
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

        function editReview(id) {
            const reviews = loadReviews();
            const review = reviews.find(r => r.id === id);
            
            if (review) {
                document.getElementById('editId').value = review.id;
                document.getElementById('editAuthor').value = review.author;
                document.getElementById('editRating').value = review.rating;
                document.getElementById('editText').value = review.text;
                document.getElementById('editDate').value = review.date;
                document.getElementById('editTime').value = review.heure;
                
                document.getElementById('editModal').style.display = 'block';
            }
        }

        function deleteReview(id) {
            if (confirm('⚠️ Êtes-vous sûr de vouloir supprimer cet avis ?')) {
                const reviews = loadReviews();
                const filtered = reviews.filter(r => r.id !== id);
                saveReviews(filtered);
                refreshData();
                alert('✅ Avis supprimé avec succès !');
            }
        }

        function closeModal() {
            document.getElementById('editModal').style.display = 'none';
        }

        document.getElementById('editForm').addEventListener('submit', function(e) {
            e.preventDefault();
            
            const id = parseInt(document.getElementById('editId').value);
            const reviews = loadReviews();
            const reviewIndex = reviews.findIndex(r => r.id === id);
            
            if (reviewIndex !== -1) {
                reviews[reviewIndex].author = document.getElementById('editAuthor').value;
                reviews[reviewIndex].rating = parseInt(document.getElementById('editRating').value);
                reviews[reviewIndex].text = document.getElementById('editText').value;
                reviews[reviewIndex].date = document.getElementById('editDate').value;
                reviews[reviewIndex].heure = document.getElementById('editTime').value;
                
                saveReviews(reviews);
                closeModal();
                refreshData();
                alert('✅ Avis modifié avec succès !');
            }
        });

        document.getElementById('clientForm').addEventListener('submit', function(e) {
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
                id: reviews.length > 0 ? Math.max(...reviews.map(r => r.id)) + 1 : 1,
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
            saveReviews(reviews);
            
            updateStats();
            renderReviews();

            this.reset();
            document.getElementById('reviewsList').scrollIntoView({ behavior: 'smooth' });
            alert('Merci pour votre avis détaillé ! Il a été enregistré avec succès. 🥞');
        });

        function refreshData() {
            updateStats();
            renderReviews();
        }

        function exportToExcel() {
            const reviews = loadReviews();
            
            if (reviews.length === 0) {
                alert('❌ Aucun avis à exporter !');
                return;
            }

            const data = reviews.map(r => ({
                'ID': r.id,
                'Date': r.date,
                'Heure': r.heure,
                'Prénom': r.author,
                'Note Globale': r.rating,
                'Intéressé Livraison': r.questionnaire?.deliveryInterest || '',
                'Moments de Commande': r.questionnaire?.moments || '',
                'Type Crêpes': r.questionnaire?.typeCrepesPreferees || '',
                'Note Goût': r.questionnaire?.noteGout || '',
                'Note Qualité': r.questionnaire?.noteQualite || '',
                'Note Recommandation': r.questionnaire?.noteRecommandation || '',
                'Commentaire': r.text
            }));

            const ws = XLSX.utils.json_to_sheet(data);
            ws['!cols'] = [
                {wch: 5}, {wch: 12}, {wch: 8}, {wch: 15}, {wch: 12},
                {wch: 18}, {wch: 25}, {wch: 15}, {wch: 10}, {wch: 12},
                {wch: 18}, {wch: 50}
            ];

            const wb = XLSX.utils.book_new();
            XLSX.utils.book_append_sheet(wb, ws, "Avis Clients");

            const stats = [
                ['Métrique', 'Valeur'],
                ['Total Avis', reviews.length],
                ['Note Moyenne', (reviews.reduce((sum, r) => sum + r.rating, 0) / reviews.length).toFixed(1)],
                ['% Clients Satisfaits (4-5★)', Math.round((reviews.filter(r => r.rating >= 4).length / reviews.length) * 100) + '%']
            ];

            const ws2 = XLSX.utils.aoa_to_sheet(stats);
            ws2['!cols'] = [{wch: 30}, {wch: 20}];
            XLSX.utils.book_append_sheet(wb, ws2, "Statistiques");

            XLSX.writeFile(wb, `ABB_Crepes_Avis_${new Date().toISOString().split('T')[0]}.xlsx`);
        }

        function clearAllData() {
            if (confirm('⚠️ ATTENTION ! Voulez-vous vraiment supprimer TOUS les avis ?')) {
                if (confirm('✋ Dernière confirmation : tous les avis seront DÉFINITIVEMENT supprimés !')) {
                    localStorage.removeItem('abb_crepes_reviews');
                    refreshData();
                    alert('✅ Toutes les données ont été supprimées.');
                }
            }
        }

        window.onclick = function(event) {
            if (event.target == document.getElementById('editModal')) {
                closeModal();
            }
        }

        // Initialiser
        initializeReviews();
        renderReviews();
        updateStats();
    </script>
</body>
</html>
