<template>
  <base-dialog v-if='inputIsInvalid' title='Invalid Data' @closeDialogWithExternalClick="confirmError">
    <template #default>
      <p>Unfortunately one of the inputs is invalid.</p>
      <p>Please make sure you enter all the data inputs correctly!</p>
    </template>
    <template #actions>
      <base-button @click='confirmError'>Review Data</base-button>
    </template>
  </base-dialog>
  <base-card>
    <form @submit.prevent='submitResourcesData'>
      <div class='form-control'>
        <label for="title">Title</label>
        <input id='title' name='title' type="text" ref='titleInput'>
      </div>
      <div class='form-control'>
        <label for="description">Description</label>
        <textarea id="description" name="description" cols="30" rows="3" ref='descriptionInput' />
      </div>
      <div class='form-control'>
        <label for="link">Link</label>
        <input id='link' name='link' type="url" ref='linkInput'>
      </div>
      <div>
        <base-button type='submit'>Add Resource</base-button>
      </div>
    </form>
  </base-card>
</template>

<script>
export default {
  inject: ['addResource'],
  data() {
    return {
      inputIsInvalid: false
    }
  },
  methods: {
    submitResourcesData() {
      const titleInputData = this.$refs.titleInput.value;
      const descriptionInputData = this.$refs.descriptionInput.value;
      const linkInputData = this.$refs.linkInput.value;

      if (titleInputData.trim() === '' || descriptionInputData.trim() === '' || linkInputData.trim() === '') {
        this.inputIsInvalid = true;
        return;
      }

      this.addResource(titleInputData, descriptionInputData, linkInputData)
    },
    confirmError() {
      this.inputIsInvalid = false;
    }
  }
}
</script>

<style scoped>
label {
  font-weight: bold;
  display: block;
  margin-bottom: 0.5rem;
}

input,
textarea {
  display: block;
  width: 100%;
  font: inherit;
  padding: 0.15rem;
  border: 1px solid #ccc;
}

input:focus,
textarea:focus {
  outline: none;
  border-color: #3a0061;
  background-color: #f7ebff;
}

.form-control {
  margin: 1rem 0;
}
</style>