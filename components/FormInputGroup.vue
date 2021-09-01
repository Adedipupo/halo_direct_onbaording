<template>
    <form-input-validate-wrapped :validator="v" :attribute='attribute'>
        <label :class="formLabelClasses" v-html="label"></label>
        <input
            v-mask="`${mask}`"
            class="form-control"
            :placeholder="placeholder"
            :type="type"
            :maxlength="maxlength"
            :max="max"
            :min="min"
            :class="formControlClasses"
            :autocomplete="autocomplete"
            :required="required"
            :invalid="hasError"
            :value="value"
            :disabled="disabled"
            @input="handleInput"
            ref="input"
        />
        <div class="text-muted"><small v-html="note"></small></div>
    </form-input-validate-wrapped>
</template>

<script>

export default {
    name: 'FormInputGroup',
    props: {
        v: {
            type: Object,
            required: true
        },
        mask: {
            type: String,
            required: false,
            // if somebody can make that better let me know and share with me ;)
            default: 'XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX'
        },
        attribute: {
            type: String,
            required: true
        },
        label: {
            type: String,
            required: true
        },
        type: {
            type: String,
            default: 'text'
        },
        maxlength : {
          type: String,
          required: false,
        },
        min : {
          type: String,
          required: false,
        },
        max : {
          type: String,
          required: false,
        },
        note: {
            type: String,
            default: ''
        },
        value: {
          value: [String, Number],
        },
        autocomplete: {
            type: String,
            default: 'off'
        },
        placeholder: {
            type: String,
            default: ''
        },
        focused: {
            type: Boolean,
            default: false
        },
        required: {
            type: Boolean,
            default: false
        },
        hasError: {
            type: Boolean,
            default: false
        },
        disabled:{
            type: Boolean,
            default: false
        }
    },
    data() {
        return {
            newMask : this.mask
        }
    },
    methods: {
        handleInput(event) {
            this.v.$touch();
            this.$emit('input', event.target.value);
        },

        focus() {
            this.$refs.input.focus();
        }
    },
    computed: {
        formControlClasses() {
            return {
                'is-invalid': this.hasError
            }
        },
        formLabelClasses() {
            return {
                'label--required': this.required === true
            }
        }
    }
}
</script>


<style scoped>
.form-control {
    width: 100%;
    height: 50px;
}
@media (max-width: 600px) { 
    .form-control {
    width: 100%;
    height: 40px;
}
 }
</style>