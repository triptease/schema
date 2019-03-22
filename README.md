## Welcome to schema.triptease.io

### Overview

[schema.org](http://schema.org/) contains rich rich vocabulary that can be used to help tools read and understand web pages in wide number of domains. 
This page details the markup that can be added to a Hotel page to help not only Triptease products but also increase your SEO and Google listings.  
For feature requests, please use the [Github repository](https://github.com/triptease/schema/). 

### Microdata vs RDFa vs JSON-LD

If the markup is static (like your Hotel name and address) then JSON-LD is generally the easiest to test and debug, while if the meta data is more dynamic (like offers or rate details) 
you may want to use the microdata format embedded in the HTML so that you keep the UI in sync with the meta data.

Triptease supports all 3 formats so if you are already using one then don’t worry about switching.

### Getting started

There are different levels of support for meta data and it's best to start with the simplest and work your way up to more advanced features as you get comfortable.

### 1 - Identification

This is the simplest and most important meta data you can add through out your marketing website and booking engine. Ideally you want this on every page that is focused on a single Hotel. 
Doing this will also automatically allow your Hotel to appear on on Goggle search pages and Google Maps. Just putting the Hotel name and @type on each page will help Triptease 
identify your hotel automatically 

#### JSON-LD Example

```html
<script type="application/ld+json">
{
 "@context": "http://schema.org",
 "@type": "Hotel",
 "name": "Sea View Hotel",
 "brand": "Great Escapes"
 "address": 
  {
  "@type": "PostalAddress",
  "streetAddress": "Jalan Otto Iskandardinata No.16",
  "addressLocality": "Bandung",
  "addressRegion": "West Java",
  "postalCode": "40171",
  "addressCountry": "IDN"
  },
 "telephone": "+62 22 424 0000",
}
</script>

```

Lets walk through this:

#### @type

Make sure you set this to 'Hotel' rather than the more generic 'Organisation' 
(Use Organisation in a separate metadata block to describe your organisation)

Used by: Google, Triptease

#### name 

The name should be unique within Group or Brand

Used by: Google, Triptease

#### brand (Optional)
  
You can put the brand here or as part of the 'name' property but don't put it in both as this might cause the brand to appear twice in some tools.

Used by: Triptease


#### address (Optional)
  
This will allow Triptease and Google to correctly associate your Hotel name with it's location.

Used by: Google, Triptease

#### telephone (Optional)
  
This will allow Google to correctly list your contact details

Used by: Google,

#### link (Optional)
  
This will allow Triptease and Google to link to your hotel home page.

Used by: Google, Triptease

#### image (Optional)
  
This will allow Google (Search and Maps) to display a thumbnail image next to your name

Used by: Google


### More Reading

[Markup for Hotels](https://schema.org/Hotel)

[Leverage structured data to turbo-drive your click-through rate](https://www.triptease.com/blog/schema-hoteliers-leverage-structured-data/)

[Understand how structured data works](https://developers.google.com/search/docs/guides/intro-structured-data)

[Structured Data Testing Tool](https://search.google.com/structured-data/testing-tool)

[Scheam.org Generator](https://developers.brewerdigitalmarketing.com/generator)

[Schema Markup Generator](https://technicalseo.com/seo-tools/schema-markup-generator/)


### Help

If you are having trouble then why not reach out to your Customer Success Manager or Direct Booking Coach
