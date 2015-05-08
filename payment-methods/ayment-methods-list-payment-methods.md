Get a list of the user’s stored payment methods. 
 
 HTTP method: GET /services/v1/payment_methods
 Client authorization: no
 User authorization: required
 TLS: required
 
 Optional Parameters
 include_fb - boolean (Default false) If true, will return Facebook Payments accounts if the user has any. **Do not include this parameter if Facebook Payments is not enabled for the device.** If you aren't sure, don't include it.
 include_mp - boolean (Default false) If true, will return MasterPass Payments accounts if the user has any. **Do not include this parameter if MasterPass Payments is not enabled for the device.** If you aren't sure, don't include it.




Response
  success - boolean
 payment_methods - objects
  data - objects Contains data for the available payment method types
 *common fields under each type:*
   id - integer ID of the payment method
   first_name - string First Name
   last_name - string Last Name
   address - boolean Address
   address2 - boolean Address Line 2
   city - boolean City
   state - boolean State
   zip - string Zip/Postal Code
   country - string 2-char country code (e.g. US, CA)
   phone - string Phone number
   is_primary - boolean True if this is the user's primary payment method   gateway      - string Gateway this method is registered in
   full_name - string User's first and last name concatenated
   text_label - string Label used to describe the account that can be displayed to the user
   c - objects All credit cards, keyed by credit_card ID
   exp_month - string Expiration month
   exp_year - string Expiration year
   last_four - string Last four digits of the credit card
   bin - string Bank Indentification Number; 6-digit number, may be "amex" or "discov"
   company - string Company name
   cardtype_name - string Name of the type of credit card (e.g. Visa, Mastercard)
   cardtype_code - string Short code for card type (e.g. VI, MC)
   p - objects All PayPal accounts, keyed by paypal_account ID
   email - string Email associated with the PayPal account
   f - objects All Facebook Payment accounts, keyed by fbpay_account ID
   label - string Masked string representing the credit card number
   type - string Code for the type of card (e.g. V, M, A)
   exp_month - string Expiration month
   exp_year - string Expiration year
   email - string Email associated with the Facebook account
   sync - boolean True if this info will be synced and updated with current data from FB
   update - boolean True if this info will be saved to FB the next time the user places an order
  list - array List of all payment methods with an appropriate text label
   type - char Type of payment method (c/p/f); payment_methods.data.*type*
   id - integer ID of the payment method; payment_methods.data.*type*.*id*
   desc - string Label used to describe the account and should be displayed to the user
  primary - object The user's primary payment method
   id - integer
   type - char
  active - object The user's currently-selected payment method
   id - integer
   type - char
  has_paypal - boolean True if the user has a PayPal account stored

 Example request
 `curl -k https://rc.jackthreads.com/services/v1/payment_methods?oauth_token=fb18fc25e7e41608dadddcf567e9fe22`
 
 Example response
        { "**success**":true, "**payment_methods**":{ "**data**":{ "**c**":{ "**123456**":{ "**id**":"123456", "**exp_month**":"3", "**exp_year**":"2015", "**last_four**":"1111", "**bin**":"411111", "**first_name**":"Matt", "**last_name**":"Doyle", "**company**":"JackThreads", "**address**":"568 Broadway", "**address2**":"Rm 506", "**city**":"New York", "**state**":"NY", "**zip**":"10012-3264", "**country**":"US", "**phone**":"1234567890", "**is_primary**":"0", "**full_name**":"Matt Doyle", "**cardtype_name**":"Visa", "**cardtype_code**":"VI", "**text_label**":"Visa ************1111" } }, "**p**":{ "**7788**":{ "**id**":"7788", "**email**":"mattbuyer@jackthreads.com", "**first_name**":"Matt", "**last_name**":"Doyle", "**address**":"568 Broadway", "**address2**":"Rm 506", "**city**":"New York", "**state**":"NY", "**zip**":"10012-3264", "**country**":"US", "**phone**":"1234567890", "**is_primary**":"1", "**full_name**":"Matt Doyle", "**text_label**":"PayPal Account - mattbuyer`@jackthreads.com" } }, "**f**":{ "**9900**":{ "**id**":"9900", "**first_name**":"Matt", "**last_name**":"Doyle", "**label**":"XXXX-XXXX-XXXX-1234", "**type**":"V", "**exp_month**":"06", "**exp_year**":"2016", "**address**":"568 Broadway", "**address2**":null, "**city**":"New York", "**state**":"NY", "**zip**":"10012", "**country**":"US", "**phone**":"1234567890", "**email**":"matt@jackthreads.com", "**is_primary**":"0",`
 "**sync**":"0",` "**update**":"0", "**full_name**":"Matt Doyle", "**text_label**":"FB Account - XXXX-XXXX-XXXX-1234" } } }, "**list**":[ { "**id**":123456, "**type**":"c", "**desc**":"Visa ************1111" }, { "**id**":7788, "**type**":"p", "**desc**":"PayPal Account - mattbuyer@jackthreads.com" }, { "**id**":9900, "**type**":"f", "**desc**":"FB Account - XXXX-XXXX-XXXX-1234" } ], "**primary**":{ "**type**":"p", "**id**":7788 }, "**active**":{ "**type**":"p", "**id**":7788 }, "**has_paypal**":true } }`