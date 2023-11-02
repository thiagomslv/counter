<script>

    export default{

        data(){

            return({    

                counter: 0,
                numbers: ["0", "0", "0", "0"]
            })
        },

        methods: {

            addCounter(){

                this.counter++;
                const countStrig = this.counter.toString();
                for(let i = 0; i < 4; i++) this.numbers[i] = "0";

                if(this.counter < 0){

                    const msb = countStrig.length - 1;

                    for(let i = 0, control = msb; i < msb; i++){


                        this.numbers[i] = countStrig[control--];
                    }

                    const mumberWithSubSimbol = "-" + this.numbers[msb - 1];
                    this.numbers[msb - 1] = mumberWithSubSimbol;

                }else{

                    const msb = countStrig.length;

                    for(let i = 0, control = msb - 1; i < msb; i++){

                        this.numbers[i] = countStrig[control--];
                    }
                }
                
            },

            subCounter(){

                this.counter--;

                const countStrig = this.counter.toString();
                const msb = countStrig.length - 1;

                for(let i = 0; i < 4; i++) this.numbers[i] = "0";

                if(this.counter < 0){

                    for(let i = 0, control = msb; i < msb; i++){


                        this.numbers[i] = countStrig[control--];
                    }

                    const mumberWithSubSimbol = "-" + this.numbers[msb - 1];
                    this.numbers[msb - 1] = mumberWithSubSimbol;

                }else{

                    for(let i = 0, control = msb; i < msb + 1; i++){

                        this.numbers[i] = countStrig[control--];
                    }
                }

                
            }
        }
    }
    
</script>

<template>

    <div class="counter">

        <h1>Contador numérico</h1>
        <div class="containerNumber">
            <span class="number">{{ numbers[3] }}</span>
            <span class="number">{{ numbers[2] }}</span>
            <span class="number">{{ numbers[1] }}</span>
            <span class="number">{{ numbers[0] }}</span>
        </div>

        <div class="containerbuttons">
            <button @click="subCounter" class="button remove" type="button">-</button>
            <button @click="addCounter" class="button add" type="button">+</button>
        </div>
        
    </div>
  
</template>

<style scoped>

h1{

    font-size: 34px;
}
.counter{

    width: 100vw;
    height: 100vh;
    
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;

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

.containerbuttons{

    width: 200px;
    height: 90px;

    display: flex;
    justify-content: space-between;

    margin-top: 30px;
}

.number{

    width: 80px;
    height: 120px;
    text-align: center;
    background-color: black;
    border-radius: 5px;
}

.button{

    width: 80px;
    height: 80px;
    font-size: 0.7em;
    
    display: flex;
    justify-content: center;
    align-items: center;

    border-radius: 50%;
    border: solid 4px rgb(54, 54, 54);

    cursor: pointer;
}

.button:focus {
    outline: none;
}

.add{

    background-color: #19d476;
}

.remove{

    background-color: #d9655a;
}

.add:hover{

    background-color: #008933;
    border: solid 4px black;
}

.remove:hover{

    background-color: #881c1d;
    border: solid 4px black;
}

</style>
