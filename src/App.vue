<script setup>

  // Importando funcao da biblioteca VueJS
  import { reactive } from 'vue';

  // Importando Componentes
  import Input from './components/Input.vue';
  import Select from './components/Select.vue';

  const state = reactive ({
    firstInput: 0,
    secondInput: 0,
    mathOperation: 'plus',
    mathResult: parseInt(0),
  });

  function mathOp(e) {
    state.mathOperation = e.target.value;
    mathHappn(); 
    // console.log(state.mathOperation);
  }

  function getInput01(e) {
    state.firstInput = parseInt(e.target.value) || 0;
    mathHappn(); 
    // console.log('input-01: ' + state.firstInput);
  }

  function getInput02(e) {
    state.secondInput = parseInt(e.target.value) || 0;
    mathHappn(); 
    // console.log('input-02: ' + state.secondInput);
  }

  function mathHappn(){
    const { firstInput, secondInput, mathOperation } = state;

    if(firstInput != '' && secondInput != ''){

      switch (mathOperation) {
      case 'plus':
        state.mathResult = firstInput + secondInput;
        break;

      case 'minus':
        state.mathResult = firstInput - secondInput;
        break;

      case 'divide':
        state.mathResult = secondInput !== 0 ? firstInput / secondInput : 'Erro';
        break;

      case 'x':
        state.mathResult = firstInput * secondInput;
        break;     
    }

    }
  }

</script>

<template>

  <main>

    <div class="calc-container">
      <h1>Calculadora VueJS</h1>
      <form>
        <Input :number-input="getInput01"/>
				<i class="fi" :class="'fi-br-' + state.mathOperation"></i>					
        <Input :number-input="getInput02"/>
      </form>  
      <Select :math-op="mathOp"/>
      <span class="resultado">{{ state.mathResult }}</span>
    </div>

  </main>

</template>

<style scoped>

  main{
    width: 100%;
    height: 100vh;

    display: flex;
    align-items: center;
    justify-content: center;

    .calc-container{
      background-color: #fff;
      border-radius: 10px;

      box-shadow: 0 5px 100px 0 rgba(0, 0, 0, 0.19);

      width: 90%;
      max-width: 500px;

      text-align: center;

      padding: 10px;

      h1{
        font-weight: 600;
        color: #34495e;

        margin: 10px 0 18px 0;
      }

      form{
        width: 100%;

        display: flex;
        align-items: center;
        justify-items: center;
        gap: 10px;
        
        i{
          line-height: 0;
          font-weight: 800;
          font-size: 14px;
          color: #41b883
        }
      }
    }
  }

  .resultado{
    background-color: #f2f2f2;
    border-radius: 10px;

    text-align: left;
    color: #34495e;

    width: 100%;
    display: block;

    margin: 10px 0 0 0;
    padding: 10px;
  }

</style>
