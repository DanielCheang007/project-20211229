<template>
  <h2>{{ formHeader }}</h2>
  <form @submit.prevent="onSubmit" class="row g-3">
    <div>
      <div>
        <label for="todo-name">Name</label>
        <input
          type="text"
          id="todo-name"
          v-model="formData.name"
          class="form-control"
          required
        />
      </div>

      <div>
        <label for="todo-color">Color</label>
        <input type="color" v-model="formData.color" class="form-control" />
      </div>

      <div>
        <label for="todo-date">Date</label>
        <input type="datetime-local" v-model="formData.date" />
      </div>

      <div>
        <button type="submit" class="btn btn-primary">
          {{ editing ? "Update" : "Add" }}
        </button>

        <button v-if="editing" type="reset" @click="cancelEditing">
          Cancel
        </button>
      </div>
    </div>

    <div class="form-text">
      {{ formData }}
    </div>
  </form>
</template>

<script>
export default {
  data() {
    return {
      formHeader: "This is the Todo form",
      formData: {
        name: null,
        color: null,
        date: null,
      },
    };
  },
};
</script>

<style scoped>
label {
  display: block;
}
</style>