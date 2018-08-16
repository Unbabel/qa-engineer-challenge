# QA Engineer Challenge

This QA Engineering challenge was created to give us a sense of how you'll operate in a real product scenario at Unbabel.

The Automation exercise will be centered on an existing Unbabel tool called ***Annotation tool***.

The Load exercise will be centered on a service specifically created for the challenge.

You should receive a demo of the tool, as well as the urls and valid credentials, before executing the exercises. If you haven't, request them.

***Important Notes:***

* Create a public repo in your github/gitlab account and send it to us right away
* Create one folder in that repo per exercise
* ***The Challenge*** can be submitted in whichever form you prefer as long as you also submit a README.md file alongside it with detailed instructions on how to run your solution
* We'll check your progress periodically
* If you have any questions, please ask.




#### Estimated time: 5 days (off hours only).


### 1. Automation

Choose a platform/framework of your liking (as long as it is free or open source) and automate the following:

* Login
* Choose one task
* Perform annotation
* Finish annotation

#### 1.1 Reporting

Create a simple report for the automation you created.


### 2. Load 

Given the service below, perform a load test on the service and present a small report with your perspective on the test results. 

It's expected that this service must support 75 users at any given moment and must be able to handle 350 requests per second. The response time must be under 200 ms.  


* The URL will be provided by email.

Find below the service documentation.



## API documentation

* **URL**
    /return_eu_countries

* **Method:**
    `POST` 

* **Description**
The basic functionality of this service is to receive a list of iso country codes and return if there are any EU countries on that list.
The iso codes of the European Union countries are listed below:

|	Country	        |	ISO	|
|	-----	        |	--	|
|	Belgium    	    |	BE	|
|	Greece  	    |	EL	|
|	Lithuania 	    |	LT	|
|	Portugal 	    |	PT	|
|	Bulgaria	    |	BG	|
|	Spain 	        |	ES	|
|	Luxembourg      |	LU	|
|	Romania 	    |	RO	|
|	Czech Republic  |	CZ	|
|	France 	        |	FR	|
|	Hungary	        |	HU	|
|	Slovenia	    |	SI	|
|	Denmark	        |	DK	|
|	Croatia	        |	HR	|
|	Malta	        |	MT	|
|	Slovakia	    |	SK	|
|	Germany	        |	DE	|
|	Italy	        |	IT	|
|	Netherlands	    |	NL	|
|	Finland		    |   FI	|




* **Data Params**

    |Name          | Type | Description                               | Example                                     |
    |--------------|------|-------------------------------------------|---------------------------------------------|
    |country_list  |Array |Array of elements to compare with Source   | {"country_list": ["BE", "DE", "NY"]}        |





* **Success Response:**
  
    **Code:** 200 <br />
    **Content:** `{"value":"Match","status":"OK","result":["BE","DE"]}`

    **Code:** 200 <br />
    **Content:** `{"value":"No match","status":"OK","result":[]}`



 
* **Error Response:**
  * **Code:** 400 <br />
  *  **Content:** `{"request_sent":{"county_list":["PT"]},"error":"No country_list on request"}`





* **Sample Call:**
    * Request:
    
    ```
    curl -X POST \
      http://{{URL}}/api/return_eu_countries \
      -H 'cache-control: no-cache' \
      -H 'content-type: application/json' \
      -d '{"country_list": ["BE", "DE", "NY"]}'
    ```
   * Response:
   
    ```
    {"value":"Match","status":"OK","result":["BE","DE"]}
    ```
