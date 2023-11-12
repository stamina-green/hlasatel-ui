<template>
    <div>
        <slot />
        <div class="navbar">
            <a @click="router.push('/')" :class="{'active': route.name === 'index'}">Home</a>
            <a @click="router.push('/fronta')" :class="{'active': route.name === 'fronta'}">Fronta</a>
        </div>
    </div>
</template>
<script setup>
const route = useRoute()
const name = route.name 
const router = useRouter()
</script>
<style>
.navbar {
    background-color: #333;
    overflow: hidden;
    position: fixed;
    bottom: 0;
    width: 100%;
}

/* Style the links inside the navigation bar */
.navbar a {
    float: left;
    display: block;
    color: #f2f2f2;
    text-align: center;
    padding: 14px 16px;
    text-decoration: none;
    font-size: 17px;
}

/* Change the color of links on hover */
.navbar a:hover {
    background-color: #ddd;
    color: black;
}

/* Add a color to the active/current link */
.navbar a.active {
    background-color: #04AA6D;
    color: white;
}
</style>