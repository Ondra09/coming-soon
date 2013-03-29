coming-soon
===========

A simple landing page email collector, but with 90% more parentheses than the leading brand.

What coming-soon is
-------------------

**coming-soon** is a simple Clojure/ClojureScript/Redis powered "landing page" application that takes just a few minute to setup. With coming-soon you can quickly put up a page to publicize your new idea and collect email addresses of people who want to be notified when you are ready to launch.

![Silver Bullet Example](http://coming-soon-resources.s3.amazonaws.com/coming-soon-example.png)

(Here is the [configuration file](https://github.com/SnootyMonkey/coming-soon/blob/master/examples/silver_bullet/config.edn) for the Silver Bullet example.)

coming-soon is inspired by the Ruby app [LandingPad.rb](https://github.com/swanson/LandingPad.rb) by [Matt Swanson](https://github.com/swanson).

What coming-soon can do
-----------------------

Some of the Fantastic Features:

* Captures: email, when they signed up, and what website they came from
* All the text on the landing page can be configured in a simple config file
* Many of the styles can be configured as well using the same config file
* User defined fonts, logo and background image using, you guessed it, the same file
* Google Analytics is supported as a setting, so you can track views and conversion rates for signing up
* Twitter, Facebook, GitHub and blog links are supported as a setting in the config file
* Go beyond the config file and change all the HTML and CSS to put whatever you'd like on the page
* The CSS is Twitter Bootstrap
* All the third-party resources are hosted on a [CDN](http://en.wikipedia.org/wiki/Content_delivery_network)
* coming-soon makes no attempt to promote itself on your page... that's just tacky
* There's no code that's not Clojure or ClojureScript, so... there's that

Why you should use coming-soon
------------------------------

It's very simple and very free (as in, there is no cost). Edit the config file. Deploy to Heroku for free. Then get on with building your app. It's even faster than using many of the software as a service options.

As an example, the above landing page and the following landing pages were configured using just the configuration file with no custom HTML, CSS or coding.

[![Falklandsophile Example](http://coming-soon-resources.s3.amazonaws.com/coming-soon-example2-small.png)](http://coming-soon-resources.s3.amazonaws.com/coming-soon-example2-full.png)

(Here is the [configuration file](https://github.com/SnootyMonkey/coming-soon/blob/master/examples/falklandsophile/config.edn) for the Falklandsophile example.)

[![IdeaFerret Example](http://coming-soon-resources.s3.amazonaws.com/coming-soon-example3-small.png)](http://coming-soon-resources.s3.amazonaws.com/coming-soon-example3-full.png)

(Here is the [configuration file](https://github.com/SnootyMonkey/coming-soon/blob/master/examples/ideaferret/config.edn) for the IdeaFerret example.)

It's also very free (as in, free to do whatever you like with it), so if it only does 80% of what you want, and you prefer to do the other 20% in Clojure/ClojureScript, it's probably for you. 

Or if you want to go nuts on the templates and build some truly custom HTML and CSS for your landing page, then you have that option. You aren't locked into off-the-shelf templates or WYSIWYG editors or limited customization options like you are with many of the software as a service landing pages.

Here is the same landing page with just some simple [custom CSS](https://github.com/SnootyMonkey/coming-soon/blob/master/examples/ideaferret/css/custom.css).

[![IdeaFerret Custom Example](http://coming-soon-resources.s3.amazonaws.com/coming-soon-example4-small.png)](http://coming-soon-resources.s3.amazonaws.com/coming-soon-example4-full.png)

Why you should NOT use coming-soon
----------------------------------

Can you answer the question, "Why do you want to host your own landing page (even if Heroku is doing the hosting for you) with open source software rather than using a landing page service?"

If you don't have a great answer to that question, then there are **lots** of fully hosted alternatives for landing pages, it's a crowded space for these services, so there is likely a better option for you in this list:

* [Launch Rock](http://launchrock.co/) - the granddaddy of launch page services, tries to get users to share
* [Unbounce](http://unbounce.com) - lots of templates, A/B testing, drag n' drop WYSIWYG, on the expensive side
* [Strikingly](https://www.strikingly.com/) - for small general websites, but has email capture
* [Kickofflabs](http://www.kickofflabs.com/) - fairly comprehensive, widgets for external integrations, email campaigns
* [My Beta List](http://my.betali.st/) - also focused on user sharing
* [Launch Effect](http://launcheffectapp.com/) - Wordpress theme
* [Prefinery](http://www.prefinery.com/) - fairly comprehensive beta management, invite codes, viral sharing, feedback and surveys
* [ooomf](http://ooomf.com) - for mobile apps
* [LaunchGator](http://launch.deskgator.com/)
* [Mailchimp](http://mailchimp.com) - you probably think of them as the email list back end only, but they can serve up the email capture page too
	
What you need to have to use it
-------------------------------

coming-soon can be hosted on [Heroku](http://heroku.com) for free. Once you update the settings, just deploy it to Heroku and point a domain at it. That's all there is to it. You are then in business, and can get back to hacking on your app so that you have something to launch and send to all those email addresses you're collecting!

Quick Start - 10 Minutes to Heroku
----------------------------------

1. Follow the [Getting Started with Heroku](https://devcenter.heroku.com/articles/quickstart) quick start steps to setup your free and instant account and the heroku toolbelt on your local machine.

2. Download coming-soon:

	[https://github.com/SnootyMonkey/coming-soon/archive/master.zip]()

	Unzip coming-soon and navigate to the directory it creates:

```console
unzip coming-soon
cd coming-soon
```

3. Open the file called 'config.edn' in a text editor. You should see a 'coming-soon' block where you can enter admin access details, and a 'landing-page' block where you can configure the appearance of the landing page (your site's name, a summary, colors, background, etc).

	The 'coming-soon' block is where you set the admin username and password for accessing your stored contacts -- **PLEASE CHANGE THIS!**

	You can set your Google Analytics tracking id in the 'landing-page' block if you have an account.

	Replace the logo file resources/public/img/logo.png with your own logo or edit the config file to include an empty string "" rather than "/img/logo.png".

4. Once you have edited 'config.edn' to add your app's settings, run the following commands in your coming-soon folder to create a [git](http://git-scm.com/) repository out of your files:

```console
git init
git add .
git commit -m "Setting up my landing page."
```

5. Now create your Heroku app by running from your project folder:

```console
heroku login
```

	Provide the email and password you used when creating your account when prompted.

```console
heroku create
```

6. Attach a free redis instance to your app. As of this writing, there are 3 options for free redis on Heroku.

	To use [MyRedis](https://addons.heroku.com/myredis), run this command:

```console
heroku addons:add myredis:gratis
```

	To use [Redis To Go](https://addons.heroku.com/redistogo), run this command:

```console
heroku addons:add redistogo:nano
```

	To use [Redis Cloud](https://addons.heroku.com/rediscloud), run this command:

```console
heroku addons:add rediscloud:20
```

	In your text editor comment in the :redis-env-variable line in the :redis section of the 'config.edn' file that matches the Redis provider you selected. Then commit your change to git.

```console
git add .
git commit -m "Selecting my redis provider."
```

7. Now push the code of your app up to the Heroku cloud.

```console
git push heroku master
```

8. Now test out your landing page. 

	Launch your app in your browser.

```console
heroku open
```

	This will open a browser and you should see your landing page. Note the ugly URL Heroku created for you so you can get back to your page.

	Now test redis connectivity by adding /redis-test to your browser's URL after the URL for your app on heroku

	For instance, if you app is **http://your-heroku-machine-name.heroku.com/** then you should load **http://your-heroku-machine-name.heroku.com/redis-test**

	You should see: "Connection to Redis is: OK"

	Go back to your landing page by removing the /redis-test from the URL and enter in your email address to signup for your own app.

	To view the contact information that's been entered into your landing page, navigate to **http://your-heroku-machine-name.heroku.com/contacts**.  You will need to enter the admin username and password that you setup in 'config.edn'.  

	You should see a table listing the name, type and referral URL for everyone that has signed up for your app.

	![](http://coming-soon-resources.s3.amazonaws.com/coming-soon-admin.png)

9.  Next, you will probably want a custom domain rather than Heroku's default. Follow [Heroku's instructions](http://devcenter.heroku.com/articles/custom-domains) to setup your domain to point to your brand-new landing page.

10. Now get back to coding your app!

Guide to the configuration file
-------------------------------

(todo list and explain the configuration settings)

It looks good, but I want it to be more blue
--------------------------------------------

You can modify any of the HTML, CSS and images to customize your page. Just remember, you need to push any changes to Heroku so your live page will be updated.

(todo list and explain HTML and CSS)

(todo list all the significant IDs and classes in the HTML)

It works well, but I want it to make my coffee too
--------------------------------------------------

You can modify any of the Clojure and ClojureScript code to customize the behavior of your landing page. Just remember, you need to push any changes to Heroku so your live page will be updated.

(todo list and explain important code and development steps)

lein ring server-headless
lein cljsbuild once
lein cljsbuild auto

Other Frequently Asked Questions
--------------------------------

**Q:** Why is it so slow to load the landing page sometimes?
**A:** Unless you are paying Heroku to host at least 2 dynos for you, you are subject to [idling](https://devcenter.heroku.com/articles/dynos#dyno-idling). This means that after an hour, your app will be spun down to save resources. The next unlucky sole to access your landing page will have to wait for 10 seconds or so for your app to spin back up. You can solve this by paying Heroku for 2 web dynos or by using a server monitoring service that pings your landing page more frequently than once an hour.

**Q:** Who made this treasure?
**A:** coming-soon is written by Sean Johnson, the founder of [Snooty Monkey](http://snootymonkey.com).

**Q:** How can I ever repay you for creating such a treasure?
**A:** It's not required by the license terms, but please [drop me a note](http://snootmonkey.com/contact.html) and let me know the URL of your landing page so I can take a look.

**Q:** Can I use it for X?
**A:** coming-soon is licensed with the [MIT license](https://github.com/SnootyMonkey/coming-soon/blob/master/MIT-LICENSE.txt), so you are free to use it pretty much however you'd like, in accordance with the license terms.
 
**Q:** Can I add X to it?
**A:** Sure, please fork coming-soon on GitHub if you'd like to enhance it.

**Q:** Can I contribute my enhancements back to the project?
**A:** Sure, send me your pull requests if you'd like to contribute back your enhancements. I promise to look at every pull request and incorporate it, or at least provide feedback on why if I won't.

Links
-----
* [GitHub Project](http://github.com/SnootyMonkey/coming-soon)
* [Issue Tracker](http://github.com/SnootyMonkey/coming-soon/issues)
* [Live Demo Example](http://polar-waters-1973.herokuapp.com)