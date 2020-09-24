<template>
<Form v-bind:button_title="button_title" v-bind:next_page="next_page" v-bind:onSubmit="onSubmit" v-bind:message="message" v-bind:title="title">
    <FormInput v-model="inputs.email" label="Email" name="email" type="email" />
    <FormInput v-model="inputs.password" label="Password" name="password" type="password" />
</Form>
</template>

<script>
import FormInput from "./FormInput";
import Form from "./Form";
import {
    reactive
} from "@vue/composition-api";

export default {
    components: {
        FormInput,
        Form,
    },
    setup() {
        const inputs = reactive({
            email: "",
            password: "",
        });

        return {
            inputs,
            message: "Don't have an account yet? Sign Up",
            title: "Sign in",
            button_title: "Sign in",
            next_page: "/signup",
            onSubmit: (e) => {
                console.log("Submitting...");
                console.log(inputs.email, inputs.password);
            },
        };
    },
};
</script>
