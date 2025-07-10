<script setup>
const props = defineProps(['tarefas']);
</script>

<template>
    <div class="mt-4">
        <ul class="list-group" v-if="props.tarefas.length > 0">
            <li 
                class="list-group-item" 
                v-for="tarefa in props.tarefas" :key="tarefa.titulo">
                <input @change="evento => tarefa.finalizada = evento.target.checked" :checked="tarefa.finalizada" :id="tarefa.titulo" type="checkbox">
                <label :class="{ done: tarefa.finalizada }" class="ms-3" :for="tarefa.titulo">{{ tarefa.titulo }}</label>
            </li>
        </ul>
        <p v-else class="text-muted">Não existem tarefas pendentes.</p>
    </div>
</template>

<style scoped>
.done {
    text-decoration: line-through;
    }
</style>
