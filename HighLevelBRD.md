# Automated Offer Codes


## Business Problem  

An abandoned basket email is sent to all customers who drop out of the sales journey during the checkout step (approx 7500 customers per day).  25% (1875) of customers open and read the abandoned basket email but currently less than 2% (38) of those who read the email return to the sales journey to complete their purchase.

The trading team would like to improve the abandoned basket sales process and encourage customers back to complete their purchase.


## Business Opportunity

The trading team believe that allowing a customer to return to the basket with an offer applied with a single click will have a significant impact on the number of customers who return to the sales journey to complete their purchase.

The automatic offer codes may be used within other marketing emails and online journeys but the abandoned basket customers have been flagged as a key opportunity.


## Business Outcome

The trading team expect at least 10% (188) of customers to return to the sales journey if the email is improved.


## Measurement Criteria

* Basket visits increase for sales journey entry type 'abandonEmail'  
* Conversion rate increase by 300% for sales journey entry type 'abandonEmail' 


## Key Stakeholders

| Role               | Name                         | Reviewed |
|--------------------|------------------------------|----------|
| Business Sponsor   |                              |          |
| Marketing Manager  |                              |          |
| Trading Manager    |                              |          |
| Campaign Manager   |                              |          |
| Project Manager    |                              |          |
| UX/ Design         |                              |          |
| Tech Lead          |                              |          |
| DBA                |                              |          |
| Test Lead          |                              |          |
| Analytics          |                              |          |
| Customer Support   |                              |          |


## Scope


### In Scope

* Apply an offer in the basket based on the offer code passed within the basket URL  
* Apply offers for
   * generic codes i.e. summer10  
   * user specific codes i.e. xw12gould25
   * single use codes
   * multiple use codes
* Update the abandoned basket email template to include the URL link button
* Update URL generator to allow offer codes to be added to basket deeplink URLs


### Out of Scope

* The catalogue prices shown within product selection will not be updated
* The offer URL will not open or be accessible within the sales app
* The offer URL will not work for non UK sites as part of this implementation
* My Account journeys will not be updated as part of this implementation


## High-Level Process


![discount flow](https://user-images.githubusercontent.com/40513613/41807383-5f56d552-76c6-11e8-9d6a-1d2608fd84cb.png)


### Pre Condition

Customers who dropped out of the sales journey during checkout will recieve an abandoned basket email which includes an offer.


### Post Condition

Customers who return to the basket with the offer applied may continue and complete their order.


### Steps

1. Recieve Abandoned Basket Email - Customers will recieve an email offering them the chance to complete their order with a special offer.
2. Select Link - Customers should be able to select a 'Buy Now' button which will deeplink them to a pre-populated basket with the offer. Example link https://www.sky.com/shop/mobile/basket-summary/?14210&14518&14677&offer=iPhoneX-wk49
3. View Basket - Customers should see the basket with the option to proceed to checkout



### Exceptions

The basket will not load in the following scenarios:

1. Link not valid - The website may not load and a generic browser 'page not found' message will appear.
2. Products not valid or no longer available - If the selected products are no longer in the catalogue or are out of stock the basket page will be displayed along with the appropiate message.
3. Offer not valid or no longer available - If the offer has expired or is no longer available the basket page should be displayed with the appropriate message.


## Requirements

|Ref     	|Description                |	User Story     	    |Acceptance Criteria	       |	Size                  |
|---------|---------------------------|---------------------|----------------------------|------------------------|
|AOC001   | Update the email template |As an email customer, I would like to view the 'Buy Now' link, So that I can easily resume my purchase journey|- Update email wording       - Add link field         - Add button |  X Small                    |
|AOC002   | Update the URL generator  |As a campaign manager, I would like to add an offer code to a basket deeplink, So that I can construct the URL |-Return valid offer codes within URL generator - Allow upto 1 offer code to be optionally appended to URL's| Medium (Requires new API call)  |
|AOC003   | Apply basket offer        |As an email customer, I would like to view the basket with the offer applied, So that I can see the correct price |- Submit offer code from the URL - Display offer price - Display offer styling - Display offer T&C's| Small (No changes required to offer styling, messaging or T&C's)|
|AOC004   | Products not available    |As an email customer, I would like to see a message if the basket doesn't load, So that I understand what to do next|- Display standard 'Ooops' message - Display a link back to the homepage|Small (No changes required, test only)|
|AOC005   | Products out of stock     |As an email customer, I would like to see an 'out of stock' status, So that I know when I can place my order| -Display basket with offer applied -Show stock state -Display delivery expectations |X Small (No changes required, test only) |
|AOC006   | Invalid offer code     |As an email customer, I would like to see an invalid offer message, So that I understand why the offer isn't applied|- Display basket without offer - Show expired offer code message|  Small (No changes required, test only) |
|AOC007   | Reporting                 | As a business owner, I would like to see the results of the change, So that I know how successful the journey is |- Add Abandoned basket sales report to the sales dashboard -Show: emails sent, emails opened, links clicked, baskets viewed and Orders Placed | X Small (No new tracking events required, dashboard config only) |


## Non Functional Requirements


### Volume 

|                           |Hourly | Daily | Weekly |Monthly |
|---------------------------|-------|-------|--------|--------|
|Abandoned basket emails    |  n/a  | 7,500 | 55,000 | 210,000|
|Basket traffic             |  30   | 180   | 1400   | 5250   |
|New orders                 |  9    | 54    | 420    | 1575   |

Notes:

Hourly assumes most customers will visit the website within 6 hours of recieving the email.  
Basket traffic assumes a 10% click through rate of the 25% who read the email.  
New orders assumes a 30% conversion rate.


Suggestion:

Thorough integration testng should be performed for each dicount code type from URL generation to email creation to basket creation. A load test is not required as the additional load from this feature sits comfortably within existing daily tolerances.


### Speed

The basket page should load with the discounted prices in less than 0.2 seconds, there should be no percieved wait time for the user.


### Security

Existing security best practices should be applied and considered when generating and sending emails.


## Assumptions

* No changes are required to the way discount codes are currently set up and managed within ref data
* No changes are required to the way discounts are currently displayed within the basket
* Existing error messages will be used
* Marketing may use the dicount deeplinks in other scenarios such as landing page promo's, PPC or display ads
* No changes are required to existing reporting for entry types


## Risks and Issues

* Existing invalid basket messages may not work as expected so some investigation and additional work maybe required to update basket messages.
