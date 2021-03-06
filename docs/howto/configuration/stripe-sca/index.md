## Enable Strong Customer Authentication with Stripe

[SCA](https://stripe.com/docs/strong-customer-authentication) is a new rule coming into effect on September 14th, 2019 in Europe.

Alf.io supports this regulation by using the new Payment Intent API, see [#593](https://github.com/alfio-event/alf.io/issues/593)

In order to enable it, you've to specify a couple of additional options in your configuration:

### Configure Stripe for Strong Customer Authentication (SCA)

- Go to the [Webhook configuration page](https://dashboard.stripe.com/webhooks)
- Create an endpoint by clicking on "Add Endpoint"

![](img/add-endpoint.png)
*If Platform Mode is enabled, you might want to add an endpoint for connected accounts instead.*

- Fill in the details, as shown by the following screenshot:

![](img/add-endpoint-detail.png)

- Once the webhook has been created, you must copy the Signing Secret, which will allow Alf.io to verify the sender of the webhooks

![](img/secret.png)

### Enable SCA on Alf.io

The final step is to enable SCA on your instance and configure the secret. 

Head to the configuration and set the following options:

- Strong Customer Authentication enabled 
- Payment Webhook signing secret


![](img/alfio-configuration.png)

and then you'll be ready to collect payments in a SCA-compliant way.