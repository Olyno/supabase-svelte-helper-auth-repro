<script lang="ts">
	import { supabase } from '$lib/db';

	let email: string;

	async function login() {
		if (!email) return;
		await supabase.auth.signInWithOtp({ email });
	}
</script>

<h1>Login</h1>

<form on:submit|preventDefault={login}>
	<label for="email">Email</label>
	<input type="email" name="email" id="email" required bind:value={email} />

	<button type="submit">Login</button>
</form>
