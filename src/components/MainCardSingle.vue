<script setup>

import { faker } from '@faker-js/faker'
import { RouterLink } from 'vue-router'


const firstname = faker.person.firstName()
const lastname = faker.person.lastName()
const job_title = faker.person.jobTitle()
const bio = faker.lorem.lines(2)

const username = faker.internet.userName({ firstName: firstname, lastName: lastname }).toLowerCase()
const fullname = faker.internet.userName({ firstName: firstname, lastName: lastname })
</script>

<template>
    <!--{{ fullname }} <br/> -->
     <RouterLink :to="{name: 'CardDetails', params: {id:username}}">
    <div class="border border-gray-400 rounded-lg shadow bg-gray200 h-full">
        <img :src="faker.image.urlLoremFlickr({width: 640, height: 480, category: 'cat'})" class="rounded-t-xl"/>

    <div class="p-4">
        <p class="mb-2 text-2xl font-bold">{{ fullname }}</p>
        <p class="mb-3 text-gray-700 font-normal">{{job_title}}</p>
        <p class="mb-3 text-gray-700 font-normal">{{ bio }}</p>
    </div>
</div>
     </RouterLink>
</template>