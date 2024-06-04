<template>
    <div class="parent">
        <p v-for="item in items" :key="item">{{item}}</p>
    </div>
</template>

<script>
export default {
    name: 'serviceArticle',
    data() {
        return {
            items: [
                'Web Development: Highlight your expertise in creating responsive and user-friendly websites',
                'UI/UX Design: Offer UI/UX design services, demonstrating your ability to create visually appealing and intuitive user interfaces',
                'Responsive Design: Emphasize your expertise in creating websites that are optimized for different screen sizes and devices',
                'Performance Optimization: Offer services related to optimizing website performance. Highlight your skills in optimizing code, reducing page load times',
                'Website Maintenance and Support: Offer ongoing maintenance and support services for existing websites'
            ]
        };
    }
};
</script>

<style scoped>
.parent {
    margin-top: 2em;
}

p{
    animation-name: ULAni;
    animation-duration: 1s;
    animation-timing-function: ease-out;
    animation-fill-mode: forwards;
    list-style: none;
    letter-spacing: 2px;
}

@keyframes ULAni {
    0% {
        opacity: 0;
        transform: translateY(-100%);
    }
    25% {
        opacity: 0.5;
        transform: translateY(-50%);
    }
    100% {
        opacity: 1;
        transform: translateY(0%);
    }
}

p {
    color: white;
    background: linear-gradient(45deg, #4CAF50, #FFC107);
    -webkit-background-clip: text;
    background-clip: text;
    color: transparent;
    font-family: system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
    margin-top: 5em;
    
}

p:after {
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

p:hover::after {
    transform: scaleX(1);
    transform-origin: bottom left;
}

p:hover {
    color: aqua;
}

p:focus {
    color: greenyellow;
}
</style>