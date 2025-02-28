<script setup>
    import { faker } from '@faker-js/faker'
    const firstname = faker.person.firstName()
    const lastname = faker.person.lastName()
    const jobtitle = faker.person.jobTitle()
    const bio = faker.lorem.lines(2)
    const username = faker.internet.userName({ firstName: firstname, lastName: lastname }).toLowerCase()
    const image = faker.image.url(960, 480, true);
    const email = faker.internet.email()
    const phone = faker.phone.number()
    const date = faker.date.recent()
    const city = faker.address.city()
    
</script>

<template>
    <RouterLink :to="{name: 'CardDetail', params: {id: username}}">
        <div class="border border-gray-500 rounded-lg shadow bg-yellow-500 h-full">
            <img class="object-fill h-480 w-960 rounded-t-lg" :src="image" style="width: 300px; height: 200px; object-fit: cover;" />
            <div class="p-4">
                <p class="mb-2 text-2xl font-bold">{{ firstname }} {{ lastname }}</p>
                <p class="mb-3 font-normal text-gray-800">{{ city }}</p>
                <p class="mb-3 font-normal text-gray-800">{{ date }}</p>
                <p class="mb-3 font-normal text-gray-800">{{ email }}</p>
                <p class="mb-3 font-normal text-gray-800">{{ phone }}</p>
                <p class="mb-3 font-normal text-gray-800">{{ bio }}</p>
            </div>
        </div>
    </RouterLink>
</template>