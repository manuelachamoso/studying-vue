<script>
export default {
    data() {
        return {
            currentValue: '',
            tags: [],
        };
    },
    methods: {
        handleSubmit() {
            if (this.currentValue !== '') {
                const exist = this.tags.some(item => item === this.currentValue);
                if (!exist) {
                    this.tags.push(this.currentValue);
                    this.currentValue = '';
                }
            }
        },
        deleteTag(tag) {
            this.tags = this.tags.filter(item => item !== tag);
        }
    }
}
</script>

<template>
<div class="InputTag">
    <div class="tags">
        <div class="tag" v-for="(tag, index) in tags" :key="index">
            {{ tag }} <button @click="deleteTag(tag)">x</button>
        </div>
    </div>
    <form @submit.prevent="handleSubmit">
        <input type="text" v-model="currentValue"/>
    </form>
</div>
</template>

<style>
/* Add your styles here */
</style>
