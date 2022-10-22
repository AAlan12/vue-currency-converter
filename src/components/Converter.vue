<template>
    <div class="converter">
        <h2>{{coinA}} to {{coinB}}</h2>
        <input type="text" v-model="coinA_value" v-bind:placeholder="coinA">
        <input type="button" value="Converter" v-on:click="toConvert">
        <h2>{{coinB_value}}</h2>
    </div>
</template>

<script>

export default{
    // eslint-disable-next-line vue/multi-word-component-names
    name: 'Converter',
    props:[
        'coinA',
        'coinB'
    ],
    data(){
        return{
            coinA_value: '',
            coinB_value: 0
        };
    },
    methods:{
        toConvert(){
            let from_to = this.coinA + "_" + this.coinB;
            let url = "http://free.currencyconverterapi.com/api/v5/convert?q=" + 
                from_to + "L&compact=y";
                fetch(url)
                .then(res => {
                    return res.json()
                })
                .then(json => {
                    let price = json[from_to];
                    this.coinB_value = (price * parseFloat(this.coinA_value)).toFixed(2);
                })
        }
    }
};
</script>

<style scoped>

.converter{
    padding: 20px;
    max-width: 300px;
    box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2);
}
</style>