[<](../index.md) Altapay - PHP Api - Customer Info
==================================================

A customer object requries a billing address

```php
$billingAddress = new \Altapay\Request\Address();
$billingAddress->Firstname = 'First name';
$billingAddress->Lastname = 'Last name';
$billingAddress->Address = 'Address';
$billingAddress->City = 'City';
$billingAddress->PostalCode = 'Postal code';
$billingAddress->Region = 'Region';
$billingAddress->Country = 'Country';
$customer = new Altapay\Request\Customer($billingAddress);
```

We can also add a shipping address

```php
$shippingAddress = new \Altapay\Request\Address();
$shippingAddress->Firstname = 'First name';
$shippingAddress->Lastname = 'Last name';
$shippingAddress->Address = 'Address';
$shippingAddress->City = 'City';
$shippingAddress->PostalCode = 'Postal code';
$shippingAddress->Region = 'Region';
$shippingAddress->Country = 'Country';
$customer->setShipping($shippingAddress);
```

Other things we can set on our customer object is

| Method  | Description | Type |
|---|---|---|
setEmail(string) | Customer email | string
setUsername(string) | Customer username | string
setPhone(string) | Customer phone | string
setBankName(string) | Customer bank name | string
setBankPhone(string) | Customer bank phone | string
setBirthdate(DateTime) | Customer birthdate | DateTime
setCreatedDate(DateTime) | When was the customer created | DateTime
setGender(true) | What gender is the customer | Boolean (true = female, false = male)

```php
$customer->setEmail('email@email.com');
$customer->setBirthdate(new \DateTime('1982-07-23'));
$customer->setGender(true);
```

* More fields filled the better fraud detection will be
* Some of the fields are required on different requests