<script>
    import { useForm, validators, HintGroup, Hint, email, required } from "svelte-use-form";
  
    const form = useForm();
</script>
  
<form use:form>
    <h1>Login</h1>

    <input type="email" name="email" use:validators={[required, email]} placeholder="Email"/>
    <HintGroup for="email">
        <Hint on="required">이메일은 필수 항목입니다.</Hint>
        <Hint on="email" hideWhenRequired>유효하지 않은 이메일입니다.</Hint>
    </HintGroup>

    <input type="password" name="password" use:validators={[required]} placeholder="Password"/>
    <Hint for="password" on="required">비밀번호는 필수 항목입니다.</Hint>

    <button disabled={!$form.valid}>로그인</button>
</form>

<style>
	:global(.touched:invalid) {
		border-color: red;
		outline-color: red;
	}
</style>