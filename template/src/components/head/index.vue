<template>
    <header>
        <el-row>
            <el-col :span="6">
                <h1 :class="style.tcenter" @click="hello">Spotlight for Vue</h1>
            </el-col>
            <el-col :span="18">
                <p :class="style.user_info">
                    <span>\{{$store.state.userInfo.name}}</span> ,你好
                </p>
            </el-col>
        </el-row>
    </header>
</template>
<script>
    import style from "B/assets/css/page.css"
    export default {
        data() {
            return {
               style
            };
        },
        mounted() {
            this.getUser()
        },
        methods: {
            getUser() {
                !this.$store.state.userInfo.name && 　this.$store.dispatch('getUserInfo')
            },
            hello() {
                this.$router.push('/')
            }
        }
    };
</script>
