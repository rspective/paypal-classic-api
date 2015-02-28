
### PayPal Classic API bindings for Node.js

This is a wrapper for PayPal "Classic" NVP API: https://developer.paypal.com/docs/classic/

### Installation
```
npm install paypal-classic-api --save
```
### Usage
**class PayPal(options)**

`options` object fields: `username`, `password` and `signature` from PayPal developer account.

*method* **call(methodName, methodArguments, callback)**

Methods names and arguments information can be found at https://developer.paypal.com/docs/classic/api/ under "Express Checkout API Operation"

### Example
```javascript
PayPal = require('paypal-classic-api');

var credentials = { username: tok261_biz_api.abc.com,
                    password: '1244612379',
                    signature: 'lkfg9groingghb4uw5' };
                    
var paypal = new PayPal(credentials);

paypal.call('TransactionSearch', { StartDate: '2012-06-11T10:50:44.681Z' }, function (error, transactions) {
  if (error) {
    console.error('API call error: ' + error);
  } else {
    console.log(JSON.stringify(transactions));
  }
});
