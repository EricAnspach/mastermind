<template>
<!-- This component will display radio buttons for the user to select colors of the pegs for the guess. -->
    <div class="row">
        <div class="col-sm-12 col-md-6 col-lg-6">
            <form>
                <!-- Peg 1 -->
                <div class="col-md-3 col-lg-3 peg">
                    <img src="../assets/dot8.png" width="75px" height="75px">
                    <label for="1-one"><input type="radio" id="1-one" value=1 v-model="peg1"> Red</label>
                    <label for="1-two"><input type="radio" id="1-two" value=2 v-model="peg1"> Orange</label>
                    <label for="1-three"><input type="radio" id="1-three" value=3 v-model="peg1"> Yellow</label>
                    <label for="1-four"><input type="radio" id="1-four" value=4 v-model="peg1"> Green</label>
                    <label for="1-five"><input type="radio" id="1-five" value=5 v-model="peg1"> Blue</label>
                    <label for="1-six"><input type="radio" id="1-six" value=6 v-model="peg1"> Purple</label>
                </div>
                <!-- Peg 2 -->
                <div class="col-md-3 col-lg-3 peg">
                    <img src="../assets/dot8.png" width="75px" height="75px">
                    <label for="2-one"><input type="radio" id="2-one" value=1 v-model="peg2"> Red</label>
                    <label for="2-two"><input type="radio" id="2-two" value=2 v-model="peg2"> Orange</label>
                    <label for="2-three"><input type="radio" id="2-three" value=3 v-model="peg2"> Yellow</label>
                    <label for="2-four"><input type="radio" id="2-four" value=4 v-model="peg2"> Green</label>
                    <label for="2-five"><input type="radio" id="2-five" value=5 v-model="peg2"> Blue</label>
                    <label for="2-six"><input type="radio" id="2-six" value=6 v-model="peg2"> Purple</label>
                </div>
                <!-- Peg 3 -->
                <div class="col-md-3 col-lg-3 peg">
                    <img src="../assets/dot8.png" width="75px" height="75px">
                    <label for="3-one"><input type="radio" id="3-one" value=1 v-model="peg3"> Red</label>
                    <label for="3-two"><input type="radio" id="3-two" value=2 v-model="peg3"> Orange</label>
                    <label for="3-three"><input type="radio" id="3-three" value=3 v-model="peg3"> Yellow</label>
                    <label for="3-four"><input type="radio" id="3-four" value=4 v-model="peg3"> Green</label>
                    <label for="3-five"><input type="radio" id="3-five" value=5 v-model="peg3"> Blue</label>
                    <label for="3-six"><input type="radio" id="3-six" value=6 v-model="peg3"> Purple</label>
                </div>
                <!-- Peg 4 -->
                <div class="col-md-3 col-lg-3 peg">
                    <img src="../assets/dot8.png" width="75px" height="75px">
                    <label for="4-one"><input type="radio" id="4-one" value=1 v-model="peg4"> Red</label>
                    <label for="4-two"><input type="radio" id="4-two" value=2 v-model="peg4"> Orange</label>
                    <label for="4-three"><input type="radio" id="4-three" value=3 v-model="peg4"> Yellow</label>
                    <label for="4-four"><input type="radio" id="4-four" value=4 v-model="peg4"> Green</label>
                    <label for="4-five"><input type="radio" id="4-five" value=5 v-model="peg4"> Blue</label>
                    <label for="4-six"><input type="radio" id="4-six" value=6 v-model="peg4"> Purple</label>
                </div>
                <div class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3 form-group">
                    <button class="btn btn-primary btn-enter" @click.prevent="enterGuess">Enter</button>
                </div>
            </form>
        </div>
    </div>
</template>

<script>
    export default {
        data: function() {
            return {
                peg1: '',
                peg2: '',
                peg3: '',
                peg4: '',
                guess: []
            };
        },
        methods: {
            enterGuess() {
                this.guess.push(this.peg1, this.peg2, this.peg3, this.peg4);
                this.$emit('guessEntered', this.guess);
                this.peg1 = '';
                this.peg2 = '';
                this.peg3 = '';
                this.peg4 = '';
                this.guess = []
            }
        }
    }
</script>

<style>
.peg {
    font-size: 20px;
}
</style>
