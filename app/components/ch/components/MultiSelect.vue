<template>
  <div class="form__group__select">
    <label v-if="label" :for="id" :class="labelClasses">
      {{ label }}<span v-if="required" class="form__group__required" />
    </label>
    <div :class="selectWrapperClasses">
      <vSelect
        :multiple="multiple"
        :placeholder="placeholder"
        :class="selectClasses"
        :disabled="disabled"
        :components="{ Deselect, OpenIndicator }"
        :options="options"
      />
      <div class="select__icon">
        <svg role="presentation" aria-hidden="true" viewBox="0 0 24 24">
          <path
            d="m5.706 10.015 6.669 3.85 6.669-3.85.375.649-7.044 4.067-7.044-4.067z"
          />
        </svg>
      </div>
    </div>
    <div
      v-if="message"
      class="badge badge--sm"
      :class="`badge--${messageType}`"
    >
      {{ message }}
    </div>
  </div>
</template>

<script>
import vSelect from 'vue-select'

export default {
  name: 'MultiSelect',
  components: {
    vSelect,
  },
  data: () => ({
    Deselect: {
      render: (createElement) => createElement('span', '×'),
    },
    OpenIndicator: {
      render: (createElement) => createElement('span'), // hide the default icon
    },
  }),
  props: {
    options: {
      type: Array,
      default: () => [],
    },
    variant: {
      type: String,
      validator: (prop) => ['outline', 'negative'].includes(prop),
      default: 'outline',
    },
    size: {
      type: String,
      validator: (prop) => ['sm', 'base', 'lg'].includes(prop),
    },
    label: {
      type: String,
    },
    hideLabel: {
      type: Boolean,
      default: false,
    },
    id: {
      type: String,
    },
    name: {
      type: String,
    },
    message: {
      type: String,
    },
    messageType: {
      type: String,
      validator: (prop) =>
        ['error', 'warning', 'success', 'info'].includes(prop),
    },
    required: {
      type: Boolean,
      default: false,
    },
    multiple: {
      type: Boolean,
      default: true,
    },
    placeholder: {
      type: String,
      default: '',
    },
    disabled: {
      type: Boolean,
      default: false,
    },
  },

  computed: {
    selectWrapperClasses() {
      let base = 'select shadow-lg '
      if (this.bare) base += `select--bare `
      return base
    },
    selectClasses() {
      let base = ''
      if (this.variant) base += `input--${this.variant} `
      if (this.size) base += `input--${this.size} `
      if (this.disabled) base += `input--disabled `
      if (this.messageType) base += `input--${this.messageType} `
      return base
    },
    labelClasses() {
      let base = ''
      if (this.variant === 'negative') base += `text--negative `
      if (this.size) base += `text--${this.size} `
      if (this.hideLabel) base += `sr-only `
      if (this.required) base += `text--asterisk `
      return base
    },
  },
}
</script>
