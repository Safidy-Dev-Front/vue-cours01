<template>
    <div>
        <h1>{{ message }}</h1>
        <p>{{ value }}</p>
        <button :class="classButtonFunc(false, false, true)" @click="toIncrement" :disabled="isButtonDisabled">incremennt {{ countId }}</button>
        <button :class="classButtonFunc(true, false, false)" @click="toDecrement" :disabled="countId <= 0 ? true : false">Decremennt {{ countId }}</button>

    </div>
    <ul>
        <UserTodo userItem=1 />
        <UserTodo userItem=2 />
        <UserTodo userItem=3 />
    </ul>
    <!-- v-html -->
    <div v-html="vHtml"></div>
    <!-- Attribute Bindings -->
    <div :id="countId">ID is {{ countId }}</div>
</template>
<script>
import UserTodo from '@/components/todoStatic.vue';
export default {
    name: 'FirstComponent',
    components: {
        UserTodo
    },
    props: ["value"],
    data() {
        return {
            message: "Salut les gens",
            countId: 0,
            vHtml: `<h1>Test Vhtmpl</h1>`,
            classButton:{
                "btn-primary": true,
                "btn": true,
                "btn-succes": false,
            }
        };
            
    },
    methods: {
        toIncrement() {
            this.countId++;
        },
        toDecrement() {
            this.countId--;
        },
        classButtonFunc(isDanger, isPrimary, isSucces){
            this.classButton["btn-primary"] = isPrimary;
            this.classButton["btn-success"] = isSucces;
            this.classButton["btn-danger"] = isDanger;

            return this.classButton;
        },
    },
    computed: {
        isButtonDisabled() {
            if (this.countId >= 20) {
                return true
            }
            return false
        }
    }
}
</script>