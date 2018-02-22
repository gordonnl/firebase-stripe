# Headless Stripe Payments Using Firebase Functions
##The simplest possible payment implementation - applicable to any website.

Implementation of Stripe's Direct Charge payment using all 3 available methods to demonstrate. These include:

 - **Stripe Elements** - pre-built UI components for building checkout flow
 - **Payment Request Button** - supporting Apple Pay, Google Pay and the Payment Request API
 - **Stripe Checkout** - embeddable payment form popup

Firebase Function implemented using a http trigger.

Example code uses Firebase Hosting, but can be hosted anywhere.

Further reading:
 - Stripe Elements Method: https://stripe.com/docs/stripe-js
 - Stripe Payment Request Method: https://stripe.com/docs/stripe-js/elements/payment-request-button
 - Stripe Checkout Method: https://stripe.com/docs/checkout
 - Firebase HTTP Triggers: https://firebase.google.com/docs/functions/http-events

## Front-end Code

See file [public/index.html](public/index.html) for all html and js code.

## Functions Code

See file [functions/index.js](functions/index.js) for the code.

The dependencies are listed in [functions/package.json](functions/package.json).

## Deploy and test

To test this integration:
 - Create a Firebase Project using the [Firebase Developer Console](https://console.firebase.google.com)
 - Enable billing on your project by switching to the Blaze or Flame plan. See [pricing](https://firebase.google.com/pricing/) for more details. This is required to be able to do requests to non-Google services.
 - Install [Firebase CLI Tools](https://github.com/firebase/firebase-tools) if you have not already and log in with `firebase login`.
 - Configure this sample to use your project using `firebase use --add` and select your project.
 - Install dependencies locally by running: `cd functions; npm install; cd -`
 - [Add your Stripe API Secret Key](https://dashboard.stripe.com/account/apikeys) to firebase config:
     ```bash
     firebase functions:config:set stripe.token=<YOUR STRIPE SECRET KEY>
     ```
 - Pass your [Stripe publishable key](https://dashboard.stripe.com/account/apikeys) to the `STRIPE_PUBLIC_KEY` variable in `public/index.html`
 - Deploy your function using `firebase deploy --only functions`
 - Pass your new [Firebase Function URL](https://firebase.google.com/docs/functions/http-events) to the `FIREBASE_FUNCTION` variable in `public/index.html`
 - Deploy your hosting using `firebase deploy --only hosting`
 - Test your Stripe integration by viewing your deployed site `firebase open hosting:site`
