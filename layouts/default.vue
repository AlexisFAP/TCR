<template>
  <v-app dark>
    <v-app-bar
      fixed
      
      flat
      color="white"
      class="hidden-xs-only"
      v-if="$route.name!='index'"
    >
      <v-toolbar flat>
        <v-img max-width="48px" src="/images/header-placeholder.jpeg"></v-img>
        <v-spacer></v-spacer>
        <v-toolbar-items class="text-toolbar">
          <v-btn class="btn-text-toolbar"  to="/" >Inicio</v-btn>
        </v-toolbar-items>
        <v-toolbar-items class="text-toolbar">
          <v-btn class="btn-text-toolbar" to="/planes"><b v-if="$route.name=='planes'">Planes</b> <div v-else>Planes</div></v-btn>
        </v-toolbar-items>
        <v-toolbar-items class="text-toolbar">
          <v-btn  class="btn-text-toolbar" to="/experiencias"><b v-if="$route.name=='experiencias'">Experiencias</b><div v-else>Experiencias</div></v-btn>
        </v-toolbar-items>
        <v-toolbar-items  class="text-toolbar">
          <v-btn class="btn-text-toolbar3" @click="toWhatsapp()">Contacto</v-btn>
        </v-toolbar-items>
      </v-toolbar>
    </v-app-bar>

    <v-app-bar
      fixed
      app
      flat
      color="white"
      class="hidden-sm-and-up"
      v-if="$route.name!='index'">
      <v-img max-width="48px" src="/images/header-placeholder.jpeg"></v-img>
      <v-spacer></v-spacer>
      <v-app-bar-nav-icon @click.stop="drawer = !drawer"></v-app-bar-nav-icon>
    </v-app-bar>

  <v-navigation-drawer
      v-model="drawer"
      fixed
      right
      temporary
    >
      <v-list
        nav
        dense
      >
        <v-list-item-group
          v-model="group"
          active-class="deep-blue--text text--accent-4"
        >
          <v-list-item to="/">
            <v-list-item-title class="navigation-link">Home</v-list-item-title>
          </v-list-item>
          <v-divider></v-divider>

          <v-list-item to="/planes">
            <v-list-item-title class="navigation-link">Planes</v-list-item-title>
          </v-list-item>

          <v-list-item to="/experiencias">
            <v-list-item-title class="navigation-link">Experiencias</v-list-item-title>
          </v-list-item>

        </v-list-item-group>
      </v-list>
    </v-navigation-drawer>

    <v-main :class="`pt-${this.checkRoute2}`">
      <Nuxt />
    </v-main>

    <v-footer color="#0EBA59">
      <v-container fluid>
        <center>
        <v-layout id="my-footer" row wrap align-start justify-space-between>
          <v-flex xs12 sm4 md3>
            <center>
              <div class="title-footer">
                Ayuda e información
              </div>
              <ul>
                <li>
                  <p class="text-footer">
                    <a href="">Terminos y condiciones</a>
                  </p>
                </li>
                <li>
                  <p class="text-footer">
                    <a href="">Politica de privacidad</a>
                  </p>
                </li>
                <li>
                  <p class="text-footer">
                    <a href="">Terminos y condiciones de la APP</a>
                  </p>
                </li>
                <li>
                  <p class="text-footer">
                    <a href="">Reglamento de la membresía</a>
                  </p>
                </li>
              </ul>
            </center>
          </v-flex>
          <v-flex xs12 sm4 md3>
            <center>
              <div class="title-footer">
                Contacto
              </div>
              <ul>
                <li>
                  <p class="text-footer">
                    Doble calzada Niquia - Hatillo
                  </p>
                </li>
                <li>
                  <p class="text-footer">
                    Kilómetro 21 Barbosa - Antioquia
                  </p>
                </li>
                <li>
                  <p class="text-footer">
                    (4) 60440444
                  </p>
                </li>
                <li>
                  <p class="text-footer">
                    membresias@antioquiatropical.club
                  </p>
                </li>
              </ul>
            </center>
          </v-flex>
          <v-flex xs12 sm4 md3 align-self-center >
            <center>
              <img width="210" alt="TRC_logo" id="tcr-logo" src="/images/footer-placeholder.jpeg" />
            </center>
          </v-flex>
        </v-layout>
        </center>
      </v-container>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  name: 'DefaultLayout',
  data () {
    return {
      fixed: false,
      title: 'TRC Logo',
      drawer: false,
      group: null,
      paddingSize: '15',
    }
  },
  computed:{
    checkRoute2(){
      // console.log($nuxt._route.name=='index');
      // console.log('tamaño');
      // console.log(this.paddingSize);
      //if($nuxt._route.name=='index'){
      // if($route.name!='index'){
      //   return '0';
      // }else{
      //   return '15';
      // }
    }
  },
  watch: {
      group () {
        this.drawer = false
      },
    },
  methods:{
    toWhatsapp(){
      let a = document.createElement('a')
      a.href = "https://www.google.com"
      a.target = '_blank'
      a.click()
    },
  }
}
</script>
<style>
#my-footer{
  width: 90%;
}
#tcr-logo{
  padding-top: 30px;
}
.v-toolbar__items > .v-btn {
  height: 45px !important;
  box-shadow: none;
  background-color: white !important;
  border-radius: 20px;
}
.text-toolbar{
  margin: 5px;
  align-items: center;
  font-family: 'Montserrat', sans-serif;
}
.btn-text-toolbar{
  color: #0F2152 !important;
  text-transform: none;
}
.btn-text-toolbar2{
  color: #0F2152 !important;
  text-transform: none;
  font-weight: bold;
}
.btn-text-toolbar3{
  color: #0F2152 !important;
  text-transform: none;
  border: solid #0F2152 2.3px;
}
.title-footer {
  padding-top: 30px;
  padding-bottom: 20px;
  font-size: 18px;
  line-height: 15px;
  letter-spacing: 0.07em;
  color: white;
  font-weight: bold;
  text-align: left;
}
.text-footer {
  font-size: 13.5px;
  color: white;
  text-align: left;
  font-weight: 200;
}
a{
  text-decoration: none;
  color: white !important;
}
li{
  color: white;
  margin-left: 15px;
}
.navigation-link{
  color: #0F2152 !important;
}
@media screen and (max-width:600px) {
  .flex.xs12{
    display: flex;
    justify-content: center;
  }

}
</style>