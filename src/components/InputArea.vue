<template>
    <form @submit.prevent="handleSubmit">
        <p>名前をいれてください</p>
    <p><span class="name">なまえ</span><input type="text" name="name" v-model="name" required/></p>
    <p>男<input type="radio" name="sex" value="1" v-model="sex" required />
        女<input type="radio" name="sex" value="2" v-model="sex"/></p>
        <button>ペンネームを決める</button>
        <p>本名のほうが面白くなります。<br> （名前はサーバに保存してません）</p>
    </form>
</template>
<script>
    export default {
        data(){
            return {
                name: '',
                sex: 0,
            }
        },
        methods:{
            handleSubmit() {
                this.$emit('inputted',{name:this.name,sex:this.sex})
            }
        }
    }
</script>
<style scoped>
    form{
        width:300px;
        text-align: left;
        margin:0 auto;
        border:solid 2px #000;
        border-radius: 2px;
        padding:10px;
        box-sizing: border-box;
    }
    p {
        font-size: 12px;
        line-height: 148%;
    }
    button{
        -webkit-appearance: push-button;
        user-select: none;
        white-space: pre;
    }
</style>