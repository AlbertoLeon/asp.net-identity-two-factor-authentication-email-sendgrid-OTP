# ASP.NET Identity Two Factor Auhtentication Email Sendgrid OTP
A modification for the ASP.NET CORE Identity Razor Pages Scaffolding for using Email with Sendrid as Sender as two factor authentication with the OTP


## The main changes from the default Scaffolding are:
### Path ~\Areas\Identity\Pages\Account\LoginWith2fa.cshtml.cs
method OnGetAsync
* Generates the new OTP
* Remove previous stored OTP
* Save / Set the new one
* Send it by email

method OnPostAsync
* Replace the call to TwoFactorAuthenticatorSignInAsync for TwoFactorSignInAsync where you can inform you will use TokenOptions.DefaultEmailProvider

### Notes
This is not an elegant solution because several aspects:
* It invalidates the Authenticar App Solution that Microsoft brings to us by default of setting an Authenticator.
* The OTP is saved in plain text, It should be saved encrypted and encrypt the code informed by the user to comparision.
* This repository is just reflecting a PoC as research purpose, don't use it in production without caring of this notes.
