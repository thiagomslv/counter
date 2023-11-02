<script setup>

</script>

<template>

    <div class="counter">

        <div class="containerNumber">
            <span class="number">0</span>
            <span class="number">0</span>
            <span class="number">0</span>
            <span class="number">0</span>
        </div>
    </div>
  
</template>

<style scoped>

.counter{

    width: 100vw;
    height: 100vh;
    
    display: flex;
    justify-content: center;
    align-items: center;

    font-size: 5em;
}

.containerNumber{

    width: 350px;
    height: 120px;

    display: flex;
    justify-content: space-around;
    align-items: center;

    background-color: #123142;
    border: solid 5px #123142;
    border-radius: 5px;
}

.number{

    width: 80px;
    height: 120px;
    text-align: center;
    background-color: black;
    border-radius: 5px;
}
</style>
