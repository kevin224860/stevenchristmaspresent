<template>
    <div class="frosty-question">
      <p>
        Based on a true story of your Dad, what movie was was based on his experience meeting Santa 🎅 and he even showed you the bell as proof?   
      </p>
      <input 
        v-model="userAnswer" 
        type="text" 
        placeholder="Type your answer here..." 
      />
      <button @click="checkAnswer">Submit Answer</button>
      <p v-if="resultMessage" :class="{'correct': isCorrect, 'incorrect': !isCorrect}">
        {{ resultMessage }}
      </p>
  
      <p class="correct">{{ clue }}</p>
  
    </div>
  </template>
  
  <script>
  export default {
    name: 'FrostyQuestion',
    data() {
      return {
        userAnswer: '',
        correctAnswers: ['the polar express', 'polar express'],  // Accepts both variations
        resultMessage: '',
        clue: '',
        isCorrect: false
      };
    },
    methods: {
      checkAnswer() {
        // Normalize the input answer to lowercase and check for both possible answers
        const normalizedAnswer = this.userAnswer.trim().toLowerCase();
        if (this.correctAnswers.includes(normalizedAnswer)) {
          this.resultMessage = '🎉 Correct!';
          this.clue = 'This next clue has to do with your dad, I’m a collection that is growing right now I am 5 pounds strong soon will be more. ';
          this.isCorrect = true;
        } else {
          this.resultMessage = '😢 Oops! That’s not the name of our jolly snowman friend.';
          this.isCorrect = false;
        }
        this.userAnswer = ''; // Clear the text box after submitting
      }
    }
  };
  </script>
  
  <style scoped>
  .frosty-question {
    text-align: center;
    background-color: #e0f7fa;
    padding: 2rem;
    border: 2px solid #03a9f4;
    border-radius: 10px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
    max-width: 600px;
    margin: 2rem auto;
  }
  
  h1 {
    color: #0288d1;
    margin-bottom: 1rem;
  }
  
  p {
    font-size: 1.1rem;
    margin-bottom: 1.5rem;
    color: #444;
  }
  
  input {
    width: 60%;
    padding: 0.5rem;
    margin-bottom: 1rem;
    border: 1px solid #ccc;
    border-radius: 5px;
  }
  
  button {
    background-color: #0288d1;
    color: white;
    font-size: 1rem;
    padding: 0.5rem 1rem;
    border: none;
    border-radius: 5px;
    cursor: pointer;
    margin-top: 1rem;
    transition: background-color 0.3s ease;
  }
  
  button:hover {
    background-color: #0277bd;
  }
  
  .correct {
    color: #4caf50;
    font-weight: bold;
    margin-top: 1rem;
  }
  
  .incorrect {
    color: #d32f2f;
    font-weight: bold;
    margin-top: 1rem;
  }
  </style>
  