<template>
  <section class="section">

    <div class="columns">
      <div class="column is-half is-offset-one-quarter">
        <!--<h1 class="title has-text-centered">Animate.css</h1>-->
        <transition
          :appear-active-class="animacao"
          appear>
          <img v-if="exibir" src="/src/assets/logo.png" alt="Logo do Vue.js">
        </transition>
        <h2 class="subtitle has-text-centered">Selecione uma animação de exemplo</h2>
      </div>
    </div>

    <div class="columns">
      <div class="column is-half is-offset-one-quarter">
        <div class="control has-addons has-addons-centered">
          <span class="select is-medium">
            <select v-model="animacaoSelecionada">
              <optgroup label="Destaques">
                <option v-for="animacao in animacoes.destaques">{{ animacao }}</option>
              </optgroup>
            </select>
          </span>
          <button @click="animar" class="button is-success is-outlined is-large">Animar</button>
        </div>
      </div>
    </div>

    <div class="column">
      <div class="column is-half is-offset-one-quarter">
        <hr>
        <small class="has-text-centered">
          Desenvolvido por: <strong>Rafael Henrique Capati</strong>
        </small>
        <small class="has-text-centered">
          Implementado com: <a href="http://vuejs.org" target="_blank">Vue.js</a>
          e <a href="http://bulma.io" target="_blank">Bulma.css</a>
        </small>
      </div>
    </div>

  </section>
</template>

<script>
  export default {
    data() {
      return {
        animacao: "",
        animacaoSelecionada: "bounce",
        exibir: true,
        animacoes: {
          destaques: [
            "bounce",
            "flash",
            "pulse",
            "rubberBamd",
            "shake",
            "swing",
            "tada",
            "wobble",
            "jello",
          ],
        },
      };
    },
    computed: {
      animacao() {
        return "animated " + this.animacaoSelecionada;
      },
    },
    methods: {
      animar() {
        
      },
    }
  }
</script>

<style scoped>
  img {
    max-width: 500px;
    display: block;
    margin: auto;
  }

  .title {
    font-size: 5em;
    padding: 30px 0 20px 0;
  }

  .subtitle {
    /*margin-bottom: 30px;*/
    margin-top: 30px;
  }

  .control {
    /*text-align: center;*/
  }

  .control .button {
    margin-left: 10px;
  }

  .select,
  .select select {
    height: 48px;
  }

  hr {
    margin-top: 0;
  }

  small {
    display: block;
  }
</style>
