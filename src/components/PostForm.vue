<template>
  <form method="#" action="">
    <div class="center">
      <h1>Login</h1>
      <div class="txt_field">
        <input type="text" required v-model="loginForm.name">
        <label>Name</label>
      </div>
      <div class="txt_field">
        <input type="text" required v-model="loginForm.phone">
        <label>Phone (вводите с 8)</label>
      </div>
      <div class="txt_field">
        <input type="text" required v-model="loginForm.email">
        <label>Email</label>
      </div>
      <button type="submit" @click.prevent="sendData">Authorize</button>
    </div>
  </form>
</template>

<script setup>
import {reactive} from "vue";
import axios from "axios";

const loginForm = reactive({
  name: '',
  phone: '',
  email: '',
})

const isFormValid = () => {
  let count = 0;
  let isValid = false;


  if (loginForm.name.length < 4) {
   alert("имя слишком короткое")
  } else {
    count += 1
  }
  if (loginForm.name.length >= 15) {
   alert("имя слишком большое")
  } else {
    count += 1
  }
  if (loginForm.phone.length <= 5) {
   alert("номер телефона очень маленький")
  } else {
    count += 1
  }
  if (loginForm.phone.length > 11) {
   alert("номер телефона слишком большой")
  } else {
    count += 1
  }
  return count === 4;

}

const sendData = () => {
  if (isFormValid() === true) {
    axios.post('http://127.0.0.1/api/users', loginForm);
  } else {
    console.log('not');
  }
}




</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Noto+Sans:wght@700&family=Poppins:wght@400;500;600&display=swap');

label {
  color: #adadad;
}

.center {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: 400px;
  background: white;
  border-radius: 10px;
  box-shadow: 10px 10px 15px rgba(0, 0, 0, 0.05);
}

.center h1 {
  text-align: center;
  padding: 20px 0;
  border-bottom: 1px solid silver;
}

.center form {
  padding: 0 40px;
  box-sizing: border-box;
}

form .txt_field {
  position: relative;
  border-bottom: 2px solid #adadad;
  margin: 30px 0;
}

.txt_field input {
  width: 100%;
  padding: 0 5px;
  height: 40px;
  font-size: 16px;
  border: none;
  background: none;
  outline: none;
}

.txt_field label {
  position: absolute;
  top: 50%;
  left: 5px;
  color: #adadad;
  transform: translateY(-50%);
  font-size: 16px;
  pointer-events: none;
  transition: .5s;
}

.txt_field input:focus ~ label,
.txt_field input:valid ~ label {
  top: -5px;
  color: #2691d9;
}

button[type="submit"] {
  width: 100%;
  height: 50px;
  border: 1px solid;
  background: #2691d9;
  border-radius: 10px;
  font-size: 18px;
  color: #e9f4fb;
  font-weight: 700;
  cursor: pointer;
  outline: none;
}

</style>