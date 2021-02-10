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
          name="name"
          @input="$v.name.$touch()"
          @blur="$v.name.$touch()"
        ></v-text-field>
        <v-select
          v-model="select"
          :items="items"
          :error-messages="selectErrors"
          label="Subject"
          required
          @change="$v.select.$touch()"
          @blur="$v.select.$touch()"
          name="subject"
        ></v-select>
        <v-text-field
          v-model="email"
          :error-messages="emailErrors"
          label="E-mail"
          required
          name="email"
          @input="$v.email.$touch()"
          @blur="$v.email.$touch()"
        ></v-text-field>
        <v-textarea
          v-model="content"
          :error-messages="contentErrors"
          label="Message"
          required
          name="message"
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
            select: { required },
            email: {required, email},
            content: {required, maxLength: maxLength(500)},
        },
        name: 'contact',
        data: () => ({
            name: '',
            email: '',
            subject: '',
            content: '',
            select: null,
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
            selectErrors () {
                const errors = []
                if (!this.$v.select.$dirty) return errors
                !this.$v.select.required && errors.push('Item is required')
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
