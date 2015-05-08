Two workflows: 
    Standard checkout without 'Connect'
    Connect JT to MasterPass after the first checkout


1. **Standard checkout without allowing 'Connect', or first checkout and connect afterwards**

Steps:
1. call /services/v1/masterpass/start_connect
2. login into masterpass sandbox accounts, pick shipping address and credit card, choose whether to connect or not
3. call /services/v1/masterpass/set_payment
4. checkout
**

**

**2. Return checkout after 'connected'**

Steps:
1. call /services/v1/masterpass/return_checkout
2. go to your test_return_checkout view, login and confirm order
3. call /services/v1/masterpass/set_payment
4. checkout


**3. Disconnect user from masterpass**

call /services/v1/masterpass/disconnect_user