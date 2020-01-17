<template>
    <div>
        <p>{{ ip }}</p>
        <button @click="api">IPアドレスを取得</button>
    </div>
</template>

<script>
import axios from 'axios'
export default {
    data() {
        return {
            ip: '0.0.0.0'
        }
    },
    methods: {
        // api() {
        //    axios.get('http://icanhazip.com')
        //    .then(resolve => {
        //        console.log(resolve.data)
        //        this.ip = resolve.data
        //    })
        // },
        async api() {
            this.ip = await this.$axios.$get('http://icanhazip.com')
        }
    }
}


</script>
