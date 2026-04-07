// Вопросы для викторины
const questions = [
    {
        question: "Что означает аббревиатура ARIMA?",
        options: [
            "Autoregressive Integrated Moving Average",
            "Artificial Intelligence Machine Algorithm",
            "Advanced Regression Integration Model",
            "Automatic Random Input Method Array"
        ],
        correct: 0,
        explanation: "ARIMA (Autoregressive Integrated Moving Average) - это классическая модель для анализа временных рядов, объединяющая авторегрессию и скользящее среднее."
    },
    {
        question: "Какая нейросетевая архитектура специально разработана для работы с долгосрочными зависимостями во временных рядах?",
        options: [
            "CNN (Свёрточная сеть)",
            "LSTM (Long Short-Term Memory)",
            "GAN (Генеративно-состязательная сеть)",
            "RBM (Ограниченная машина Больцмана)"
        ],
        correct: 1,
        explanation: "LSTM (Long Short-Term Memory) - сети с долгой краткосрочной памятью, специально созданные для запоминания информации на длительных промежутках времени."
    },
    {
        question: "Какой механизм является ключевым в архитектуре Трансформер?",
        options: [
            "Свёртка",
            "Пулдинг",
            "Самовнимание (Self-attention)",
            "Рекуррентность"
        ],
        correct: 2,
        explanation: "Механизм самовнимания (self-attention) позволяет модели оценивать важность различных элементов входной последовательности независимо от их расстояния."
    },
    {
        question: "Какой метод прогнозирования показал точность до 95% при анализе данных с инсулиновых помп?",
        options: [
            "Простая ARIMA",
            "LSTM с кластеризацией временных рядов",
            "Экспоненциальное сглаживание",
            "Линейная регрессия"
        ],
        correct: 1,
        explanation: "Кластеризация временных рядов с последующим обучением отдельных LSTM-моделей для каждого кластера пациентов позволила достичь точности до 95%."
    },
    {
        question: "Что из перечисленного является ансамблевым методом машинного обучения?",
        options: [
            "ARIMA",
            "CatBoost",
            "Трансформер",
            "LSTM"
        ],
        correct: 1,
        explanation: "CatBoost - это метод градиентного бустинга над деревьями решений, который относится к ансамблевым методам машинного обучения."
    },
    {
        question: "Какой подход используется в гибридных моделях для улучшения прогнозирования?",
        options: [
            "Использование только нейросетей",
            "Комбинирование ARIMA для линейных трендов и нейросетей для нелинейных остатков",
            "Отказ от исторических данных",
            "Использование только экспертных оценок"
        ],
        correct: 1,
        explanation: "Гибридные модели объединяют сильные стороны разных подходов: ARIMA моделирует линейные тренды, а нейросети улавливают сложные нелинейные зависимости."
    },
    {
        question: "На сколько процентов возрастает загруженность дорог при снегопаде, согласно исследованиям?",
        options: [
            "На 10%",
            "На 30%",
            "На 50%",
            "На 70%"
        ],
        correct: 1,
        explanation: "Исследования показывают, что загруженность дорог возрастает на 30% при снегопаде и на 20% при дожде."
    },
    {
        question: "Какой метод позволяет проигрывать различные сценарии развития событий?",
        options: [
            "Точечный прогноз",
            "Имитационное моделирование",
            "Линейная экстраполяция",
            "Метод наименьших квадратов"
        ],
        correct: 1,
        explanation: "Имитационное моделирование позволяет создавать цифровые копии систем и проигрывать различные сценарии развития событий с оценкой вероятностей исходов."
    },
    {
        question: "Какое основное ограничение классической модели ARIMA?",
        options: [
            "Слишком высокая точность",
            "Требование стационарности процесса и линейность",
            "Невозможность использования на компьютере",
            "Отсутствие математического обоснования"
        ],
        correct: 1,
        explanation: "ARIMA требует стационарности процесса (постоянство статистических характеристик) и предполагает линейные зависимости, что ограничивает её применение для сложных нестационарных процессов."
    },
    {
        question: "Какая из перечисленных сфер НЕ является областью применения современных методов прогнозирования?",
        options: [
            "Медицина (прогноз уровня глюкозы)",
            "Транспорт (прогноз загруженности дорог)",
            "Астрология (предсказание судьбы)",
            "Энергетика (прогноз потребления электроэнергии)"
        ],
        correct: 2,
        explanation: "Астрология не является научной областью применения методов прогнозирования, в отличие от медицины, транспорта и энергетики, где эти методы дают реальные практические результаты."
    }
];

