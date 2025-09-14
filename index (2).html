<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Saudi National Day Quiz</title>
    <!-- Tailwind CSS CDN -->
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Tajawal:wght@400;700&display=swap');
        body {
            font-family: 'Tajawal', sans-serif;
            background-color: #1a202c;
            color: #f7fafc;
        }
        .correct-answer-animation {
            animation: bounceIn 0.5s forwards;
        }
        .incorrect-answer-animation {
            animation: shake 0.5s forwards;
        }
        @keyframes bounceIn {
            0% { transform: scale(0.5); opacity: 0; }
            100% { transform: scale(1); opacity: 1; }
        }
        @keyframes shake {
            0% { transform: translateX(0); }
            20% { transform: translateX(-10px); }
            40% { transform: translateX(10px); }
            60% { transform: translateX(-10px); }
            80% { transform: translateX(10px); }
            100% { transform: translateX(0); }
        }
    </style>
</head>
<body class="flex items-center justify-center min-h-screen p-4">

    <div id="game-container" class="bg-white text-gray-800 p-8 rounded-3xl shadow-2xl w-full max-w-2xl mx-auto flex flex-col items-center text-center space-y-6">

        <!-- Header -->
        <h1 class="text-4xl md:text-5xl font-extrabold text-[#1a5b35] mb-4">Saudi National Day Quiz</h1>

        <!-- Quiz Image (Placeholder) -->
        <img src="https://placehold.co/600x200/1a5b35/ffffff?text=Happy+Saudi+National+Day" alt="Saudi National Day" class="rounded-xl shadow-lg mb-6 w-full max-w-md">

        <!-- Question Section -->
        <div id="quiz-section" class="w-full">
            <p id="question-text" class="text-xl md:text-2xl font-semibold mb-6"></p>
            <div id="answer-buttons" class="grid grid-cols-1 md:grid-cols-2 gap-4">
                <!-- Answer buttons will be generated here -->
            </div>
        </div>

        <!-- Feedback & Results -->
        <div id="feedback-message" class="text-2xl font-bold mt-4 min-h-[4rem]"></div>
        <button id="next-button" class="bg-[#1a5b35] hover:bg-[#154a2a] text-white font-bold py-3 px-8 rounded-full shadow-lg transition-all transform hover:scale-105 duration-300 hidden">Next Question</button>
        <button id="restart-button" class="bg-[#2d3748] hover:bg-[#4a5568] text-white font-bold py-3 px-8 rounded-full shadow-lg transition-all transform hover:scale-105 duration-300 hidden">Restart Quiz</button>

    </div>

    <script>
        // Use the firebase log level to debug.
        // setLogLevel('Debug');
        
        const questionText = document.getElementById('question-text');
        const answerButtons = document.getElementById('answer-buttons');
        const nextButton = document.getElementById('next-button');
        const restartButton = document.getElementById('restart-button');
        const feedbackMessage = document.getElementById('feedback-message');

        let currentQuestionIndex = 0;
        let score = 0;

        // Web Audio API to create simple sounds without external files
        const audioContext = new (window.AudioContext || window.webkitAudioContext)();

        function playCorrectSound() {
            const oscillator = audioContext.createOscillator();
            const gainNode = audioContext.createGain();
            
            oscillator.type = 'sine';
            oscillator.frequency.value = 880; // A5 frequency
            
            gainNode.gain.setValueAtTime(0.5, audioContext.currentTime);
            gainNode.gain.exponentialRampToValueAtTime(0.001, audioContext.currentTime + 0.3);
            
            oscillator.connect(gainNode);
            gainNode.connect(audioContext.destination);
            
            oscillator.start();
            oscillator.stop(audioContext.currentTime + 0.3);
        }

        function playIncorrectSound() {
            const oscillator = audioContext.createOscillator();
            const gainNode = audioContext.createGain();
            
            oscillator.type = 'triangle';
            oscillator.frequency.value = 220; // A3 frequency
            
            gainNode.gain.setValueAtTime(0.5, audioContext.currentTime);
            gainNode.gain.exponentialRampToValueAtTime(0.001, audioContext.currentTime + 0.5);
            
            oscillator.connect(gainNode);
            gainNode.connect(audioContext.destination);
            
            oscillator.start();
            oscillator.stop(audioContext.currentTime + 0.5);
        }

        const questions = [
            {
                question: "When is the Saudi National Day celebrated?",
                answers: [
                    { text: "September 23", correct: true },
                    { text: "January 15", correct: false },
                    { text: "March 10", correct: false },
                    { text: "December 2", correct: false }
                ]
            },
            {
                question: "What is the official name of the day?",
                answers: [
                    { text: "Saudi Day", correct: false },
                    { text: "The Unification of the Kingdom", correct: true },
                    { text: "King's Day", correct: false },
                    { text: "Founders' Day", correct: false }
                ]
            },
            {
                question: "Who was the founder of the Kingdom of Saudi Arabia?",
                answers: [
                    { text: "King Salman", correct: false },
                    { text: "King Abdullah", correct: false },
                    { text: "King Abdulaziz", correct: true },
                    { text: "King Fahd", correct: false }
                ]
            },
            {
                question: "What is the new vision for the Kingdom's future?",
                answers: [
                    { text: "Vision 2040", correct: false },
                    { text: "Vision 2030", correct: true },
                    { text: "Future Saudi Arabia", correct: false },
                    { text: "The Saudi Initiative", correct: false }
                ]
            },
            {
                question: "What colors are on the Saudi flag?",
                answers: [
                    { text: "Red and White", correct: false },
                    { text: "Blue and Gold", correct: false },
                    { text: "Green and White", correct: true },
                    { text: "Black and Gold", correct: false }
                ]
            }
        ];

        function startGame() {
            currentQuestionIndex = 0;
            score = 0;
            nextButton.classList.add('hidden');
            restartButton.classList.add('hidden');
            showQuestion();
        }

        function showQuestion() {
            resetState();
            const currentQuestion = questions[currentQuestionIndex];
            questionText.textContent = `Question ${currentQuestionIndex + 1}: ${currentQuestion.question}`;

            currentQuestion.answers.forEach(answer => {
                const button = document.createElement('button');
                button.textContent = answer.text;
                button.classList.add('bg-gray-100', 'hover:bg-gray-200', 'py-3', 'px-6', 'rounded-lg', 'shadow-md', 'transition-all', 'duration-200', 'transform', 'hover:scale-105', 'w-full', 'text-lg', 'text-left');
                if (answer.correct) {
                    button.dataset.correct = answer.correct;
                }
                button.addEventListener('click', selectAnswer);
                answerButtons.appendChild(button);
            });
        }

        function resetState() {
            nextButton.classList.add('hidden');
            feedbackMessage.textContent = '';
            while (answerButtons.firstChild) {
                answerButtons.removeChild(answerButtons.firstChild);
            }
        }

        function selectAnswer(e) {
            const selectedButton = e.target;
            const isCorrect = selectedButton.dataset.correct === "true";

            if (isCorrect) {
                score++;
                selectedButton.classList.remove('bg-gray-100');
                selectedButton.classList.add('bg-green-500', 'text-white');
                feedbackMessage.textContent = '✅ Correct! Excellent!';
                feedbackMessage.classList.remove('text-red-500', 'incorrect-answer-animation');
                feedbackMessage.classList.add('text-green-500', 'correct-answer-animation');
                playCorrectSound();
            } else {
                selectedButton.classList.remove('bg-gray-100');
                selectedButton.classList.add('bg-red-500', 'text-white');
                feedbackMessage.textContent = '❌ Unfortunately, that is not the correct answer.';
                feedbackMessage.classList.remove('text-green-500', 'correct-answer-animation');
                feedbackMessage.classList.add('text-red-500', 'incorrect-answer-animation');
                playIncorrectSound();
                // Highlight the correct answer
                Array.from(answerButtons.children).find(button => button.dataset.correct === "true")
                    .classList.add('bg-green-500', 'text-white');
            }

            Array.from(answerButtons.children).forEach(button => {
                button.disabled = true;
                button.classList.remove('hover:bg-gray-200', 'hover:scale-105');
            });

            if (currentQuestionIndex < questions.length - 1) {
                nextButton.classList.remove('hidden');
            } else {
                showResults();
            }
        }

        function handleNextButton() {
            currentQuestionIndex++;
            if (currentQuestionIndex < questions.length) {
                showQuestion();
            } else {
                showResults();
            }
        }

        function showResults() {
            resetState();
            questionText.textContent = `You scored ${score} out of ${questions.length}!`;
            if (score === questions.length) {
                feedbackMessage.textContent = '🎉 Congratulations! You are an expert!';
                feedbackMessage.classList.remove('text-red-500');
                feedbackMessage.classList.add('text-green-500', 'correct-answer-animation');
            } else if (score > questions.length / 2) {
                feedbackMessage.textContent = '👏 Great job! You have good knowledge!';
                feedbackMessage.classList.remove('text-red-500');
                feedbackMessage.classList.add('text-green-500', 'correct-answer-animation');
            } else {
                feedbackMessage.textContent = 'Keep learning! Every day is a chance to improve!';
                feedbackMessage.classList.remove('text-green-500');
                feedbackMessage.classList.add('text-red-500', 'incorrect-answer-animation');
            }
            restartButton.classList.remove('hidden');
        }

        nextButton.addEventListener('click', handleNextButton);
        restartButton.addEventListener('click', startGame);

        window.onload = startGame;
    </script>
</body>
</html>
