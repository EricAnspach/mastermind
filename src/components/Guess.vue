<template>
<!-- This component displays one row of colored pegs for a single guess.
    To the right, up to four black and/or white pegs per row will display correct or partially correct guesses. -->
    <div>
        <div class="panel panel-default">
            <div class="panel-body">
                <slot></slot>

            </div>
        </div>
    </div>
</template>

<script>
    export default {
        props: ['guesses']
    }
</script>

<style>
   
</style>