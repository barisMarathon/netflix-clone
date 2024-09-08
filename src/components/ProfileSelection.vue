<template>

    <div v-if="isVisible">
        <div class="fixed inset-0 bg-black bg-opacity-90 flex items-center justify-center z-20">
            <div class="grid grid-cols-3 gap-4">

                <div v-for="(item, index) in items" :key="index" class=" p-8 rounded-lg shadow-lg w-1/7 text-center">
                    <p>{{ item.message }}</p>
                    <img :src="item.image" width="120" height="120" @click="close" />
                    <button @click="close" class="mt-4 px-4 py-2 bg-red-800 text-white rounded">{{ item.message
                        }}</button>
                </div>
            </div>
        </div>
        <button @click="close">Close</button>
    </div>
</template>

<script setup>
import { defineProps, defineEmits, ref } from 'vue';

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
