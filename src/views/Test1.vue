<template>
    <div>
        <h1>dssadijasnfijasnf</h1>
        <!--<div v-for="item in items">{{item}}</div>-->
        <div>{{obj}}</div>
    </div>

</template>

<script>
//    require('es6-promise').polyfill();
//    require('isomorphic-fetch');
import axios from 'axios';
    export default {
        data() {
            return {items: this.$store.state.arrs,obj: this.$store.state.arrs222}
        },
        asyncData({store}) {
            return axios.get('http://cm.dev.rs.com/contract-web/process/loginForMobile?userId=51006793')
                .then(function (response) {
                    console.log('fetch1')
                    store.commit('SET_TEST222', response.data.dataMap);
//                    return response.json();
                })
                .catch(function (error) {
                    console.log(error);
                });


//            fetch('http://cm.dev.rs.com/contract-web/process/loginForMobile',{
//                body:JSON.stringify({userId:51006793})
//            })
//                .then(function (response) {
//                    if (response.status >= 400) {
//                        throw new Error("Bad response from server");
//                    }
//                    console.log('fetch')
//                    console.log(response.json())
//                    store.commit('SET_TEST222', response.json());
//                    return response.json();
//                })
//                .then(function(stories) {
//                    console.log(stories);
//                });
        }
    }
</script>