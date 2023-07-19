<template>
    <section class="home d-flex justify-content-center" id="home">

        <div class="container text-end">
            <h3 class="fw-bold text-uppercase text-white">fullfifll your trip</h3>
            <h1 class="fw-bold text-uppercase text-white" style="font-size: 3.5rem;">with our luxurious hotels</h1>
        </div>

        </section>

        <section class="great-place mt-5 pt-5">

        <div class="section-label text-center">
            <div class="text-trustmebro">
                <h3 class="yellow text-uppercase fw-bold">RECOMMENDATION</h3>
            </div>
            <div class="text-tourists">
                <h1 class="fw-bold">TOP-TIER HOTELS</h1>
            </div>
        </div>

        <div class="container mt-5">
            <div class="row">
                <div class="col-md-4" v-for="hotel in hotels">
                    <div class="card w-100 rounded-4 text-center">
                        <img :src="hotel.img" alt="idk" class="rounded-top-4">
                        <div class="card-body">
                            <h5>{{ hotel.rating }}</h5>
                            <h5 class="fw-bold">{{ hotel.name }}</h5>
                            <p>{{ hotel.address }}</p>
                            <NuxtLink :to="hotel.id" class="btn btn-yellow w-100 py-2 fw-bold text-white">VIEW DETAILS</NuxtLink>
                        </div>
                    </div>
                </div>


            </div>
        </div>
    </section>
</template>
<script setup>
    const { data: hotels } = await useFetch('https://api.npoint.io/96df3001fb467d027167/hotel');
</script>