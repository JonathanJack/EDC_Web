<template>
       
     <div>              
        <div class="card-temp" >
            <div class="d-flex justify-content-between">
                <div>
                    <h2>{{infoLocal.location.name}}</h2>
                     <div class="clima-descricao">
                        <span>{{infoLocal.current.condition.text}}</span>
                    </div> 
                </div> 
                <div class="d-flex">
                    <h2>{{infoLocal.current.temp_c}}<span v-html="'&deg'"></span></h2>
                 <img class="clima-img" v-bind:src="infoLocal.current.condition.icon"/>
                </div>                                 
                </div>
                <div class="itens-container">             
                     <div class="sub-itens" title="Velocidade do vento">
                         <img src="https://img.icons8.com/dotty/50/000000/wind.png"/>
                         <span>{{infoLocal.current.wind_kph}} km/h</span>
                     </div>
                     <div class="sub-itens" title="Direção do vento">
                         <img src="https://img.icons8.com/dotty/50/000000/compass.png"/>
                         <span>{{infoLocal.current.wind_dir}}</span>
                     </div>
                     <div class="sub-itens" title="Precipitação">
                         <img src="https://img.icons8.com/dotty/50/000000/rainwater-catchment.png"/>
                         <span>{{infoLocal.current.precip_mm}} mm</span>
                     </div>
                     <div class="sub-itens" title="Humidade do ar">
                         <img src="https://img.icons8.com/dotty/50/000000/wet.png"/>
                         <span>{{infoLocal.current.humidity}} %</span>
                     </div>
                     <div class="sub-itens" title="Céu encoberto">
                         <img src="https://img.icons8.com/dotty/50/000000/partly-cloudy-day.png"/>
                         <span>{{infoLocal.current.cloud}} %</span>
                     </div>
                     <div class="sub-itens" title="Incidência UV">
                         <img src="https://img.icons8.com/external-justicon-lineal-justicon/50/000000/external-uv-index-weather-justicon-lineal-justicon-1.png"/>
                         <span>uv {{infoLocal.current.uv}}</span>
                     </div>
                       <div class="sub-itens" title="Sensação térmica">
                         <img src="https://img.icons8.com/dotty/50/000000/fat-man.png"/>
                         <span>{{infoLocal.current.feelslike_c}}<span v-html="'&deg'"></span></span>
                     </div>                
                 </div>
        </div> 

        <!--
        <select  v-model="selected" @change="onChange($event)">
            <option  v-for="location in locations" :key="location.key">{{location.nome}}</option>        
        </select>
        -->   
    </div>
     
</template>

<script>

export default{
        props: {
            propLocal: String
        },                                                        
        data() {
            return{                             
                infoLocal: []                                                              
            }                             
        },
        methods: {                 
            
            getWeather(local){                      
                var url = 'http://api.weatherapi.com/v1/current.json?key=7cb2dafb2ba8476484a154218220702&q=' + local;                                          
                fetch(url)                        
                .then(res => res.json())
                .then(res =>{this.infoLocal = res})                    
                .catch(err => console.log(err))                                          
            }
        },
        mounted(){  
            this.$getLocation([])
            .then(coordinates => {
                
                this.getWeather(coordinates.lat +',' + coordinates.lng);
                
            });                                                                                
        
        //   navigator.geolocation.getCurrentPosition(function(position) {
        //          console.log(String(position.coords.latitude) + String(position.coords.longitude));                
        //     })                                                                         
        }
                              
}
    
</script>

<style>
*, h6,h5,h2,h3,h4{
    margin: 0px;
}

.card-temp{
    width: 300px;
    border: 1px solid black;
    padding: 10px;
    border-radius: 20px;
}
.clima-descricao{
    display: flex;
    justify-content: end;
    font-size: 12px;
    margin-bottom: 7px;
}
.clima-img{
    width: 30px;
    height: 30px;
    margin-left: 6px;
    border: 1px solid #5c5b64;
    border-radius: 15px;
}
.row{
    display:flex;
}
.itens-container{
    display: flex;
    flex-wrap: wrap;
    margin-top: 6px;
    justify-content: space-between;
}
.sub-itens{
    white-space: nowrap;
    margin:0px 15px 10px 0px;

}

.sub-itens span{
    font-size: 12px

}
img{
    width: 25px;
}
</style>