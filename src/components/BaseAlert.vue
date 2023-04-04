<template>
    <div :class = "baseClass">
        {{ text }}
    </div>
</template>

<script>
    export default {
        props: ['variant', 'text'],
        computed: {
            baseClass() {
                return [
                    'alert',
                    this.variant ? `alert-${this.variant}` : ''
                ]
            }
        }
    }
</script>

<style scoped>

.alert {
    padding: 5px;
    border-radius: 6px;
    color: gray;
    background-color: #ddd;
}

.alert-success {
    background-color: rgb(0, 53, 35);
    color: #fff;
    width: 30%;
}

.alert-danger {
    background-color: rgb(200, 58, 58);
    color: #fff;
    width: 30%;
}
.alert-warnning {
    background-color: rgb(238, 198, 52);
    color: #000;
    width: 30%;
}
</style>