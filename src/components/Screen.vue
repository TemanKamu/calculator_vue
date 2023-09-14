 <template>
    <input type="text" :value="dataInBtn" readonly>
</template>

<script>
    export default {
        emits: ["respone"],
        props: {
            dataInBtn : "0",
        },
        methods: {
            getData(){
                this.$emit("respone", this.dataInBtn)
            }
        },
    }
</script>
<style scoped>
    input{
        width: 206px;
    }
</style>