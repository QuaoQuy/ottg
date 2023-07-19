<template>
    <div class="container mt-5 pt-5">
        <select name="typeselect" id="typeselect" v-model="typeselect" v-on:change="updatePrice" class="form-control">
            <option value="0" disabled>-Choose room type-</option>
            <option v-for="roomtype in hotel.types" :key="roomtype.price" :value="{ price: roomtype.price, label: roomtype.clname }">{{ roomtype.clname }}</option>
        </select>
        <select name="sizeselect" id="sizeselect" v-model="sizeselect" v-on:change="updatePrice" class="form-control">
            <option value="0" disabled>-Choose room size-</option>
            <option v-for="roomsize in hotel.sizes" :key="roomsize.multi" :value="{ multi: roomsize.multi, label: roomsize.szname}">{{ roomsize.szname }}</option>
        </select>

        <p class="mt-5">Price: {{ typeselect.price * sizeselect.multi }}</p>
        <p>Selected room class: {{ typeselect.label }}</p>
        <p>Selected room size: {{ sizeselect.label }}</p>

        <button type="button" class="btn btn-primary mb-5" @click="saveToLocalStorage">Add to Cart</button>

    </div>
    
</template>
<script setup>
    
    const shoppingCart = [];

    const typeselect = ref(0);
    const sizeselect = ref(0);

    const saveToLocalStorage = () => {
        const price = typeselect.value.price * sizeselect.value.multi;
        const datas = {
            hotelName: hotel.value.name,
            selectedType: typeselect.value.label,
            selectedSize: sizeselect.value.label,
            totalPrice: price,
        };
        console.log(datas)
        localStorage.setItem('cart', JSON.stringify(datas));
    };
    

    const route = useRoute();
    const { data: hotel } = await useFetch('https://api.npoint.io/96df3001fb467d027167/hotel/' + route.params.hotel_id);

    useHead(() => {
        return {
        title: `${ hotel.value.name }`,
        };
    });

    useSeoMeta({
        ogTitle: `${ hotel.value.name }`,
        ogDescription: `${ hotel._value.name }`,
        ogImage: `${ hotel._value.img }`,
        twitterTitle: `${ hotel._value.name }`,
        twitterDescription: `${ hotel._value.name }`,
        twitterImage: `${ hotel._value.img }`,
    })
  
</script>