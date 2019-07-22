<template>
    <div class="hello">
		Counter数量:
        <input placeholder="请输入数字" v-model="inputNumber"></input>
        <div v-for="n of parseInt(inputNumber)" :key="n">
            <CounterGroup v-on:calculate="calculate"></CounterGroup>
        </div>
		<CounterSum :counterSum = "totalCount"></CounterSum>
    </div>
</template>

<script>
    import CounterGroup from './CounterGroup.vue'
	import CounterSum from './CounterSum.vue'

    export default {
        data() {
            return {
                inputNumber : 0,
                totalCount: 0,
                counterNumber: []
            };
        },
        components: {
            CounterGroup,
			CounterSum
        },
        name: 'HelloWorld',
        methods: {
          calculate (number) {
              this.totalCount +=number;

          }
        },
        watch: {
            inputNumber () {
                this.totalCount = 0;
            }
        }
        }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
    h3 {
        margin: 40px 0 0;
    }

    ul {
        list-style-type: none;
        padding: 0;
    }

    li {
        display: inline-block;
        margin: 0 10px;
    }

    a {
        color: #42b983;
    }
</style>
