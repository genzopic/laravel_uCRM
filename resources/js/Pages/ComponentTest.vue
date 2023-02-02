<script setup>
    import GuestLayout from '@/Layouts/GuestLayout.vue'
    import Label from '@/Components/InputLabel.vue'
    import Input from '@/Components/TextInput.vue'

    // const emitTest = (e) => {
    //     console.log(e);
    // }
    // 下記のように省略してかける
    const emitTest = e => console.log(e)    

</script>

<template>
    <GuestLayout>
        何か文字を書く
        <Label value="件名">タイトル</Label>
        <Input 
            modelValue="初期値が表示されます"
            @update:modelValue="emitTest"
        ></Input>
    </GuestLayout>    
</template>