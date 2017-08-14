# Overview
To start the work I need a little - the help of your developers. I do not want to get into the code, as this can damage their work. But if there is such a need, I will do it using **pull requests**. In any case, let me explain how and what we will do.

# Cross-Domain Tracking
## Problem and solution.
At the moment you have different Tracking IDs per websites. In order to correctly configure cross-domain tracking between your website, you should use one Google Analytics (Universal Analytics) Tracking ID.  
## How to see the data per website?
In turn, to divide traffic between domains - we need to create a new **reporting views** and add Filters.

## How to set the pixel correctly if you have several domains and you want to link them?
For this, it is necessary to: 

- [ ] Implement code snippet before closing `</head> ` tag.
- [x] Customize your pixel and enable allowLinker
- [ ] Add necessary domains into the snippets
- [x] Enable linker plugin
- [ ] Add all your domains into referral exclusion list

## Just say what to do?
It's simple. You just need to say what kind of property I can use to setup for all domains!  guess that you will say - **UA-66686611-1**
If so, the pixels to implement should be:
### pacificmedicaltraining.com (Primary Domain)
```
<!-- GOOGLE ANALYTICS -->
  <script>
  (function(i,s,o,g,r,a,m){i['GoogleAnalyticsObject']=r;i[r]=i[r]\|\|function(){
  (i[r].q=i[r].q\|\|[]).push(arguments)},i[r].l=1*new Date();a=s.createElement(o),
  m=s.getElementsByTagName(o)[0];a.async=1;a.src=g;m.parentNode.insertBefore(a,m)
  })(window,document,'script','https://www.google-analytics.com/analytics.js','ga');
  ga('create', 'UA-66686611-1', 'auto', {'allowLinker': true});
  ga('require', 'linker');
  ga('linker:autoLink', ['pharmtechcareer.com', 'monitortech.org', 'scribeschool.net'] );
  ga('send', 'pageview');
  </script>
<!-- GOOGLE ANALYTICS -->
```
### scribeschool.net (Landing Page)
```
<!-- GOOGLE ANALYTICS -->
  <script>
  (function(i,s,o,g,r,a,m){i['GoogleAnalyticsObject']=r;i[r]=i[r]\|\|function(){
  (i[r].q=i[r].q\|\|[]).push(arguments)},i[r].l=1*new Date();a=s.createElement(o),
  m=s.getElementsByTagName(o)[0];a.async=1;a.src=g;m.parentNode.insertBefore(a,m)
  })(window,document,'script','https://www.google-analytics.com/analytics.js','ga');
  ga('create', 'UA-66686611-1', 'auto', {'allowLinker': true});
  ga('require', 'linker');
  ga('linker:autoLink', ['lms.pacificmedicaltraining.com', 'pharmtechcareer.com', 'monitortech.org'] );
  ga('send', 'pageview');
  </script>
<!-- GOOGLE ANALYTICS -->
```
### pharmtechcareer.com (Landing Page)
```
<!-- GOOGLE ANALYTICS -->
  <script>
  (function(i,s,o,g,r,a,m){i['GoogleAnalyticsObject']=r;i[r]=i[r]\|\|function(){
  (i[r].q=i[r].q\|\|[]).push(arguments)},i[r].l=1*new Date();a=s.createElement(o),
  m=s.getElementsByTagName(o)[0];a.async=1;a.src=g;m.parentNode.insertBefore(a,m)
  })(window,document,'script','https://www.google-analytics.com/analytics.js','ga');
  ga('create', 'UA-66686611-1', 'auto', {'allowLinker': true});
  ga('require', 'linker');
  ga('linker:autoLink', ['lms.pacificmedicaltraining.com', 'scribeschool.net', 'monitortech.org']);
  ga('send', 'pageview');
  </script>
<!-- GOOGLE ANALYTICS -->
```
### monitortech.org (Landing Page)
```
<!-- GOOGLE ANALYTICS -->
  <script>
  (function(i,s,o,g,r,a,m){i['GoogleAnalyticsObject']=r;i[r]=i[r]\|\|function(){
  (i[r].q=i[r].q\|\|[]).push(arguments)},i[r].l=1*new Date();a=s.createElement(o),
  m=s.getElementsByTagName(o)[0];a.async=1;a.src=g;m.parentNode.insertBefore(a,m)
  })(window,document,'script','https://www.google-analytics.com/analytics.js','ga');
  ga('create', 'UA-66686611-1', 'auto', {'allowLinker': true});
  ga('require', 'linker');
  ga('linker:autoLink', ['lms.pacificmedicaltraining.com','pharmtechcareer.com', 'scribeschool.net']);
  ga('send', 'pageview');
  </script>
<!-- GOOGLE ANALYTICS -->
```
> Don't forget to place all GA pixels before closing `</head>`, and not `</body>`

