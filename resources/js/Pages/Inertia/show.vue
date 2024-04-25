<script setup>
import { Inertia } from "@inertiajs/inertia";

defineProps({
    id: String,
    blog: Object,
});

const dileteConfirm = (id) => {
    Inertia.delete(`/inertia/${id}`, {
        onBefore: () => confirm("本当に削除しますか"),
    });
};

// onMounted(() => {
//     console.log(blogs);
// });
</script>

<template>
    <ul>
        <li>{{ blog.id }}</li>
        <li>{{ blog.title }}</li>
        <li>{{ blog.content }}</li>
    </ul>
    <button @click="dileteConfirm(id)">削除</button>
</template>
