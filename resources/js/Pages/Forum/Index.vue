<script setup>
import ForumLayout from "@/Layouts/ForumLayout.vue";
import Select from "@/Components/Select.vue";
import InputLabel from "@/Components/InputLabel.vue";

import { Head } from "@inertiajs/vue3";
</script>

<template>
    <Head title="Inicio" />

    <ForumLayout>
        <div class="bg-white overflow-hidden shadow-sm sm:rounded-lg">
            <div class="p-6 text-gray-900">
                <InputLabel for="topic" value="Temas" class="sr-only" />
                <Select name="topics" id="topic">
                    <option value="">Todos los temas</option>
                    <option
                        :value="topic.title"
                        v-for="topic in $page.props.topics"
                        :key="topic.id"
                    >
                        {{ topic.title }}
                    </option>
                </Select>
            </div>
        </div>

        <template #side>
            <div class="bg-white overflow-hidden shadow-sm sm:rounded-lg">
                <div class="p-6 text-gray-900">Side</div>
            </div>
        </template>
    </ForumLayout>
</template>
