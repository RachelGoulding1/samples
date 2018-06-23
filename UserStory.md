**User Story**

As an email customer
I would like to view the basket with the offer applied   
So that I can see the correct price


**Acceptance Criteria**


  - [ ] Extract the offer code from the Basket URL
  - [ ] Submit the offer code to the basket service
  - [ ] Display the offer prices
  - [ ] Display offer text
  - [ ] Display offer T&C's
  
  Example offer URL: https://www.sky.com/shop/mobile/basket-summary/?14210&14518&14677&offer=iPhoneX-wk49
  Offer code should be extracted after 'offer=' and upto the next '&'


**Design**


