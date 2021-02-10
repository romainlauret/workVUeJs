<template>
    <div class="header-container">
        <div id="headerBar">
            <h1>Header</h1>
            <ul  v-if="!loginInfos.is_logged">
                <li><router-link :to="{name: 'Login'}">Login</router-link></li>
            </ul>
            <ul   v-else>
                <li class="not-a-link">Hello {{ loginInfos.username }} ! </li>
            </ul>
            </div> 
    </div>
</template>

<script>
    export default {
        name: 'HederBar'
    }
</script>

<style lang="scss" scoped>
.header-container {
    background-color: #45AAF2;
}
h1 {
    font-size: 2.1em;
}
a:hover {
    text-decoration: underline;
}
#headerBar {
    margin: auto;
    display: flex;
    justify-content: space-between;
    color: white;
    align-items: center;
    ul {
        width: 30%;
        display: flex;
        justify-content: space-between;
        list-style: none;
        li {
            font-size: 1.5em;
            font-weight: 400;
            font-family: 'Roboto', sans-serif;
        }
    }
}
</style>