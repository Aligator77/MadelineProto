# Logging in

There are many ways you can login with MadelineProto.

* [Automatic](#automatic)
* [Manual (user)](#manual-user)
* [Manual (bot)](#manual-bot)
* [Logout](#logout)

## Automatic

```
$MadelineProto->start();
```

This will start an interactive login prompt via console (if running via CLI), or a login web UI (if running in the browser).  
You will get to choose if login as user, or as bot.


## Manual (user)

```
MadelineProto->phone_login(readline('Enter your phone number: '));
$authorization = $MadelineProto->complete_phone_login(readline('Enter the phone code: '));
if ($authorization['_'] === 'account.password') {
    $authorization = $MadelineProto->complete_2fa_login(readline('Please enter your password (hint '.$authorization['hint'].'): '));
}
if ($authorization['_'] === 'account.needSignup') {
    $authorization = $MadelineProto->complete_signup(readline('Please enter your first name: '), readline('Please enter your last name (can be empty): '));
}
```

First, you must call `phone_login` to send the verification code, see [here for the parameters and the result](https://docs.madelineproto.xyz/phone_login.html).  
Then, use `complete_phone_login` to complete the login, see [here for the parameters and the result](https://docs.madelineproto.xyz/complete_phone_login.html).  

Use `complete_2FA_login` to complete the login to an account with 2FA enabled, see [here for the parameters and the result](https://docs.madelineproto.xyz/complete_2FA_login.html).    

If the account does not have an account, use `complete_signup` to signup, see [here for the parameters and the result](https://docs.madelineproto.xyz/complete_signup.html).  


## Manual (bot)

```
$MadelineProto->bot_login('34298141894:aflknsaflknLKNFS');
```

Use `bot_login` to login as a bot, see [here for the parameters and the result](https://docs.madelineproto.xyz/bot_login.html).  

Note that when you login as a bot, MadelineProto also logins using the [PWRTelegram](https://pwrtelegram.xyz) API, to allow persistant storage of peers, even after a logout and another login.  


## Logout

```
$MadelineProto->logout();
```

Use `logout` to logout, see [here for the parameters and the result](https://docs.madelineproto.xyz/logout.html).  


