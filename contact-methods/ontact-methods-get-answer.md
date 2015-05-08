Get the answer for a specific question.

HTTP method: GET /services/v1/contact/questions/<id>/answer
Client authorization: no
User authorization: no
TLS: no

Required parameters
 id - integer Question ID

Response
 question - string Question
 answer - string Answer

Example request
        curl http://16.camp.jackthreads.com:9016/services/v1/contact/questions/1/answer

Example response
        {`
``  ``"success"``:``true``,``
``  ``"question"``:``"When will my order ship?"``,``
``  ``"answer"``:``"<p>Most in-stock orders arrive 5-7 business days after you place your order, but if you look at the product page you'll notice the estimated delivery date below the \"Add to Cart\" button. \r\nTo check on estimated arrival of pending orders, go to your account page and click the order number.<\/p>\r\n<p>Sometimes -- to offer you even deeper discounts -- we offer pre-sales, meaning we don't physically have the inventory in stock during the time of the sale. \r\nOnce the sale is over we place an order for everything you've bought, and it is shipped to our warehouse. From there we send it to you.  \r\nSometimes these custom orders take brands longer to fulfill (sometimes 3-4 weeks), but once they reach us they're sent to you with the same speed as in-stock purchases.<\/p>\r\n"``
``}`