# Enhanced E-commerce tracking
Firstly, it is important to say that this functionality can not be fully integrated for your project. However, I will propose the best option. I will do my best.
## What do we have now?
### Classic e-commerce reporting instead of Enhanced E-commerce reporting 
Right now we have classic e-commerce integration with enabled Enhanced E-commerce reporting in GA. This is not recommended and it may affect the data. 
### So what is the difference in our case? Let's look at an example of sending transaction data.
#### HOW TO LOAD PLUGIN

Classic e-commerce(our case) | Enhanced e-commerce
------------ | -------------
`ga('require', 'ecommerce', 'ecommerce.js');` | `ga('require', 'ec');`

![image](https://user-images.githubusercontent.com/18442582/29288222-a4c03b64-8140-11e7-80d4-3417c03fc07b.png)

#### HOW THE DATA IS SENT

Classic e-commerce(our case) | Enhanced e-commerce
------------ | -------------
```ga('ecommerce:addTransaction', {'id': '1234','affiliation': 'Acme Clothing','revenue': '11.99','shipping': '5','tax': '1.29'});```  | ```ga('ec:setAction', 'purchase', {'id': 'T12345','affiliation': 'Google Store - Online','revenue': '37.39','tax': '2.85','shipping': '5.34','coupon': 'SUMMER2013'});```
```ga('ecommerce:addItem', {'id': '1234','name': 'Fluffy Pink Bunnies','sku': 'DD23444', 'category': 'Party Toys', 'price': '11.99', 'quantity': '1'});``` | ```ga('ec:addProduct', {'id': 'P12345','name': 'Android Warhol T-Shirt','category': 'Apparel','brand': 'Google','variant': 'black','price': '29.20','coupon': 'APPARELSALE','quantity': 1}); ```

![image](https://user-images.githubusercontent.com/18442582/29288960-7a692e7c-8143-11e7-9001-91adbf21210e.png)

## Just say what to do?
It is necessary to understand what data we **want** to send and what data we **can** send.
Let's go in order and discuss it.

### Transaction Data
Here is an example of data that I would like to see on thank you page.
```
ga('create', 'UA-XXXXX-Y');
ga('require', 'ec');

ga('ec:addProduct', {               // Provide product details in an productFieldObject.
  'id': 'ACLSR',                   // Product ID or SKU (string).
  'name': 'ACLS Recertification Course', // Product name (string).
  'category': 'Course',            // Product category (string).
  'price': '175.00',                 // Product price (currency).
  'quantity': 1                     // Product quantity (number).
});
ga('ec:addProduct', {               // Provide product details in an productFieldObject.
  'id': 'TLEA',                   // Product ID or SKU (string).
  'name': '12-Lead Electrocardiography', // Product name (string).
  'category': 'Product',            // Product category (string).
  'price': '250.00',                 // Product price (currency).
  'quantity': 1                     // Product quantity (number).
});

ga('ec:setAction', 'purchase', {          // Transaction details are provided in an actionFieldObject.
  'id': '14305',                         // (Required) Transaction id (string).
  'affiliation': 'Pacific Medical Training', // Affiliation (string).
  'revenue': '425.00',                     // Revenue (currency).
  'tax': '12.75',                          // Tax (currency).
  'coupon': '15% Multiple course discount'                  // Transaction coupon (string).
});

ga('send', 'pageview');     // Send transaction data with initial pageview.
```

### Product Detail View
In any place where the product detail was viewed. In our case it can be:

- Landing Pages
- Product description articles on primary domain (i.e.https://pacificmedicaltraining.com/education-hospital-acls.html)

```
ga('create', 'UA-XXXXX-Y');
ga('require', 'ec');

ga('ec:addProduct', {               // Provide product details in an productFieldObject.
  'id': 'ACLSR',                   // Product ID or SKU (string).
  'name': 'ACLS Recertification Course', // Product name (string).
  'category': 'Course',            // Product category (string).
  'price': '175.00',                 // Product price (currency).
  'quantity': 1                     // Product quantity (number).
});

ga('ec:setAction', 'detail');

ga('send', 'pageview');       // Send product details view with the initial pageview.
```
### Product Click
In any place where the product was clicked
```
// Called when a link to a product is clicked.
function onProductClick() {
ga('ec:addProduct', {               // Provide product details in an productFieldObject.
  'id': 'ACLSR',                   // Product ID or SKU (string).
  'name': 'ACLS Recertification Course', // Product name (string).
  'category': 'Course',            // Product category (string).
  'price': '175.00',                 // Product price (currency).
  'quantity': 1                     // Product quantity (number).
});
  ga('ec:setAction', 'click', {list: 'Landing Page: scribeschool.net'});

  // Send click with an event, then send user to product page(Landing Page).
  ga('send', 'event', 'Ecommerce', 'click', 'Landing Page', {
    hitCallback: function() {
      document.location = '/';
    }
  });
 // Send click with an event, then send user to product page(Article).
  ga('send', 'event', 'Ecommerce', 'click', 'Article', {
    hitCallback: function() {
      document.location = '/education-hospital-acls.html';
    }
  });
}
```

### Product was displayed
In any place where the product was displayed
```
ga('create', 'UA-XXXXX-Y');
ga('require', 'ec');

ga('ec:addImpression', {               // Provide product details in an productFieldObject.
  'id': 'ACLSR',                   // Product ID or SKU (string).
  'name': 'ACLS Recertification Course', // Product name (string).
  'category': 'Course',            // Product category (string).
  'price': '175.00',                 // Product price (currency).
  'quantity': 1                     // Product quantity (number).
  'list': 'Eductaion Page (/education.html)',
  'position': 1
});

ga('ec:addImpression', {               // Provide product details in an productFieldObject.
  'id': 'TLEA',                   // Product ID or SKU (string).
  'name': '12-Lead Electrocardiography', // Product name (string).
  'category': 'Product',            // Product category (string).
  'price': '250.00',                 // Product price (currency).
  'quantity': 1                     // Product quantity (number).
  'list': 'Eductaion Page (/education.html)',
  'position': 2
});

ga('send', 'pageview');              // Send product impressions with initial pageview.
```

### Add to Cart
In any place where the product was added to cart. 
It can be send when someone click on button or URL on your landing pages or main domain, OR In our case it's the same action with starting checkout process - visit this page - [lms.pacificmedicaltraining.com/](url)
![image](https://user-images.githubusercontent.com/18442582/29290669-a5049486-8149-11e7-8ba1-bc837e3d01d3.png)

```
ga('create', 'UA-XXXXX-Y');
ga('require', 'ec');

ga('ec:addProduct', {               // Provide product details in an productFieldObject.
  'id': 'ACLSR',                   // Product ID or SKU (string).
  'name': 'ACLS Recertification Course', // Product name (string).
  'category': 'Course',            // Product category (string).
  'price': '175.00',                 // Product price (currency).
  'quantity': 1                     // Product quantity (number).
});

 ga('ec:setAction', 'add');
 ga('send', 'event', 'Ecommerce', 'click', 'add to cart');     // Send data using an event.
ga('send', 'pageview');              // Send product impressions with initial pageview.
```

### Checkout Process
Because we have one-step checkout page, we can just track one step. But optionally I will explain how to do this if you can integrate it with the developers.
Fields can be grouped into several possible steps:
- Contact Details
- Shipping Details
- Payment Details

![image](https://user-images.githubusercontent.com/18442582/29290831-32ce3a2e-814a-11e7-976a-e9af73d96a6d.png)

Upon the successful completion of each group we can send event:
```
ga('create', 'UA-XXXXX-Y');
ga('require', 'ec');

ga('ec:addProduct', {               // Provide product details in an productFieldObject.
  'id': 'ACLSR',                   // Product ID or SKU (string).
  'name': 'ACLS Recertification Course', // Product name (string).
  'category': 'Course',            // Product category (string).
  'price': '175.00',                 // Product price (currency).
  'quantity': 1                     // Product quantity (number).
});

ga('ec:setAction','checkout', {
    'step': 1,            // A value of 1 indicates this action is first checkout step.
});

ga('send', 'pageview');    
```
And if we want to track each group we have to additionally implement:
```
ga('ec:setAction','checkout', {
    'step': 2,            // A value of 1 indicates this action is first checkout step.
});
```
Also, we can send additional **checkout_option**, for example - payment method: 

```
ga('ec:setAction','checkout', {
    'step': 3,            // A value of 1 indicates this action is first checkout step.
    'option': 'Visa'      // Used to specify additional info about a checkout stage, e.g. payment method.
});
```
More information about this part of integration you can find here:
[](https://developers.google.com/analytics/devguides/collection/analyticsjs/enhanced-ecommerce#checkout-process)

