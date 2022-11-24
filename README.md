<!DOCTYPE html>
<html lang="ko">
  <head>
    <meta charset="UTF-8">
    <title>2-6</title>
    <link rel="stylesheet" href="style.css">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
  </head>
  <body>
    <section class="login-form">
      <h1>2-6</h1>
      <form action="">
        <div class="int-area">
          <input type="email" id="singUpEmail">
          <label for="email">아이디</label>
        </div>
        <div class = "int-area">
          <input type="password" id="singUpPassword">
          <label for="password">비밀번호</label>
        </div>
      </form>
      <div class="btn-area">
        <button type = "submit" id="signUpButton">회원가입</button>
      </div>
      <div class="caption">
        <a href="">Forgot Password?</a>
      </div>
      <script type="module">

      import { initializeApp } from "https://www.gstatic.com/firebasejs/9.14.0/firebase-app.js";
      import { getAnalytics } from "https://www.gstatic.com/firebasejs/9.14.0/firebase-analytics.js";
      const firebaseConfig = {
        apiKey: "AIzaSyB97L7VYS5ugAN-aXiV01XSoKpoh9HCDuE",
        authDomain: "login-33325.firebaseapp.com",
        projectId: "login-33325",
        storageBucket: "login-33325.appspot.com",
        messagingSenderId: "939793812016",
        appId: "1:939793812016:web:30b0209ffa3d4f61183bf5",
        measurementId: "G-M88XBSCP2N"
      };
      const app = initializeApp(firebaseConfig);
      const analytics = getAnalytics(app);

      import { getAuth, createUserWithEmailAndPassword} from "https://www.gstatic.com/firebasejs/9.14.0/firebase-auth.js";
      document.getElementById('signUpButton').addEventListener('click', (event) => {
        event.preventDefault()
        const auth = getAuth();
        const email = document.getElementById('singUpEmail').value
        const password = document.getElementById('singUpPassword').value
        createUserWithEmailAndPassword(auth, email, password)
          .then((userCredential) => {
            const user = userCredential.user;
          })
          .catch((error) => {
            const errorCode = error.code;
            const errorMessage = error.message;
            // ..
          });
      });
    </script>
    </section>
  </body>
</html>
