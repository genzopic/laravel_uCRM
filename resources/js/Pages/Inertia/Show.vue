<script setup>
    import { Link } from '@inertiajs/inertia-vue3';
    import { Inertia } from '@inertiajs/inertia';
    defineProps({
        id: String,
        // 1件の時はArrayでなく、Object
        blog: Object
    });

    const deleteConfirm = id => {
        Inertia.delete(`/inertia/${id}`,{
            onBefore: () => confirm('本当に削除しますか？')
        })
        console.log(id);
    };

</script>

<template>
    {{ id }}<br>
    {{ blog.title }}<br>
    {{ blog.content }}<br>
    <button class="px-4 py-2 bg-red-300" @click="deleteConfirm(blog.id)">削除</button>
</template>
