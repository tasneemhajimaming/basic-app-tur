<script setup>
const type = ref("text"); //ref เพื่อให้ค่าเปลี่ยนตามที่เราแก้ในโค้ด ถ้าไม่ใช้พำด ค่าที่เราเปลี่ยนในโค้ดจะไม่เปลี่ยนตาม
const placeholder = ref("Enter First Name");

const form = reactive({
    firstName: "First Name",
    lastName: "Last Name",
    Number: 100,
});

//ref
// const boolean = true || flase

const onChange = (e, name) => {
    form[name] = e;
};

</script>

<template>
    <p>{{ form.firstName }}</p>
        <p>{{ form.lastName}}</p>
        <p>{{ form.Number }}</p>
    <div class="w-full h-screen flex gap-4 items-center justify-center">
        <Input :type="type" id="firstName" name="firstName" :placeholder="placeholder" :value="form.firstName" :onChange="onChange"/>
        <Input type="password" id="lastName" name="lastName" placeholder="Enter last Name " :value="form.lastName" :onChange="onChange"/>
        <Input type="number" id="number" name="number" placeholder="Enter number " :value="form.number" :onChange="onChange"/> 
    </div>


</template>