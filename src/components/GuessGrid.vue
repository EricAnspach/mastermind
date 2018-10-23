<template>
<!-- Component will display a column of Guess components with rows of colored pegs depicting previous guesses. -->
    <div class="row">
        <div class="col-sm-12 col-md-6 col-md-offset-6 col-lg-6 col-lg-offset-6">
           <app-guess v-for="guess in guesses">
                <!-- Code here to pass dot images into the slot in Guess.vue.
                Loop through array for each guess to display the right color dot image at each position -->
                <img src="../assets/dot1.png" width="75px" height="75px">
                <img src="../assets/dot2.png" width="75px" height="75px">
                <img src="../assets/dot3.png" width="75px" height="75px">
                <img src="../assets/dot4.png" width="75px" height="75px">

           </app-guess>
        </div>


    </div>
</template>

<script>
    import Guess from './Guess.vue';

    export default {
        props: ['guesses'],
        components: {
            appGuess: Guess
        }
    }
</script>

<style>

</style>
