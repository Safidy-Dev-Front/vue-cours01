<template>
    <div>
       <h1>{{ message }}</h1> 
       <p>{{ value }}</p>
       <button @click="toIncrement">incremennt {{count}}</button>
    </div>
</template>


<script>
 export default{
    name: 'FirstComponent',
    props: ["value"],
    data(){
        return {
            message: "Salut les gens",
            count: 0
        };
    },
    methods: {
        toIncrement() {
            this.count++;
        }
    }
 }
</script>