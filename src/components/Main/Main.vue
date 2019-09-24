<template>
    <div>
        <h1>主页面</h1>
        欢迎!
        <el-form >
          <el-button @click='jump'>点这里登录</el-button>
          <el-button @click="onc">didi</el-button>
        </el-form>
    </div>
</template>

<script>
    export default {
        methods: {
            jump () {
                this.$router.replace('/login')
            },
            onc () {
              this.$router.replace('/layout')
            }
        }
    }
</script>
