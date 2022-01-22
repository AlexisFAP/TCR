<template>
    <div>
        <h2 id="experiencias-title-container" class="title-container pt-4">Expericencias</h2>
        <v-card color="#EDEFFB" flat>
        <v-card class="grid-container">
            <template v-for="(item) in recomendaciones">
              <v-card flat class="grid-item"
              :key="item">
                <iframe 
                class="video-card"
                width="336" height="189"
                :src="item.link">
                </iframe>
                <v-card-title class="grid-title">{{item.title}}</v-card-title>
              </v-card>
            </template>
        </v-card>
        </v-card>
    </div>
</template>
<script>
export default {
    data(){
        return{
            recomendaciones: [
                {title: '¡Celebrando en familia! Antioquia Trópical Club', link: 'https://www.youtube.com/embed/9CGZD37sx_Y?controls=0'},
                {title: '¡Disfrutando en pareja! Antioquia Trópical Club', link: 'https://www.youtube.com/embed/yTkCuxZmSxw?controls=0'},
                {title: 'Disfrutando de los beneficios del Antioquia Trópical Club', link: 'https://www.youtube.com/embed/A6lBQaqnagw?controls=0'},
                {title: 'Día de Sol - Antioquia Trópical Club', link: 'https://www.youtube.com/embed/gNX-FeZmjtk?controls=0'},
                {title: 'Alojamiento - Antioquia Trópical Club', link: 'https://www.youtube.com/embed/smNZzdplg7E?controls=0'},
            ],
        }
    }
}
</script>
<style>
#experiencias-title-container{
    color: #1a2b5a;
    text-align: center;
    background-color: #EDEFFB;
    margin-bottom: 0;
    padding-bottom: 12px;
}
.grid-container{
    display: grid;
    justify-content: space-around;
    margin: 0 auto;
    max-width: 0;
}
.grid-item {
    width: 350px;
    border-radius: 15px !important;
    box-shadow: none;
    padding: 10px;
    background-color: #EDEFFB !important;
}
.grid-title{
    color: #1a2b5a;
    font-weight: 900;
}
.video-card{
    border-radius: 15px;
}
@media (min-width: 1050px) {
    .grid-container{grid-template-columns: repeat(3, 1fr);}
}
@media (max-width: 1050px) {
    .grid-container{grid-template-columns: repeat(2, 1fr);}
}
@media (max-width: 735px) {
    .grid-container{grid-template-columns: repeat(1, 1fr);}
}
</style>