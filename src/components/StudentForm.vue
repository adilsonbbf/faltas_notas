<template>
  <section class="max-w-xl mx-auto mt-10 bg-white p-6 rounded-xl shadow-lg">
    <h2 class="text-2xl font-bold text-center mb-6">Inserir Notas e Faltas</h2>
    
    <form @submit.prevent="handleSubmit" class="space-y-4">
      <div>
        <label for="studentName" class="block font-semibold mb-1">Nome do Aluno</label>
        <input v-model="form.name" id="studentName" type="text" required
          class="w-full border rounded-lg p-2" />
      </div>

      <div>
        <label for="subject" class="block font-semibold mb-1">Disciplina</label>
        <input v-model="form.subject" id="subject" type="text" required
          class="w-full border rounded-lg p-2" />
      </div>

      <div class="grid grid-cols-2 gap-4">
        <div>
          <label for="grade" class="block font-semibold mb-1">Nota</label>
          <input v-model.number="form.grade" id="grade" type="number" min="0" max="10" required
            class="w-full border rounded-lg p-2" />
        </div>

        <div>
          <label for="absences" class="block font-semibold mb-1">Faltas</label>
          <input v-model.number="form.absences" id="absences" type="number" min="0" required
            class="w-full border rounded-lg p-2" />
        </div>
      </div>

      <button type="submit"
        class="w-full bg-blue-600 hover:bg-blue-700 text-white py-2 px-4 rounded-lg font-semibold">
        Salvar Dados
      </button>
    </form>

    <div v-if="submitted" class="mt-4 text-green-600 font-medium">
      Dados salvos com sucesso!
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      form: {
        name: '',
        subject: '',
        grade: null,
        absences: null,
      },
      submitted: false
    };
  },
  methods: {
    handleSubmit() {
      console.log(this.form);
      this.submitted = true;
      // Aqui você pode integrar com uma API ou banco de dados
    }
  }
}
</script>
