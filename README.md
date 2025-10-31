Deploy to Production/Developer Edition Orgs :

<a href="https://githubsfdeploy.herokuapp.com?owner=findocklabs&repo=fundraising-abandoned-cart-status?tab=readme-ov-file&ref=master">
  <img alt="Deploy to Salesforce"
       src="https://raw.githubusercontent.com/afawcett/githubsfdeploy/master/deploy.png">
</a>

Deploy to Sandboxes :

<a href="https://githubsfdeploy-sandbox.herokuapp.com?owner=findocklabs&repo=fundraising-abandoned-cart-status?tab=readme-ov-file&ref=master">
  <img alt="Deploy to Salesforce"
       src="https://raw.githubusercontent.com/afawcett/githubsfdeploy/master/deploy.png">
</a>

# FinDock for Fundraising: Update Abandoned Gift Transaction 
For organizations using FinDock for Fundraising, when an individual initiates a donation but doesn't follow through with payment, FinDock will have created a Gift Transaction but marked no payment against it, commonly known as an "abandoned cart."  

This Scheduled Flow is one way of handling these incomplete Gift Transactions where daily this Flow will run and identify Gift Transactions initiated by FinDock that have been in "Pending" Status for at least 24 hours (this is the time period Stripe allows before expiring the checkout session), and if so, update the Status to "Canceled" with a note in the Description of "Abandoned Cart"

Consider adding additional automation, such as a follow up email, task, or notification.

Note: this template is designed for donations using Credit Card as a payment method, you may want to consider other time periods for different payment methods as they have varying settlement times.

## Requirements
The prerequisites to deploy this repository are:

- Fundraising enabled and configured in your Salesforce environment
- The FinDock for Fundraising package is installed

## Installation
Ensure your User has permissions to all objects referenced by the components in this repository. This includes FinDock permissions and Fundraising permissions.

1. Press the "Deploy to Salesforce" button at the top of this README and then press "Login to Salesforce" in the top right of your screen. Please note, the GitHub Salesforce Deploy Tool is provided open source by andyinthecloud. No FinDock support is provided.
2. Once deployed, update the criteria on the "getGiftTransactionsPending" element to use the User ID for your FinDock Integration User, which will ensure that this Flow is only triggered on Gift Transactions initiated by FinDock.
3. Review Flow and update as desired before activating.

## Contributing
When contributing to this repository, please first discuss the change you wish to make via an issue or any other method with FinDock before making a change.

## Support
FinDock Labs is a non-supported group in FinDock that releases applications. Despite the name, assistance for any of these applications is not provided by FinDock Support because they are not officially supported features. For a list of these apps, visit the FinDock Labs account on Github.

## License
This project is licensed under the MIT License - see the [LICENSE](https://github.com/ashley-findock/fundraising-abandoned-cart/blob/master/LICENSE) file for details
