- title : Missing Model Mysteries
- description : Exploring the "dark matter" of software
- author : Kijana Woodard
- theme : night
- transition : default

***

# Missing Model Mysteries

## Austin .Net User Group
### February 2, 2015

**Kijana Woodard**

***

## Advanced Distributed Systems Design course with Udi Dahan

FREE - 2 days of the 5 day course.

Valid for the next two weeks only!

###http://particular.net/austin-nug

###Code: KWXBI

- Distributed Systems Theory
- Coupling: Platform, Temporal, & Spatial
- Bus & Broker Architectural Styles 

***
## About Me

Live in Dallas, TX

Programming professionally since 1996

.Net since 1.0

Contracting since 2010

***
## On the web

@kijanawoodard

http://kijanawoodard.com

RavenDB forum

DDD/CQRS forum

NServiceBus forum

***
## Dark Matter

> Dark matter is a hypothetical kind of matter that cannot be seen with telescopes but accounts for most of the matter in the Universe. The existence and properties of dark matter are inferred from its gravitational effects on visible matter, radiation and the large-scale structure of the Universe.

> [Wikipedia](en.wikipedia.org/wiki/Dark_matter)

***

## Dark Matter of Software	

- Missing Models
- Lurking Business Requirements
- Phantom Business Requirements
- Strangled Business Requirements

***

> Essentially, all models are wrong, but some are useful. 

> [George E. P. Box](http://en.wikiquote.org/wiki/George_E._P._Box)

***
## Missing Models

> When being confronted with "complex projections" it's a sign one should reflect whether or not one is missing a model that is able to answer a question.

> [Yves Reynhout](https://seabites.wordpress.com/) - DDD/CQRS forum Jan 20, 2015

***

## Domain
###Mobile Dry Cleaning and Laundry

- Customers bring Garments to convenient Locations [e.g. their office]
- Drivers pick up Orders at the Locations
- Central Facilities clean the Garments
- Drivers take Orders back to Location

***

## An Order
	Order Number	
	Customer Info //name, phone, email, etc
	Garments //type, special instructions, etc
	Location //1313 Mockingbird Ln, SomeTown USA
	Order Status //pending, processing, delivered

## A Route

	Driver
	Vehicle
	Stops //location, status [pending, completeted]

***
## New Requirement!

***

## Killer Feature

### Separate pick up and drop off locations

***
## An Order
	Order Number	
	Customer Info //name, phone, email, etc
	Garments //type, special instructions, etc
	Pickup Location //1313 Mockingbird Ln, SomeTown USA
	Drop Off Location //512 Main St, NearTown USA
	Order Status //pending, processing, delivered

***
## New Requirement!
###  It's hard to organize Drivers

- Please normalize addresses.
- Add more status info.

***
## An Order
	Order Number	
	Customer Info //name, phone, email, etc
	Garments //type, special instructions, etc
	Pickup Location //locations/1
	Drop Off Location //locations/15
	Order Status //pending, picked up, processing, en route, delivered

***
## New Requirement!
### We need better visibility at Facilities

***
## An Order
	Order Number	
	Customer Info //name, phone, email, etc
	Garments //type, special instructions, etc
	Pickup Location //locations/1
	Drop Off Location //locations/15
	Order Status //pending, picked up, prep, perc, package, en route, delivered

***

## Problems!

***
## An Order
	Order Number	
	Customer Info //name, phone, email, etc
	Garments //type, special instructions, etc
	Pickup Location //locations/1
	Drop Off Location //locations/15
	Order Status //pending, picked up, prep, perc, package, en route, delivered

- We don't want customers to see Processing status
- We don't want Drivers and Facilities to see Customer Info

***
## New Requirement!
### We need Custom Locations

- One time pick up or drop off locations
- Show recent custom locations

***
## An Order
	Order Number	
	Customer Info //name, phone, email, etc
	Garments //type, special instructions, etc
	Pickup Location //1313 Mockingbird Ln???????
	Drop Off Location //?????
	Order Status //pending, picked up, prep, perc, package, en route, delivered

***
## Correction

- A Customer Order
- A Delivery Order
- A Processing Order
- A Planning Route
- An In Progress Route
- A Route Report

***
## Why does this happen?

- Agile iterations missing the big picture
- Noun-itis

***
## Lurking Business Requirements

### Requirements floating in the ether

Hat Tip: [Larry McNutt](https://www.linkedin.com/in/larrymcnutt)

***
## Example

### Invoice Billing
- Frequent Customers can choose to be invoiced monthly
- We want to be able to extend Credits to Customers
- Customers should be able to pay in advance
- Customers should be able to get refunds of Credit Balances

***
## Accounts Receivable System
### Oops, we just built one

- Can be extreme

***
## Why does this happen?

- Inexperienced developers
- Insufficient domain conversations
- Stakeholders underestimate relative weights

***

## Phantom Business Requirements
### Inferred requirements that never seem to materialize
Hat Tip: [Dan Bishop](https://github.com/Bishbulb)

***
## Example

### Mandatory Stops
- Even if there are no Orders for a Location, drive there anyway
- Drop off marketing materials, garment tags, etc

***
## Feels like a Lurking Business Requirement

***
## Implementation

- Add flag to Location?
- Is it a Route feature?
- Do we need to model "Marketing Materials"?

***
## Does it clarify or muddle the domain? 

- Do the users want to talk about this?
- Are you adding more code and tests to prop up this feature?

***
## Why does this happen?

- Experienced developers
- Don't want to miss something important

***

## Muzzled Models

### Model is artificially constrained for non-business reasons

Hat Tip: Me

***
## Example

### Long form with required fields

- Don't have one piece of information
- Leave computer to get it
- Session Expired!

***
## Example

### Loading Orders on Truck

- Dispatcher marks Truck as unavailable
- Driver is trying to Load truck
- App errors and won't allow progress
- Lies!

***
## Why does this happen?

- Data integrity
- UX Not fully considered
- UX tacked on at the end of the project

***
## Messaging - SOA

> A service is the technical authority for a specific business capability.

> [Udi Dahan](http://www.udidahan.com/2015/02/02/finding-service-boundaries-%E2%80%93-illustrated-in-healthcare/)

***
## How can Messaging help?

- Clear separation of concerns
- Could these be separate applications? 

***

## Thank you!

***

## Discuss

***
## Advanced Distributed Systems Design course with Udi Dahan

FREE - 2 days of the 5 day course.

Valid for the next two weeks only!

###http://particular.net/austin-nug

###Code: KWXBI

- Distributed Systems Theory
- Coupling: Platform, Temporal, & Spatial
- Bus & Broker Architectural Styles 


