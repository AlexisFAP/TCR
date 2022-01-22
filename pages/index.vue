<template>
    <div>
      <v-img
        src="images/header-navbar-placeholder.jpeg"
        class="hidden-xs-only"
        alt="bienvenida"
        v-if="$route.name=='index'"
        >
        <v-toolbar flat v-if="$route.name=='index'">
          <v-img id="header-img" max-width="58px" src="/images/header-placeholder.jpeg"></v-img>
          <v-spacer></v-spacer>
          <v-toolbar-items class="text-toolbar">
            <v-btn class="btn-text-toolbar2 btn-index" to="/">Inicio</v-btn>
          </v-toolbar-items>
          <v-toolbar-items class="text-toolbar">
            <v-btn class="btn-text-toolbar btn-index" to="/planes" >Planes</v-btn>
          </v-toolbar-items>
          <v-toolbar-items class="text-toolbar">
            <v-btn  class="btn-text-toolbar btn-index" to="/experiencias">Experiencias</v-btn>
          </v-toolbar-items>
          <v-toolbar-items  class="text-toolbar">
            <v-btn class="btn-text-toolbar3 btn-index2" @click="toWhatsapp()">Contacto</v-btn>
          </v-toolbar-items>
        </v-toolbar>
        <h2 class="banner-welcome-title">Obten cupones de descuento, días de sol ilimitados y mas</h2>
        <v-btn id="btn-header" class="btn-afiliarme">Quiero afiliarme</v-btn>
        <v-img id="banner-img" class="hidden-sm-and-down" src="images/header-phone.png"></v-img>
      </v-img>

      <!-- HEADER-XS -->
      <v-img
        src="images/header-navbar-placeholder.jpeg"
        alt="bienvenida"
        class="hidden-sm-and-up"
        v-if="$route.name=='index'"
        >
        <v-app-bar
          flat
          absolute
          v-if="$route.name=='index'"
          color="transparent"
          class="hidden-sm-and-up mt-4">
          <v-img class="rounded-circle ma-4" max-width="48px" src="/images/header-placeholder.jpeg"></v-img>
          <v-spacer></v-spacer>
          <v-app-bar-nav-icon color="white" @click.stop="drawer2 = !drawer2"></v-app-bar-nav-icon>
        </v-app-bar>

        <h2 class="banner-welcome-title">Obten cupones de descuento, días de sol ilimitados y mas</h2>
        <v-btn id="btn-header" class="btn-afiliarme">Quiero afiliarme</v-btn>
      </v-img>
      <v-navigation-drawer
          v-model="drawer2"
          fixed
          right
        >
          <v-list
            nav
            dense
          >
            <v-list-item-group
              v-model="group2"
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

      <!-- BENEFICIOS -->
      <v-card flat class="pt-10 pb-6" color="white">
        <h2 class="my-0 title-container">Conoce lo que ofrece tarjeta virtual</h2>
        <h5 class="subtitle-container">Los beneficios son de acuerdo al plan</h5>
        <div class="d-inline-flex" >
        <div class="container-menu" align-start justify-start width="420px">
          <div class="d-inline-flex">
            <v-icon class="icon-menu ma-2" color="#0eba59">mdi-white-balance-sunny</v-icon>
            <div class="ma-4" align-end>
              <div class="menu-title">Días de sol ilimitado</div>
              <div class="menu-subtitle">En todos los planes, solo pagas codivnsumo</div>
              <div v-if="show1">
                <br>
                <div class="menu-title">Lunes a viernes: consumo minimo de $25.000</div><br>
                <div class="menu-subtitle">por persona, totalmente consumibles en alimentos y bebidas.</div>
                <div class="menu-subtitle"><b>Podras visitarnos con 10 acompañantes</b></div><br>
                <div class="menu-title">Sábado, domingo y festivos consumo minimo de $30.000</div><br>
                <div class="menu-subtitle">por persona, totalmente consumibles en alimentos y bebidas.</div>
                <div class="menu-subtitle"><b>Podras visitarnos con 4 acompañantes</b></div>
              </div>
              <v-btn class="btn-menu" @click="showMenu1()">
               <div v-if="!show1">Ver mas</div><div v-else>Ver menos</div><v-icon color="#FF9737">mdi-chevron-down</v-icon>
              </v-btn>
            </div>
          </div>
          <div class="d-inline-flex">
            <v-icon class="icon-menu ma-2" color="#0eba59">mdi-ticket-percent-outline</v-icon>
            <div class="ma-4" align-end>
              <div class="menu-title">Hasta 21 cupones de alojamiento gratis</div>
              <div class="menu-subtitle">Solo pagas consumo</div>
              <div v-if="show2">
                <v-sheet class="mx-auto" width="300px">
                  <div id="menu2-carousel">
                  <v-slide-group show-arrows> 
                  <template v-slot:prev="{ on, attrs }">
                    <v-btn
                      v-bind="attrs"
                      v-on="on"
                      icon
                      id="btn1-menu2"
                    ><v-icon 
                    >mdi-chevron-left</v-icon></v-btn>
                  </template>
                  <template v-slot:next="{ on, attrs }">
                    <v-btn
                      v-bind="attrs"
                      v-on="on"
                      icon
                      id="btn2-menu2"
                    ><v-icon >mdi-chevron-right</v-icon></v-btn>
                  </template>
                  <v-slide-item
                    v-for="n in carousel"
                    :key="n"
                    v-slot="{ active, toggle }"
                    class="pa-0"
                  >
                  <v-container :input-value="active"
                    @click="toggle">
                    <v-card flat class="card-coupons">
                      <div class="circle"></div>
                      <v-img :src="n.img" class="coupons-img"></v-img>
                      <div class="card-coupons-text">Desde 130 pts.</div>
                      <div class="card-coupons-title"><h2>30%</h2> Dscto</div>
                      <div class="card-coupons-title2">En toda la barra</div>
                      <div class="card-coupons-text2"> VENCE: 10-09-2020</div>
                    </v-card>
                  </v-container>
                  </v-slide-item>
                  </v-slide-group>
                  </div>
              </v-sheet>
              </div>
              <v-btn class="btn-menu" @click="showMenu2()">
                <div v-if="!show2">Ver mas</div><div v-else>Ver menos</div><v-icon color="#FF9737">mdi-chevron-down</v-icon>
              </v-btn>
            </div>
          </div>
          <div class="d-inline-flex">
            <v-icon class="icon-menu ma-2" color="#0eba59">mdi-sale</v-icon>
            <div class="ma-4" align-end>
              <div class="menu-title">Descuento en alojamiento del 40%</div>
              <div class="menu-subtitle">En todos los planes</div>
              <div v-if="show3">
                <br>
                <div class="menu-title">40% de descuento</div>
                <div class="menu-subtitle">Lunes a viernes</div><br>
                <div class="menu-title">20% de descuento</div>
                <div class="menu-subtitle">Sábado, domingos y festivos</div>
              </div>
              <v-btn class="btn-menu" @click="showMenu3()">
                <div v-if="!show3">Ver mas</div><div v-else>Ver menos</div><v-icon color="#FF9737">mdi-chevron-down</v-icon>
              </v-btn>
            </div>
          </div>
          <div class="hidden-md-and-up my-14" v-if="show2 || show1 || show3"></div>
        </div>
        <v-img id="img-menu" width="220px" height="273px" src="images/tarjeta-placeholder.jpeg"></v-img>
        </div>
        <center><v-btn id="btn-beneficios" class="btn-afiliarme">Quiero afiliarme</v-btn></center>
      </v-card>

      <!-- CAROUSEL-ZONAS -->
      <v-card flat color="#F4F6FF">
        <h2 class="mb-0 title-container">Disfruta de nuestras instalaciones</h2>
        <h5 class="subtitle-container">Podras pasar días increibles al lado de tus seres queridos</h5>
        <v-sheet class="mx-auto">
          <div id="carousel-btns">
          <v-slide-group show-arrows>
          <template v-slot:prev="{ on, attrs }">
            <v-btn
              v-bind="attrs"
              v-on="on"
              id="carousel-leftbtn"
            ><v-icon >mdi-chevron-left</v-icon></v-btn>
          </template>
          <template v-slot:next="{ on, attrs }">
            <v-btn
              v-bind="attrs"
              v-on="on"
              id="carousel-rightbtn"
            ><v-icon >mdi-chevron-right</v-icon></v-btn>
          </template>

          <v-slide-item
            v-for="n in carousel"
            :key="n"
            v-slot="{ active, toggle }"
            class="pa-0"
          >
          <v-container :input-value="active"
            @click="toggle">
            <v-img :src="n.img" class="carousel-img"><v-icon @click="dialog=true,dialogImage=n.img" class="carousel-icon">mdi-overscan</v-icon></v-img>
          </v-container>
          </v-slide-item>
          </v-slide-group></div>
        </v-sheet>
        <v-dialog
          v-model="dialog"
          width="500"
          >
            <v-img :src="dialogImage"></v-img>
          </v-dialog>
      </v-card>

      <!-- ZONAS -->
      <v-card class="py-6" flat color="#F4F6FF">
        <h2 class="py-4 title-container">Tenemos estas zonas para ti</h2>
        <center>
        <v-card class="card-place" flat>
          <v-img class="card-place-icon" width="61px" :src="testimonios[indice].icon"></v-img>
          <v-card-text class="card-place-title">
              {{testimonios[indice].titulo}}
          </v-card-text>
          <v-card-text class="card-place-text">
            {{testimonios[indice].descripcion}}
          </v-card-text>
          <v-btn class="card-place-prev" @click="previousPlace" icon><v-icon color="#FF9737">mdi-chevron-left</v-icon></v-btn>
          <v-btn class="card-place-next" @click="nextPlace" icon><v-icon color="#FF9737">mdi-chevron-right</v-icon></v-btn>
        </v-card>
        <v-img class="place-img" :src="testimonios[indice].img"></v-img>
        </center>
      </v-card>

      <!-- OPINIONES -->
      <v-card class="py-6" flat color="white">
        <h2 class="title-container">Algunas opiniones</h2>
          <center>
          <div id="container-testimonio">
          <div class="index-grid-container">
            <v-card class="card-testimonio" flat>
              <center>
              <v-img class="card-testimonio-img" src="images/testimonio-placeholder.jpeg" width="50px"></v-img>
              <v-card-text class="card-testimonio-text">
                Excelentes instalaciones. buena comida. Y habitaciones cómodas.
                aire fresco y un agradable clima. Ideal para el descanso en familia.
              </v-card-text>
              <v-img class="card-testimonio-person" src="images/testimonio-person1-placeholder.jpeg" width="60px"></v-img>
              <v-card-text class="card-testimonio-title">
                Jairo Ramirez Muñoz
              </v-card-text>
              <v-card-text class="card-testimonio-subtitle">
                Plan tropical
              </v-card-text>
              </center>
            </v-card>
            <v-card class="card-testimonio" flat>
              <center>
              <v-img class="card-testimonio-img" src="images/testimonio-placeholder.jpeg" width="50px"></v-img>
              <v-card-text class="card-testimonio-text">
                Excelentes instalaciones, magnífica atención. Se disfruta al máximo. Súper recomendado.
              </v-card-text>
              <v-img class="card-testimonio-person" src="images/testimonio-person2-placeholder.jpeg" width="60px"></v-img>
              <v-card-text class="card-testimonio-title">
                Julio Arcila Cacheton
              </v-card-text>
              <v-card-text class="card-testimonio-subtitle">
                Plan tropical
              </v-card-text>
              </center>
            </v-card>
            <v-card class="card-testimonio" flat>
              <center>
              <v-img class="card-testimonio-img" src="images/testimonio-placeholder.jpeg" width="50px"></v-img>
              <v-card-text  class="card-testimonio-text">
                Instalaciones para el disfrute de todo público adulto mayor, adultos, niños y
                niñas para todo tipo de celebración. Excelente servicio!!!!
              </v-card-text>
              <v-img class="card-testimonio-person" src="images/testimonio-person3-placeholder.jpeg" width="60px"></v-img>
              <v-card-text class="card-testimonio-title">
                Jairo Rodriguez Castañeda
              </v-card-text>
              <v-card-text class="card-testimonio-subtitle">
                Plan tropical
              </v-card-text>
              </center>
            </v-card>
          </div>
          </div>
        </center>
        <center><v-btn class="btn-afiliarme">Quiero afiliarme</v-btn></center>
      </v-card>
    </div>
