# desenvolve-introducao-web

### Projeto Desenvolve - [Bom Despacho]

**Disciplina:** Introdução à Programação Web  
**Matrícula:** 227

  # Análise de URL

**URL analisada:**  
https://www.nytimes.com/2023/08/28/science/birds-flycatcher-migration.html

---

**• Protocolo:**  
`https`  


---

**• Domínio:**  
`www.nytimes.com`  
Este é o endereço principal do site 

---

**• Caminho:**  
`/2023/08/28/science/birds-flycatcher-migration.html`  
Esse é o caminho dentro do site

---

**• Parâmetros:**  
**Não há parâmetros nesta URL.**  



<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Jogo de Perguntas</title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            background-color: #f0f0f0;
            text-align: center;
            padding: 50px;
        }
        h1 {
            color: #4CAF50;
        }
        .question-container {
            background-color: #fff;
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
            margin: 20px;
            padding: 30px;
            max-width: 400px;
            margin: 0 auto;
        }
        .question-container button {
            padding: 10px 20px;
            margin: 10px;
            background-color: #4CAF50;
            color: white;
            border: none;
            font-size: 18px;
            cursor: pointer;
            border-radius: 5px;
        }
        .question-container button:hover {
            background-color: #45a049;
        }
        #finalScore {
            font-size: 24px;
            font-weight: bold;
            color: #333;
        }
    </style>
</head>
<body>

    <h1>Teste seus Conhecimentos!</h1>
    <div id="game" class="question-container">
        <p id="questionText">Qual é a capital do Brasil?</p>
        <button onclick="checkAnswer('Brasília')">Brasília</button>
        <button onclick="checkAnswer('Rio de Janeiro')">Rio de Janeiro</button>
        <button onclick="checkAnswer('São Paulo')">São Paulo</button>
        <button onclick="checkAnswer('Salvador')">Salvador</button>
    </div>
    
    <div id="finalScore" style="display:none;"></div>

    <script>
        // Definindo as perguntas e respostas
        const questions = [
            {
                question: "Qual é a capital do Brasil?",
                options: ["Brasília", "Rio de Janeiro", "São Paulo", "Salvador"],
                correctAnswer: "Brasília"
            },
            {
                question: "Qual é o maior planeta do sistema solar?",
                options: ["Terra", "Júpiter", "Saturno", "Marte"],
                correctAnswer: "Júpiter"
            },
            {
                question: "Qual é o elemento químico da água?",
                options: ["H2O", "CO2", "O2", "N2"],
                correctAnswer: "H2O"
            }
        ];

        let currentQuestionIndex = 0;
        let score = 0;

        // Exibe a próxima pergunta
        function showQuestion() {
            const question = questions[currentQuestionIndex];
            document.getElementById("questionText").textContent = question.question;
            const buttons = document.querySelectorAll(".question-container button");

            // Atualiza as opções de resposta
            buttons.forEach((button, index) => {
                button.textContent = question.options[index];
            });
        }

        // Verifica a resposta
        function checkAnswer(answer) {
            const correctAnswer = questions[currentQuestionIndex].correctAnswer;

            if (answer === correctAnswer) {
                score++;
            }

            currentQuestionIndex++;

            if (currentQuestionIndex < questions.length) {
                showQuestion();
            } else {
                showFinalScore();
            }
        }

        // Mostra a pontuação final
        function showFinalScore() {
            document.getElementById("game").style.display = "none";
            const finalScoreDiv = document.getElementById("finalScore");
            finalScoreDiv.style.display = "block";
            finalScoreDiv.textContent = `Você acertou ${score} de ${questions.length} perguntas!`;
        }

        // Inicia o jogo
        showQuestion();
    </script>

</body>
</html>
