# Jeporady
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Jeopardy Game</title>
  <style>
    body {
      font-family: Arial, sans-serif;
    }
    #board {
      display: grid;
      grid-template-columns: repeat(4, 1fr);
      gap: 10px;
      margin: 20px;
    }
    .category {
      text-align: center;
      font-weight: bold;
    }
    .question {
      cursor: pointer;
      padding: 10px;
      text-align: center;
      border: 1px solid #ccc;
      background-color: #f5f5f5;
    }
  </style>
</head>
<body>

<div id="board"></div>

<script>
  // Jeopardy data (example)
  const jeopardyData = [
    { category: "History", questions: ["Question 1", "Question 2", "Question 3", "Question 4"] },
    { category: "Science", questions: ["Question 5", "Question 6", "Question 7", "Question 8"] },
    { category: "Programming", questions: ["Question 9", "Question 10", "Question 11", "Question 12"] },
    { category: "Movies", questions: ["Question 13", "Question 14", "Question 15", "Question 16"] },
  ];

  const boardElement = document.getElementById('board');

  // Create the game board
  jeopardyData.forEach((category, columnIndex) => {
    const categoryElement = document.createElement('div');
    categoryElement.classList.add('category');
    categoryElement.textContent = category.category;
    boardElement.appendChild(categoryElement);

    category.questions.forEach((question, rowIndex) => {
      const questionElement = document.createElement('div');
      questionElement.classList.add('question');
      questionElement.textContent = `$${(rowIndex + 1) * 100}`;
      questionElement.addEventListener('click', () => showQuestion(category.category, question));
      boardElement.appendChild(questionElement);
    });
  });

  // Function to display the question
  function showQuestion(category, question) {
    alert(`Category: ${category}\n\n${question}`);
  }
</script>

</body>
</html>
