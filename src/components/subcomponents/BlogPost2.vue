<script>
    export default {
        // Add code if/as necessary
        // Hint: Add properties subject, entry and mood
        props : {
            mood : String,
            subject : String,
            entry : String
        },

        computed:{
            imageSrc(){
                return `../../../public/assets/${this.mood.toLowerCase()}.png`
                // can use this also, assume all the images will be placed under public folder 
                // `/assets/${this.mood.toLowerCase()}.png`
                /*
                Yes — you can absolutely return:
                    return `/assets/${this.mood.toLowerCase()}.png`

                    ✅ It will work and give the same output, as long as your assets are in the public/assets/ folder in a Vue project created with Vite (or Vue CLI).

                    Why you can just use /assets/... (absolute path) instead of ../../..

                    In Vue Vite, anything inside the public/ folder is served as root (/).
                    So if you put your image at:
                    public/assets/happy.png
                    You can access it from your code like:
                    /assets/happy.png ✅

                    No need to use relative paths like ../../assets/... — that is only needed when importing from inside src/.
                 */
            }
    }
}
</script>


<template>
    <!-- TODO: add your template code here Use boostrap card --> 
     <div class="card" style="width:400px">
        <img class="card-img-top" :src="imageSrc" alt="Card image">
        <div class="card-body">
            <h4 class="card-title">{{subject}}</h4>
            <p class="card-text">{{entry}}</p>
            <slot></slot>
        <!--
            slot is placeholder, you are leaving this space for smth that u are putting later 
            -->
            

        </div>
    </div>

</template>

