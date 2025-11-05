<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Misteri Peluang dengan Ustadz Surahman, S.Pd - SMP Islam Ibadurrahman</title>
    <style>
        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background: linear-gradient(135deg, #1a2980, #26d0ce);
            color: white;
            min-height: 100vh;
            padding: 20px;
            display: flex;
            flex-direction: column;
            align-items: center;
        }
        
        .container {
            max-width: 1200px;
            width: 100%;
            background: rgba(0, 0, 0, 0.7);
            border-radius: 20px;
            padding: 25px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.5);
        }
        
        .school-header {
            display: flex;
            align-items: center;
            justify-content: space-between;
            margin-bottom: 20px;
            padding-bottom: 15px;
            border-bottom: 2px solid #ffcc00;
        }
        
        .school-logo-container {
            display: flex;
            align-items: center;
            gap: 15px;
        }
        
        .school-logo {
            width: 80px;
            height: 80px;
            border-radius: 50%;
            background: white;
            display: flex;
            align-items: center;
            justify-content: center;
            overflow: hidden;
            border: 3px solid #ffcc00;
        }
        
        .school-logo img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }
        
        .school-info {
            text-align: left;
        }
        
        .school-name {
            font-size: 1.5em;
            font-weight: bold;
            color: #ffcc00;
        }
        
        .school-motto {
            font-style: italic;
            color: #cccccc;
            font-size: 0.9em;
        }
        
        header {
            text-align: center;
            margin-bottom: 30px;
            position: relative;
        }
        
        h1 {
            color: #ffcc00;
            text-shadow: 0 0 10px rgba(255, 204, 0, 0.5);
            margin-bottom: 10px;
            font-size: 2.2em;
        }
        
        .subtitle {
            font-style: italic;
            margin-bottom: 20px;
            font-size: 1.2em;
        }
        
        .teacher-section {
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 20px;
            margin-bottom: 20px;
            background: rgba(255, 255, 255, 0.1);
            padding: 15px;
            border-radius: 15px;
            border: 2px solid #ffcc00;
        }
        
        .teacher-avatar {
            width: 100px;
            height: 100px;
            border-radius: 50%;
            background: linear-gradient(135deg, #4a4ae3, #ffcc00);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 40px;
            color: white;
            border: 4px solid white;
        }
        
        .teacher-info {
            text-align: left;
        }
        
        .teacher-name {
            font-size: 1.5em;
            font-weight: bold;
            color: #ffcc00;
        }
        
        .teacher-quote {
            font-style: italic;
            margin-top: 5px;
            color: #cccccc;
        }
        
        .game-area {
            display: flex;
            flex-wrap: wrap;
            gap: 25px;
            margin-bottom: 25px;
        }
        
        .theory-panel {
            flex: 1;
            min-width: 300px;
            background: rgba(30, 30, 70, 0.8);
            padding: 20px;
            border-radius: 15px;
            border: 2px solid #4a4ae3;
        }
        
        .game-board {
            flex: 2;
            min-width: 300px;
            background: rgba(40, 40, 80, 0.8);
            padding: 25px;
            border-radius: 15px;
            border: 2px solid #4a4ae3;
        }
        
        .player-stats {
            display: flex;
            justify-content: space-around;
            margin-bottom: 25px;
            background: rgba(0, 0, 0, 0.3);
            padding: 15px;
            border-radius: 10px;
        }
        
        .stat {
            text-align: center;
        }
        
        .stat-value {
            font-size: 1.8em;
            font-weight: bold;
            color: #ffcc00;
        }
        
        .panel-title {
            color: #ffcc00;
            border-bottom: 2px solid #ffcc00;
            padding-bottom: 10px;
            margin-bottom: 15px;
            font-size: 1.5em;
        }
        
        .theory-content {
            line-height: 1.6;
        }
        
        .theory-content h3 {
            color: #4a4ae3;
            margin: 15px 0 10px 0;
        }
        
        .theory-content ul {
            margin-left: 20px;
            margin-bottom: 15px;
        }
        
        .question {
            font-size: 1.3em;
            margin-bottom: 25px;
            line-height: 1.6;
            background: rgba(0, 0, 0, 0.2);
            padding: 15px;
            border-radius: 10px;
        }
        
        .options {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 15px;
            margin-bottom: 25px;
        }
        
        .option {
            background: rgba(70, 70, 150, 0.8);
            padding: 15px;
            border-radius: 10px;
            cursor: pointer;
            transition: all 0.3s;
            text-align: center;
            border: 2px solid transparent;
            font-size: 1.1em;
        }
        
        .option:hover {
            background: rgba(90, 90, 180, 0.8);
            transform: translateY(-3px);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.3);
        }
        
        .option.selected {
            border-color: #ffcc00;
            background: rgba(100, 100, 200, 0.8);
        }
        
        .controls {
            display: flex;
            justify-content: space-between;
            margin-top: 25px;
        }
        
        button {
            background: linear-gradient(to bottom, #ffcc00, #ff9900);
            border: none;
            color: #1a1a4a;
            padding: 12px 25px;
            border-radius: 50px;
            font-weight: bold;
            cursor: pointer;
            transition: all 0.3s;
            font-size: 1.1em;
        }
        
        button:hover {
            transform: translateY(-3px);
            box-shadow: 0 5px 15px rgba(255, 204, 0, 0.4);
        }
        
        button:disabled {
            background: #666;
            cursor: not-allowed;
            transform: none;
            box-shadow: none;
        }
        
        .feedback {
            margin-top: 20px;
            padding: 15px;
            border-radius: 10px;
            text-align: center;
            font-weight: bold;
            display: none;
        }
        
        .feedback.correct {
            background: rgba(0, 150, 0, 0.3);
            border: 2px solid #00cc00;
            display: block;
        }
        
        .feedback.incorrect {
            background: rgba(150, 0, 0, 0.3);
            border: 2px solid #cc0000;
            display: block;
        }
        
        .visualization {
            margin-top: 25px;
            padding: 20px;
            background: rgba(0, 0, 0, 0.3);
            border-radius: 10px;
            display: none;
        }
        
        .visualization.active {
            display: block;
        }
        
        .teacher-message {
            background: rgba(255, 204, 0, 0.2);
            border: 2px solid #ffcc00;
            border-radius: 15px;
            padding: 15px;
            margin-top: 20px;
            display: none;
        }
        
        .teacher-message.active {
            display: block;
        }
        
        .teacher-message p {
            margin-bottom: 10px;
        }
        
        .teacher-signature {
            text-align: right;
            font-style: italic;
            color: #ffcc00;
            margin-top: 10px;
        }
        
        .progress-bar {
            height: 20px;
            background: rgba(255, 255, 255, 0.2);
            border-radius: 10px;
            margin-top: 5px;
            overflow: hidden;
        }
        
        .progress {
            height: 100%;
            background: linear-gradient(to right, #4a4ae3, #ffcc00);
            width: 0%;
            transition: width 0.5s;
        }
        
        .game-complete {
            text-align: center;
            padding: 40px;
            display: none;
        }
        
        .trophy {
            font-size: 100px;
            margin-bottom: 20px;
            color: #ffcc00;
        }
        
        .card-dice-visual {
            display: flex;
            justify-content: space-around;
            margin: 20px 0;
            flex-wrap: wrap;
        }
        
        .card, .dice {
            width: 120px;
            height: 160px;
            background: white;
            border-radius: 10px;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            color: black;
            font-weight: bold;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.3);
            margin: 10px;
        }
        
        .card.red {
            color: red;
        }
        
        .dice {
            font-size: 2em;
            background: linear-gradient(135deg, #f5f5f5, #e0e0e0);
        }
        
        @media (max-width: 768px) {
            .options {
                grid-template-columns: 1fr;
            }
            
            .game-area {
                flex-direction: column;
            }
            
            h1 {
                font-size: 1.8em;
            }
            
            .teacher-section {
                flex-direction: column;
                text-align: center;
            }
            
            .school-header {
                flex-direction: column;
                text-align: center;
                gap: 15px;
            }
            
            .school-logo-container {
                justify-content: center;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="school-header">
            <div class="school-logo-container">
                <div class="school-logo">
                    <img src="https://i.ibb.co.com/YFsWrFB1/Logo-SMP-Islam-Ibadurraham-temas.jpg" alt="Logo SMP Islam Ibadurrahman">
                </div>
                <div class="school-info">
                    <div class="school-name">SMP ISLAM IBADURRAHMAN</div>
                    <div class="school-motto">"Membentuk Generasi Berakhlak Mulia, Berprestasi, dan Berwawasan Global"</div>
                </div>
            </div>
            <div class="game-title">
                <h1>Misteri Peluang</h1>
            </div>
        </div>
        
        <header>
            <p class="subtitle">Tantangan Peluang Kejadian Saling Lepas dan Tidak Saling Lepas</p>
            
            <div class="teacher-section">
                <div class="teacher-avatar">📚</div>
                <div class="teacher-info">
                    <div class="teacher-name">Ustadz Surahman, S.Pd</div>
                    <div class="teacher-quote">"Matematika adalah bahasa universal untuk memahami pola-pola dalam kehidupan"</div>
                </div>
            </div>
        </header>
        
        <div class="player-stats">
            <div class="stat">
                <div>Level</div>
                <div class="stat-value" id="level">1</div>
            </div>
            <div class="stat">
                <div>Skor</div>
                <div class="stat-value" id="score">0</div>
            </div>
            <div class="stat">
                <div>Nyawa</div>
                <div class="stat-value" id="lives">3</div>
            </div>
        </div>
        
        <div class="game-area">
            <div class="theory-panel">
                <h2 class="panel-title">Teori Peluang</h2>
                <div class="theory-content">
                    <h3>Kejadian Saling Lepas</h3>
                    <p>Dua kejadian A dan B dikatakan saling lepas jika tidak memiliki irisan (A ∩ B = ∅).</p>
                    <p><strong>Rumus:</strong> P(A ∪ B) = P(A) + P(B)</p>
                    <ul>
                        <li>Contoh: Peluang muncul mata dadu 2 atau 5</li>
                        <li>P(2) = 1/6, P(5) = 1/6</li>
                        <li>P(2 atau 5) = 1/6 + 1/6 = 2/6 = 1/3</li>
                    </ul>
                    
                    <h3>Kejadian Tidak Saling Lepas</h3>
                    <p>Dua kejadian A dan B dikatakan tidak saling lepas jika memiliki irisan (A ∩ B ≠ ∅).</p>
                    <p><strong>Rumus:</strong> P(A ∪ B) = P(A) + P(B) - P(A ∩ B)</p>
                    <ul>
                        <li>Contoh: Peluang terambil kartu hati atau kartu bernomor 10 dari setumpuk kartu bridge</li>
                        <li>P(hati) = 13/52, P(10) = 4/52, P(10 hati) = 1/52</li>
                        <li>P(hati atau 10) = 13/52 + 4/52 - 1/52 = 16/52 = 4/13</li>
                    </ul>
                    
                    <h3>Kartu Bridge</h3>
                    <p>1 set kartu bridge terdiri dari 52 kartu:</p>
                    <ul>
                        <li>4 jenis: Hati (♥), Wajik (♦), Keriting (♣), Sekop (♠)</li>
                        <li>Masing-masing jenis memiliki 13 kartu: As, 2-10, J, Q, K</li>
                    </ul>
                </div>
                
                <div class="progress-bar">
                    <div class="progress" id="level-progress"></div>
                </div>
                <p>Progress: <span id="progress-text">0/5</span></p>
            </div>
            
            <div class="game-board">
                <h2 class="panel-title" id="level-title">Level 1: Dasar Peluang</h2>
                
                <div class="question" id="question">
                    Memuat pertanyaan...
                </div>
                
                <div class="card-dice-visual" id="visual-aid">
                    <!-- Visual kartu dan dadu akan ditampilkan di sini -->
                </div>
                
                <div class="options" id="options">
                    <!-- Opsi akan diisi oleh JavaScript -->
                </div>
                
                <div class="feedback" id="feedback"></div>
                
                <div class="teacher-message" id="teacher-message">
                    <p id="message-text"></p>
                    <div class="teacher-signature">- Ustadz Surahman, S.Pd</div>
                </div>
                
                <div class="controls">
                    <button id="hint-btn">Minta Petunjuk Ustadz</button>
                    <button id="submit-btn" disabled>Jawab</button>
                    <button id="next-btn" disabled>Lanjut</button>
                </div>
                
                <div class="visualization" id="visualization">
                    <h3>Penjelasan</h3>
                    <div id="visual-content"></div>
                </div>
            </div>
        </div>
        
        <div class="game-complete" id="game-complete">
            <div class="trophy">🏆</div>
            <h2>Selamat! Kamu telah menyelesaikan Misteri Peluang!</h2>
            <p>Skor akhir kamu: <span id="final-score">0</span></p>
            
            <div class="teacher-message active">
                <p>Alhamdulillah, anak-anak hebat! Kalian telah menguasai konsep peluang dengan baik. Teruslah belajar dan jadilah generasi yang cinta matematika!</p>
                <div class="teacher-signature">- Ustadz Surahman, S.Pd</div>
            </div>
            
            <button id="restart-btn">Main Lagi</button>
        </div>
    </div>

    <script>
        // Data pertanyaan untuk setiap level
        const levels = [
            {
                title: "Level 1: Dasar Peluang",
                questions: [
                    {
                        question: "Sebuah dadu dilempar sekali. Berapa peluang munculnya mata dadu genap atau mata dadu prima?",
                        type: "tidak saling lepas",
                        object: "dadu",
                        options: ["1/2", "2/3", "5/6", "1/3"],
                        correct: 2,
                        explanation: "Mata dadu genap: {2,4,6} = 3/6. Mata dadu prima: {2,3,5} = 3/6. Irisan: {2} = 1/6. P(genap atau prima) = 3/6 + 3/6 - 1/6 = 5/6",
                        teacherMessage: "Bagus! Perhatikan bahwa mata dadu 2 termasuk dalam kedua kejadian (genap dan prima), jadi kita harus mengurangi irisannya."
                    },
                    {
                        question: "Dari satu set kartu bridge, diambil satu kartu secara acak. Berapa peluang terambil kartu Hati atau kartu As?",
                        type: "tidak saling lepas",
                        object: "kartu",
                        options: ["4/13", "1/2", "7/13", "5/13"],
                        correct: 0,
                        explanation: "P(Hati) = 13/52, P(As) = 4/52, P(As Hati) = 1/52. P(Hati atau As) = 13/52 + 4/52 - 1/52 = 16/52 = 4/13",
                        teacherMessage: "Tepat sekali! Kartu As Hati termasuk dalam kedua kejadian, jadi kita kurangkan satu kali."
                    },
                    {
                        question: "Sebuah dadu dilempar sekali. Berapa peluang muncul mata dadu kurang dari 3 atau lebih dari 4?",
                        type: "saling lepas",
                        object: "dadu",
                        options: ["1/2", "2/3", "1/3", "5/6"],
                        correct: 1,
                        explanation: "Mata dadu < 3: {1,2} = 2/6. Mata dadu > 4: {5,6} = 2/6. Tidak ada irisan. P(<3 atau >4) = 2/6 + 2/6 = 4/6 = 2/3",
                        teacherMessage: "Benar! Kedua kejadian ini saling lepas karena tidak ada mata dadu yang sekaligus kurang dari 3 dan lebih dari 4."
                    },
                    {
                        question: "Dari satu set kartu bridge, diambil satu kartu secara acak. Berapa peluang terambil kartu King atau Queen?",
                        type: "saling lepas",
                        object: "kartu",
                        options: ["1/13", "2/13", "1/2", "1/4"],
                        correct: 1,
                        explanation: "P(King) = 4/52, P(Queen) = 4/52. Tidak ada kartu yang既是 King dan Queen. P(King atau Queen) = 4/52 + 4/52 = 8/52 = 2/13",
                        teacherMessage: "Hebat! Tidak mungkin satu kartu既是 King dan Queen, jadi kejadiannya saling lepas."
                    },
                    {
                        question: "Sebuah dadu dilempar sekali. Berapa peluang muncul mata dadu ganjil atau mata dadu faktor dari 6?",
                        type: "tidak saling lepas",
                        object: "dadu",
                        options: ["1/2", "2/3", "5/6", "1/3"],
                        correct: 2,
                        explanation: "Mata dadu ganjil: {1,3,5} = 3/6. Faktor 6: {1,2,3,6} = 4/6. Irisan: {1,3} = 2/6. P(ganjil atau faktor 6) = 3/6 + 4/6 - 2/6 = 5/6",
                        teacherMessage: "Bagus! Mata dadu 1 dan 3 termasuk dalam kedua kejadian, jadi kita kurangkan irisan keduanya."
                    }
                ]
            },
            {
                title: "Level 2: Tantangan Kartu Bridge",
                questions: [
                    {
                        question: "Dari satu set kartu bridge, diambil satu kartu secara acak. Berapa peluang terambil kartu bernomor (bukan gambar) atau kartu berwarna hitam?",
                        type: "tidak saling lepas",
                        object: "kartu",
                        options: ["11/13", "8/13", "5/13", "7/13"],
                        correct: 1,
                        explanation: "Kartu bernomor (2-10): 9×4 = 36/52. Kartu hitam (keriting & sekop): 26/52. Irisan (nomor hitam): 9×2 = 18/52. P(nomor atau hitam) = 36/52 + 26/52 - 18/52 = 44/52 = 11/13",
                        teacherMessage: "Tepat! Kartu bernomor hitam dihitung dua kali, jadi kita kurangkan satu kali."
                    },
                    {
                        question: "Dari satu set kartu bridge, diambil satu kartu secara acak. Berapa peluang terambil kartu Sekop atau kartu bernilai 10?",
                        type: "tidak saling lepas",
                        object: "kartu",
                        options: ["4/13", "1/4", "5/13", "7/13"],
                        correct: 0,
                        explanation: "P(Sekop) = 13/52, P(10) = 4/52, P(10 Sekop) = 1/52. P(Sekop atau 10) = 13/52 + 4/52 - 1/52 = 16/52 = 4/13",
                        teacherMessage: "Benar! Kartu 10 Sekop termasuk dalam kedua kejadian."
                    },
                    {
                        question: "Dari satu set kartu bridge, diambil satu kartu secara acak. Berapa peluang terambil kartu Jack atau kartu King?",
                        type: "saling lepas",
                        object: "kartu",
                        options: ["1/13", "2/13", "3/13", "4/13"],
                        correct: 1,
                        explanation: "P(Jack) = 4/52, P(King) = 4/52. Tidak ada irisan. P(Jack atau King) = 4/52 + 4/52 = 8/52 = 2/13",
                        teacherMessage: "Hebat! Tidak mungkin satu kartu既是 Jack dan King, jadi langsung jumlahkan saja peluangnya."
                    },
                    {
                        question: "Dari satu set kartu bridge, diambil satu kartu secara acak. Berapa peluang terambil kartu bernomor genap (2,4,6,8,10) atau kartu Wajik?",
                        type: "tidak saling lepas",
                        object: "kartu",
                        options: ["11/26", "15/26", "19/26", "21/26"],
                        correct: 2,
                        explanation: "Kartu nomor genap: 5×4 = 20/52. Kartu Wajik: 13/52. Irisan (nomor genap Wajik): 5/52. P(nomor genap atau Wajik) = 20/52 + 13/52 - 5/52 = 28/52 = 7/13 = 14/26",
                        teacherMessage: "Bagus! Perhatikan bahwa kartu nomor genap Wajik termasuk dalam kedua kejadian."
                    },
                    {
                        question: "Dari satu set kartu bridge, diambil satu kartu secara acak. Berapa peluang terambil kartu As atau kartu bernomor 7?",
                        type: "saling lepas",
                        object: "kartu",
                        options: ["1/13", "2/13", "3/13", "4/13"],
                        correct: 1,
                        explanation: "P(As) = 4/52, P(7) = 4/52. Tidak ada irisan. P(As atau 7) = 4/52 + 4/52 = 8/52 = 2/13",
                        teacherMessage: "Tepat! Tidak ada kartu yang既是 As dan 7, jadi kejadiannya saling lepas."
                    }
                ]
            },
            {
                title: "Level 3: Kombinasi Kartu & Dadu",
                questions: [
                    {
                        question: "Sebuah dadu dilempar dan satu kartu diambil dari setumpuk kartu bridge. Berapa peluang muncul mata dadu prima atau terambil kartu Hati?",
                        type: "saling lepas",
                        object: "kombinasi",
                        options: ["5/12", "7/12", "3/4", "2/3"],
                        correct: 2,
                        explanation: "P(dadu prima) = 3/6 = 1/2. P(kartu Hati) = 13/52 = 1/4. Kejadian saling lepas. P(prima atau Hati) = 1/2 + 1/4 = 3/4",
                        teacherMessage: "Benar! Karena dua kejadian ini berasal dari objek yang berbeda, mereka saling lepas."
                    },
                    {
                        question: "Sebuah dadu dilempar dan satu kartu diambil dari setumpuk kartu bridge. Berapa peluang muncul mata dadu genap atau terambil kartu bernomor 5?",
                        type: "saling lepas",
                        object: "kombinasi",
                        options: ["5/12", "7/12", "3/4", "2/3"],
                        correct: 1,
                        explanation: "P(dadu genap) = 3/6 = 1/2. P(kartu 5) = 4/52 = 1/13. Kejadian saling lepas. P(genap atau kartu 5) = 1/2 + 1/13 = 13/26 + 2/26 = 15/26 ≈ 7/12",
                        teacherMessage: "Bagus! Kedua kejadian ini independen dan saling lepas."
                    },
                    {
                        question: "Dua dadu dilempar bersamaan. Berapa peluang jumlah mata dadu 7 atau kedua mata dadu sama?",
                        type: "tidak saling lepas",
                        object: "dadu",
                        options: ["1/3", "5/18", "2/9", "7/36"],
                        correct: 0,
                        explanation: "P(jumlah 7) = 6/36. P(dua mata sama) = 6/36. Irisan: tidak ada (jumlah 7 mustahil dengan dua mata sama). P(jumlah 7 atau mata sama) = 6/36 + 6/36 = 12/36 = 1/3",
                        teacherMessage: "Tepat! Meskipun berasal dari objek yang sama, kedua kejadian ini saling lepas karena tidak mungkin terjadi bersamaan."
                    },
                    {
                        question: "Dari satu set kartu bridge, diambil satu kartu secara acak. Berapa peluang terambil kartu gambar (J,Q,K) atau kartu berwarna merah?",
                        type: "tidak saling lepas",
                        object: "kartu",
                        options: ["11/13", "8/13", "5/13", "7/13"],
                        correct: 1,
                        explanation: "P(kartu gambar) = 12/52. P(kartu merah) = 26/52. Irisan (gambar merah) = 6/52. P(gambar atau merah) = 12/52 + 26/52 - 6/52 = 32/52 = 8/13",
                        teacherMessage: "Hebat! Kartu gambar merah (J, Q, K hati dan wajik) termasuk dalam kedua kejadian."
                    },
                    {
                        question: "Sebuah dadu dilempar dan satu kartu diambil dari setumpuk kartu bridge. Berapa peluang muncul mata dadu faktor dari 12 atau terambil kartu As?",
                        type: "saling lepas",
                        object: "kombinasi",
                        options: ["5/12", "7/12", "3/4", "2/3"],
                        correct: 2,
                        explanation: "Faktor 12 pada dadu: {1,2,3,4,6} = 5/6. P(As) = 4/52 = 1/13. Kejadian saling lepas. P(faktor 12 atau As) = 5/6 + 1/13 = 65/78 + 6/78 = 71/78 ≈ 0.91 (mendekati 3/4)",
                        teacherMessage: "Bagus! Karena dua kejadian ini berasal dari objek berbeda, mereka saling lepas."
                    }
                ]
            }
        ];

        // Variabel game state
        let currentLevel = 0;
        let currentQuestion = 0;
        let score = 0;
        let lives = 3;
        let selectedOption = null;

        // Elemen DOM
        const levelElement = document.getElementById('level');
        const scoreElement = document.getElementById('score');
        const livesElement = document.getElementById('lives');
        const levelTitleElement = document.getElementById('level-title');
        const levelProgressElement = document.getElementById('level-progress');
        const progressTextElement = document.getElementById('progress-text');
        const questionElement = document.getElementById('question');
        const visualAidElement = document.getElementById('visual-aid');
        const optionsElement = document.getElementById('options');
        const feedbackElement = document.getElementById('feedback');
        const teacherMessageElement = document.getElementById('teacher-message');
        const messageTextElement = document.getElementById('message-text');
        const submitButton = document.getElementById('submit-btn');
        const nextButton = document.getElementById('next-btn');
        const hintButton = document.getElementById('hint-btn');
        const visualizationElement = document.getElementById('visualization');
        const visualContentElement = document.getElementById('visual-content');
        const gameCompleteElement = document.getElementById('game-complete');
        const finalScoreElement = document.getElementById('final-score');
        const restartButton = document.getElementById('restart-btn');

        // Inisialisasi game
        function initGame() {
            currentLevel = 0;
            currentQuestion = 0;
            score = 0;
            lives = 3;
            updateUI();
            loadQuestion();
            gameCompleteElement.style.display = 'none';
        }

        // Memuat pertanyaan saat ini
        function loadQuestion() {
            const level = levels[currentLevel];
            const question = level.questions[currentQuestion];
            
            // Update UI level
            levelElement.textContent = currentLevel + 1;
            levelTitleElement.textContent = level.title;
            
            // Update progress
            const progress = ((currentQuestion) / level.questions.length) * 100;
            levelProgressElement.style.width = `${progress}%`;
            progressTextElement.textContent = `${currentQuestion}/${level.questions.length}`;
            
            // Tampilkan pertanyaan
            questionElement.textContent = question.question;
            
            // Tampilkan visual bantuan
            displayVisualAid(question);
            
            // Kosongkan opsi sebelumnya
            optionsElement.innerHTML = '';
            selectedOption = null;
            
            // Buat opsi baru
            question.options.forEach((option, index) => {
                const optionElement = document.createElement('div');
                optionElement.className = 'option';
                optionElement.textContent = option;
                optionElement.dataset.index = index;
                optionElement.addEventListener('click', selectOption);
                optionsElement.appendChild(optionElement);
            });
            
            // Reset tombol dan feedback
            submitButton.disabled = true;
            nextButton.disabled = true;
            feedbackElement.className = 'feedback';
            feedbackElement.textContent = '';
            teacherMessageElement.classList.remove('active');
            visualizationElement.classList.remove('active');
        }

        // Menampilkan visual bantuan
        function displayVisualAid(question) {
            visualAidElement.innerHTML = '';
            
            if (question.object === "dadu") {
                visualAidElement.innerHTML = `
                    <div class="dice">1</div>
                    <div class="dice">2</div>
                    <div class="dice">3</div>
                    <div class="dice">4</div>
                    <div class="dice">5</div>
                    <div class="dice">6</div>
                `;
            } else if (question.object === "kartu") {
                visualAidElement.innerHTML = `
                    <div class="card red">A<br>♥</div>
                    <div class="card">K<br>♠</div>
                    <div class="card">Q<br>♣</div>
                    <div class="card red">J<br>♦</div>
                `;
            } else if (question.object === "kombinasi") {
                visualAidElement.innerHTML = `
                    <div class="dice">?</div>
                    <div class="card">?<br>?</div>
                `;
            }
        }

        // Memilih opsi jawaban
        function selectOption(event) {
            // Hapus seleksi sebelumnya
            document.querySelectorAll('.option').forEach(opt => {
                opt.classList.remove('selected');
            });
            
            // Tandai opsi yang dipilih
            event.target.classList.add('selected');
            selectedOption = parseInt(event.target.dataset.index);
            submitButton.disabled = false;
        }

        // Memeriksa jawaban
        function checkAnswer() {
            const level = levels[currentLevel];
            const question = level.questions[currentQuestion];
            const isCorrect = selectedOption === question.correct;
            
            // Tampilkan feedback
            feedbackElement.textContent = isCorrect 
                ? "Benar! +10 poin" 
                : `Salah! Jawaban benar: ${question.options[question.correct]}`;
            
            feedbackElement.className = `feedback ${isCorrect ? 'correct' : 'incorrect'}`;
            
            // Tampilkan pesan dari Ustadz Surahman
            messageTextElement.textContent = question.teacherMessage;
            teacherMessageElement.classList.add('active');
            
            // Tampilkan penjelasan
            visualizationElement.classList.add('active');
            visualContentElement.innerHTML = `
                <p><strong>Tipe Kejadian:</strong> ${question.type}</p>
                <p><strong>Penjelasan:</strong> ${question.explanation}</p>
            `;
            
            // Update skor dan nyawa
            if (isCorrect) {
                score += 10;
                scoreElement.textContent = score;
            } else {
                lives--;
                livesElement.textContent = lives;
                
                if (lives <= 0) {
                    endGame(false);
                    return;
                }
            }
            
            // Update tombol
            submitButton.disabled = true;
            nextButton.disabled = false;
        }

        // Pindah ke pertanyaan berikutnya
        function nextQuestion() {
            currentQuestion++;
            
            // Cek apakah level selesai
            if (currentQuestion >= levels[currentLevel].questions.length) {
                currentLevel++;
                currentQuestion = 0;
                
                // Cek apakah game selesai
                if (currentLevel >= levels.length) {
                    endGame(true);
                    return;
                }
            }
            
            loadQuestion();
        }

        // Menampilkan bantuan
        function showHint() {
            const level = levels[currentLevel];
            const question = level.questions[currentQuestion];
            
            teacherMessageElement.classList.add('active');
            visualizationElement.classList.add('active');
            
            if (question.type === "saling lepas") {
                messageTextElement.textContent = "Ingat nak, untuk kejadian saling lepas, gunakan rumus P(A atau B) = P(A) + P(B). Pastikan kedua kejadian tidak memiliki irisan!";
                visualContentElement.innerHTML = `
                    <p><strong>Tips:</strong> Kejadian ${question.type}. Gunakan rumus P(A ∪ B) = P(A) + P(B)</p>
                    <p>Pastikan kedua kejadian tidak memiliki irisan.</p>
                `;
            } else {
                messageTextElement.textContent = "Perhatikan baik-baik, untuk kejadian tidak saling lepas, jangan lupa kurangkan irisan keduanya: P(A atau B) = P(A) + P(B) - P(A dan B)";
                visualContentElement.innerHTML = `
                    <p><strong>Tips:</strong> Kejadian ${question.type}. Gunakan rumus P(A ∪ B) = P(A) + P(B) - P(A ∩ B)</p>
                    <p>Jangan lupa kurangi irisan kedua kejadian.</p>
                `;
            }
        }

        // Mengakhiri game
        function endGame(isWin) {
            if (isWin) {
                finalScoreElement.textContent = score;
                gameCompleteElement.style.display = 'block';
            } else {
                alert(`Game Over! Skor akhir kamu: ${score}`);
                initGame();
            }
        }

        // Update UI
        function updateUI() {
            levelElement.textContent = currentLevel + 1;
            scoreElement.textContent = score;
            livesElement.textContent = lives;
        }

        // Event listeners
        submitButton.addEventListener('click', checkAnswer);
        nextButton.addEventListener('click', nextQuestion);
        hintButton.addEventListener('click', showHint);
        restartButton.addEventListener('click', initGame);

        // Mulai game
        initGame();
    </script>
</body>
</html>
