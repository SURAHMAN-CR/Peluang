<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Petualangan Peluang di Dunia Fantasi</title>
    <style>
        * {
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            margin: 0;
            padding: 20px;
            background: linear-gradient(135deg, #1a2a6c, #b21f1f, #fdbb2d);
            color: white;
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            align-items: center;
        }
        
        .container {
            max-width: 1000px;
            width: 100%;
            background-color: rgba(0, 0, 0, 0.7);
            border-radius: 20px;
            padding: 20px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.5);
        }
        
        h1 {
            text-align: center;
            color: #ffcc00;
            text-shadow: 0 0 10px rgba(255, 204, 0, 0.5);
            margin-bottom: 10px;
        }
        
        .subtitle {
            text-align: center;
            margin-bottom: 30px;
            font-style: italic;
        }
        
        .game-area {
            display: flex;
            flex-wrap: wrap;
            gap: 20px;
            margin-bottom: 20px;
        }
        
        .level-info {
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
            padding: 20px;
            border-radius: 15px;
            border: 2px solid #4a4ae3;
        }
        
        .player-stats {
            display: flex;
            justify-content: space-between;
            margin-bottom: 20px;
            background: rgba(0, 0, 0, 0.3);
            padding: 10px;
            border-radius: 10px;
        }
        
        .stat {
            text-align: center;
        }
        
        .stat-value {
            font-size: 1.5em;
            font-weight: bold;
            color: #ffcc00;
        }
        
        .level-title {
            color: #ffcc00;
            border-bottom: 2px solid #ffcc00;
            padding-bottom: 10px;
            margin-bottom: 15px;
        }
        
        .question {
            font-size: 1.2em;
            margin-bottom: 20px;
            line-height: 1.5;
        }
        
        .options {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 15px;
            margin-bottom: 20px;
        }
        
        .option {
            background: rgba(70, 70, 150, 0.8);
            padding: 15px;
            border-radius: 10px;
            cursor: pointer;
            transition: all 0.3s;
            text-align: center;
            border: 2px solid transparent;
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
            margin-top: 20px;
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
            font-size: 1em;
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
            margin-top: 20px;
            padding: 15px;
            background: rgba(0, 0, 0, 0.3);
            border-radius: 10px;
            display: none;
        }
        
        .visualization.active {
            display: block;
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
            padding: 30px;
            display: none;
        }
        
        .trophy {
            font-size: 80px;
            margin-bottom: 20px;
            color: #ffcc00;
        }
        
        @media (max-width: 768px) {
            .options {
                grid-template-columns: 1fr;
            }
            
            .game-area {
                flex-direction: column;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>Petualangan Peluang di Dunia Fantasi</h1>
        <p class="subtitle">Uji pengetahuanmu tentang peluang dan raih kemenangan!</p>
        
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
            <div class="level-info">
                <h2 class="level-title" id="level-title">Gerbang Peluang</h2>
                <p id="level-description">Selamat datang di Gerbang Peluang! Di sini kamu akan mempelajari dasar-dasar peluang.</p>
                <div class="progress-bar">
                    <div class="progress" id="level-progress"></div>
                </div>
                <p>Progress: <span id="progress-text">0/5</span></p>
                
                <div class="visualization" id="visualization">
                    <h3>Visualisasi Peluang</h3>
                    <div id="visual-content"></div>
                </div>
            </div>
            
            <div class="game-board">
                <div class="question" id="question">
                    Memuat pertanyaan...
                </div>
                
                <div class="options" id="options">
                    <!-- Opsi akan diisi oleh JavaScript -->
                </div>
                
                <div class="feedback" id="feedback"></div>
                
                <div class="controls">
                    <button id="hint-btn">Bantuan</button>
                    <button id="submit-btn" disabled>Jawab</button>
                    <button id="next-btn" disabled>Lanjut</button>
                </div>
            </div>
        </div>
        
        <div class="game-complete" id="game-complete">
            <div class="trophy">🏆</div>
            <h2>Selamat! Kamu telah menyelesaikan Petualangan Peluang!</h2>
            <p>Skor akhir kamu: <span id="final-score">0</span></p>
            <button id="restart-btn">Main Lagi</button>
        </div>
    </div>

    <script>
        // Data pertanyaan untuk setiap level
        const levels = [
            {
                title: "Gerbang Peluang",
                description: "Pelajari dasar-dasar konsep peluang dan ruang sampel.",
                questions: [
                    {
                        question: "Dalam sebuah kantong terdapat 3 bola merah, 2 bola biru, dan 5 bola hijau. Jika diambil satu bola secara acak, berapa peluang terambilnya bola biru?",
                        options: ["1/5", "2/5", "1/2", "3/10"],
                        correct: 0,
                        explanation: "Peluang = Jumlah bola biru / Total bola = 2/10 = 1/5"
                    },
                    {
                        question: "Sebuah dadu dilempar sekali. Berapa peluang munculnya mata dadu ganjil?",
                        options: ["1/6", "1/3", "1/2", "2/3"],
                        correct: 2,
                        explanation: "Mata dadu ganjil: 1, 3, 5 (3 kemungkinan). Total kemungkinan: 6. Jadi peluang = 3/6 = 1/2"
                    },
                    {
                        question: "Dua koin dilempar bersamaan. Berapa peluang munculnya satu gambar dan satu angka?",
                        options: ["1/4", "1/2", "3/4", "1/3"],
                        correct: 1,
                        explanation: "Ruang sampel: AA, AG, GA, GG. Satu gambar satu angka: AG, GA (2 kemungkinan). Peluang = 2/4 = 1/2"
                    },
                    {
                        question: "Sebuah kotak berisi 4 kelereng merah dan 6 kelereng biru. Jika diambil 2 kelereng sekaligus, berapa peluang terambilnya kedua kelereng berwarna sama?",
                        options: ["7/15", "2/5", "1/3", "8/15"],
                        correct: 0,
                        explanation: "Peluang kedua merah: C(4,2)/C(10,2) = 6/45. Peluang kedua biru: C(6,2)/C(10,2) = 15/45. Total = 21/45 = 7/15"
                    },
                    {
                        question: "Dalam sebuah kelas terdapat 15 siswa laki-laki dan 10 siswa perempuan. Jika dipilih 2 siswa secara acak, berapa peluang terpilihnya satu laki-laki dan satu perempuan?",
                        options: ["1/2", "1/3", "1/4", "2/5"],
                        correct: 0,
                        explanation: "Total cara memilih 2 siswa: C(25,2) = 300. Cara memilih 1 laki dan 1 perempuan: 15 × 10 = 150. Peluang = 150/300 = 1/2"
                    }
                ]
            },
            {
                title: "Hutan Kombinasi",
                description: "Tantangan kombinasi dan permutasi menanti di hutan ini.",
                questions: [
                    {
                        question: "Dari angka 1, 2, 3, 4, 5 akan dibentuk bilangan ribuan yang berbeda. Berapa peluang terbentuknya bilangan genap?",
                        options: ["1/5", "2/5", "3/5", "1/2"],
                        correct: 1,
                        explanation: "Total bilangan: 5×4×3×2 = 120. Bilangan genap: angka satuan harus genap (2 atau 4) = 2×4×3×2 = 48. Peluang = 48/120 = 2/5"
                    },
                    {
                        question: "Dalam sebuah kotak terdapat 5 bola bernomor 1 sampai 5. Jika diambil 2 bola sekaligus, berapa peluang jumlah nomor bola yang terambil adalah 6?",
                        options: ["1/5", "1/10", "1/15", "2/15"],
                        correct: 1,
                        explanation: "Total cara: C(5,2) = 10. Pasangan dengan jumlah 6: (1,5) dan (2,4) = 2 cara. Peluang = 2/10 = 1/5"
                    },
                    {
                        question: "Sebuah keluarga memiliki 3 anak. Berapa peluang keluarga tersebut memiliki paling sedikit satu anak laki-laki?",
                        options: ["1/8", "3/8", "1/2", "7/8"],
                        correct: 3,
                        explanation: "Peluang semua perempuan: (1/2)^3 = 1/8. Peluang paling sedikit satu laki-laki: 1 - 1/8 = 7/8"
                    },
                    {
                        question: "Dua dadu dilempar bersamaan. Berapa peluang jumlah mata dadu yang muncul adalah 8?",
                        options: ["1/6", "1/9", "5/36", "1/12"],
                        correct: 2,
                        explanation: "Total kemungkinan: 6×6 = 36. Jumlah 8: (2,6), (3,5), (4,4), (5,3), (6,2) = 5 kemungkinan. Peluang = 5/36"
                    },
                    {
                        question: "Sebuah tim yang terdiri dari 5 orang akan dipilih dari 7 laki-laki dan 5 perempuan. Berapa peluang tim tersebut terdiri dari 3 laki-laki dan 2 perempuan?",
                        options: ["1/3", "1/2", "2/3", "3/4"],
                        correct: 1,
                        explanation: "Total cara: C(12,5) = 792. Cara memilih 3 laki dan 2 perempuan: C(7,3)×C(5,2) = 35×10 = 350. Peluang = 350/792 ≈ 0.44 (mendekati 1/2)"
                    }
                ]
            },
            {
                title: "Istirahat di Desa Peluang",
                description: "Istirahat sejenak dengan soal-soal aplikasi peluang dalam kehidupan sehari-hari.",
                questions: [
                    {
                        question: "Dalam sebuah kantong terdapat 10 kupon undian. Hanya 1 kupon yang berhadiah. Jika Rani mengambil 2 kupon sekaligus, berapa peluang Rani mendapatkan kupon berhadiah?",
                        options: ["1/5", "1/10", "1/15", "2/15"],
                        correct: 0,
                        explanation: "Peluang tidak dapat hadiah: C(9,2)/C(10,2) = 36/45 = 4/5. Peluang dapat hadiah: 1 - 4/5 = 1/5"
                    },
                    {
                        question: "Sebuah restoran menawarkan paket makan dengan pilihan 3 jenis appetizer, 4 jenis main course, dan 2 jenis dessert. Jika seorang pelanggan memilih secara acak satu dari setiap kategori, berapa peluang dia memilih paket tertentu?",
                        options: ["1/9", "1/12", "1/18", "1/24"],
                        correct: 3,
                        explanation: "Total paket: 3×4×2 = 24. Peluang memilih paket tertentu: 1/24"
                    },
                    {
                        question: "Dalam sebuah kotak terdapat 4 baterai baik dan 2 baterai rusak. Jika diambil 2 baterai secara acak, berapa peluang terambilnya satu baterai baik dan satu baterai rusak?",
                        options: ["1/3", "8/15", "4/15", "2/5"],
                        correct: 1,
                        explanation: "Total cara: C(6,2) = 15. Cara mengambil 1 baik dan 1 rusak: C(4,1)×C(2,1) = 4×2 = 8. Peluang = 8/15"
                    },
                    {
                        question: "Sebuah perusahaan memiliki 10 karyawan, 4 di antaranya adalah perempuan. Jika dipilih 3 orang untuk mewakili perusahaan, berapa peluang ketiganya laki-laki?",
                        options: ["1/6", "1/5", "1/4", "1/3"],
                        correct: 0,
                        explanation: "Total cara: C(10,3) = 120. Cara memilih 3 laki-laki: C(6,3) = 20. Peluang = 20/120 = 1/6"
                    },
                    {
                        question: "Dalam sebuah permainan, seorang pemain melempar dua dadu. Jika jumlah mata dadu 7 atau 11, dia menang. Berapa peluang pemain tersebut menang?",
                        options: ["1/6", "2/9", "1/4", "5/18"],
                        correct: 1,
                        explanation: "Total kemungkinan: 36. Jumlah 7: 6 kemungkinan. Jumlah 11: 2 kemungkinan. Total menang: 8. Peluang = 8/36 = 2/9"
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
        const levelDescriptionElement = document.getElementById('level-description');
        const levelProgressElement = document.getElementById('level-progress');
        const progressTextElement = document.getElementById('progress-text');
        const questionElement = document.getElementById('question');
        const optionsElement = document.getElementById('options');
        const feedbackElement = document.getElementById('feedback');
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
            levelDescriptionElement.textContent = level.description;
            
            // Update progress
            const progress = ((currentQuestion) / level.questions.length) * 100;
            levelProgressElement.style.width = `${progress}%`;
            progressTextElement.textContent = `${currentQuestion}/${level.questions.length}`;
            
            // Tampilkan pertanyaan
            questionElement.textContent = question.question;
            
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
            visualizationElement.classList.remove('active');
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
            
            // Tampilkan penjelasan
            visualizationElement.classList.add('active');
            visualContentElement.innerHTML = `
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
            
            visualizationElement.classList.add('active');
            visualContentElement.innerHTML = `
                <p><strong>Tips:</strong> ${getHint(question)}</p>
            `;
        }

        // Fungsi untuk menghasilkan tips berdasarkan pertanyaan
        function getHint(question) {
            const questionText = question.question.toLowerCase();
            
            if (questionText.includes('dadu')) {
                return "Ingat, sebuah dadu memiliki 6 sisi dengan angka 1 sampai 6.";
            } else if (questionText.includes('koin')) {
                return "Koin memiliki 2 sisi: angka dan gambar. Untuk dua koin, ruang sampelnya adalah AA, AG, GA, GG.";
            } else if (questionText.includes('bola') || questionText.includes('kelereng')) {
                return "Peluang = Jumlah kejadian yang diinginkan / Total kemungkinan kejadian.";
            } else if (questionText.includes('bilangan') || questionText.includes('angka')) {
                return "Perhatikan aturan bilangan genap/ganjil dan syarat pembentukan bilangan.";
            } else if (questionText.includes('kombinasi') || questionText.includes('permutasi')) {
                return "Kombinasi digunakan ketika urutan tidak penting, permutasi ketika urutan penting.";
            } else {
                return "Baca soal dengan teliti dan identifikasi informasi yang diberikan.";
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
