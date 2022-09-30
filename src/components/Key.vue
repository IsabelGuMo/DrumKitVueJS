<template>
     <button :class="`key ${clicked ? 'clicked' : ''}`" @click="play" class="h-32 w-32 transition ease-in-out delay-150 bg-blue-500 hover:-translate-y-1 hover:scale-110 hover:bg-indigo-500 duration-200 bg-gradient-to-r from-green-400 to-blue-500 hover:from-pink-500 hover:to-yellow-500 rounded-xl m-2 text-4xl text-slate-300">
         {{ sound.letter }} 
     </button>
</template>
<script>
export default {
    name: "key",
    props: ["sound"],
    data () {
        return{
            clicked: false,
            }
    },
    methods: {
        play() {
            this.clicked = true;
            new Audio(this.sound.audio).play();

            setTimeout(() => {
                this.clicked = false;
            }, 200);
        }  
    },
    mounted () {
        document.addEventListener('keydown', (event) => {
            if (event.key.toLowerCase() == this.sound.letter.toLowerCase()) {
                this.play();
            }
        })
    }
}
</script>

<style>
button:hover {
    /* opacity: 0.7;
    transform: scale(0.95); */
    cursor: url('../assets/icons/musician.png'), auto;
}

button:active, button.clicked {
    transform: scale(1.1);
    box-shadow: 0px 0px 6px rgba(0, 0, 0, 0.7);
    background: #40E0D0;  /* fallback for old browsers */
    background: -webkit-linear-gradient(to right, #FF0080, #FF8C00, #40E0D0);  /* Chrome 10-25, Safari 5.1-6 */
    background: linear-gradient(to right, #FF0080, #FF8C00, #40E0D0); /* W3C, IE 10+/ Edge, Firefox 16+, Chrome 26+, Opera 12+, Safari 7+ */
;
}
</style>