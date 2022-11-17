<template>

    <body>
        <div class="container">
            <div class="interfaz">
                <div id="screen">

                </div>
                <button @click="this.pulsebut1()" id="number1">1</button>
                <button @click="this.pulsebut2()" id="number2">2</button>
                <button @click="this.pulsebut3()" id="number3">3</button>
                <button @click="this.pulseButMult()" id="operadorx">x</button>

                <button @click="this.pulsebut4()" id="number4">4</button>
                <button @click="this.pulsebut5()" id="number5">5</button>
                <button @click="this.pulsebut6()" id="number6">6</button>
                <button @click="this.pulseButResta()" id="operador-">-</button>

                <button @click="this.pulsebut7()" id="number7">7</button>
                <button @click="this.pulsebut8()" id="number8">8</button>
                <button @click="this.pulsebut9()" id="number9">9</button>
                <button @click="this.pulseButMas()" id="operador+">+</button>

                <button @click="this.pulsebut0()" class="numb0">0</button>
                <button @click="pulseButDiv()" id="operador/">/</button>
                <button @click="this.pulseButIgual()" class="operador=">=</button>
                <button @click="this.resetear()">C</button>
            </div>
        </div>
    </body>
</template>


<script>

export default {

    name: 'CalculadoraComponente',

    components: {


    },

    data() {


        return {


            resultado: !"",
            operacion: !"",
            operandoa: 0,
            operandob: 0,
            comprueba: false,
            res: 0


        }


    },

    mounted() {

        this.resultado = document.getElementById("screen");

    },

    methods: {


        pulsebut0() {



            this.resultado.textContent = this.resultado.textContent + "0";

        },

        pulsebut1() {
            this.resultado.textContent = this.resultado.textContent + "1";
            

        },

        pulsebut2() {

            this.resultado.textContent = this.resultado.textContent + "2";

        },

        pulsebut3() {

            this.resultado.textContent = this.resultado.textContent + "3";

        },

        pulsebut4() {

            this.resultado.textContent = this.resultado.textContent + "4";

        },

        pulsebut5() {

            this.resultado.textContent = this.resultado.textContent + "5";


        },


        pulsebut6() {

            this.resultado.textContent = this.resultado.textContent + "6";

        },

        pulsebut7() {

            this.resultado.textContent = this.resultado.textContent + "7";

        },

        pulsebut8() {

            this.resultado.textContent = this.resultado.textContent + "8";

        },

        pulsebut9() {

            this.resultado.textContent = this.resultado.textContent + "9";


        },


        pulseButMas() {
            this.operandoa = this.resultado.textContent
            this.operacion = "+"
            this.limpiar();


        },

        pulseButResta() {
            this.operandoa = this.resultado.textContent;
            this.operacion = "-"
            this.limpiar();

        },


        pulseButMult() {
            this.operandoa = this.resultado.textContent;
            this.operacion = "*"
            this.limpiar();
        },


        pulseButDiv() {
            this.operandoa = this.resultado.textContent;
            this.operacion = "/"
            this.limpiar();
        },


        pulseButIgual() {
                this.operandob = this.resultado.textContent;
                this.resuelve();
               
    
        },


        limpiar() {

            this.resultado.textContent = ""
        },



        resetear() {

            this.resultado.textContent = "";
            this.operandoa = 0;
            this.operandob = 0;
            this.operacion = "";
        },


        resuelve() {
            this.res = 0;
            switch (this.operacion) {
                case "+":
                    this.res = parseFloat(this.operandoa) + parseFloat(this.operandob);
                    break;

                case "-":
                    this.res = parseFloat(this.operandoa) - parseFloat(this.operandob);
                    break;

                case "/":
                    this.res = parseFloat(this.operandoa) / parseFloat(this.operandob);
                    break;

                case "*":
                    this.res = parseFloat(this.operandoa) * parseFloat(this.operandob);
                    break;

            }
            this.resetear();
            this.resultado.textContent = this.res;
        }











    }


}






</script>