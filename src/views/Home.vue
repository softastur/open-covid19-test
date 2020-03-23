<template>
  <div class="home">
    <div class="margin-container"></div>
    <div>
      <h1>Afáyate en prueba-covid19-ast</h1>
      <p class="home-p">
        Un cuestionariu d'autoevaluación pal COVID-19 que determina si tas
        contaxáu de Coronavirus según les opciones que marques.
      </p>
      <p class="home-p">
        Sí quies saber más entra
        <a href="https://github.com/softastur/prueba-covid19-ast"
          >nel depósitu d'esta aplicación en GitHub
          <font-awesome-icon :icon="['fab', 'github']"></font-awesome-icon
        ></a>
        pa saber cómo funciona.
      </p>
      <info-panel
        class="home-info-panel"
        text="La información que se consiga pente l'usu d'esta aplicación nun sustitúi
        nin quier sustituyir, en nengún casu, el conseyu d'un profesional
        sanitariu. Si cuides que tienes síntomes compatibles col COVID-19, llama a
        dalgún d'estos númberos: 984 100 400, 900 878 232 ó al 112 y depués calca la
        tecla 1. Tamién pues tentar d'acudir al to centru de salú más cercanu."
      ></info-panel>
      <div class="center">
        <router-link to="/test">
          <button>¡Entendílo! Quiero facer el cuestionariu</button>
        </router-link>
      </div>
    </div>
    <div class="margin-container"></div>
  </div>
</template>

<script>
import InfoPanel from '@/components/InfoPanel.vue';

export default {
  name: 'Home',
  components: {
    InfoPanel
  }
};
</script>

<style>
a {
  color: cornflowerblue;
}

.home {
  padding-top: 30px;
  display: flex;
  flex-direction: row;
}

.home-p {
  padding: 1% 5%;
}

.home-info-panel {
  margin: 1% 5%;
}

.margin-container {
  display: flex;
  width: 20%;
}
</style>
