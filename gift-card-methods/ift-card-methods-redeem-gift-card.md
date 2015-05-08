Redeem a gift card.

HTTP method: POST /services/v1/gift_cards/redeem
Client authorization: no
User authorization: required
TLS: required

Required parameters
 code  - string Gift card code

Optional parameters
 address_id  - string JITR Address id used to calculate address-related coupons

Response
 amount - string Gift card amount
 balance - string Credit balance, after gift card was redeemed
**        coupons - object Coupon information**        
**  amount - string Total coupon amount
  coupons - array List of individual coupons

id  - integer Coupon ID
name  - string Coupon name
method - string Either “manual” or “auto”
amount - string Amount
desc  - string Description**

Example request
        curl -k -d 'code=bmBzLySTnvNjnWx&oauth_token=fb18fc25e7e41608dadddcf567e9fe22q' https://16.camp.jackthreads.com:9116/services/v1/gift_cards/redeem

Example response
        
**{
   "success":true,
   "amount":"0.00",
   "balance":"150.00",
   "coupons":{
      "amount":"2.01",
      "coupons":[
         {
            "id":69,
            "name":"Rothco Paracord",
            "method":"auto",
            "amount":"2.01",
            "desc":"Bracelets"
         }
      ]
   }
}**