<template>
    <div>
        <h1>dssadijasnfijasnf</h1>
        <div v-for="item in items">{{item}}</div>
        <div>{{obj}}</div>
        <router-link to="/t1">1111111</router-link>
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
            return axios.get('http://react-china.org/t/15805.json?track_visit=true&forceLoad=true&_=1513605282810')
                .then(function (response) {
                    console.log('axios')
                    console.log(response);
                    console.log(response.data.post_stream);
                    store.commit('SET_TEST', response.data.post_stream.stream);
                    store.commit('SET_TEST222', response.data.post_stream);

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