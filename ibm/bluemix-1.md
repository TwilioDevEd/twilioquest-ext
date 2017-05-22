IBM Bluemix is a PaaS based on CloudFoundry that you can use to quickly deploy and scale web applications. But what makes Bluemix really awesome is the wide array of built-in services and boilerplate apps you can use to quickly create sophisticated applications for many different use cases.

In the missions to follow, we'll set up and customize an IoT application built on [Node-RED](https://nodered.org/). So first things first - let's get you set up with a Bluemix account and a sample application deployed on it.  Once you've got our boilerplate app deployed on your own account, wave an NPC over to receive your XP and limited edition IBM loot!

### Victory conditions

* Sign up for a Bluemix account
* Successfully deploy the IoT boilerplate app to Bluemix

### Path to victory

For this challenge and the rest to follow, you'll need a Bluemix account. [Sign up to get one here](https://console.ng.bluemix.net/registration/). Once you've signed up for an account, you'll be prompted to set up a "space" - this is a container for related services and applications. For example, you might have "dev", "stage", and "prod" spaces for different versions of your application.

### Deploying the Node RED boilerplate app

Once you've signed up and accessed your dashboard, you can visit the [Catalog](https://console.ng.bluemix.net/catalog/?taxonomyNavigation=cf-apps&category=blueprints) section of the console to view different types of services and applications you can deploy. Sorted under "Boilerplates", you'll find the "Internet of Things Platform Starter".

<img src="https://s3.amazonaws.com/com.twilio.prod.twilio-docs/images/bluemix.original.png" style="width:100%"/>

On the configuration screen that follows, name your application and hit the "Create" button.  In a few moments, you'll be able to visit your application at `https://<app name>.mybluemix.net`.

Visit your application, and you should be greeted with a wizard-style interface to configure your [Node-RED](https://nodered.org/) application.  Configure a username and password combination, and after you're done go to the pre-configured flow editor for this application.

<img src="https://s3.amazonaws.com/com.twilio.prod.twilio-docs/images/bluemix2.original.png" style="width:100%"/>

Once you've gotten to this point, you've earned your XP! Wave an NPC over to show them your progress, and then move on to the next objective in this mission.