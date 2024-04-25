<script setup>
import { Link } from "@inertiajs/inertia-vue3";
import { ref } from "vue";

const newTitle = ref("");
const newContent = ref("");
</script>

<template>
    Inertiaテスト<br />
    <a href="/">aタグ経由</a><br />

    <Link href="/">Link経由です</Link><br />
    <Link :href="route('index')">名前つきルート</Link>
    <Link :href="route('show', { id: 2 })">ルートパラメータ</Link>

    <div class="mb-8"></div>
    <input type="text" name="newTitle" v-model="newTitle" id="" />{{ newTitle
    }}<br />
    <input type="text" name="newContent" v-model="newContent" id="" />{{
        newContent
    }}<br />

    <Link
        as="button"
        method="post"
        :href="route('store')"
        :data="{
            title: newTitle,
            content: newContent,
        }"
        >DB保存テスト
    </Link>
</template>
