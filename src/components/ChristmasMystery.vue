<template>
    <div class="christmas-mystery">
      <h1>🎄 The Grinch Stole Your Christmas Present! 🎁</h1>
      <p>
        Oh no! Just as you were about to unwrap your Christmas present, 
        the sneaky Grinch swooped in and snatched it away! 🥺🎁  
      </p>
      <p>
        But don’t worry—you can still save Christmas! To recover your present, 
        you'll need to solve tricky questions and search for hidden clues 
        scattered across Whoville. 🕵️‍♂️🔍
      </p>
      <p>
        Are you ready to embark on this festive quest and outsmart the Grinch? 
        The fate of your Christmas joy depends on you! 🎅💪
      </p>
      <button @click="startAdventure">Start Your Adventure</button>
    </div>
  </template>
  
  <script>
  export default {
    name: 'ChristmasMystery',
    methods: {
      startAdventure() {
        this.$router.push('/adventure');
      },
      
    }
  };
  </script>
  
  <style scoped>
  .christmas-mystery {
    text-align: center;
    background-color: #f0f8ff;
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
    line-height: 1.5;
    margin-bottom: 1rem;
    color: #444;
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
  </style>
  