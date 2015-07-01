- title : Missing Model Mysteries
- description : Exploring the "dark matter" of software
- author : Kijana Woodard
- theme : night
- transition : default

***

# Missing Model Mysteries

## North Dallas .Net User Group
July 1, 2015

###Kijana Woodard

***

##Slides
http://kijanawoodard.github.io/Talk-Missing-Model-Mysteries

***

## Advanced Distributed Systems Design course with Udi Dahan

FREE - 2 days of the 5 day course

###http://particular.net/northdallas

###Code: OWYRYY
###Expires: July  20th

- Distributed Systems Theory
- Coupling: Platform, Temporal, & Spatial
- Bus & Broker Architectural Styles 

###September 7-11: ADSD Course - Austin
###December 1-4: NSBCon 2015
http://particular.net/nsbcon2015

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

NServiceBus forum

RavenDB forum

DDD/CQRS forum

***
## Dark Matter

> Dark matter is a hypothetical kind of matter that cannot be seen with telescopes but accounts for most of the matter in the Universe. The existence and properties of dark matter are inferred from its gravitational effects on visible matter, radiation and the large-scale structure of the Universe.

> [Wikipedia](en.wikipedia.org/wiki/Dark_matter)

***

## Dark Matter of Software	

- Missing Models
- Lurking Business Requirements
- Phantom Business Requirements
- Muzzled Models

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

<!--## A Route

	Driver
	Vehicle
	Stops //location, status [pending, completeted]
-->

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

- Normalize addresses
- Add more status info

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

- We don't want Customers to see Processing status
- We don't want Drivers to see Customer Info
- We don't want Facilities to see Customer Info

***
## Why does this happen?

- Agile iterations can miss the big picture
- Noun-centered thinking

***
## Suggestions

- A Sales Order
- A Delivery Order
- A Processing Order

- A Recurring/Planned Route
- A Route Instance
- A Route Report

***
## Lurking Business Requirements

### Requirements floating in the ether

Hat Tip: [Larry McNutt](https://www.linkedin.com/in/larrymcnutt)

***
## Example

### Invoice Billing
- Send Invoices
- Collect Payments
- Frequent Customers can choose to be invoiced monthly
- We want to be able to extend Credits to Customers
- Customers should be able to pay in advance
- Customers should be able to get refunds of Credit Balances

***
##No one ever mentioned...

### Accounts Receivable System

- Oops, we just built one

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
## Does it clarify the domain? 

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

### Storing Orders 

- Outbound racks are full
- Inbound racks are empty
- Rule: cannot put outgoing order on inbound rack
- App errors won't allow progress
- Ok, I'll lie!

***
> The warehouse is the system of record, not your software.

> [Greg Young](http://geteventstore.com)

***
## Why does this happen?

- Overzealous Data integrity rules
- UX not fully considered
- UX tacked on at the end of the project

***
## What can we do?
***
## SOA + Messaging

> A service is the technical authority for a specific business capability. 

> All data and business rules reside within the service.

> [Udi Dahan](http://www.udidahan.com/2015/02/02/finding-service-boundaries-%E2%80%93-illustrated-in-healthcare/)

- A service is Autonomous
- A service exerts it's authority everywhere

***
## How can SOA + Messaging help?
### Clear separation of concerns

- Sales
- Delivery Management
- Processing

- No shared API
- No shared database

***
## Document Database

- RavenDB
- MongoDB
 
***
## Event Sourcing 

- A log of everything that's happened

***
## Why wouldn't we do this?

- Too hard to deploy applications
- Too hard to create more models
- Too hard to administer more databases
- Too hard to make global changes
- Too hard to introduce new technologies

***

## Discuss

***
## Advanced Distributed Systems Design course with Udi Dahan

FREE - 2 days of the 5 day course

###http://particular.net/northdallas

###Code: OWYRYY
###Expires: July  20th

- Distributed Systems Theory
- Coupling: Platform, Temporal, & Spatial
- Bus & Broker Architectural Styles 

###September 7-11: ADSD Course - Austin
###December 1-4: NSBCon 2015
http://particular.net/nsbcon2015


