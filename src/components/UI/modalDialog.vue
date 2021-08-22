<template>
    <div class="dialog" v-if="show" @click.stop="hideWindow" >
        <div @click.stop class="dialog__content">
            <slot></slot>
        </div>
    </div>
</template>

<script>
export default {
    name: 'modal-dialog',
    props: {
        show: {
            type: Boolean,
            default: false
        }
    },
    methods: {
        hideWindow() {
            this.$emit('update:show', false)
        }
    }
}
</script>

<style>
.dialog {
    top: 0;
    bottom: 0;
    left: 0;
    right: 0;
    background: rgba(0, 0, 0, 0.5);
    position: fixed;
    display: flex;
}
.dialog__content {
    margin: auto;
    background: white;
    border-radius: 13px;
    min-height: 50px;
    min-width: 300px;
}
</style>