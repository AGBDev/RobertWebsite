<script lang="ts">
    import { sign } from "crypto";
import { text } from "stream/consumers";

    interface TextImageObject {
        text: string;
        font: string;
        size: string;
    }

    export let object: TextImageObject;

    export const main: TextImageObject = {text: "DJ Robert Lenz", size: "xx-larger", font: ""}

    let image: string = "robert.jpg";
</script>

<div class="gfg">
    <img src={image} alt="" />
    <div class="text-container">
        <h1
            style="font-family: {object.font}; font-size:{object.size}"
        >
            {object.text}
        </h1>
    </div>
</div>
