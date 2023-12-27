<script setup>
const props = defineProps({
    id: {
        type: String,
        default: "text",
    },
    name:{
        type: String,
        default: "text",
    },
    type: {
        type: String,
        default: "text",
    },
    placeholder: {
        type: String,
        default: "Enter Name",
    },
    value: {
        type: String,
    },
    onChange: {
        type: Function,
    }, 
});


//สร้าง function ที่เป็นตัวแปร เมื่อมีการเรียกใช้ prop 
const onchange = (e) => {
    // console.log(e); //ไว้ดูระบบผิดพลาดยังไง //(e)จะไดค่าที่ console log ได้ค่าเปลี่ยนแปลงจากอีเว้นท์
    // console.log("EEEE",e.target.value);
    // console.log('porp',props.name);
    props.onChange(e.target.value, props.name);
};
</script>
<template>
    <input 
    class="w-[300px] h-[80px] rounded-lg border-2 border-solid border-gray-600 bg-slate-600" 
    :type="props.type"
    :placeholder="props.placeholder" 
    v-model="props.value"
    @change="onchange" 
    />
</template>