<template >
    <button v-for="item in number" @click="getNumber(item)">{{ item }}</button>
</template>
<script>
    export default{
        data(){
            return {
                number: ["C",".","%","/",7,8,9,"*",4,5,6,"-",1,2,3,"+",0,"="],
                numberInVal: ""
                // operator: "",
            }
        },
        emits: ['respone'],
        methods: {
            getNumber(data){
                try{
                    if(data === "="){
                        this.numberInVal = eval(this.numberInVal)
                        this.$emit("respone", this.numberInVal)
                    }else if(data === "C"){
                        this.numberInVal = ""
                        this.$emit("respone", this.numberInVal)
                    }else if(data === "%"){
                        this.numberInVal = this.numberInVal / 100
                        // JIka emit merespon maka kirim data this.numberInVal
                        this.$emit("respone", this.numberInVal)
                    }else{
                        if(this.numberInVal === "Error"){
                            this.numberInVal = ""
                        }
                        this.numberInVal += data.toString()
                        this.$emit("respone", this.numberInVal)
                    }
                }catch(error){
                    this.numberInVal = "Error";
                    this.$emit("respone", this.numberInVal)
                }
            }
        }
    }
</script>

<style scoped>

    button{
        width: 50px;
        margin: 1px;
        outline: none;
        border: none;
        background-color: #919191;
    }
    button:last-child{
        width: 152px;
    }
</style>