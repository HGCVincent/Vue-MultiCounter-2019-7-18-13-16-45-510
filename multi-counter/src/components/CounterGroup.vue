<template>
    <div>
        <p> {{number}}</p>
        <button type="danger" @click="add()">点我+</button>
        <button type="danger" @click="minus()">点我-</button>
        <br/><br/>
    </div>
</template>
<script>
    export default {
        name: "CounterGroup",
        props: ['calculate'],
        data() {
            return {
                number: 0
            };
        },
        methods: {
            add() {
                this.number++;
               this.$emit('calculate', 1)
            },
            minus() {
                this.number--;
                this.$emit('calculate', -1)
            }
        },
        mounted() {
            this.$emit('calculate', 0)
        }
    }

</script>

<style scoped>

</style>