<script setup>
import { ref, onMounted } from 'vue'

const emit = defineEmits(['save'])
const props = defineProps({
  fields: {
    type: Array,
    require: true
  },
  title: {
    type: String,
    require: true
  }
})

const formData = ref({})
const saveForm = () => {
  const formValues = Object.values(formData.value).map((item) => item['value'])
  emit('save', formValues)
}
onMounted(() => {
  props.fields.forEach((field) => {
    formData.value[field['name']] = {
      value: field['type'] === 'text' ? '' : 0,
      type: field['type'],
      options: field['type'] === 'select' ? field['options'] : null
    }
  })
})
</script>

<template>
  <div class="common-form">
    <div class="common-form__title">{{ title }}</div>
    <div class="common-form__group" v-for="(item, index) in formData" :key="index">
      <label for="" class="common-label">{{ index }}</label>
      <input
        type="text"
        class="common-input"
        v-if="item['type'] === 'text'"
        v-model="formData[index]['value']"
      />
      <select type="text" class="common-input" v-else v-model="formData[index]['value']">
        <option v-for="(option, index) in item['options']" :key="index">
          {{ option }}
        </option>
      </select>
    </div>
    <div class="text-center">
      <button class="common-form__btn-save" @click="saveForm()">Guardar</button>
    </div>
  </div>
</template>

<style scoped>
.common-form__title {
  text-align: center;
  font-size: 1.5rem;
}

.common-form__group {
  display: flex;
  flex-direction: column;
  margin: 1rem;
}

.common-form__btn-save {
  font-size: 1rem;
  padding: 0.5rem;
}
</style>
