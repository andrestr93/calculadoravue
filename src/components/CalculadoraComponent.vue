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
            but1: 1,
            but2: 2,
            but3: 3,
            but4: 4,
            but5: 5,
            but6: 6,
            but7: 7,
            but8: 8,
            but9: 9,
            but0: 0,
            resultado: "",
            operacion: "",
            operandoa: 0,
            operandob: 0


        }


    },

    mounted() {


        this.visualizalizacion();




    },

    methods: {

        visualizalizacion() {
            this.but1 = document.getElementById("numb1");
            this.but2 = document.getElementById("numb2");
            this.but3 = document.getElementById("numb3");
            this.but4 = document.getElementById("numb4")
            this.but5 = document.getElementById("numb5")
            this.but6 = document.getElementById("numb6");
            this.but7 = document.getElementById("numb7");
            this.but8 = document.getElementById("numb8");
            this.but9 = document.getElementById("numb9");
            this.but0 = document.getElementById("numb0");
            this.butsuma = document.getElementById("operador+")
            this.butresta = document.getElementById("operador-")
            this.butdivision = document.getElementById("operador/")
            this.butmultiplicacion = document.getElementById("operadorx")
            this.butigual = document.getElementById("operador=")
            this.resultado = document.getElementById("screen");

        },


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

            this.operandoa = this.resultado.textContent;
            this.resultado.textContent = "+"
            this.resetear();
            this.operacion = "+"
        },

        pulseButResta() {

            this.operandoa = this.resultado.textContent;
            this.resultado.textContent = "-"
            this.resetear();
            this.operacion = "-"
        },


        pulseButMult() {
            this.operandoa = this.resultado.textContent;
            this.resetear();
            this.operacion = "*"
        },


        pulseButDiv() {

            this.operandoa = this.resultado.textContent;
            this.resultado.textContent = "/"
            this.resetear();
            this.operacion = "/"
        },


        pulseButIgual() {

            this.operandob = this.resultado.textContent;
            this.operaciones()


        },




        operaciones() {
            let res = 0;
            switch (this.operacion) {

                case "+":
                    res = parseFloat(this.operandoa) + parseFloat(this.operandob)
                    break;

                case "-":
                    res = parseFloat(this.operandoa) - parseFloat(this.operandob)
                    break;
            
                case "*":
                    res = parseFloat(this.operandoa) * parseFloat(this.operandob)
                    break;

                case "/":
                    res = parseFloat(this.operandoa) / parseFloat(this.operandob)
                    break;


            }
            this.resultado.textContent = res;


        },
        resetear() {

            this.resultado.textContent = "";
        }





    }


}






</script>