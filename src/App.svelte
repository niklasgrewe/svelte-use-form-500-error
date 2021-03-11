<script>
    import { useForm, minLength, email, required } from 'svelte-use-form'

    const form = useForm({
        email: {
            validators: [required, email],
            errorMap: { required: "Please enter an email address", email: "This is not a valid email address" }
        },
        password: {
            validators: [required, minLength(6)],
            errorMap: { required: "Please enter your password", minLength: value => `The Password requires at least ${value} characters` }
        }
    })
</script>

<form use:form>
    <input type="email">
    <input type="password">
</form>

