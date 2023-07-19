<template>
    <nav class="navbar navbar-expand-lg navbar-light fixed-top py-2" id="mainNav">
        <div class="container px-1">
            <NuxtLink to="/" class="navbar-brand fw-bold fs-4 text-white">OTTG</NuxtLink>
            <button class="navbar-toggler border navbar-toggler-right" type="button" data-bs-toggle="collapse" data-bs-target="#navbarResponsive" aria-controls="navbarResponsive" aria-expanded="false" aria-label="Toggle navigation"><i class="bi-list collapse-icon"></i></button>
            <div class="collapse navbar-collapse" id="navbarResponsive">
                <ul class="navbar-nav ms-auto my-2 my-lg-0">
                    <li class="nav-item fw-bold"><NuxtLink to="/" class="line-bottom nav-link text-white">HOME</NuxtLink></li>
                    <li class="nav-item fw-bold"><NuxtLink to="activities" class="line-bottom nav-link text-white">ACTIVITIES</NuxtLink></li>
                    <li class="nav-item fw-bold"><NuxtLink to="hotels" class="line-bottom nav-link text-white">HOTELS</NuxtLink></li>
                </ul>
            </div>
        </div>
    </nav>
</template>