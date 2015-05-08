Get a list of contact questions.

HTTP method: GET /services/v1/contact/questions
Client authorization: no
User authorization: no
TLS: no

**Optional Parameters:**

    include_answers - int Any non-zero value will include the answer in the response

Response
 questions - array List of questions
  id  - integer Question ID
  text  - string Question

Example request
        curl http://jackthreads:kobol@16.camp.jackthreads.com:9016/services/v1/contact/questions?include_answers=1

Example response
        {`
``  ``"success"``:``true``,``
``  ``"questions"``:``[``
``     ``{``
``        ``"id"``:``1``,``
``        ``"text"``:``"When will my order ship?",`
                "**answer**":"`To check the status of your order, go to your account and click on 'view order details' under the order number.`"
             `}``,``
``     ``{``
``        ``"id"``:``2``,``
``        ``"text"``:``"I need to cancel or modify my order"`
        "**answer**":"`If your order was placed in the past thirty minutes, you might be able to modify your order directly from your JackThreads account.`"
             `}``
``  ``]``
``}`