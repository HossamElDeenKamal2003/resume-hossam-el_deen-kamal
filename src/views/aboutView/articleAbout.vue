<template>
    <div class="about container draggable" :style="{ top: position.y + 'px', left: position.x + 'px' }"
        @mousedown="startDrag" @mousemove="handleDrag" @mouseup="stopDrag">
        <p>
            Hello! I'm Hossam El_Deen, a passionate frontend developer with a knack for crafting elegant and user-friendly
            interfaces.
            With a background in computer science and a love for coding, I bring creativity and attention to detail to every
            project.
        </p>
        <h2>Skills</h2>
        <ul>
            <li>HTML5, CSS3, JavaScript (ES6+)</li>
            <li>React.js, Vue.js</li>
            <li>Responsive Web Design</li>
            <li>UI/UX Design Principles</li>
        </ul>
    </div>
</template>
<script>
export default {
    name: 'articleAbout',
    data() {
        return {
            isDragging: false,
            position: { x: 0, y: 0 },
            offset: { x: 0, y: 0 },
        };
    },
    methods: {
        startDrag(event) {
            this.isDragging = true;
            this.offset = {
                x: event.clientX - this.position.x,
                y: event.clientY - this.position.y,
            };
        },
        handleDrag(event) {
            if (this.isDragging) {
                this.position = {
                    x: event.clientX - this.offset.x,
                    y: event.clientY - this.offset.y,
                };
            }
        },
        stopDrag() {
            this.isDragging = false;
        },
    },

}
</script>
<style scoped>
.about {
    margin-top: 5em;
}

.draggable {
    position: absolute;
    cursor: grab;
    user-select: none;
    transition: transform 0.2s ease;
}

.draggable:active {
    cursor: grabbing;
}

p,
h2,
li {
    font-size: 2em;
    background: linear-gradient(45deg, #4CAF50, #FFC107);
    -webkit-background-clip: text; /* Vendor-prefixed version for WebKit browsers */
    background-clip: text;
    color: transparent;
    display: inline-block;
    animation-name: desani;
    animation-duration: 2s;
    animation-timing-function: ease-out;
    animation-fill-mode: forwards;
    font-family: fantasy;
}   
@keyframes desani {
    0% {
        opacity: 0;
        transform: translateY(0);
    }

    100% {
        opacity: 1;
        transform: translateY(0);
    }
}
ul {
    list-style: none;
    animation: fadeInUp 1s ease-out forwards;

    @keyframes fadeInUp {
        from {
            opacity: 0;
            transform: translateY(20px);
            /* Initial position */
        }

        to {
            opacity: 1;
            transform: translateY(0);
            /* Final position */
        }
    }
}</style>