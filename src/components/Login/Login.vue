<template>
    <el-row type="flex" justify="center">
        <el-form ref="loginForm" :model="user" :rules="rules" status-icon label-width="80px">
<!--ref用于form调用login方法 :model数据对象 :rules 启用数据验证  status-icon 显示状态图标-->
            <el-form-item label="用户名" prop="name">
                <!--el-form-item一个表单组 prop元素名  -->
                <el-input v-model="user.name"></el-input>
                <!--v-model指令 输入的是user对象的name属性-->
            </el-form-item>
            <el-form-item label="密码" prop="pass">
              <!--@keyup.enter.native="login"监听键盘回车 第三方UI框架 加native 原生不用加 -->
                <el-input v-model="user.pass" type="password" @keyup.enter.native="login"></el-input>
            </el-form-item>
            <el-form-item>
                <el-button type="primary" icon="el-icon-upload" @click="login">登录</el-button>
                <!--@click调用login方法 -->
                <el-button @click="back()">返回主页</el-button>
            </el-form-item>
        </el-form>
    </el-row>
</template>

<script>
    export default {
        methods: {
            login () {
                this.$refs.loginForm.validate((valid) => {
                    if (valid) {
                        if (this.user.name === 'admin' && this.user.pass === '123') {
                            this.$notify({
                                type: 'success',
                                message: '欢迎你,' + this.user.name + '!',
                                duration: 3000
                            })
                            this.$router.replace('/')
                        } else {
                            this.$message({
                                type: 'error',
                                message: '用户名或密码错误',
                                showClose: true
                            })
                        }
                    }
                    else {
                        return false
                    }
                })
            },
            back () {
              this.$router.replace('/')
            }
        },
        data () {
            return {
                user: {},
                rules: {
                    name: [
                        {required: true, message: '用户名不能为空', trigger: 'blur'}
                    ],
                    pass: [
                        {required: true, message: '密码不能为空', trigger: 'blur'}
                    ]
                }
            }
        }
    }
</script>
