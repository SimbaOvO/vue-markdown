<template>
    <div>
        <Markdown
            ref="markdown"
            v-model="val"
            @on-ready="onReady"
            @on-copy="onCopy"
            @on-upload-image="onUpladImage"
            @on-save="onSave"
            :height="500"
            @upload="test"
        />
    </div>
</template>

<script>
    // import Markdown from './dist/simple';
    // import Markdown from 'vue-meditor';
    // import Markdown from './src/pro';
    import Markdown from './src/simple';

    export default {
        components: {
            Markdown
        },
        data: function () {
            return {
                val: ''
            }
        },
        methods: {
            test () {
                console.log('test')
                this.$refs.markdown.insertContent('\n![image](imgUrl)');
            },
            onReady(data) {
                console.log(data)
            },
            onCopy(text) {
                console.log(text);
            },
            onUpladImage(file) {
                console.log(file)
            },
            onSave(data) {
                console.log(data);
            }
        }
    }
</script>

<style lang="less">

</style>
