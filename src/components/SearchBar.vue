<template>

    <div v-if="isVisible">
        <div class="fixed top-5 left-0 right-0 bg-black bg-opacity-30 flex items-center justify-center z-20">
            <div class="justify-between z-20 w-[600px] md:block hidden">
                <div class="rounded-full flex items-center bg-[#222222]">
                    <input type="text" class="form-control
                            block
                            w-full
                            px-5
                            py-1.5
                            text-base
                            font-normal
                            text-gray-200
                            bg-gray-600
                            placeholder-gray-400
                            bg-clip-padding
                            border
                            vorder-solid
                            border-l-gray-700
                            border-y-gray-700
                            rounded-l-full
                            transition
                            ease-in-out
                            m-0
                            border-transparent
                            focus:ring-0" placeholder="Search" />
                    <MagnifyIcon class="mx-6" fillColor="#FFFFFF" :size="23" />
                </div>
            </div>
        </div>
        <button @click="close">Close</button>
    </div>
</template>

<script setup>
import { defineProps, defineEmits, ref } from 'vue';
import MagnifyIcon from 'vue-material-design-icons/Magnify.vue';
const items = ref([
    { message: 'Carl', image: '/public/defaultIcon1.png' },
    { message: 'Hannah', image: '/public/defaultIcon2.png' },
    { message: 'Richard', image: '/public/defaultIcon3.png' }
]);

const props = defineProps({
    isVisible: {
        type: Boolean,
        default: true
    }
});

const emit = defineEmits(['close']);

const close = () => {
    emit('close');
};
</script>
