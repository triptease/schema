## Welcome to structured-data.triptease.io

### Overview

[schema.org](http://schema.org/) contains a rich vocabulary that can be used to help tools read and understand web pages in wide number of domains. 
This page details the markup that can be added to a Hotel page to help not only Triptease products but also increase your SEO and Google listings.  

Notice anything wrong please raise an [issue](https://github.com/triptease/schema/issues). 

### Microdata vs RDFa vs JSON-LD

If the markup is static (like your Hotel name and address) then JSON-LD is generally the easiest to test and debug, while if the meta data is more dynamic (like offers or rate details) 
you may want to use the microdata format embedded in the HTML so that you keep the UI in sync with the meta data.

Triptease supports all 3 formats so if you are already using one then don’t worry about switching.

### Getting started

There are different levels of support for meta data and it's best to start with the simplest and work your way up to more advanced features as you get comfortable.

### 1 - Identification

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

Make sure you set this to 'Hotel' rather than the more generic 'Organisation' 
(Use Organisation in a separate metadata block to describe your organisation)

Used by: Google, Triptease

#### name 

The name should be unique within Group or Brand

Used by: Google, Triptease

#### identifier (Optional) 

The identifier can be used set to a unique property ID

Used by: Triptease

#### brand (Optional)
  
You can put the brand here or as part of the 'name' property but don't put it in both as this might cause the brand to appear twice in some tools.

Used by: Triptease

#### address (Optional)
  
This will allow Triptease and Google to correctly associate your Hotel name with it's location.

Used by: Google, Triptease

#### telephone (Optional)
  
This will allow Google to correctly list your contact details

Used by: Google,

#### url (Optional)
  
This will allow Triptease and Google to link to your hotel home page.

Used by: Google, Triptease

#### image (Optional)
  
This will allow Google (Search and Maps) to display a thumbnail image next to your name

Used by: Google


### More Reading

[Leverage structured data to turbo-drive your click-through rate](https://www.triptease.com/blog/schema-hoteliers-leverage-structured-data/)

[Markup for Hotels](https://schema.org/Hotel)

[Understand how structured data works](https://developers.google.com/search/docs/guides/intro-structured-data)

[Structured Data Testing Tool](https://search.google.com/structured-data/testing-tool)

[Scheam.org Generator](https://developers.brewerdigitalmarketing.com/generator)

[Schema Markup Generator](https://technicalseo.com/seo-tools/schema-markup-generator/)

[Microdata](https://www.w3.org/TR/microdata/)

### Help

If you are having trouble then why not reach out to your Customer Success Manager or Direct Booking Coach
