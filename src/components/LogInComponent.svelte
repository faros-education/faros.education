<script>
  import { user } from './stores.js'
  import router, { curRoute } from './router.js';
  // const unsibscribe = authState(auth).subscribe( u => user => u );

  let userVal = "";
  let userPasswordVal = "";


  function moveToEmployeeView(){
		curRoute.set('/employee');
		window.history.pushState({path: '/employee'}, '', window.location.origin + '/employee');
	}

  function moveToLandingView(){
    curRoute.set('/');
    window.history.pushState({path: '/'}, '', window.location.origin);
  }

	function signUp(){

	}


	function logIn() {

	}

  function logOut(){
    let newUser = {userName:"", userId:""}
    user.update(u => newUser);
    moveToLandingView();
  }

</script>


<main>
  { #if $user.userId === "" }
    <h2 class="title is-4">
      LOG IN
    </h2>
    <div class="field">
      <p class="control has-icons-left has-icons-right">
        <input class="input" type="email" placeholder="Email" bind:value={userVal}>
        <span class="icon is-small is-left">
          <i class="fas fa-envelope"></i>
        </span>
        <span class="icon is-small is-right">
          <i class="fas fa-check"></i>
        </span>
      </p>
    </div>
    <div class="field">
      <p class="control has-icons-left">
        <input class="input" type="password" placeholder="Password" bind:value={userPasswordVal}>
        <span class="icon is-small is-left">
          <i class="fas fa-lock"></i>
        </span>
      </p>
    </div>
    <div class="field">
      <p class="control">
        <button class="button is-success is-outlined" on:click={signUp}>
          Sign Up
        </button>
        <button class="button is-success is-right" on:click={logIn}>
          Log In
        </button>
      </p>
    </div>
  { :else }
    <h1 class="title is-4 is-dark">LOGGED IN AS {$user.userName}</h1>
    <div class="field">
      <p class="control">
        <button class="button is-success" on:click={logOut}>
          Log Out
        </button>
      </p>
    </div>
  { /if }

</main>


<style>
main {
  width: 100%;
}

</style>
