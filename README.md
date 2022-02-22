# Stripe Payment Element in ASP.NET &amp; C# - Accept One-Time &amp; Recurring Payments
Accept payment methods from around the globe with a single secure, embeddable UI component. This guide walks you through how to get one-time payments and sell fixed-price subscriptions and provides an example of a well-working integration. Using the codes and documentation in this example, you can customize it according to your needs and integrate it into your own application. You will use Stripe Elements to create a custom payment form that you embed in your app.

Live Demo: https://techtolia.com/Stripe/New/

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/s48q3l7iig0s9sorcmnk.PNG)

Learn how to embed a custom Stripe payment form in your website or application. The client-side and server-side code builds a checkout form with Elements to complete a payment using various payment methods.

The Payment Element is an embeddable UI component that lets you accept up to 18+ payment methods with a single integration. Whether you’re just collecting card payments or dozens of payment methods, the Payment Element is the easiest way to build an embedded and customized payments experience.
- Automatically adjusts input fields to collect information based on the payment method and country.
- Dynamically sorts payment methods based on a customer’s locale and location to optimize for conversion.
- Reduces friction for card payments with input validation, masking, styling and error handling.
- Adds new payment methods without any front-end changes, and gives you access to new payment methods as soon as Stripe supports them.

### What are the core features of Payment Element?
With Payment Element, Stripe is launching a new generation of Elements (see: https://stripe.com/payments/elements) Previous to the Payment Element, merchants would need to build and maintain a new integration for each separate payment method. Because this is no longer necessary, you would save significant time and resources by utilizing the Payment Element.

See some core features of Payment Element below:
- Support for multiple payment methods via a single Elements integration
- It surfaces relevant payment options to each buyer through sorting logic based on customer country location (derived from IP address) and preferred language (derived from browser locale)
- It is localized for 42 locales: https://stripe.com/docs/js/appendix/supported_locales
- It can be styled to merchant brand (font, colors, spacing, etc.)
- It is mobile responsive
- It has in-built input validations
- It is PCI-DSS Compliant

### Apple Pay and Google Pay
You can offer these payment methods on their associated platforms when you pass the card type.

For most users, the Payment Element is the best option to process cards. The integration effort is the same as the Card Element and it supports all the common payment flows. It also gives you instant access to additional payment methods, including Google Pay and Apple Pay.

### How do I use the Payment Element to offer all the payment methods Stripe supports?
To use the Payment Element to offer all the payment methods Stripe supports, you can pass an array of payment methods to payment_method_types when you create a PaymentIntent. However, you can’t pass all supported payment methods at the same time because some payment methods require different currencies. You can only create a PaymentIntent with payment methods that support the same currency. Please see the Payment method and product support table here: https://stripe.com/docs/payments/payment-methods/integration-options

### Configure payment methods
With automatic_payment_methods enabled, Stripe automatically detects the payment methods relevant to your customer. Card payments are enabled by default but you can enable and disable other payment methods in the Stripe Dashboard. Before the payment form is displayed, Stripe evaluates the currency, payment method restrictions, and other parameters to determine the list of supported payment methods. Payment methods that increase conversion and that are most relevant to the currency and customer’s location are prioritized. Lower priority payment methods are hidden beneath an overflow menu.

### What is Strong Customer Authentication?
Strong Customer Authentication (SCA) is a new European regulatory requirement to reduce fraud and make online payments more secure. To accept payments and meet SCA requirements, you need to build additional authentication into your checkout flow.

Banks will need to start declining payments that require SCA and don’t meet these criteria. Although the regulation was introduced on 14 September 2019, we expect these requirements to be enforced by regulators over the course of 2020 and 2021.

3D Secure 2—the new version of the authentication protocol rolling out in 2019—will be the main method for authenticating online card payments and meeting the new SCA requirements. This new version introduces a better user experience that will help minimise some of the friction that authentication adds into the checkout flow.

The application supports 3D Secure 2

The Payment Intents API that uses Stripe’s SCA logic to apply the right exemption and trigger 3D Secure when necessary.

The application uses the Payment Intents API
