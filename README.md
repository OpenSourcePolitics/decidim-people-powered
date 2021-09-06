# Decidim app by OSP

Citizen Participation and Open Government application.

## Setting up the application

You will need to do some steps before having the app working properly once you've deployed it:

1. Open a Rails console in the server: `bundle exec rails console`
2. Create a System Admin user:
```ruby
email = <your email>
password = <a secure password>
user = Decidim::System::Admin.new(email: email, password: password, password_confirmation: password)
user.save!
```
3. Visit `<your app url>/system` and login with your system admin credentials
4. Create a new organization. Check the locales you want to use for that organization, and select a default locale.
5. Set the correct default host for the organization, otherwise the app will not work properly. Note that you need to include any subdomain you might be using.
6. Fill the rest of the form and submit it.

You're good to go!

## Machine translation configuration

Machine translation is configured through the provider [DeepL](https://www.deepl.com) by using the gem https://github.com/wikiti/deepl-rb.

In order to make it work these ENV variables need to be configured:

```
TRANSLATOR_API_KEY=*******
TRANSLATOR_HOST=https://api-free.deepl.com
```

- Obtain the `TRANSLATOR_API_KEY` by creating an account at https://www.deepl.com/pro#developer
- For `TRANSLATOR_HOST`, set it to `https://api-free.deepl.com` if using the "DeeL API Free" plan. If using the "DeepL API Pro", then set it to `https://api.deepl.com`

> Note: you still need to enable machine translation at the organization settings.
