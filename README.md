## Welcome to structured-data.triptease.io

### Overview

[schema.org](http://schema.org/) contains a rich vocabulary that can be used to help tools read and understand web pages in wide number of domains. 
This page details the markup that can be added to a Hotel page to help not only Triptease products but also increase your SEO and Google listings.  

Notice anything wrong please raise an [issue](https://github.com/triptease/structured-data/issues). 

### Microdata vs RDFa vs JSON-LD

If the markup is static (like your Hotel name and address) then JSON-LD is generally the easiest to test and debug, while if the meta data is more dynamic (like offers or rate details) 
you may want to use the microdata format embedded in the HTML so that you keep the UI in sync with the meta data.

Triptease supports all 3 formats so if you are already using one then don’t worry about switching.

### Getting started

There are different levels of support for meta data and it's best to start with the simplest and work your way up to more advanced features as you get comfortable.

1. [Identification](#identification)
1. [Reservation](#reservation)



### Identification

This is the simplest and most important meta data you can add through out your marketing website and booking engine. Ideally you want this on every page. 
Doing this will also automatically allow your Hotel to appear on on Goggle search pages and Google Maps. Just putting the Hotel name and @type on each page will help Triptease 
identify your hotel automatically 

#### JSON-LD Example

```html
<script type="application/ld+json">
{
 "@context": "http://schema.org",
 "@type": "Hotel",
 "name": "Sea View Hotel",
 "identifier": "1234567",
 "brand": "Great Escapes",
 "address": 
  {
  "@type": "PostalAddress",
  "streetAddress": "1 Piccadilly",
  "addressLocality": "St. James's",
  "addressRegion": "London",
  "postalCode": "W1 9B",
  "addressCountry": "United Kingdom"
  },
 "telephone": "+44 1234 5678",
 "image": "http://example.com/image.png",
 "url": "http://example.com/"
}
</script>

```

#### Microdata Example

```html
<div itemscope itemtype="http://schema.org/Hotel">
    <h1 itemprop="name">Sea View Hotel</h1>
    <span itemprop="identifier">123456</span>
    <h2 itemprop="brand">Great Escapes</h1>
    <div itemprop="address" itemscope itemtype="http://schema.org/PostalAddress">
        <span itemprop="streetAddress">1 Piccadilly</span>
        <span itemprop="addressLocality">St. James's</span>
        <span itemprop="addressRegion">London</span>
        <span itemprop="postalCode">W1 9B</span>
        <span itemprop="addressCountry">United Kingdom</span>
    </div>
 <div>Telephone: <span itemprop="telephone">+44 1234 5678</span></div>
 <div>
    <a href="http://example.com/" itemprop="url">
        <img itemprop="image" src="http://example.com/image.png"/>
    </a>
 </div>
</div>

```

Lets walk through this:

#### @type

Make sure you set this to [Hotel](https://schema.org/Hotel) rather than the more generic [Organisation](https://schema.org/Organisation)
(Use Organisation in a separate metadata block to describe your parent organisation or group)

Used by: Google, Triptease

#### name 

The [name](https://schema.org/name) should be unique within Group or Brand

Used by: Google, Triptease

#### identifier (Optional) 

The [identifier](https://schema.org/identifier) can be used set to a unique property ID.

Used by: Triptease

#### brand (Optional)
  
The [brand](https://schema.org/brand) can help Triptease group together your hotels.

Used by: Triptease

#### address (Optional)
  
The [address](https://schema.org/address) allows Triptease and Google to correctly associate your Hotel with it's location. At a minimum add the [postalCode](https://schema.org/postalCode).

Used by: Google, Triptease

#### telephone (Optional)
  
The [telephone](https://schema.org/telephone) will allow Google to correctly list your contact details

Used by: Google,

#### url (Optional)
  
The [url](https://schema.org/url) will allow Triptease and Google to link to your hotel home page.

Used by: Google, Triptease

#### image (Optional)
  
The [image](https://schema.org/image) will allow Google (Search and Maps) to display a thumbnail image next to your name

Used by: Google




### Reservation

After identifying the Hotel the next most important data you can provide is the reservation information after a customer completes their booking. 

#### JSON-LD Example

```html
<script type="application/ld+json">
{
  "@context": "http://schema.org",
  "@type": "LodgingReservation",
  "reservationId": "abc456",
  "reservationStatus": "http://schema.org/ReservationConfirmed",
  "checkinTime": "2017-04-11T16:00:00-00:00",
  "checkoutTime": "2017-04-13T11:00:00-00:00"
  "totalPrice": "800.00"
  "priceCurrency": "GBP"
}
</script>

```

#### Microdata Example

```html
<div itemscope itemtype="http://schema.org/LodgingReservation">
    <h1>Reservation #<span itemprop="reservationId">abc456</span></h1>
    <h2>Details</h2>
    <dl>
        <dt>Status</dt>
        <dd itemprop="reservationStatus" content="http://schema.org/ReservationConfirmed">Confirmed</dd>
        <dt>Checkin</dt>
        <dd itemprop="checkinTime" content="2017-04-11T16:00:00-00:00">On 11th April from 4pm</dd>
        <dt>Checkout</dt>
        <dd itemprop="checkoutTime" content="2017-04-13T11:00:00-00:00">On 13th April by 11am</dd>
        <dt>Total</dt>
        <dd><span itemprop="totalPrice">800.00</span> <span itemprop="priceCurrency">GBP</span></dd>
    </dl>
</div>

```

Lets walk through this:

#### @type

Set this to [LodgingReservation](https://schema.org/LodgingReservation) 


#### reservationId

The [reservationId](https://schema.org/reservationId) should be unique and verifiable.  


#### reservationStatus

The [reservationStatus](https://schema.org/reservationStatus) should be set to [ReservationConfirmed](https://schema.org/ReservationConfirmed). 
If you wish to expose reservations earlier in the funnel then make sure you use one of the other [ReservationStatusType](https://schema.org/ReservationStatusType).


#### checkinTime

The [checkinTime](https://schema.org/checkinTime) is a combination of date and time, it can not just be a time as the name might suggest.


#### checkoutTime

The [checkoutTime](https://schema.org/checkoutTime) is a combination of date and time, it can not just be a time as the name might suggest.

#### totalPrice

The [totalPrice](https://schema.org/totalPrice) is the total price for the duration of the stay including taxes etc. Does not include the currency symbol.

#### priceCurrency

The [priceCurrency](https://schema.org/priceCurrency) is the 3 digit ISO currency code. 




### More Reading

[Leverage structured data to turbo-drive your click-through rate](https://www.triptease.com/blog/schema-hoteliers-leverage-structured-data/)

[Markup for Hotels](https://schema.org/docs/hotels.html)

[Understand how structured data works](https://developers.google.com/search/docs/guides/intro-structured-data)

[Structured Data Testing Tool](https://search.google.com/structured-data/testing-tool)

[Scheam.org Generator](https://developers.brewerdigitalmarketing.com/generator)

[Schema Markup Generator](https://technicalseo.com/seo-tools/schema-markup-generator/)

[Microdata](https://www.w3.org/TR/microdata/)




### Help

If you are having trouble then why not reach out to your Customer Success Manager or Direct Booking Coach
