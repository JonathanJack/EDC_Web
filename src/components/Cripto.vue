<template>
 <div>             
        <h4>{{propCoin}}</h4>
        <pre>{{infos}}</pre>        
    </div>
</template>

<script>    
export default{
    props: {
        propCoin: String
    },
    data() {
                return{
                titulo: 'Preços do Bitcoin',
                infos: [],
                valores: []
                }                                               
            },
            methods: {
                getCoins(param){
                    var url = 'https://api.coinbase.com/v2/exchange-rates?currency=' + param;
                    fetch(url)
                    .then(res => res.json())
                    .then(res => this.infos = res.data.rates)
                    .catch(err => console.log(err + 'asdsa'));                    
                }
            },
            created(){
                this.getCoins(this.propCoin)                
            }
}                     
    </script>

<style></style>