</template>
<script>
export default {
  data(){
      return{
        testimonios:[
        {icon:'images/testimonios/icon1-placeholder.jpeg',img:'images/testimonios/place1-placeholder.jpeg',titulo:'Piscina de olas',descripcion:'Te ofrecemos una exclusiva piscina de olas que alcanza los 2.50 Metros de profundidad.'},
        {icon:'images/testimonios/icon2-placeholder.jpeg',img:'images/testimonios/place2-placeholder.jpeg',titulo:'Fonda "Mi Viejo Medellín"',descripcion:'Entre bambucos y boleros degustarás un trago antioqueño y saborearás la apetitosa gastronomía de la cocina local e internacional.'},
        {icon:'images/testimonios/icon3-placeholder.jpeg',img:'images/testimonios/place3-placeholder.jpeg',titulo:'Zonas Humedas',descripcion:'Para un mayor descanso, relajación y cuidado del cuerpo'},
        {icon:'images/testimonios/icon4-placeholder.jpeg',img:'images/testimonios/place4-placeholder.jpeg',titulo:'Tobogan',descripcion:'El tobogán de 100 metros de recorrido termina en otra piscina con un ambiente tropical.'},
        {icon:'images/testimonios/icon5-placeholder.jpeg',img:'images/testimonios/place5-placeholder.jpeg',titulo:'Solarium',descripcion:'Espacio exclusivo y privado para broncearte y relajarte.'},
        {icon:'images/testimonios/icon6-placeholder.jpeg',img:'images/testimonios/place6-placeholder.jpeg',titulo:'Zona de Juegos',descripcion:'Juegos infantiles, billares y juegos de mesa'}
        ],
        indice:0,
        carousel:[
          {img:'images/zonas/zona1-placeholder.jpeg'},
          {img:'images/zonas/zona2-placeholder.jpeg'},
          {img:'images/zonas/zona3-placeholder.jpeg'},
          {img:'images/testimonios/place3-placeholder.jpeg'},
          {img:'images/testimonios/place1-placeholder.jpeg'},
          {img:'images/testimonios/place6-placeholder.jpeg'},
        ],
        drawer2: false,
        group2: null,
        dialog: false,
        paddingSize2: '15',
        dialogImage:'',
        show1: false,
        show2: false,
        show3: false,
      }
  },
   watch: {
      group2 () {
        this.drawer2 = false
      },
    },
  methods:{
    showMenu1(){
      if( this.show1 == true){
        this.show1= false
      }
      else{
        this.show1= true,
        this.show2= false,
        this.show3= false
      }
    },
    showMenu2(){
      if( this.show2 == true){
        this.show2= false
      }
      else{
        this.show1= false,
        this.show2= true,
        this.show3= false
      }
    },
    showMenu3(){
      if( this.show3== true){
        this.show3= false
      }
      else{
        this.show1= false,
        this.show2= false,
        this.show3= true
      }
    },
    nextPlace(){
      if(this.indice >= 0 && this.indice <= this.testimonios.length - 2){
        this.indice += 1;
      }
    },
    previousPlace(){
      if(this.indice > 0 && this.indice <= this.testimonios.length - 1){
        this.indice -= 1;
      }
    }
  }
}
</script>
<style>
#container-testimonio{
  overflow-x: auto;
  scroll-behavior: smooth;
  -webkit-overflow-scrolling: touch;
  scroll-snap-points-x: repeat(50px);
  scroll-snap-type:mandatory;
}
.index-grid-container{
  display: grid;
  max-width: 1000px;
  justify-content: left;
  grid-template-columns: repeat(3, 1fr);
}
#container-testimonio::-webkit-scrollbar{
  width: 10px;
  height: 10px;
}
#container-testimonio::-webkit-scrollbar-thumb{
  background: #808080;
  border-radius: 10px;
  visibility: hidden;
}
#container-testimonio::-webkit-scrollbar-track{
  background: transparent;
}
#container-testimonio:hover#container-testimonio::-webkit-scrollbar-thumb{
  visibility: visible;
}
.theme--light.v-toolbar.v-sheet{
    background-color: transparent;
}
.v-toolbar__items > .v-btn {
  background-color: transparent !important;
}
.coupons-img{
  width: 150px;
  height: 200px;
  border-radius: 20px;
}
.card-coupons{
  max-width: 300px;
  width: 300px;
  height: 200px;
  border-radius: 13.5% !important;
  box-shadow: none;
  margin: 10px;
  margin-bottom: 50px;
  text-align: left;
}
.circle::before{
  content: '';
  position: absolute;
  bottom: 0;
  right: 0;
  left: 0;
  top: 0;
  box-shadow: 2px 2px 6px 6px #888888;
  border-radius: 20px;
  width: 300px;
  height: 200px;
}
.card-coupons::before{
  content: '';
  position: absolute;
  left: 20px;
  top: 20px;
  z-index: 6;
  border: 3px gray dashed;
  border-radius: 20px;
  width: 275px;
  height: 160px;
}
.card-coupons-text{
  position: absolute;
  top: 7.5%;
  left: 0;
  font-style: italic;
  font-weight: 700;
  z-index: 7;
  color: white !important;
  background-color: #17C2E8;
  border-top-right-radius: 25px;
  border-bottom-right-radius: 25px;
}
.card-coupons-title2{
  position: absolute;
  top: 50%;
  left: 50%;
  z-index: 5;
  color: #0F2152 !important;
}
.card-coupons-title{
  position: absolute;
  top: 20%;
  left: 50%;
  z-index: 5;
  color: #0F2152 !important;
}
.card-coupons-text2{
  position: absolute;
  top: 65%;
  left: 45%;
  font-weight: bold;
  z-index: 5;
  color: #17C2E8 !important;
}
#btn1-menu2{
  border: solid 2px #FF9737;
  border-radius: 50%;
  color: #FF9737 !important;
}
#btn2-menu2{
  border: solid 2px #FF9737;
  border-radius: 50%;
  color: #FF9737 !important;
}
#menu2-carousel .v-slide-group__next {
  position: absolute !important;
  min-width: 0 !important;
  bottom: 0;
  right: 0;
}
#menu2-carousel .v-slide-group__prev{
  position: absolute !important;
  min-width: 0 !important;
  bottom: 0;
  z-index: 6;
  right: 13%;
}
.btn-index{
  color: white !important;
}
.btn-index2{
  color: white !important;
  border-color: white;
}
#header-img{
  border-radius: 50%;
  margin-left: 25px;
  margin-top: 30px;
}
#btn-header{
  margin-left: 82px !important;
  margin-top: 10px;
  width: 225px;
  height: 52px !important;
}
.container-menu{
  margin-right: 20px;
  margin-top: 32px;
  margin-left: 145px;
  width: 425px;
}
#img-menu{
  max-width: 220px;
  margin-left: 145px
}
.menu-title{
  font-weight: bold;
  color: #0F2152 !important;
  padding:0;
}
.menu-subtitle{
  padding-bottom: 0;
  padding-top: 0;
  color: #0F2152 !important;
}
.icon-menu{
  background-color: #B6FAD3 !important;
  padding: 12px;
  border-radius: 12px;
  max-height: 48px;
}
.btn-menu{
  box-shadow: none;
  background-color: transparent !important;
  color: #FF9737 !important;
  padding-left: 0 !important;

}
.carousel-img{
  width: 250px;
  height: 310px;
}
#carousel-btns .v-slide-group__prev::before{
  content: '';
  position: absolute;
  bottom: 0;
  right: 0;
  left: 0;
  top: 0;
  background: rgba(31, 29, 29, 0.6);
}
#carousel-btns .v-slide-group__next::before{
  content: '';
  position: absolute;
  bottom: 0;
  right: 0;
  left: 0;
  top: 0;
  background: rgba(31, 29, 29, 0.6);
}
#carousel-btns .v-slide-group__prev {
  position: absolute;
  bottom: 40%;
  z-index: 5;
  min-width: 40px;
  max-width: 40px;
}
#carousel-btns .v-slide-group__next {
  position: absolute;
  bottom: 40%;
  right: 0;
  min-width: 40px;
  max-width: 40px;
}
#carousel-leftbtn{
  height: 85px !important;
  background-color:transparent;
  color: white;
  padding: 0;
  min-width: 40px;
}
#carousel-rightbtn{
  height: 85px !important;
  background-color:transparent;
  color: white;
  padding: 0;
  min-width: 40px;
}
.carousel-icon{
  position: absolute;
  bottom: -87%;
  left: 83%;
  color: white !important;
  background-color: rgba(31, 29, 29, 0.6);
  padding: 5px;
  border-radius: 50%;
}
.card-place{
  width: 355px;
  height: 275px;
  border-radius: 16px !important;
  border:3px solid #DFE2F1 !important;
  position: absolute;
  z-index: 10 ;
  left: 15%;
  top: 35%;
}
.card-place-icon{
  left: -35%;
  top: 10%;
}
.card-place-title{
  font-family: 'Montserrat', sans-serif;
  color: #0F2152 !important;
  text-align: left;
  font-size: 1.225rem;
  font-weight: bold;
  margin-left: 10px;
  margin-top: 25px;
}
.card-place-text{
  font-family: 'Montserrat', sans-serif;
  color: #0F2152 !important;
  text-align: left;
  font-size: 0.9rem;
  font-weight: 300;
  width: 80%;
  margin-left: -40px;
  padding-top: 0;
}
.card-place-prev{
  position: absolute;
  bottom: 8%;
  right: 20%;
  border-radius: 50%;
  color: #FF9737;
  border: solid #FF9737 2px;
}
.card-place-next{
  position: absolute;
  bottom: 8%;
  right: 5%;
  border-radius: 50%;
  color: #FF9737;
  border: solid #FF9737 2px;
}
.place-img{
  width: 550px;
  border-radius: 20px;
  left: 5%;
}
.card-testimonio{
  border-radius: 16px !important;
  border:3px solid #DFE2F1 !important;
  width: 300px;
  height: 445px;
  margin: 10px 10px;
}
.card-testimonio-img{
  margin-left: 200px;
  margin-top: 35px;
}
.card-testimonio-text{
  font-family: 'Montserrat', sans-serif;
  color: #0F2152;
  width: 250px;
  text-align: center;
  font-size: 0.942rem;
  font-weight: 400;
  line-height: 25px;
}
.card-testimonio-person{
  position: absolute;
  left: 40%;
  bottom: 20%;
}
.card-testimonio-title{
  font-family: 'Montserrat', sans-serif;
  color: #0F2152;
  font-size: 1.2rem;
  font-weight: bold;
  position: absolute;
  bottom: 10%;
}
.card-testimonio-subtitle{
  font-family: 'Montserrat', sans-serif;
  color: #0F2152;
  font-size: 0.96rem;
  font-weight: 500;
  padding-top: 0;
  padding-bottom: 20px;
  position: absolute;
  bottom: 2%;
}
.banner-welcome-title{
  font-size: 50px;
  padding-left: 78px;
  padding-top: 42px;
  font-weight: bold;
  color: white;
  width: 530px;
}
#banner-img{
  width: 600px !important;
  position: absolute;
  top: 20%;
  left: 50%;
}
.title-container{
  color: #1a2b5a;
  text-align: center;
  font-family: 'Montserrat', sans-serif;
  font-weight: bold !important;
  line-height: 48px;
  font-size: 32px;
  margin-top: 20px;
  margin-bottom: 20px;
}
.subtitle-container{
  color: #1a2b5a;
  text-align: center;
  font-family: 'Montserrat', sans-serif;
  line-height: 32px;
  font-size: 17px;
  font-weight: 300;
  margin-bottom: 12px;
}
.btn-afiliarme{
  background-color: #FF9737 !important;
  color: white !important;
  border-radius: 25px;
  width: 185px;
  height: 42px !important;
  margin: 30px auto !important;
}
@media screen and (max-width:600px) {
  .title-container{
    font-size: 26px;
  }
  .subtitle-container{
    font-size: 14px;
    margin-bottom: 12px;
  }
  .banner-welcome-title{
    width: 420px;
    font-size: 32px;
    padding-top: 72px !important;
    padding-left: 40px;
  }
  #btn-header{
    width: 225px;
    height: 58px !important;
    margin-left: 40px !important;
  }
  .btn-afiliarme{
    width: 70%;
    height: 62px !important;
    border-radius: 35px;
    font-size: 0.925rem !important;
  }
  .place-img{
    width: 450px;
    position: relative;
    overflow: hidden;
    margin-bottom: 225px;
    margin-left: 0 !important;
    margin-right: 10% !important;
  }
  .card-place{
    position: absolute;
    margin-top: 120px;
    margin-right: 40px;
  }
  .container-menu{
    margin-top: 32px;
    margin-left: 20%;
    padding-bottom: 345px;
    width: 80%;
  }
  .menu-subtitle{
    line-height: 20px;
  }
  #img-menu{
    position: absolute;
    max-width: 220px;
    bottom: 3%;
    left: 5%;
  }
  #btn-beneficios{
    position: absolute !important;
    bottom: 30%;
    left: 15%;
  }
}
@media screen and (min-width:600px) and (max-width:850px) {
  .place-img{
    width: 475px;
    position: relative;
    margin-bottom: 225px;
  }
  .card-place{
    position: absolute;
    margin-top: 120px;
    margin-left: 15%;
    margin-right: 15%;
  }
}
@media screen and (min-width:900px) and (max-width:1000px) {
 .container-menu{
    margin-right: 15px;
    margin-top: 32px;
    margin-left: 100px;
  }
  #img-menu{
    max-width: 220px;
    margin-left: 120px
  }
}
@media screen and (min-width:600px) and (max-width:900px) {
 .container-menu{
    margin-top: 32px;
    margin-left: 25%;
    padding-bottom: 325px;
    width: 80%;
  }
  .menu-subtitle{
    line-height: 20px;
  }
  #img-menu{
    position: absolute;
    max-width: 220px;
    bottom: 3%;
    left: 15%;
  }
  #btn-beneficios{
    position: absolute !important;
    bottom: 33.5%;
    left: 32.5%;
  }
}
</style>
