<template>
     <div class="post-list">
                <div v-for="post in posts" :key="post.id" class="post">
                    <div class="user-info">
                        <a href="#" class="user-name">{{ userById(post.userId).name }}</a>
                        <a href="#">
                            <img :src="userById(post.userId).avatar" alt="user avatar" class="avatar-large">
                        </a>
                        <p class="desktop-only text-small">100 posts</p>
                    </div>
                   <div class="post-content">
                    <div>
                        <p>{{post.text}}</p>
                    </div>
                   </div>
                   <div class="post-date text-faded">
                    <app-date :time-stamp="post.publishedAt"/>
                   </div>
    
            </div>
            </div>
</template>

<script>
// import AppDate from "../components/AppDate.vue"


export default {
//   components: { AppDate },
        props: {
            posts: {
                required: true ,
                posts: Array
            }
        },

        data() {
            return {
                users: this.$store.state.users
            }
        },
        methods: {
             userById(userId) {
        return this.users.find(p => p.id === userId)
             }
        }
}
</script>

<style>

</style>