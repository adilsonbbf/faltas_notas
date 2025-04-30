<template>
  <div class="min-h-screen bg-gray-100 p-4">
    <header class="text-center py-6">
      <h1 class="text-4xl font-bold text-gray-800">Sistema Escolar</h1>
      <p class="text-gray-600">Gestão de Notas e Faltas</p>
    </header>
    <StudentForm />
  </div>
</template>

<script>
import StudentForm from './components/StudentForm.vue';
export default {
  components: { StudentForm }
}
</script>
