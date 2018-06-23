# Automated Discount Codes


## Business Problem  

An abandoned basket email is sent to all customers who drop out of the sales journey during the checkout step (approx 7500 customers per day).  25% (1875) of customers open and read the abandoned basket email but currently less than 2% (38) of those who read the email return to the sales journey to complete their purchase.

The Trading team would like to improve the abandoned basket sales process and encourage customers back to complete their purchase.

## Business Opportunity

The Trading team believe that allowing a customer to return to the basket with the discount applied with a single click will have a significant impact on the number of customers who return to the sales journey.


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

* Automatically Apply Discounts based on the discount code passed within the basket URL  
* Apply dicounts for
   * generic codes i.e. summer10  
   * user specific codes i.e. xw12gould25
   * single use codes

* Update URL generator to allow discount codes to be added to basket URLs
 

### Out of Scope

* Catalogue prices shown within product selection
* The app
* Non UK websites
* My Account journeys


## High-Level Process





## Requirements

|Ref     	|Description           |	User Story     	   |Acceptance Criteria	       |	Notes                 |
|---------|----------------------|---------------------|----------------------------|------------------------|
|ADC001   | Update URL Generator |   As a Campaign Manager, I would like to add a discount code to the URL's I generate, So that i can easily configure the discount URL's |                         |                        |
|ADC002   |  Add URL to email    |                    |                            |                        |
|ADC003   |  Update basket       |                    |                            |                        |
|ADC004   |  Error Handling      |                    |                            |                        |
|ADC005   |  Reporting           |                    |                            |                        |





## Non Functional Requirements

### Volume 

|                           |hourly | Daily | Weekly |Monthly |
|---------------------------|-------|-------|--------|--------|
|Abandoned basket emails    |  n/a  |       |        |        |
|Basket traffic             |       |       |        |        |
|New Orders                 |       |       |        |        |

Thorough integration testng should be performed for each dicount code test from email creation to basket creation but a load test is not required as the additional load from this feature sits comfortably within existing daily tolerances.

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
