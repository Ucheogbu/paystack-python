# paystack-python
[![Coverage Status](https://coveralls.io/repos/github/andela-sjames/paystack-python/badge.svg?branch=feature-customerclass)](https://coveralls.io/github/andela-sjames/paystack-python?branch=feature-customerclass)  

Python plugin for [Paystack](https://paystack.com/) 

# Installation
```
pip install paystackapi
```


# Usage  

To start using the Paystack Python API, you need to start by setting your secret key

```python
from paystackapi.constants import PAYSTACK_SECRET_KEY
PAYSTACK_SECRET_KEY = 'your_secret_key`
```  

> Don't forget to get your API key from [Paystack](https://paystack.com/) and assign to the variable `PAYSTACK_SECRET_KEY`

## Transactions  

##### `Transaction.initialize(reference, amount, email, plan)` - Initialize transaction.

*Usage*

```python
from paystackapi.transaction import Transaction  
response = Transaction.initialize(reference, amount, email, plan)  
```

*Arguments*

- `reference`: Unique transaction reference
- `amount`: Amount
- `email`: Email address
- `plan`: Specified plan

*Returns*

JSON data from Paystack API.

##### `Transaction.charge(reference, authorization_code, email, amount)` - Charge authorization.

```python
from paystackapi.transaction import Transaction  
response = Transaction.charge(reference, authorization_code, 
                              email, amount)
```

*Arguments*

- `reference`: Unique transaction reference
- `authorization_code`: Authorization code for the transaction
- `email`: Email Address of the user with the authorization code
- `amount`: Amount in kobo

*Returns*

JSON data from Paystack API.

##### `Transaction.charge_token(reference, token, email, amount)` - Charge Token.

```python
from paystackapi.transaction import Transaction  
response = Transaction.charge_token(reference, token, email, amount)
```

*Arguments*

- reference: unique transaction reference
- token: paystack token
- email: Email Address
- amount: Amount in Kobo

*Returns*

JSON data from Paystack API.

##### `Transaction.get(id)` - Get a single transaction.

```python
from paystackapi.transaction import Transaction  
response = Transaction.get(id)
```

*Arguments*

- `id`: Transaction id(integer).

*Returns*

JSON data from paystack API.

##### `Transaction.list()` - List transactions.

```python
from paystackapi.transaction import Transaction  
response = Transaction.list()
```

*Arguments*

No argument required.

*Returns*

JSON data from paystack API.

##### `Transaction.totals()` - Get totals.

```python
from paystackapi.transaction import Transaction  
response = Transaction.totals()
```
*Arguments*

No argument required.
    
*Returns*

JSON data from paystack API.

##### `Transaction.verify(reference)` - Verify transactions.

```python
from paystackapi.transaction import Transaction  
response = Transaction.verify(reference)
```

*Arguments*

- `reference`: a unique value needed for transaction.

*Returns*

JSON data from paystack API.


## Plans  

##### `Transaction.create(name, description, amount, interval, send_invoices, send_sms, hosted_page, hosted_page_url, hosted_page_summary, currency)` - Create a plan  

```python
from paystackapi.transaction import Transaction  
response = Transaction.create(name, description, amount, interval, 
                              send_invoices, send_sms,
                              hosted_page, hosted_page_url,
                              hosted_page_summary, currency)
```

*Arguments*

- `name`: plan's name.
- `description`: description of the plan.
- `amount`: amount for the plan in kobo
- `interval`: plan's interval(daily...etc)
- `send_invoices`: boolean
- `send_sms`: (optional)
- `hosted_page`: (optional)
- `hosted_page_url`: url of hosted page (optional)
- `hosted_page_summary`: summary of the hosted page
- `currency`: plans currency (NGN)

*Returns*

JSON data from paystack API.

##### `Transaction.get(id)` - Get a single plan.

```python
from paystackapi.transaction import Transaction  
response = Transaction.get(id)
```

*Arguments*

- `id`: paystack plan id.

*Returns*

JSON data from paystack API.

##### `Transaction.list()` - List paystack plan

```python
from paystackapi.transaction import Transaction  
response = Transaction.list()
```

*Arguments*

No argument required.

*Returns*

JSON data from paystack API.

##### `Transaction.update(id, name=None, description=None, amount=None, interval=None, send_invoices=None, send_sms=None, hosted_page=None, hosted_page_url=None, hosted_page_summary=None, currency=None)` - Update paystack plan

```python
from paystackapi.transaction import Transaction  
response = Transaction.update(id, name=None, description=None,
                              amount=None, interval=None,
                              send_invoices=None, send_sms=None,
                              hosted_page=None, hosted_page_url=None,
                              hosted_page_summary=None, currency=None)
```

*Arguments*

- `id`: plan identity number.
- `name`: name of plan
- `description`: plan description(optional)
- `amount`: plan amount in Naira
- `interval`: plan interval9(monthly, yearly, quarterly...etc)
- `send_invoice`: (optional)
- `send_sms`: (optional)
- `hosted_page`: (optional)
- `hosted_page_url`: (optional)
- `hosted_page_summary`: (optional)
- `currency`: Naira in kobo(NGN)

*Returns*

JSON data from paystack API.


## Customers 

##### `Transaction.create(first_name, last_name, email, phone)` - Create customer

```python
from paystackapi.transaction import Transaction  
response = Transaction.create(first_name, last_name, email, phone)
```

*Arguments*

- `first_name`: customer's first name.
- `last_name`: customer's last name.
- `email`: customer's email address.
- `phone`: customer's phone number.

*Returns*

JSON data from paystack API.

##### `Transaction.get(id)` - Get customers by id

```python
from paystackapi.transaction import Transaction  
response = Transaction.get(id)
```

*Arguments*

- `id`: paystack customer id

*Returns*

JSON data from paystack API.

##### `Transaction.list()` - List paystack customers

```python
from paystackapi.transaction import Transaction  
response = Transaction.list()
```

*Arguments*

No argument required.

*Returns*

JSON data from paystack API.

##### `Transaction.update(id, first_name=None, last_name=None, email=None, phone=None)` - Update paystack customer data by id.

```python
from paystackapi.transaction import Transaction  
response = Transaction.update(id, first_name=None, 
                              last_name=None,
                              email=None, phone=None)
```  

*Arguments*
- `id`: paystack customer id.
- `first_name`: customer's first name(optional).
- `last_name`: customer's last name(optional).
- `email`: customer's email address(optional).
- `phone`: customer's phone number(optional).

*Returns*

JSON data from paystack API.
