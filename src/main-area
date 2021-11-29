<template>
  <div>
    <abrir-chamadas v-if="subPages[0].showing"></abrir-chamadas>
    <historico-chamadas v-if="subPages[1].showing"></historico-chamadas>
    <div v-if="mainArea">
      <div class="wrapper">
        <div class="container-fluid">
          <section class="presentation">
            <div class="presentation-view">
              <div class="header-text">
                <h1 style="margin-top: 2rem;">Chamada RFID</h1>
              </div>
              <br /><br />
              <div class="btns">
                <ul class="list-inline">
                  <div>
                    <li class="itens">
                      <button
                        class="buttonEnter_mainArea"
                        @click="changeComponent('abrir-chamadas')"
                      >
                        <div style="margin-right: auto;">
                          <i class="fas fa-search"></i>
                        </div>
                        <div class="btn-text">
                          Abrir Chamadas
                        </div>
                      </button>
                    </li>
                  </div>
                  <div>
                    <li class="itens">
                      <button
                        class="buttonEnter_mainArea"
                        @click="changeComponent('historico-chamadas')"
                      >
                        <div style="margin-right: auto;">
                          <i class="fas fa-list"></i>
                        </div>

                        <div class="btn-text">
                          Histórico de chamadas
                        </div>
                      </button>
                    </li>
                  </div>
                </ul>
              </div>
            </div>
          </section>
        </div>
      </div>
    </div>
  </div>
</template>

<script>

import abrirChamadas from "../abrir-chamadas/abrir-chamadas.vue";
import historicoChamadas from "../historico-chamadas/historico-chamadas.vue";
export default {
  name: "StudentArea",
  components: {
    abrirChamadas: abrirChamadas,
    historicoChamadas: historicoChamadas,
  },
  data() {
    return {
      mainArea: true,
      subPages: [
        {
          component: "abrir-chamadas",
          showing: false,
        },
        {
          component: "historico-chamadas",
          showing: false,
        },
      ],
    };
  },
  methods: {
    changeComponent(component) {
      this.subPages.forEach(page => (page.showing = false));
      this.$forceUpdate();
      switch (component) {
        case "abrir-chamadas":
          this.mainArea = false;
          this.subPages.find(
            page => page.component == "abrir-chamadas",
          ).showing = true;
          break;
        case "historico-chamadas":
          this.mainArea = false;
          this.subPages.find(
            page => page.component == "historico-chamadas",
          ).showing = true;
          break;
      }
    },
  },
};
</script>

<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Inter:wght@200;300;400;500&display=swap");
@import url("https://fonts.googleapis.com/css2?family=Roboto:ital,wght@1,700&display=swap");

body {
  background-color: transparent;

  height: 100%;
  max-width: 100%;
}
* {
  background-size: cover;
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: "Inter", sans-serif;
}
.container {
  width: 100%;
  height: 100%;
}
/* TExt */
.header-text {
  text-align: center;
  display: flex;
  justify-content: center;
  align-items: center;
}
/* SECTION PRESENTATION */
button:hover {
  transform: scale(1.05);
}
.presentation h1 {
  font-size: 55px;
  word-wrap: break-word;
  color: #f1f1f1;
}
/* Test1 */
.presentation {
  display: flex;
  align-items: center;
  justify-content: center;
}
.presentation-view {
  width: 100%;
  min-height: 45vh;
  background-size: cover;
  background-image: linear-gradient(
    to right,
    rgba(43, 50, 178, 1),
    rgba(43, 50, 178, 1)
  );
  background-position: center;
}

.btns {
  margin-top: 2rem;
  display: grid;
  justify-content: center;
  align-items: center;
}
.buttonEnter {
  width: 20rem;
  height: 3rem;
  border-radius: 20px;
  background-color: rgba(255, 255, 255, 1);

  opacity: 1;
  border: 0.1em solid transparent;
  box-shadow: 4 4 1rem #fff;
  color: rgba(32, 92, 191, 1);
  text-decoration: none;
  text-align: center;
  display: inline-grid;
  grid-auto-flow: column;
  grid-gap: 12px;
  justify-content: center;
  align-items: center;
  font-weight: bold;
  font-size: 14px;
  padding: 0.3em 2em;
  transition: all 0.5s;
  cursor: pointer;
  border: 0 solid;
  margin: 0 2rem 1em 1em;
}
.fa-search {
  position: left;
  width: 15px;
  height: 15px;
}
.fa-list {
  position: inherit;
  width: 15px;
  height: 15px;
}
.fa-info-circle {
  position: left;
  width: 15px;
  height: 15px;
}
.btn-text {
  display: grid;
  position: relative;
}
.list-inline {
  width: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
  list-style: none;
  flex-wrap: wrap;
}
table {
  border:7px solid rgb(48, 0, 182);
  font-size: 15px;
  width: 70%;
  margin-left: auto;
  margin-right: auto;
}
th {
  border:4px solid rgb(48, 0, 182);
  font-size: 17px;
  width: 30%;
}
td {
  border:3px solid rgb(48, 0, 182);
  font-size: 14px;
  width: 30%;
}
</style>
