<template>
    <div class="grinch-question">
      <h1>🎩 The Grinch's Riddle 🦌</h1>
      <p>
        "I didn’t have a real reindeer to pull my sleigh,  
        so I used my loyal dog instead.  
        What was my dog's name?"  
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
    name: 'GrinchQuestion',
    data() {
      return {
        userAnswer: '',
        correctAnswer: 'Max',
        resultMessage: '',
        clue: "",
        isCorrect: false
      };
    },
    methods: {
      checkAnswer() {
        if (this.userAnswer.trim().toLowerCase() === this.correctAnswer.toLowerCase()) {
          this.resultMessage = '🎉 Correct! Max was the Grinch’s faithful reindeer-dog!';
          this.clue = 'In a place that is cold you can find your next steps';
          this.isCorrect = true;
        } else {
          this.resultMessage = '😢 Oops! That’s not the name of the Grinch’s reindeer-dog.';
          this.isCorrect = false;
        }
        this.userAnswer = ''; // Clear the text box after submitting
      }
    }
  };
  </script>
  
  <style scoped>
  .grinch-question {
    text-align: center;
    background-color: #fdfde5;
    padding: 2rem;
    border: 2px solid #4caf50;
    border-radius: 10px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
    max-width: 600px;
    margin: 2rem auto;
  }
  
  h1 {
    color: #d32f2f;
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
    background-color: #4caf50;
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
    background-color: #388e3c;
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
  