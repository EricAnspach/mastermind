<template>
  <div class="container">
    <h1>Mastermind</h1>
    <br>
    <br>
    <app-new-guess @guessEntered = "addGuess"></app-new-guess>
    <app-guess-grid :guesses="guesses"></app-guess-grid>
      

      <!-- 1. Game starts, randomly generate four pieces of puzzle -->

        <!-- a. Create array with four items. -->        
        <!-- b. Using loop create 4 random pegs with six possible colors. -->
        <!-- c. Display component with grey shaded circles. -->

      <!-- 2. Display component for each guess. Radio buttons for user to choose colors of guess -->

        <!-- a. Create array for guess. -->
        <!-- b. Store values from radio buttons in guess array. -->

      <!-- 3. Button for user to submit guess -->

      <!-- 4. Compare guess to puzzle -->

        <!-- a. Compare each item in guess with item of same index in solution.
            For each match, add one to black peg count. -->
        <!-- b. If black peg count is four, player wins. Display win message and ask whether to play again. -->
        <!-- c. Else, compare for matches of each guess item to all indexes in solution array.
            For each match, add one to white peg count. -->
        <!-- d. Subtract number of black pegs from white peg count.
            Display component for guess, black and white peg count. -->
        <!-- e. Clear guess array, black and white peg counts. -->

      <!-- 5. If correct, game over. Display component for number of guesses it took.
          Ask if user wants to play again, and if so, restart game. -->

      <!-- 6. Else, determine number of black pegs, number of white pegs. Display pegs. Return to step 2. -->

  </div>
  
</template>

<script>
  import NewGuess from './components/NewGuess.vue';
  import GuessGrid from './components/GuessGrid.vue';

  export default {
    name: 'app',
    data: function() {
      return {
        solution: [1, 2, 3, 4],
        guess: [],
        guesses: [],
        blackPegCount: 0,
        whitePegCount: 0,
        gameOver: false,
        maxGuesses: 10
      }
    },
    methods: {
      addGuess(guess) {
        this.guesses.push(guess);
      },
      makeSolution() {
        // generate four random numbers, from 1 to 6, put in array
        for (var i = 0; i < 4; i++) {
          solution[i] = Math.floor(Math.random() * 6);
        }
      },
      compareArrays() {
        // compare each guess item to each solution item of same index
        // compare each guess item to all solution items
        for (var i = 0; i < 4; i++) {
          if (guess[i] == solution[i]) {
            blackPegCount++;
          }

          for (var j = 0; j < 4; j++) {
            if (guess[i] == solution[j]) {
            whitePegCount++;
            }
          }        
        }
        whitePegCount = whitePegCount - blackPegCount;      
      }
    },
    components: {
      appGuessGrid: GuessGrid,
      appNewGuess: NewGuess
    }
  }
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

h1, h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
</style>
