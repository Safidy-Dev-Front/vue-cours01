<template>
    <div>
        <h1>{{ message }}</h1>
        <p>{{ value }}</p>
        <button @click="toIncrement" :disabled="isButtonDisabled">incremennt {{ countId }}</button>
    </div>
    <ul>
        <UserTodo userItem=1 />
        <UserTodo userItem=2 />
        <UserTodo userItem=3 />
    </ul>
    <!-- v-html -->
    <div v-html="vHtml"></div>
    <!-- Attribute Bindings -->
    <div :id="countId">ID is {{countId}}</div>
</template>


<script>
import UserTodo from '@/components/todoStatic.vue';
export default {
    name: 'FirstComponent',
    components:{
        UserTodo
    },
    props: ["value"],
    data() {
        return {
            message: "Salut les gens",
            countId: 0,
           vHtml: `<h1>Test Vhtmpl</h1>`
        };
    },
    methods: {
        toIncrement() {
            this.countId++;
        },
    },
    computed: {
        isButtonDisabled(){
            if(this.countId >= 20){
                return true
            }
            return false
        }
    }
}
</script>