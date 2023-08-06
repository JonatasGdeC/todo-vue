<script setup>
    const props = defineProps(['tarefas', 'mensagemSemPendentes'])
</script>

<template>
    <ul class="list-group mt-4">
        <li class="list-group-item" v-for="tarefa in props.tarefas">
            <input @change="evento => tarefa.finalizada = evento.target.checked" :checked="tarefa.finalizada" :id="tarefa.titulo" type="checkbox">
            <label :class="{ done: tarefa.finalizada === true }" class="ms-3" :for="tarefa.titulo">{{ tarefa.titulo }}</label>
        </li>
    </ul>

    <div v-if="props.mensagemSemPendentes" class="mt-3 mb-3 text-center">
        <h2>Não há tarefas pendentes</h2>
        <img class="mt-3" src="https://media.tenor.com/754N-r_D8_IAAAAM/girl-doida-aniversario-happy-birthday.gif" alt="Gif comemorativa">
    </div>
</template>

<style scoped>
.done{
    text-decoration: line-through;
}
</style>