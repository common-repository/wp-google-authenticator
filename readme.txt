=== Authenticator for WordPress ===
Contributors: julien731
Donate link: https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=E9SPA3AV3J364
Tags: security,authenticator,2-factor,authentication,2fa,google,app,google,authy
Requires at least: 3.0
Tested up to: 5.7.1
Stable tag: 1.1.1
License: GPLv2 or later
License URI: http://www.gnu.org/licenses/gpl-2.0.html

Adds 2-factor authentication to your site. Use Google Authenticator or Authy for enforced security.

== Description ==

If you are concerned about security, you should look into 2-factor authentication.

*Quick reminder:* 2-factor authentication adds an extra layer of security by requesting a one time password in addition to standard username / password credentials.

[Download the Google Authenticator app](https://support.google.com/accounts/answer/1066447?hl=en) or [Authy](https://www.authy.com/) on your phone (iPhone, Android or Blackberry). Install this plugin on your site. After activating it and generating a secret key, you will be able to add the site to your app by scanning a QR code. That's it!

The QR code is generated with Google Charts API using HTTPS to avoid security issues while sending your secret for generation.

= What the Plugin Does =
- Adds 2-factor authentication to WordPress login page,
- Can be eanbled for each user independantly,
- Admin can force users to use 2FA (and limit the number of allowed logins without setting up 2FA). The use of 2FA can be forced for all users or for specific roles,
- Support applications passwords (with access log),
- If admin forces users to use 2FA, users who didn't set it up will be reminded with a warning in their dashboard,
- Set any name you want to appear in the Google Authenticator app,
- Allow clock discrepancy (mins +/-),
- Users can generate a new secret key anytime,
- Admin can revoke any user's key at anytime,
- If a user is locked-out after logging-in too many times without using 2FA, admin can reset the counter,
- Used one time passwords are hashed and stored in the DB to avoid multiple use (in case of interception by an attacker)
- Recovery code in case the user can't use the app

= Using Authy =

You're using [Authy](https://www.authy.com/)? Google Authenticator for WordPress is fully compatible with Authy. You can add the 2-steps authentication and use Authy to generate the one time password.

== Installation ==

1. Upload `wp-google-authenticator` folder to the `/wp-content/plugins/` directory
2. Activate the plugin through the 'Plugins' menu in WordPress
3. Activate, generate your secret, scann the QR code with your phone

Setup tutorial [available here](http://julienliabeuf.com/wordpres-2-factor-authentication/).

== Frequently asked questions ==

= How can I use the WordPress mobile app? =

Since version 1.1.0, the plugin supports applications password. Go to your profile and you'll find a new menu item called "My Apps Passwords". From here you can create application specific passwords.

= I'm using Authy, does this plugin work? =

Yes it does. You might have noticed that Authy has a dedicated WordPress plugin available on the Extend, but WP Google Authenticator is more powerful and fully functional with Authy. You can safely keep or start using WP Google Authenticator in combination to using Authy on your phone.

= I just updated to 1.0.4: how do I get a recovery code? =

If you just updated the plugin to version 1.0.4 (which introduces recovery code feature), you need to go to your profile page and hit the save button. This will generate a new recovery code. You will see this code in clear for 5 minutes in your profile page. After that, you will be required to type your password to show the code.

= What if a user is unable to generate his TOTP (phone lost, stolen, reset...)? =

The user can use his recovery code to disable 2FA for his account. Alternatively, an admin can edit the user's profile and revoke his secret. The user will then be able to login again and re-generate a secret.

== Screenshots ==

1. Plugin settings
2. Edit profile screen
3. Admin view of the user edit screen
4. Applications Passwords

== Changelog ==

= 1.1.1 =

* Fix an issue with the settings page not showing up
* Contextual help deprecated bug
* Remove mentions of Google in the plugin name chore

= 1.1.0 =
* Add support for apps passwords
* Admins can now force 2FA by user role
* Add Finnish translation (props [Makke375](https://wordpress.org/support/profile/makke375))
* Improve performance by reducing plugin footprint
* Fix the bug that allowed users to login 1 more time after they reached the limit when they don't have 2FA setup yet

= 1.0.8 =
* When a user set his personnal secret the login count is reset.

= 1.0.7 =
* Add cron task to clean TOTPs list from DB

= 1.0.6 =
* Fix issue with spaces in site name (jeremyawhite)

= 1.0.5 =
* Add issuer to the Google Authenticator account

= 1.0.4 =
* Add recovery code feature
* Update translations

= 1.0.3 =
* Add support for WordPress Android / iPhone app
* Add French translation

= 1.0.2 =
* Update version number
* Remove double confirmation message after saving options
* Update option label and disable TOTP if plugin is not set to Active

= 1.0.1 =
* Only push the trunk

= 1.0.0 =
* First release of the plugin
