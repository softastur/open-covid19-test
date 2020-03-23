<template>
  <div class="results">
    <div class="margin-container"></div>
    <div v-if="filledInTest" class="main-container">
      <h2>Resultaos</h2>
      <div v-if="hasSympthoms">
        <p>
          Les rempuestes suxeren qu'igual tienes sintomatoloxía compatible
          con COVID-19.
        </p>
        <p>
          Dalgunos conseyos si cuides que tienes COVID-19:
        </p>
        <ul>
          <li>
            Mira cómo evoluciones y si los síntomes empeoren, sobre manera si
            tienes dificultá p'alendar, llama a dalgún d'estos númberos:
            984 100 400, 900 878 232 ó al 112 y depués calca la tecla 1.
            Tamién pues tentar d'acudir al to centru de salú más cercanu.
          </li>
          <li>
            Queda en casa por responsabilidá y pa evitar más contaxos.
          </li>
          <li>
            Usa una mazcarina (de siguío o cambiándola cada 24 hores).
          </li>
          <li>
            Si vives con otres persones, queda nuna habitación separtada
            cola puerta zarrada y usa un bañu propiu si fore posible.
            Ventila l'habitación evitando les rabaseres y nun compartas
             nada (cacía, ropa, preseos, etc.) con naide.
          </li>
          <li>
            Llimpia les superficies y los oxetos con llexía o productos
            desinfectantes.
          </li>
          <li>
            Guarda la ropa sucio nuna bolsa zarrada y llávala per separtao a
            60-90º.
          </li>
          <li>
            Desfaite de la borrafa per separtao col usu d'un cubu con tapa.
          </li>
        </ul>
        <p>
          El COVID-19 tresmítese per gotes que s'espulsen al tusir o espirriar
          , poro la hixene y evitar el contactu ye perimportante p'amenorgar
          el contaxu.
        </p>
      </div>
      <div v-else>
        <p>
          Les rempuestes suxeren que nun tienes síntomes o nun son abondos
          pa determinar un contaxu de COVID-19.
        </p>
      </div>
      <info-panel
        text="Alcuérdate que la información que s'amuesa nesta aplicación
          nun sustitúi nin quier sustituyir, en nengún casu, el conseyu
          d'un profesional sanitariu. Si cuides que tienes síntomes
          compatibles col COVID-19 llama a dalgún d'estos númberos:
          984 100 400, 900 878 232 ó al 112 y depués calques la tecla 1.
          Tamién pues tentar d'acudir al to centru de salú más cercanu."
      ></info-panel>
      <h3>Dalgunos enllaces d'interés</h3>
      <a
        href="https://pbs.twimg.com/media/ETv1qnqX0AQS3Oz?format=jpg"
        target="_blank"
      >
        7 formes d'evitar el contaxu col Coronavirus, d'Iniciativa pol Asturianu
      </a>
      <br /><br />
      <a
        href="https://www.astursalud.es/documents/31867/964950/Inforgraf%C3%ADa_Informacion_para_la+ciudadania.pdf/76185e82-3bbb-1d64-ff29-4819c7188463"
        target="_blank"
      >
        Imaxe creada pola Conseyería de Salú del Principáu d'Asturies con información tocante al COVID-19 (en castellán)
      </a>
      <br /><br />
      <a
        href="https://www.mscbs.gob.es/profesionales/saludPublica/ccayes/alertasActual/nCov-China/home.htm"
        target="_blank"
      >
        Web del Gobiernu d'España con información tocante al COVID-19 (en castellán)
      </a>
      <br /><br />
      <a href="https://www.who.int/es/emergencies/diseases/novel-coronavirus-2019/advice-for-public/q-a-coronaviruses" target="_blank">
        Web de la Organización Mundial de la Salú pal Coronavirus (en castellán)
      </a>
      <div>
        <router-link to="/test">
          <button>Facer el cuestionariu de nueves</button>
        </router-link>
      </div>
    </div>
    <div class="margin-container"></div>
  </div>
</template>

<script>
import InfoPanel from '@/components/InfoPanel.vue';

export default {
  name: 'Results',
  components: {
    InfoPanel
  },
  computed: {
    filledInTest() {
      return this.$store.state.filledInTest;
    },
    hasSympthoms() {
      return this.$store.state.hasSympthoms;
    }
  },
  created: function() {
    if (!this.filledInTest) {
      this.$router.push({
        name: 'Home'
      });
    }
  }
};
</script>

<style>
.results {
  padding-top: 30px;
  display: flex;
  flex-direction: row;
}

.margin-container {
  width: 15%;
}

.main-container {
  width: 70%;
}

.disclaimer {
  border-radius: 12px;
  border: 1px solid cornflowerblue;
}
</style>
