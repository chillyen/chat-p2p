<script>
  import { user } from "./user";

  let username;
  let password;

  function login() {
    user.auth(username, password, ({ err }) => err && alert(err));
  }

  function signup() {
    user.create(username, password, ({ err }) => {
      if (err) {
        alert(err);
      } else {
        login();
      }
    });
  }
</script>

<div class="logo_container">
  <div class="circular-image">
    <img src="/nyan-cat-60fps.gif" alt="my_image" />
  </div>
</div>
<div>
  <label for="username">Username</label>
  <input name="username" bind:value={username} minlength="3" maxlength="16" />

  <label for="password">Password</label>
  <input name="password" bind:value={password} type="password" />

  <button class="login" on:click={login}>Login</button>
  <button class="login" on:click={signup}>Sign Up</button>
</div>

<div class="author_container">
  <div class="author-image">
    <img src="/logo.jpg" alt="" />
  </div>
</div>
