<template>
  <v-col
    cols="12"
    class="flex-center"
  >
    <v-card
      width="600"
    >
      <form

      >
        <v-text-field
          v-model="name"
          :error-messages="nameErrors"
          :counter="10"
          label="Name"
          required
          @input="$v.name.$touch()"
          @blur="$v.name.$touch()"
        ></v-text-field>
        <v-text-field
          v-model="subject"
          :error-messages="subjectErrors"
          :counter="30"
          label="Subject"
          required
          @input="$v.name.$touch()"
          @blur="$v.name.$touch()"
        ></v-text-field>
        <v-text-field
          v-model="email"
          :error-messages="emailErrors"
          label="E-mail"
          required
          @input="$v.email.$touch()"
          @blur="$v.email.$touch()"
        ></v-text-field>
        <v-textarea
          v-model="content"
          :error-messages="contentErrors"
          label="Content"
          required
          @input="$v.name.$touch()"
          @blur="$v.name.$touch()"
        ></v-textarea>
        <v-btn
          @click="submit"
          class="flex-center"
        >
          submit
        </v-btn>
      </form>
    </v-card>
  </v-col>
</template>

<script>
    import {validationMixin} from 'vuelidate'
    import {required, maxLength, email} from 'vuelidate/lib/validators'

    export default {
        mixins: [validationMixin],

        validations: {
            name: {required, maxLength: maxLength(10)},
            subject: {required, maxLength: maxLength(30)},
            email: {required, email},
            content: {required, maxLength: maxLength(500)},
        },
        name: 'contact',

        data: () => ({
            name: '',
            email: '',
            subject: '',
            content: '',
        }),

        computed: {
            nameErrors() {
                const errors = []
                if (!this.$v.name.$dirty) return errors
                !this.$v.name.maxLength && errors.push('Name must be at most 10 characters long')
                !this.$v.name.required && errors.push('Name is required.')
                return errors
            },
            emailErrors() {
                const errors = []
                if (!this.$v.email.$dirty) return errors
                !this.$v.email.email && errors.push('Must be valid e-mail')
                !this.$v.email.required && errors.push('E-mail is required')
                return errors
            },
            subjectErrors() {
                const errors = []
                if (!this.$v.name.$dirty) return errors
                !this.$v.subject.maxLength && errors.push('Subject must be at most 30 characters long')
                return errors
            },
            contentErrors() {
                const errors = []
                if (!this.$v.name.$dirty) return errors
                !this.$v.subject.maxLength && errors.push('Content must be at most 500 characters long')
                return errors
            },
        },

        methods: {
            submit() {
                this.$v.$touch()
            },
        },
    }
</script>
