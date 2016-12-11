<template>
  <section class="section">

    <div class="columns">
      <div class="column is-half is-offset-one-quarter">
        <!--<h1 class="title has-text-centered">Animate.css</h1>-->
        <transition
          :appear-active-class="animation"
          v-on:before-leave="beforeLeave"
          appear>
          <img v-if="show" :class="['animated', selectedAnimation]" src="/src/assets/logo.png" alt="Vue.js logo">
        </transition>
        <h2 class="subtitle has-text-centered">Select an animation to run</h2>
      </div>
    </div>

    <div class="columns">
      <div class="column is-half is-offset-one-quarter">
        <div class="control has-addons has-addons-centered">
          <span class="select is-medium">
            <select v-model="selectedAnimation">
              <optgroup label="Highlights">
                <option v-for="animation in animations.highlights">{{ animation }}</option>
              </optgroup>
            </select>
          </span>
          <button @click="animate" class="button is-success is-outlined is-large">Animate it</button>
        </div>
      </div>
    </div>

    <div class="column">
      <div class="column is-half is-offset-one-quarter">
        <hr>
        <small class="has-text-centered">
          Developed by: <strong><a href="http://www.rhcapati.com.br/">Rafael Henrique Capati</a></strong>
        </small>
        <small class="has-text-centered">
          Featured with: <a href="http://vuejs.org" target="_blank">Vue.js</a>
          and <a href="http://bulma.io" target="_blank">Bulma.css</a>
        </small>
      </div>
    </div>

  </section>
</template>

<script>
  export default {
    data() {
      return {
        animation: "",
        selectedAnimation: "bounce",
        show: true,
        animations: {
          highlights: [
            "bounce",
            "flash",
            "pulse",
            "rubberBand",
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
      animation() {
        return "animated " + this.selectedAnimation;
      },
    },
    methods: {
      animate(event) {
        this.show = false;
        event.target.blur();
      },
      beforeLeave() {
        this.show = true;
      }
    },
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
