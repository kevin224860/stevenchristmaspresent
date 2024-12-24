<template>
  <div class="scrooge-question">
    <h1>🎄 Scrooge's Christmas Lesson 🎩</h1>
    <p>
      "A very cheap, old man named Ebenezer Scrooge is visited by three ghosts who teach him a lesson about Christmas.  
      In which movie does this heartwarming story take place?"
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
  </div>
</template>

<script>
export default {
  name: 'ScroogeQuestion',
  data() {
    return {
      userAnswer: '',
      correctAnswers: ['a christmas carol', 'a christmas carol movie', 'christmas carol'],  // Accepts different variations
      resultMessage: '',
      clue: '',
      isCorrect: false
    };
  },
  methods: {
    checkAnswer() {
      // Normalize the input answer to lowercase and check for all correct variations
      const normalizedAnswer = this.userAnswer.trim().toLowerCase();
      if (this.correctAnswers.includes(normalizedAnswer)) {
        this.resultMessage = '🎉 Correct! Ebenezer Scrooge learns a valuable lesson in A Christmas Carol!';
        this.clue = 'Well done Steven! 🎉🎉 You have solved all the tasks and you can have your present back! To find your present look by the Christmas tree 🎄'
        this.isCorrect = true;
      } else {
        this.resultMessage = '😢 Oops! That’s not the name of the classic Christmas story.';
        this.isCorrect = false;
      }
      this.userAnswer = ''; // Clear the text box after submitting
    }
  }
};
</script>

<style scoped>
.scrooge-question {
  text-align: center;
  background-color: #fce4ec;
  padding: 2rem;
  border: 2px solid #f50057;
  border-radius: 10px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  max-width: 600px;
  margin: 2rem auto;
}

h1 {
  color: #f50057;
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
  background-color: #f50057;
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
  background-color: #c51162;
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
