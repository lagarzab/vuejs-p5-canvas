<template>
    <div class='canvas-parent'>
        <div class='canvas-parent__canvas' :id='elementId'></div>
    </div>
</template>

<script>
import P5 from 'p5'

export default {
    name: 'p5Canvas',
    props: {
        script: {
            type: Function
        }
    },
    data () {
        return {
            elementId: 'p5DefaultCanvas',
            defaultScript: (p5) => {
                let w = window.innerWidth - 20
                let h = window.innerHeight - 20
                // P5 Setup
                p5.setup = () => {
                    p5.createCanvas(w, h)
                    .parent('p5DefaultCanvas')
                    p5.textSize(32)
                    p5.textAlign(p5.CENTER, p5.CENTER)
                }

                // Loop, which continues to draw canvas
                p5.draw = () => {
                    p5.background([ 255, 0, 0 ])
                    p5.fill(255)
                    p5.text('white text on a red background', w / 2, h / 2)
                }
            }
        }
    },
    mounted () {
        let p5s = this.defaultScript
        if (this.script) {
            p5s = this.script
            this.elementId = ''
        }

        /* P5 instance mode else we may experience issues
           with P5 being created in global scope */
        new P5(p5s)
    },
}
</script>

<style lang='scss'>
.canvas-parent {
    position: relative;
    &__canvas {
        position:absolute;
        left:10px;
        top:10px;
    }
}
</style>
