<template>
    <div color="#EDEFFB">
        <h2 id="planes-title-container" class="title-container pt-4">Descubre nuestros planes</h2>
        <v-card flat class="hidden-sm-and-up">
            <v-sheet height="750px" color="#EDEFFB" >
                <v-slide-group show-arrows>
                    <template v-slot:prev="{ on, attrs }">
                        <v-btn
                            v-bind="attrs"
                            v-on="on"
                            id="slide-button2"
                            icon
                        > <v-icon>mdi-chevron-left</v-icon> </v-btn>
                    </template>
                    <template v-slot:next="{ on, attrs }">
                        <v-btn
                            v-bind="attrs"
                            v-on="on"
                            icon
                            id="slide-button"
                        ><v-icon>mdi-chevron-right</v-icon> </v-btn>
                    </template>
                    <v-slide-item
                        v-for="indice in 3"
                        :key="indice"
                        v-slot="{ active, toggle }"
                    >  
                    <v-container :input-value="active"
                        active-class="purple white--text"
                        @click="toggle">
                        <v-card class="card-planes" color="#0F2152" v-if="indice==1">
                            <v-img class="img-card" src="/images/tarjeta-plan1-placeholder.jpeg"></v-img>
                            <v-card-text class="card-title2">
                                Plata <br> (2 años)
                            </v-card-text>
                            <v-card-text class="card-subtitle">
                                $3330.000
                            </v-card-text>
                            <v-card-text class="card-title2">
                                $999.000
                            </v-card-text>
                            <div class="d-inline-flex">
                                <v-icon class="card-icon" color="green">mdi-check</v-icon>
                                <p class="card-text2">1 tarjeta de membresía ATC</p>
                            </div>
                            <div class="d-inline-flex">
                                <v-icon class="card-icon" color="green">mdi-check</v-icon>
                                <p class="card-text2">Acceso ilimitado a días de sol *solo paga consumos</p>
                            </div>
                            <div class="d-inline-flex">
                                <v-icon class="card-icon" color="green">mdi-check</v-icon>
                                <p class="card-text2"><b>21 cupones de alojamiento</b> gratis *solo paga consumos</p>
                            </div>
                            <div class="d-inline-flex">
                                <v-icon class="card-icon" color="green">mdi-check</v-icon>
                                <p class="card-text2">Descuento en alojamiento del 40%</p>
                            </div>
                            <v-btn class="btn-afiliarme-planes">Quiero afiliarme</v-btn>
                        </v-card>

                        <v-card v-if="indice==2" class="card-planes" color="white">
                            <v-img class="img-card" src="/images/tarjeta-plan-placeholder.jpeg"></v-img>
                            <v-card-text class="card-title">
                                Plata <br> (2 años)
                            </v-card-text>
                            <v-card-text class="card-subtitle">
                                $3330.000
                            </v-card-text>
                            <v-card-text class="card-title">
                                $999.000
                            </v-card-text>
                            <div class="d-inline-flex">
                                <v-icon class="card-icon" color="green">mdi-check</v-icon>
                                <p class="card-text">1 tarjeta de membresía ATC</p>
                            </div>
                            <div class="d-inline-flex">
                                <v-icon class="card-icon" color="green">mdi-check</v-icon>
                                <p class="card-text">Acceso ilimitado a días de sol *solo paga consumos</p>
                            </div>
                            <div class="d-inline-flex">
                                <v-icon class="card-icon" color="green">mdi-check</v-icon>
                                <p class="card-text"><b>14 cupones de alojamiento</b> gratis *solo paga consumos</p>
                            </div>
                            <div class="d-inline-flex">
                                <v-icon class="card-icon" color="green">mdi-check</v-icon>
                                <p class="card-text">Descuento en alojamiento del 40%</p>
                            </div>
                            <v-btn class="btn-afiliarme-planes">Quiero afiliarme</v-btn>
                        </v-card>

                        <v-card v-if="indice==3" class="card-planes" color="white">
                            <v-img class="img-card" src="/images/tarjeta-plan3-placeholder.jpeg"></v-img>
                            <v-card-text class="card-title">
                                Tropical <br> (1 año)
                            </v-card-text>
                            <v-card-text class="card-subtitle">
                                $2590.000
                            </v-card-text>
                            <v-card-text class="card-title">
                                $1690.000
                            </v-card-text>
                            <div class="d-inline-flex">
                                <v-icon class="card-icon" color="green">mdi-check</v-icon>
                                <p class="card-text">1 tarjeta de membresía ATC</p>
                            </div>
                            <div class="d-inline-flex">
                                <v-icon class="card-icon" color="green">mdi-check</v-icon>
                                <p class="card-text">Acceso ilimitado a días de sol *solo paga consumos</p>
                            </div>
                            <div class="d-inline-flex">
                                <v-icon class="card-icon" color="green">mdi-check</v-icon>
                                <p class="card-text"><b>7 cupones de alojamiento</b> gratis *solo paga consumos</p>
                            </div>
                            <div class="d-inline-flex">
                                <v-icon class="card-icon" color="green">mdi-check</v-icon>
                                <p class="card-text">Descuento en alojamiento del 40%</p>
                            </div>
                            <v-btn class="btn-afiliarme-planes">Quiero afiliarme</v-btn>
                        </v-card>
                    </v-container>       
                    </v-slide-item>
                </v-slide-group>
            </v-sheet>
        </v-card>

        <v-card flat class="hidden-xs-only">
            <div id="container-planes">
            <div id="planes-grid-container">
                <v-card class="card-planes" color="#0F2152">
                    <v-img class="img-card" src="/images/tarjeta-plan1-placeholder.jpeg"></v-img>
                    <v-card-text class="card-title2">
                        Gold <br> (3 años)
                    </v-card-text>
                    <v-card-text class="card-subtitle">
                        $3330.000
                    </v-card-text>
                    <v-card-text class="card-title2">
                        $999.000
                    </v-card-text>
                    <div class="d-inline-flex">
                        <v-icon class="card-icon" color="green">mdi-check</v-icon>
                        <p class="card-text2">1 tarjeta de membresía ATC</p>
                    </div>
                    <div class="d-inline-flex">
                        <v-icon class="card-icon" color="green">mdi-check</v-icon>
                        <p class="card-text2">Acceso ilimitado a días de sol *solo paga consumos</p>
                    </div>
                    <div class="d-inline-flex">
                        <v-icon class="card-icon" color="green">mdi-check</v-icon>
                        <p class="card-text2"><b>21 cupones de alojamiento</b> gratis *solo paga consumos</p>
                    </div>
                    <div class="d-inline-flex">
                        <v-icon class="card-icon" color="green">mdi-check</v-icon>
                        <p class="card-text2">Descuento en alojamiento del 40%</p>
                    </div>
                    <v-btn class="btn-afiliarme-planes">Quiero afiliarme</v-btn>
                </v-card>
                <v-card class="card-planes" color="white">
                    <v-img class="img-card" src="/images/tarjeta-plan-placeholder.jpeg"></v-img>
                    <v-card-text class="card-title">
                        Plata <br> (2 años)
                    </v-card-text>
                    <v-card-text class="card-subtitle">
                        $3330.000
                    </v-card-text>
                    <v-card-text class="card-title">
                        $999.000
                    </v-card-text>
                    <div class="d-inline-flex">
                        <v-icon class="card-icon" color="green">mdi-check</v-icon>
                        <p class="card-text">1 tarjeta de membresía ATC</p>
                    </div>
                    <div class="d-inline-flex">
                        <v-icon class="card-icon" color="green">mdi-check</v-icon>
                        <p class="card-text">Acceso ilimitado a días de sol *solo paga consumos</p>
                    </div>
                    <div class="d-inline-flex">
                        <v-icon class="card-icon" color="green">mdi-check</v-icon>
                        <p class="card-text"><b>14 cupones de alojamiento</b> gratis *solo paga consumos</p>
                    </div>
                    <div class="d-inline-flex">
                        <v-icon class="card-icon" color="green">mdi-check</v-icon>
                        <p class="card-text">Descuento en alojamiento del 40%</p>
                    </div>
                    <v-btn class="btn-afiliarme-planes">Quiero afiliarme</v-btn>
                </v-card>
                <v-card class="card-planes" color="white">
                    <v-img class="img-card" src="/images/tarjeta-plan3-placeholder.jpeg"></v-img>
                    <v-card-text class="card-title">
                        Tropical <br> (1 año)
                    </v-card-text>
                    <v-card-text class="card-subtitle">
                        $2590.000
                    </v-card-text>
                    <v-card-text class="card-title">
                        $1690.000
                    </v-card-text>
                    <div class="d-inline-flex">
                        <v-icon class="card-icon" color="green">mdi-check</v-icon>
                        <p class="card-text">1 tarjeta de membresía ATC</p>
                    </div>
                    <div class="d-inline-flex">
                        <v-icon class="card-icon" color="green">mdi-check</v-icon>
                        <p class="card-text">Acceso ilimitado a días de sol *solo paga consumos</p>
                    </div>
                    <div class="d-inline-flex">
                        <v-icon class="card-icon" color="green">mdi-check</v-icon>
                        <p class="card-text"><b>7 cupones de alojamiento</b> gratis *solo paga consumos</p>
                    </div>
                    <div class="d-inline-flex">
                        <v-icon class="card-icon" color="green">mdi-check</v-icon>
                        <p class="card-text">Descuento en alojamiento del 40%</p>
                    </div>
                    <v-btn class="btn-afiliarme-planes">Quiero afiliarme</v-btn>
                </v-card>
            </div>
            </div>
            <h4 id="planes-subtitle-container">Todos los planes están sujetos al conocimiento y aceptación de los <a href="">Términos y condiciones</a> </h4>
        </v-card>
    </div>
