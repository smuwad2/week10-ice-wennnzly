<script>
    // TODO: Complete the code
    export default { 
        data() {
            return {

                
            }
        },
        // Hint: insert properties task (Object) and idx (Number)
        props : {
            desc : String,
            deadline : String
        },
        methods: {
            markDone() {
                this.$emit('task-done', this.desc);
            }
        }
    }
</script>

<template>
    <!-- TODO: add your template code here --> 
     <div class="card">
        <div class="card-body align-content-start">
            <h4 class="card-title">Deadline: {{ deadline }}</h4>
            <p class="card-text">{{desc}}</p>
            <button class="btn btn-primary" @click="markDone">Done</button>
        </div>
    </div>

   
</template>


