---
title: Login Example
layout: default
---
# An Example
## Using the login page
Login parts:
login.html
app/components/login-form/template.hbs
app/components/login-form/component.js
app/login/template.hbs
app/login/route.js


The look of the form was developed by Michal using HTML while Amber worked on making the login worked.

### The look and its code
![GitHub](./images/login.png)

### login.html
<!--
<head>
<title>KUB Login Form</title>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
</head>

<body>
  <div class="container">

    <div class="row" >
      <div class="col-md-4"></div>

      <div class="col-md-4">
        <section class="login-form">
          <form method="post" action="#" role="login">
            <img src="../assets/images/kub.png" height="100" width="100" class="img-responsive" alt="" />
            <input type="email" name="email" placeholder="Email" required class="form-control input-lg"  />

            <!-- Amber div tag -->
            <div> </div>

            <input type="password" class="form-control input-lg"  placeholder="Password" required="" />


            <div class="pwstrength_viewport_progress"></div>


            <button type="submit" name="go" class="btn btn-lg btn-primary btn-block">Sign in</button>
            <div>
              <a href="#">Forgot password ?</a>
            </div>

            <div>
              <a href="#">Contact administrator</a>
            </div>
          </form>

          <div class="form-links">
            <a href="#">www.kub.com</a>
          </div>
        </section>
        </div>

        <div class="col-md-4"></div>


    </div>
  </div>
</body>
-->
### app/components/login-form/template.hbs
<div class="container">

  <div class="row" >
    <div class="col-md-4"></div>

    <div class="col-md-4">
      <section class="login-form">
        <form method="post" action="#" role="login">
          <img src="../assets/images/kub.png" height="100" width="100" class="img-responsive" alt="" />
          <!-- Amber div tag -->
          <div> </div>
          {{input type="email" value = userEmail placeholder="Email" required=true class="form-control input-lg"  }}

          {{input type="password" value = userPassword class="form-control input-lg"  placeholder="Password" required="star symbol" }}

          <div class="pwstrength_viewport_progress"></div>

          <button {{action 'login'}} class="btn btn-lg btn-primary btn-block">Sign in</button>
          <div>
            <a href="#">Forgot password?</a>
          </div>
          <br>
          <div>
            <a href="#">Contact administrator</a>
          </div>
        </form>

        <div class="form-links">
          <a href="https://www.kub.org">www.kub.org</a>
        </div>
      </section>
      </div>

      <div class="col-md-4"></div>

  </div>
</div>

### app/components/login-form/component.js

import Ember from 'ember';

export default Ember.Component.extend({

    actions: {
      login() {

        this.sendAction('login', this.get('userEmail'), this.get('userPassword'));

      },

      forgotPassword() {
        this.sendAction('forgotPassword');
      }
    }
});
### app/login/template.hbs
{{login-form login="login" forgotPassword="forgotPassword"}}
### app/login/route.js
import Ember from 'ember';

export default Ember.Route.extend({

  redirect() {
    if (this.get('session.isAuthenticated')) {
      this.transitionTo('protected');
    }
  },

  actions: {

    login(email, password) {
      let session = this.get('session');
      session.open('firebase', {
        provider: 'password',
        email,
        password

      }).then(() => {

        let user = session.content.currentUser;
        let email = user.email;
        let username = email.substring(0, email.indexOf('@'));
        user.username = username;
        this.set('currentUser.content', user);
        this.transitionTo('protected');

      });
    },

    forgotPassword() {
      this.transitionTo('password-reset');
    }
  }

});
