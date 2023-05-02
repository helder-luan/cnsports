<script setup>
  var vm = new Vue({
    el: '.login__container',
    data: {
      title: 'Entrar',
      button: 'Entrar',
      a: 'Criar conta',
      stateStart: true,
      form: {
        email: '',
        senha: ''
      },
      style: {
        logo: {
          backgroundImage: 'url("src/assets/images/form-login.jpg")',
          backgroundSize: 'cover',
          backgroundPosition: 'center',
          width: '100%',
          height: '100%'
        },
        formContainer: {
          left: '50%'
        },
        logoContainer: {
          left: '0'
        }
      },
    },
    mounted() {
      console.log('Componente montado');
    },
  })

  function changeForm() {    
    if (vm.stateStart) {
      vm.style.formContainer.left = '0';
      vm.style.logoContainer.left = '50%';

      vm.style.logo.backgroundImage = 'url("src/assets/images/form-cadastro.jpg")';
      vm.title = 'Criar conta';
      vm.button = 'Criar conta';
      vm.a = 'Entrar';
      vm.stateStart = false;
    } else {
      vm.style.logoContainer.left = '0';
      vm.style.formContainer.left = '50%';

      vm.style.logo.backgroundImage = 'url("src/assets/images/form-login.jpg")';
      vm.title = 'Entrar';
      vm.button = 'Entrar';
      vm.a = 'Criar conta';
      vm.stateStart = true;
    }
  }
</script>

<template>
  <div class="login__container">
    <div class="login__container--logo" :style="vm.style.logoContainer">
      <div class="logo" :style="vm.style.logo"></div>
    </div>
    <div class="login__container--form" :style="vm.style.formContainer">
      <form class="p-2">
        <h2 id="title">{{ vm.title }}</h2>
        <div class="mb-3">
          <label for="email" class="form-label">Email</label>
          <input v-model="vm.form.email" type="email" class="input-person" id="email" placeholder="name@example.com">
        </div>
        <div class="mb-3">
          <label for="password" class="form-label">Senha</label>
          <input v-model="vm.form.senha" type="password" class="input-person" id="password" placeholder="**********">
        </div>
        <button type="submit" class="button-person">{{ vm.button }}</button>
        <p>{{ vm.form.email }}</p>
      </form>
      <a href="#" v-on:click="changeForm()">{{ vm.a }}</a>
    </div>
  </div>
</template>

<style>
  .input-person {
    display: block;
    background: linear-gradient(white, white) padding-box, linear-gradient(90deg, #00C9FF 0%, #92FE9D 100%) border-box;
    border-radius: 8px;
    width: 100%;
    border: 2px solid transparent;
    padding: 0.25rem 1rem;
    outline: none;
    box-shadow: -5px 5px 10px 0px rgba(0, 0, 0, 0.25);
  }

  .button-person {
    display: block;
    background: linear-gradient(90deg, #00C9FF 0%, #92FE9D 100%);
    border-radius: 8px;
    width: 100%;
    border: 0;
    margin-top: 2rem;
    padding: 0.25rem 1rem;
    outline: none;
    color: #fff;
    font-weight: bold;
    cursor: pointer;
    box-shadow: -5px 5px 10px 0px rgba(0, 0, 0, 0.25);
  }

  .login__container {
    position: relative;
    display: flex;
    flex: 1;
    width: 100%;
    height: 100%;
  }

  .login__container--logo {
    position: absolute;
    width: 50%;
    height: 100%;
    flex: 1;
    display: flex;
    justify-content: center;
    align-items: center;
    transition: all 0.5s ease-in-out;
  }

  .login__container--logo .logo {
    position: relative;
  }

  .login__container--logo .logo::before {
    content: '';
    width: 100%;
    height: 100%;
    background: linear-gradient(90deg, #00c8ff4d 0%, #92FE9D4d 100%);
    position: absolute;
  }

  .login__container--form {
    position: absolute;
    width: 50%;
    height: 100%;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    transition: all 0.5s ease-in-out;
  }

  .login__container--form form {
    width: 100%;
    max-width: 400px;
  }
</style>