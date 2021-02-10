<template>
  <v-col
    cols="12"
    class="flex-center"
  >
    <v-card
      width="600"
    >
      <form
        name="contact"
        netlify
        method="post"
        action="/"
        @submit.prevent="submit"
      >
        <v-text-field
          v-model="name"
          :error-messages="nameErrors"
          :counter="30"
          label="Name"
          name="name"
          required
          @change="$v.name.$touch()"
          @blur="$v.name.$touch()"
        ></v-text-field>
        <v-select
          v-model="subject"
          :items="items"
          :error-messages="subjectErrors"
          label="Subject"
          required
          @change="$v.subject.$touch()"
          @blur="$v.subject.$touch()"
          name="subject"
        ></v-select>
        <v-text-field
          v-model="email"
          :error-messages="emailErrors"
          label="E-mail"
          required
          @change="$v.email.$touch()"
          @blur="$v.email.$touch()"
          name="email"
        ></v-text-field>
        <v-textarea
          v-model="content"
          :counter="500"
          :error-messages="contentErrors"
          label="Message"
          required
          @input="$v.content.$touch()"
          @blur="$v.content.$touch()"
          name="message"
        ></v-textarea>
        <v-btn
          type="submit"
          value="Send message"
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
            name: {required, maxLength: maxLength(30)},
            subject: { required },
            email: {required, email},
            content: {required, maxLength: maxLength(500)},
        },
        name: 'contact',
        data: () => ({
            name: '',
            email: '',
            subject: '',
            content: '',
            items: [
                'General Inquiry',
                'Paddle Order',
            ],
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
            subjectErrors () {
                const errors = []
                if (!this.$v.subject.$dirty) return errors
                !this.$v.subject.required && errors.push('Item is required')
                return errors
            },
            contentErrors() {
                const errors = []
                if (!this.$v.content.$dirty) return errors
                !this.$v.content.maxLength && errors.push('Content must be at most 500 characters long')
                !this.$v.content.required && errors.push('Item is required')
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
