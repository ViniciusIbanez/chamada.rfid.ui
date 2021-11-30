<template>
  <div>
    <historico-chamadas v-if="subPages[0].showing"></historico-chamadas>
    <div v-if="mainArea">
      <div class="wrapper">
        <div class="container-fluid">
          <section class="presentation">
            <div class="presentation-view">
              <div class="header-text">
                <h1 style="margin-top: 2rem;">Abrir Chamadas</h1>
              </div>
              <br /><br />
              <div class="btns">
                <ul class="list-inline">
                  <div>
                    <li class="itens">
                      <button
                        class="buttonEnter"
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
          <table>
            <tr>
              <th>Nome da Sala</th>
              <th>Quantidade de Alunos</th>
              <th>Horario da Aula</th>
              <th></th>
            </tr>
            <tr>
              <td>Teste</td>
              <td>Teste</td>
              <td>Teste</td>
              <td>Teste</td>
            </tr>
          </table>
        </div>
      </div>
    </div>
  </div>
</template>

<script>

import historicoChamadas from "./historico-chamadas.vue";
export default {
  name: "abrirChamadas",
  components: {
    historicoChamadas: historicoChamadas,
  },
  data() {
    return {
      aulas: [],
      mainArea: true,
      subPages: [
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
        case "historico-chamadas":
          this.mainArea = false;
          this.subPages.find(
            page => page.component == "historico-chamadas",
          ).showing = true;
          break;
      }
    },
  },
  findData() {
      let vm = this;
      let url = ""
      let params = null
      this.sendData(url, params, vm).then(async response => {
        this.aulas = await response.data;
      });
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
