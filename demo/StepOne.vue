<template>
    <div style="padding: 2rem 3rem; text-align: left;">
        <div class="field">
            <label class="label">Username</label>
            <div class="control">
                <input :class="['input', '']" type="text" placeholder="Text input"
                       v-model="form.username">
            </div>
            
        </div>
        <div class="field">
            <label class="label">Email</label>
            <div class="control">
                <input :class="['input', '']"  type="text" placeholder="Email input" v-model="form.demoEmail">
            </div>
            
        </div>
        <div class="field">
            <label class="label">Message</label>
            <div class="control">
                <textarea :class="['textarea', '']"  placeholder="Textarea" v-model="form.message"></textarea>
            </div>
        </div>
    </div>
</template>

<script>
    //import {validationMixin} from 'vuelidate'
    //import {required, email} from 'vuelidate/lib/validators'

    export default {
        props: ['clickedNext', 'currentStep'],
        //mixins: [validationMixin],
        data() {
            return {
                form: {
                    username: '',
                    demoEmail: '',
                    message: ''
                }
            }
        },
        methods: {
            canContinue() {
                this.$emit('can-continue', {value: true});
            }
        },
        mounted() {
            
        },
        // validations: {
        //     form: {
        //         username: {
        //             required
        //         },
        //         demoEmail: {
        //             required,
        //             email
        //         },
        //         message: {
        //             required
        //         }
        //     }
        // },
        watch: {
            // $v: {
            //     handler: function (val) {
            //         if(!val.$invalid) {
            //             this.$emit('can-continue', {value: true});
            //         } else {
            //             this.$emit('can-continue', {value: false});
            //             setTimeout(()=> {
            //                 this.$emit('change-next', {nextBtnValue: false});
            //             }, 3000)
            //         }
            //     },
            //     deep: true
            // },

            clickedNext(val) {

                console.log('next clicado')

                // if(val === true) {
                //     this.$v.form.$touch();
                // }
            }
        }
    }
</script>