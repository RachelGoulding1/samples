ref: AOC003

**User Story**

As an email customer  
I would like to view the basket with the offer applied   
So that I can see the correct price


**Acceptance Criteria**


  - [ ] Extract the offer code from the Basket URL if present
  - [ ] Submit the offer code to the basket service
  - [ ] Display the below returned offer information
   - [ ] offer price
   - [ ] offer text
   - [ ] offer T&C's
   

Notes: 
  
1.  Example offer URL: https://www.sky.com/shop/mobile/basket-summary/?14210&14518&14677&offer=iPhoneX-wk49   
    The Offer code should be extracted after 'offer=' and upto the next '&' if present
  
2.  Additional feature background information can be found [here](https://github.com/RachelGoulding1/samples/blob/master/HighLevelBRD.md) 


**Design**

Desktop

<img width="785" alt="screen shot 2018-06-23 at 19 32 35" src="https://user-images.githubusercontent.com/40513613/41812541-b15ef82e-771c-11e8-87d9-ddaeb5dafaf9.png">

Mobile

<img width="399" alt="screen shot 2018-06-23 at 19 33 31" src="https://user-images.githubusercontent.com/40513613/41812542-b80d5d64-771c-11e8-9b12-37c192107158.png">