</template>
<script>
export default {
     data(){
        return{
            model: null,
            button1:null,
            button2:null,
            atras:null,
            adelante:null,
            cards:[ {img:'/images/tarjeta-plan1-placeholder.jpeg'},],
            indice:0
        }
    },
    methods:{
        toWhatsapp(){
            this.button1 = document.createElement('button')
            this.button2 = document.createElement('button')
        },
    }
}
</script>
<style>
#planes-title-container{
    background-color: #EDEFFB !important;
    margin-bottom: 0;
    padding-bottom: 12px;
}
#planes-grid-container{
    display: grid;
    grid-template-columns: repeat(3, 1fr);
}
#container-planes{
    background-color: #EDEFFB;
    overflow-x: auto;
    scroll-behavior: smooth;
    -webkit-overflow-scrolling: touch;
    scroll-snap-points-x: repeat(50px);
    scroll-snap-type:mandatory;
}
#container-planes::-webkit-scrollbar{
    width: 10px;
    height: 10px;
}
#container-planes::-webkit-scrollbar-thumb{
    background: #808080;
    border-radius: 10px;
    visibility: hidden;
}
#container-planes::-webkit-scrollbar-track{
    background: transparent;
}
#container-planes:hover#container-planes::-webkit-scrollbar-thumb{
    visibility: visible;
}
.title-container{
    color: #1a2b5a;
    text-align: center;
    font-family: 'Montserrat', sans-serif;
    font-weight: bold !important;
    line-height: 48px;
    font-size: 32px;
    margin: 15px 0;
}
#planes-subtitle-container{
    background-color: #EDEFFB;
    color: #1a2b5a !important;
    text-align: center;
    font-family: 'Montserrat', sans-serif;
    padding-top: 16px;
    padding-bottom: 16px;
    font-size: 15px;
    font-weight: 100;
}
.card-planes{
    max-width: 315px;
    border-radius: 30px !important;
    padding: 20px 0;
    margin: 15px 30px;
}
.card-title{
    font-family: 'Montserrat', sans-serif;
    font-size: 24px;
    color: #1a2b5a !important;
    font-weight: bold;
    padding: 3px 32px;
}
.card-title2{
    font-family: 'Montserrat', sans-serif;
    font-size: 24px;
    color: white !important;
    font-weight: bold;
    padding: 3px 32px;
}
.card-subtitle{
    font-family: 'Montserrat', sans-serif;
    color: #6F7FA9 !important;
    font-size: 15px;
    font-weight: 700;
    text-decoration: line-through;
    padding: 3px 32px;
}
.card-icon{
    padding: 12px 3px 12px 32px;
}
.card-text{
    font-family: 'Montserrat', sans-serif;
    color: #1a2b5a !important;
    padding: 10px 32px 10px 3px;
    width: 80%;
    font-size: 0.9rem;
}
.card-text2{
    font-family: 'Montserrat', sans-serif;
    color: white !important;
    padding: 10px 32px 10px 3px;
    width: 80%;
    font-size: 0.9rem;
}
.img-card{
    margin: 10px 9.6% 10px 7%;
    max-width: 250px;
    border-radius: 0 !important;
}
.btn-afiliarme-planes{
    background-color: #FF9737 !important;
    color: white !important;
    width: 75%;
    height: 42px !important;
    border-radius: 25px;
    margin: 10px 12.5%;
}
h4 > a{
    color: #1a2b5a !important;
    text-decoration: underline;
    font-weight: bold;
}
#slide-button{
    border: solid #FF9737 2px;
    color: #FF9737 !important;
    position: absolute !important;
    bottom: 0%;
    right: 5%;
    border-radius: 50%;
    padding: 0 !important;
}
#slide-button2{
    border: solid #FF9737 2px;
    color: #FF9737 !important;
    position: absolute !important;
    bottom: 0;
    right: 15%;
    border-radius: 50%;
    padding: 0 !important;
}
</style>