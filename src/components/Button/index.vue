<template>
    <button class="button" 
     :class="[color, size, {disabled: disabled}]"
     :type="type" 
     @click="$emit('onClick')"
     :disabled="disabled"
     style="margin:10px"
     >
        <span class="button-text" v-if="innerText"> {{  innerText  }} </span>
        <span class="button-text" v-else>
            <slot></slot>
        </span>
    </button>
</template>
<script>
export default {
    name: 'GButton',
    props: {
        color: {
            type: String,
            default: 'primary'
        },
        disabled: {
            type: Boolean,
            default: false
        },
        size: {
            type: String,
            default: 'medium'
        },
        innerText: {
            type: String,
        },
        type:{
            type:String,
            default:'submit'
        }
    }
}
</script>
<style lang='scss'>
@import '../../style/style.scss';
</style>