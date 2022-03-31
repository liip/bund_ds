<template>
  <div class="form__group__select">
    <v-select
      :class="classes"
      :disabled="disabled"
      :clearable="clearable"
      :placeholder="placeholder"
      :searchable="searchable"
      :options="options"
      :closeOnSelect="false"
    >
      <template #open-indicator="{ attributes }">
        <div class="v-select__icon">
          <SvgIcon icon="ChevronDown" size="xl" />
        </div>
      </template>
    </v-select>
  </div>
</template>

<script>
import vSelect from 'vue-select'
import SvgIcon from './SvgIcon.vue'
import 'vue-select/dist/vue-select.css'
export default {
  name: 'CustomSelect',
  components: {
    vSelect,
    SvgIcon,
  },

  props: {
    variant: {
      type: String,
      validator: (prop) => ['default', 'negative'].includes(prop),
      default: 'default',
    },
    disabled: {
      type: Boolean,
      default: false,
    },
    label: {
      type: String,
    },
    options: {
      type: Array,
    },
    clearable: {
      type: Boolean,
      default: false,
    },
    searchable: {
      type: Boolean,
      default: false,
    },
    placeholder: {
      type: String,
      default: '',
    },
  },

  computed: {
    classes() {
      let base = 'custom-select '
      if (this.variant) base += `custom-select--${this.variant} `
      if (this.size) base += `custom-select--${this.size} `
      if (this.iconPos) base += `custom-select--icon-${this.iconPos} `
      return base
    },
  },
}
</script>
