<template>
  <div class="col-ful">
                    <form @submit.prevent="save">
                        <div class="form-group">
                            <textarea  v-model="text" name="" id="" cols="30" rows="10" class="form-input"></textarea>
                        </div>
                        <div class="form-actions">
                            <button class="btn-blue">Submit Post</button>
                        </div>
                    </form>
            </div>
</template>

<script>
export default {
    data() {
        return {
               text: ""
        }
    },
    methods: {
        save(){
            const postId = "atetbdhdudbhd" + Math.random();
        const post = {
            id: postId,
            text: this.text,
            publishedAt: Math.floor(Date.now() / 1000),
          
            userId: "ALXhxjwgY9PinwNGHpfai6OWyDu2"
        }
        this.text = "";
        this.$emit("save", { post })  //custom event
        }

}
}
</script>

<style>

</style>