<template>
<Form v-bind:button_title="button_title" v-bind:next_page="next_page" v-bind:onSubmit="onSubmit" v-bind:message="message" v-bind:title="title">
    <FormInput v-model="inputs.name" label="Display name" name="name" type="text" />
    <FormInput v-model="inputs.email" label="Email" name="email" type="text" v-bind:validators="validators.email" />
    <FormInput v-model="inputs.password" label="Password" name="password" type="password" />
    <FormInput v-model="inputs.confirm_password" label="Confirm password" name="confirm_password" type="password" />
</Form>
</template>

<script>
import FormInput from "./FormInput";
import Form from "./Form";
import {
    ref,
    reactive
} from "@vue/composition-api";
import {
    isEmail
} from "../../../helpers/validators";

export default {
    components: {
        FormInput,
        Form,
    },
    setup() {
        const inputs = reactive({
            name: "",
            email: "",
            password: "",
            confirm_password: "",
        });

        return {
            inputs,
            validators: {
                email: [isEmail()],
            },
            message: "Already have an account? Sign In",
            title: "Sign up",
            button_title: "Sign up",
            next_page: "/signin",
            onSubmit: (e) => {
                console.log("Submitting...");
                // Call api
            },
        };
    },
};
</script>