let currentQuestionIndex = 0;
let score = 0;
let answered = false;

// DOM элементы
const questionText = document.getElementById('questionText');
const optionsContainer = document.getElementById('optionsContainer');
const nextBtn = document.getElementById('nextBtn');
const feedback = document.getElementById('feedback');
const quizCard = document.getElementById('quizCard');
const resultCard = document.getElementById('resultCard');
const scoreSpan = document.getElementById('score');
const currentSpan = document.getElementById('current');
const totalSpan = document.getElementById('total');

// Инициализация
totalSpan.textContent = questions.length;

function loadQuestion() {
    // Сброс состояния
    answered = false;
    nextBtn.style.display = 'none';
    feedback.innerHTML = '';
    feedback.className = 'feedback';
    
    const question = questions[currentQuestionIndex];
    questionText.textContent = question.question;
    
    // Создаем варианты ответов
    optionsContainer.innerHTML = '';
    question.options.forEach((option, index) => {
        const optionDiv = document.createElement('div');
        optionDiv.className = 'option';
        optionDiv.textContent = option;
        optionDiv.onclick = () => checkAnswer(index);
        optionsContainer.appendChild(optionDiv);
    });
    
    currentSpan.textContent = currentQuestionIndex + 1;
}

function checkAnswer(selectedIndex) {
    if (answered) return;
    
    const question = questions[currentQuestionIndex];
    const isCorrect = selectedIndex === question.correct;
    
    // Подсветка правильного и неправильного ответов
    const options = document.querySelectorAll('.option');
    options.forEach((option, index) => {
        option.classList.add('disabled');
        if (index === question.correct) {
            option.classList.add('correct');
        }
        if (index === selectedIndex && !isCorrect) {
            option.classList.add('wrong');
        }
    });
    
    // Подсветка выбранного неправильного ответа
    if (!isCorrect) {
        options[selectedIndex].classList.add('wrong');
    }
    
    // Обновление счёта
    if (isCorrect) {
        score++;
        scoreSpan.textContent = score;
        feedback.innerHTML = `✅ Правильно! ${question.explanation}`;
        feedback.classList.add('correct');
    } else {
        feedback.innerHTML = `❌ Неправильно! Правильный ответ: ${question.options[question.correct]}. ${question.explanation}`;
        feedback.classList.add('wrong');
    }
    
    answered = true;
    nextBtn.style.display = 'block';
}

function nextQuestion() {
    currentQuestionIndex++;
    
    if (currentQuestionIndex < questions.length) {
        loadQuestion();
    } else {
        endGame();
    }
}

function endGame() {
    quizCard.style.display = 'none';
    resultCard.style.display = 'block';
    
    const percentage = (score / questions.length) * 100;
    const finalScore = document.getElementById('finalScore');
    const resultMessage = document.getElementById('resultMessage');
    
    finalScore.textContent = `${score} / ${questions.length} (${Math.round(percentage)}%)`;
    
    if (percentage === 100) {
        resultMessage.innerHTML = "🏆 Идеально! Вы эксперт в методах прогнозирования! 🏆";
    } else if (percentage >= 80) {
        resultMessage.innerHTML = "🌟 Отлично! Вы очень хорошо разбираетесь в теме! 🌟";
    } else if (percentage >= 60) {
        resultMessage.innerHTML = "👍 Хороший результат! Но есть куда расти! 👍";
    } else if (percentage >= 40) {
        resultMessage.innerHTML = "📚 Неплохо, но рекомендуем повторить материал! 📚";
    } else {
        resultMessage.innerHTML = "💪 Не расстраивайтесь! Прочитайте реферат и попробуйте снова! 💪";
    }
}

function restartGame() {
    currentQuestionIndex = 0;
    score = 0;
    answered = false;
    scoreSpan.textContent = score;
    
    quizCard.style.display = 'block';
    resultCard.style.display = 'none';
    
    loadQuestion();
}

// Добавляем обработчик для кнопки "Следующий вопрос"
nextBtn.addEventListener('click', nextQuestion);

// Загружаем первый вопрос
loadQuestion();
