<script setup>
import GuestLayout from "@/Layouts/GuestLayout.vue";
import Label from "@/Components/InputLabel.vue";
import Input from "@/Components/TextInput.vue";

const emitTest = (e) => {
    console.log(e);
};
</script>

<template>
    <GuestLayout>
        なんか文字を書く
        <Label value="件名"></Label>
        <Input modelValue="初期値" @update:modelValue="emitTest"></Input>
    </GuestLayout>
</template>
