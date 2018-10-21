<template>
<!-- Component will display a column of Guess components with rows of colored pegs depicting previous guesses. -->
    <div class="row">
        <div class="col-sm-12 col-md-6 col-md-offset-6 col-lg-6 col-lg-offset-6">
           <app-guess v-for="guess in guesses">{{ guess }}</app-guess>
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
