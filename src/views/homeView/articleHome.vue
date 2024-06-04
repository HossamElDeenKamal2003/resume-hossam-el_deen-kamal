<template>
    <div class="home">
        <div class="description">
            <h1 class="des">Hello, I am Hossam El_Deen Kamal <br> Frontend Developer with VueJs</h1>
        </div>
        <div class="img-container">
            <img class="img" src="../../assets//NEPH8786.jpg" alt="not support" width="300px" height="300px">
        </div>
    </div>
</template>

<script>
export default {
    name: 'articleHome',
}
</script>

<style scoped>
.home {
    background-color: black;
    height: 100%;
    display: flex;
    justify-content: space-around;
    align-items: center;
    flex-wrap: wrap;
    margin-top: 10em;
}

.img-container {
    position: relative;
    overflow: hidden;
    box-shadow: 0 10px 10px blue;
    border-radius: 50%;
}

.description {
    animation-name: slide-in;
    animation-duration: 1s;
    animation-timing-function: ease-out;
    animation-fill-mode: forwards;
}

.img-container img {
    display: block;
    transition: transform 0.3s ease-in-out;
    border-radius: 100%;
    animation-name: slide-in;
    animation-duration: 1s;
    animation-timing-function: ease-out;
    animation-fill-mode: forwards;
}

@keyframes slide-in {
    0% {
        opacity: 0;
        transform: translateX(-100%);
    }

    100% {
        opacity: 1;
        transform: translateX(0);
    }
}

.img-container:hover img {
    transform: scale(1.8);
}

h1 {
    color: white;
    display: inline-block;
    position: relative;
    text-decoration: none;
    font-family: fantacy;
}

h1:after {
    content: '';
    position: absolute;
    width: 100%;
    transform: scaleX(0);
    height: 2px;
    bottom: 0;
    left: 0;
    background-color: #0087ca;
    transform-origin: bottom right;
    transition: transform 1s ease-out;
}

h1:hover::after {
    transform: scaleX(1);
    transform-origin: bottom left;
}

h1:hover {
    color: aqua;
}

h1:focus {
    color: greenyellow;
}
</style>