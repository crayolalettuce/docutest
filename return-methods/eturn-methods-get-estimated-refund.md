### []()





Get estimated refund for a specific return.

HTTP method: GET /services/v1/returns/get_estimated_refund
Client authorization: no
User authorization: required
TLS: required

Required parameters
 return_items - array Return Items
[(
 order_item_id => [
        order_item_id => 1,

        reason => 1,

        qty => 1

    ] 
)] 

Response
 refund_details   - object Return refund details
  items   - object return items
  deductions   - object return items
  totals   - object return items

Example request
        curl -k https://api.jackthreads.com/services/v1/returns/get_estimated_refund`?oauth_token=fb18fc25e7e41608dadddcf567e9fe22q`

Example response
        {`
``  ``"success"``:``true``,``
``  ``"refund_details"``:``[``
``     ``{`     
            "items"`:``[`
                'order_item_id' => $order_item_id,
                'name' => $item['name'], 
                'refund_reason' => $item['refund_reason'], 
                'cash_subtotal' => $item['cash_subtotal'],
                'cash_shipping' => $item['cash_shipping'],
                'cash_tax' => $item['cash_tax'],
                'credit_subtotal' => $item['credit_subtotal'],
                'credit_shipping' => $item['credit_shipping'],
                'credit_tax' => $item['credit_tax'],
                'eligible_cash' => $item['eligible_cash'],
                'eligible_credit' => $item['eligible_credit'],
                'refund_total' => $item['refund_total'],
             }
             `"deductions"``:``[``
``     ``{`
        'name' => $deduction['deduction_type'], 
         'subtotal' => 0.00, 'shipping' => 0.00, 'tax' => 0.00, 'credit_subtotal' => 0.00, 'eligible_cash' => 0.00, 'eligible_credit' => 0.00, 'total' => $deduction['deduction']
             }]
         "totals"`:`
            {

         'refund_total' => $totals['total'], 'eligible_credit' => $totals['eligible_cash'], 'eligible_cash' => $totals['eligible_cash'], 'transactions_total' => $totals['transactions_total'], 'card_max' => $totals['card_max'], 'cash_refund' => $totals['cash_refund'], 'credit_refund' => $totals['credit_refund'],
            }

          ],
          `]``
``}`