<template>
    <div class='canvas-parent'>
        <div :id='elementId' class='canvas-parent__canvas'></div>
    </div>
</template>

<script>
import P5 from 'p5'

export default {
    name: 'p5Canvas',
    props: {
        elementId: {
            type: String,
            required: true
        }
    },
    created () {
        const p5Script = (p5) => {
            let w = window.innerWidth - 20
            let h = window.innerHeight - 20
            // P5 Setup
            p5.setup = () => {
                p5.createCanvas(w, h)
                  .parent(this.elementId)
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

        /* P5 instance mode else we may experience issues
           with P5 being created in global scope */
        new P5(p5Script)
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
