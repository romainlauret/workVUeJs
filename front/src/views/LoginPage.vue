<template>
    <div classe="MyLogin">
        <form>
        
        <div class="segment">
            <h1>Sign up</h1>
        </div>
        
        <label>
            <input type="text" placeholder="Email Address" v-model="username_input"/>
        </label>
        <label>
            <input type="password" placeholder="Password"/>
        </label>
        <button class="red" @click="emitLogUser" type="button"> Log in</button>
        
        </form>
    </div>
</template>

<script>
    export default {
        name: 'MyLogin',
        data() {
            return {
                username_input: '',
                password_input: ''
            }
        },
        methods: {
            emitLogUser() {
                this.$emit('userLogged', {
                    username: this.username_input,
                    password: this.password_input
                })
                this.$router.push({ name: 'Home' });
            }
        },
    }
</script>

<style lang="scss" scoped>
</style>