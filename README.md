# What2Do2Day
[![what2do2day](documentation/images/w2d2day%20logo.png "What2do2day App")](http://what2do2day.herokuapp.com/)

[what2do2day - An app to match kids up with free events in their neighborhoods](http://what2do2day.herokuapp.com/)
## Author
Malia Havlicek
## Project Overview
[![what2do2day](documentation/images/ResponsiveScreenShot.png "What2do2day App")](http://what2do2day.herokuapp.com/)

[What2do2day](http://what2do2day.herokuapp.com/) provides people a way to find free events in their community as a means to solve the question of "What are we gonna do today?" without breaking the bank or needing to travel far from home. Along with finding inexpensive options of what to do today, the site allows users to flag that they are planning on attending an event so other members know they will not be the only one going to a function. The target user for this app is 12 -18 years of age: children who are independent without individual transportation or lots of spare change. 

Users can also view a list of all the places in the community and read reviews about them and see all the future events associated with a given place. Members of the community can add reviews about places to share their experiences and rate organizations. The website has a crisp, young feel to it and was built with ease of use and a younger audience in mind. 

Possibilities to monetize this site abound. Site owners can easily add affiliate linking from any organization listed on the site that results in a sale by appending attributes to the place's URL. By adding a Google Click Identifier (GCLID) to a place's website when leaving What2Do2Day's site, offline conversions could be tracked and negotiated to a monetary value for the site owners. Site admins can also examine site data and sell ads on this site to help earn money by targeting audiences of similar interests. (Note how the Places' page on desktop has natural sidebars when users are looking at events and reviews, On mobile devices ad space could be inserted below filtering options and above the footer too.) The site can easily be scaled up to include more predefined age ranges if the market determines there is a need or re-skinned for older age groups under a different name if so desired.

The name and concept of this site is loosely based on the key phrase, "I know what we're gonna do today!" from the cartoon series [Phineas and Ferb](https://en.wikipedia.org/wiki/Phineas_and_Ferb).

<details>
<summary>Table of Contents</summary>

  * [UX](#ux)
    + [Strategy](#strategy)
    + [Scope](#scope)
    + [Goals](#goals)
      - [Customer Goals](#customer-goals)
      - [Place Owner Goals](#place-owner-goals)
      - [WebSite Goals](#website-goals)
  * [Structure](#structure)
    + [Database Choice](#database-choice)
    + [Data Models](#data-models)
    + [Collections Data Structure](#collections-data-structure)
      - [Activities](#activities)
      - [Addresses](#addresses)
      - [Countries](#countries)
      - [Events](#events)
      - [Metrics Clicks](#metrics-clicks)
      - [Metrics Page](#metrics-page)
      - [Places](#places)
      - [Reviews](#reviews)
      - [Users](#users)
    + [Skeleton](#skeleton)
      - [Content Considerations](#content-considerations)
  * [Design Choices](#design-choices)
    + [Surface:](#surface-)
      - [Color Choice](#color-choice)
      - [Typography](#typography)
      - [Image Choice](#image-choice)
        * [Home Page](#home-page)
        * [Activity Icons](#activity-icons)
        * [Input Icons](#input-icons)
        * [Header Image](#header-image)
        * [Modals and Errors](#modals-and-errors)
        * [Loading Giff](#loading-giff)
      - [Design Elements](#design-elements)
      - [Animations & Transitions](#animations---transitions)
    + [User Stories:](#user-stories-)
      - [For kids looking for something free to do today in their neighborhood:](#for-kids-looking-for-something-free-to-do-today-in-their-neighborhood-)
      - [For places and organizations involved in building the community](#for-places-and-organizations-involved-in-building-the-community)
      - [For site owners hosting a website to store community information](#for-site-owners-hosting-a-website-to-store-community-information)
  * [Features](#features)
    + [Implemented Features](#implemented-features)
      - [Structural](#structural)
      - [Common Elements](#common-elements)
      - [Forms](#forms)
      - [Database Operations](#database-operations)
      - [API Integration](#api-integration)
      - [Metrics](#metrics)
    + [Features Left to Implement](#features-left-to-implement)
      - [Features Deferred from original plan](#features-deferred-from-original-plan)
      - [User Roles & Permissions](#user-roles---permissions)
      - [Place Administrator Dashboard](#place-administrator-dashboard)
      - [External User Adult Dashboard](#external-user-adult-dashboard)
      - [External User Minor Dashboard](#external-user-minor-dashboard)
      - [Content Admin Dashboard](#content-admin-dashboard)
      - [Site Admin Dashboard](#site-admin-dashboard)
      - [More Sophisticated Attendance Tracking](#more-sophisticated-attendance-tracking)
      - [API Integrations](#api-integrations)
      - [Switch to Relational Database](#switch-to-relational-database)
    + [Project Tracking](#project-tracking)
  * [Technologies Used](#technologies-used)
    + [Programming languages](#programming-languages)
    + [Framework & Extensions](#framework---extensions)
    + [Fonts](#fonts)
    + [Tools](#tools)
    + [APIs](#apis)
  * [Testing](#testing)
    + [Validation Testing](#validation-testing)
    + [Unit Testing](#unit-testing)
    + [Cross Browser/ Cross Device Verification](#cross-browser--cross-device-verification)
    + [Cross Site Scripting and Forgery](#cross-site-scripting-and-forgery)
    + [Accessibility Testing](#accessibility-testing)
    + [Regression Testing](#regression-testing)
    + [Automated Testing](#automated-testing)
    + [Defect Tracking](#defect-tracking)
      - [Noteworthy Bugs](#noteworthy-bugs)
      - [Outstanding Defects](#outstanding-defects)
  * [Deployment](#deployment)
    + [GitHub](#github)
      - [Requires](#requires)
      - [Running Locally](#running-locally)
    + [Heroku](#heroku)
      - [Deployment To Shared Environment](#deployment-to-shared-environment)
  * [Credits](#credits)
    + [Content](#content)
    + [Media](#media)
    + [Acknowledgements](#acknowledgements)
    
</details>

## UX
### Strategy
Before launching any website, business partners want to know how they can earn money and if there is a need or demand for the project. Defining business goals for a project from the standpoint of an external user as well as site owners helps you evaluate possible returns on investment.

I had a couple of [ideas](documentation/proejct_definition.md) in mind that could fulfill the requirements of this project and wrote out high-level user goals to aid in determining which project would work best. What2do2day was the winner.

### Scope
The concept of What2Do2Day can get extremely intertwined when looking at permissions and roles. I decided that a beta version that eliminates authentication, permissions and roles can still provide a clean and efficient minimal viable product (MVP).  Thus user-profiles and management of users will not be in the first deliverable. 

Restricting results based on user's location increments of 1, 5, and 10 miles would be ideal for a long term solution but it is not necessary for the MVP. Simply put, not enough data will be loaded to make searching and geolocation viable initially.

For the MVP, users do not need to be registered, verified or logged in. Creating options are consolidated under a Contribute menu and can easily be moved behind permissions at a later date. Likewise, updating including deleting functionality will only be accessible from the Update menu option. This allowed the MVP to be built to serve the majority of long term users and kept the UX cleaner without an overwhelming amount of buttons. 

Ideally, the update functions would be hidden behind administrative roles. Likewise, adding functions would be distributed across another set of users as adding a review is much less restricted than adding events and places. A long term project would also look at providing admin proximity/ease of use functionality by including cloning options. 

The MVP solution consolidates the Delete functionality into a toggle which shares and event, or place on the site. This property eliminates helper pages to develop and reduces the number of items in the menus which makes overall navigation easier while protecting the data's integrity by avoiding jumps in auto-generated id's.

Business logic to track the pages and the events and places that users interact with will be collected.  This will aide in negotiating affiliate link deals and ads will be include. The user click data being collected does include which pages the click occurred on but funnel reports will not be included in the MVP, only a count of the pages and clicks collected ordered by max to min. 

### Goals
#### Customer Goals
The target audience for What2do2day is children ages 12-18 who have a bit of freedom to move around unsupervised but very little means to addend costly mass entertainment complexes.

Customer Goals are:

- Bring up the site and look for an event to attend close to home
- Look at places to see how they rank without having to read much
- Quickly find activities that interest them without having to type much
- Read reviews about places that interest them
- See events related to places that interest them
- Easily know where an event they are interested in is located
- Join an event of interest
- See how many others are interested in an event
- Receive notification about an event they've joined
- Receive updates about events they've joined

What2do2day helps the customer meet these goals because:

 - The application was developed around easily and intuitively Listing Events, Places, writing reviews and Joining events from the planning stages to the end of development.
 - All the navigation is done either by the clearly identified nav bar or from clearly labeled buttons on list pages.
 - Icons and Text accompany all buttons to make the intent of the button's action more easily understood
 - Forms have place holder text to help guide users to successful completion
 - Forms have validation and logical error messages and colors to help aid users to successful form completion
 - Details that are not relevant to quick browsing are omitted on the events page so users can see more options at a time in order to find something to do more quickly. 
 - Allowing event filtering by icons and name pairs, date ranges and age limits
 - Listing aggregated ratings with the number of reviews to show community engagement
 - Sending emails when users join an event
 - Sending emails when an event is updated to all users that have joined it
 - Listing the number of available spots and adding text that lets users know if the event is full or close to being filled
 - By proving a map on the count me in layer
 - By providing a map on the lists page
 
#### Place Owner Goals

Owners of Places would ideally have a different set of user permissions and the Update and Contribute sections of navigation would be under a strict workflow, but in the initial phase, I wanted to show off the ability to add, update and delete items from the website's view so it's not hidden behind permissions or workflow at this point.
Place owners are those that have a business or an organization that hosts free events within a community. Examples are a group that wants to play pickup soccer or a bicycle shop that leads group rides once a month.

Place Owner Goals:

- I want my place to be easily found on the site so I can get more customers
- I want users to share community reviews so I build trust with future customers
- I want to add events to my place to build a repertoire with my clients 
- I want users to join my events so I can track how successful community events are to my bottom line
- I want the ability to update my place's details
- I want to update events associated with my organization
- I want to protect against bloated ratings
- I want to protect against accidental deletion of my information

What2do2day aides Place Owners by:

 - Listing places alphabetically on the website
 - Associating activity icons to events and places in an iconic format
 - Listing events on the website by most recent 
 - Allowing event filtering by icons and name pairs, date ranges and age limits
 - Allows users to enter a review for a place only once a week
 - Tracks users that want to attend an event
 - Soft deletes information so events are not completely lost
 - Will have specific workflow and permissions in its final deployment
 
 #### WebSite Goals
 The primary goal of what2do2day is to create a user-friendly app that allows customers to quickly find an event they want to attend. It's a meeting point between business/organizations and kids/parents to improve the likelihood of kids getting off their devices and interacting with others face to face at a low cost with minimal supervision.
 
 What2do2day has three main audiences: 

  - Kids looking for something to do with others that have similar interests
  - Businesses looking to build a repertoire with the community looking to build a follower base within the community
  - Parents wanting to loosen the reigns and build trust with their kids by allowing them to attend community events without direct parental involvement
 
 In order to support the maintenance and development of cool features on the site, what2do2day hopes to produce monetary gains through the following means:
 
 - Workflow Management Plans for Businesses around:
   - oversee approval/disapproval of reviews to ensure spamming and bad-mouthing in reviews does not occur
   - batch event creation to help save time
   - user account management to help with password recovery and assigning or removing roles as employees change
   - sharing of user emails that attend events
 - Affiliate linking - link to at-cost services provided by businesses and receive a kickback
 - Ads - target online sales related to equipment based on activities a place or event is associated with

## Structure

While it was tempting to start with the UI immediately, I took the time to look into the data I wanted to present on the site. My first stop was to look at Google's Maps Places API to determine what fields the Place object should have. Knowing the data fields I may want to have and those that were extraneous, helped me devise an Entity Relationship Diagram(ERD). 

![final](documentation/images/data_model/Final%20Data%20Diagram-Objects%20For%20App.png)

Like all projects, the data model morphed a few times. [See progression of data models.](documentation/data_model.md)

### Database Choice
As a course requirement, this project was based on a NoSQL database structure. While the project's data is better suited for a relational database such as SQL, MongoDB was used. 

### Data Models
Data stored in what2do2day's MongoDB consist of these types:
- ObjectId
- String
- Double
- Int32
- Array
- Boolean
- Date

### Collections Data Structure
There are 9 data structures associate with what2do2day despite eliminating user permissions and roles:
- Activities
- Addresses
- Countries
- Events
- Metrics Clicks
- Metrics Pages
- Places
- Reviews
- Users

#### Activities
Activities is a table to hold a unique icon image and name values that users have associated with events and places. It helps with sorting events and prevents the need from carrying around two data objects in the larger Events and Places data structures. The purpose of an Activities object is to provide an imagery association to a category.

| DB Key 	| Data Type 	|          Purpose          	| Form Validation                        	| DB processing    	|
|--------	|:---------:	|:-------------------------:	|----------------------------------------	|------------------	|
| _id    	| ObjectId  	| unique identifier         	| None                                   	| n/a              	|
| name   	| String    	| Name of Activity          	| Required<br>Min 1 char<br>Max 50 chars 	| trim<br>to lower 	|
| icon   	| String    	| system path to image file 	| Required                               	|                  	|

- [x] Create
- [x] Read
- [ ] Update
- [ ] Delete

Activity entries are used by events, places and filtering.

The Activities table is read when a user is adding an event, updating an event, adding a place or updating a place, to determine if a new value should be created or not. The activities table is queried for using the name and icon pair, if it is found, the ObjectId is passed to the event and places. If no match is found, a new Activity is created and that ObjectID is passed to the the place or event.
 
 This table has no deletion or updates associated with it. It's strictly create and read. Eventually, maintenance scripts should be written to delete unused/deprecated entries.
An activity is potentially created when a user successfully creates a place, creates and event, updates an event, or updates a place. 

The reading/writing of the activities table is housed in the [views.py](what2do2day/activities/views.py) file.
#### Addresses
Addresses are optionally entered in association with Places and Events. This data structure is used by both Events and Places to provide users with a physical location. Only the _id is stored in Places and Events to reduce the amount of data being stored as many places may use the same address as a meeting point for their events.

| DB Key          	| Data Type 	|             Purpose             	| Form Validation                                                                                                                                                                      	| DB processing    	|
|-----------------	|:---------:	|:-------------------------------:	|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------	|------------------	|
| _id             	| ObjectId  	| unique identifier               	| None                                                                                                                                                                                 	| n/a              	|
| address_line_1  	| String    	| Street Address                  	| Required<br>Min 1 char<br>Max 50 chars                                                                                                                                               	| trim<br>to lower 	|
| address_line_2  	| String    	| Building, Suite, Unit Number    	| Optional<br>Min 1 char<br>Max 50 chars                                                                                                                                               	| trim<br>to lower 	|
| city            	| String    	| City                            	| Required<br>Min 1 char<br>Max 50 chars                                                                                                                                               	| trim<br>to lower 	|
| state           	| String    	| State/Region                    	| Required<br>Min 1 char<br>Max 50 chars                                                                                                                                               	| trim<br>to lower 	|
| postal_code     	| String    	| Postal Code                     	| Optional<br>min 2 char<br>first char must be a character<br>2nd char must be number or character or dash<br>must be no longer than 11 characters<br>must end with a number of letter 	| trim<br>to lower 	|
| country         	| ObjectID  	| Cross Reference to Countries    	| Required                                                                                                                                                                             	|                  	|
| lat             	| Double    	| Latitude Map value              	| system generated via google maps API                                                                                                                                                 	|                  	|
| lng             	| Double    	| Longitude Map value             	| system generated via google maps API                                                                                                                                                 	|                  	|
| one_line        	| String    	| One line address representation 	| system generated for future maps interactions                                                                                                                                        	|                  	|
| google_place_id 	| String    	| Unique Place ID for google Maps 	| system generated via google maps API                                                                                                                                                 	|                  	|


- [x] Create
- [x] Read
- [ ] Update
- [ ] Delete

Users input address_line_1, address_line_2, city, state, country and postal_code values. The system checks to see if the user entered data is already in the database and if not it will call Google Map's API to retrieve the google_place_id, latitude and longitude values so maps can be rendered without requesting those pieces of information each time a list of event is displayed on the site. Address ObjectId's are associated withe events and places.

Addresses cannot be updated or deleted, they are only added or read, so long term, there should be a process that checks for unused addresses and delete those items as part of a cleanup process.

#### Countries
Countries are cross referenced to addresses. Since the list of countries is long and does not change often this collection was initialized via the helper countries.py helper function
```$ python helpers/upload_countries.py ```
It is a read only table after being initialized.

| DB Key  	| Data Type 	|      Purpose      	| Form Validation 	| DB processing 	|
|---------	|:---------:	|:-----------------:	|:---------------:	|---------------	|
| _id     	| ObjectId  	| unique identifier 	| None            	|               	|
| country 	| String    	| Country's name    	| None            	| to lower      	|

- [ ] Create
- [x] Read
- [ ] Update
- [ ] Delete

The ObjectId for a country is stored in an address. It's used to populate the address collection country drop-down menu. When displaying Places and Events to the screen, the Countries table is queried to provide a textual value for the country associated to an address.


#### Events
Events are one of the more complex data structures in What2do2day. An event has cross references to places, addresses, activities, and users and has some data attributed by a call to google maps api:

| DB Key                	| Data Type 	|          Purpose         	| Form Validation                                                                                                                                            	| DB processing                                	|
|-----------------------	|:---------:	|:------------------------:	|------------------------------------------------------------------------------------------------------------------------------------------------------------	|----------------------------------------------	|
| _id                   	| ObjectId  	| unique identifier        	| None                                                                                                                                                       	|                                              	|
| place                 	| ObjectId  	| Place Id                 	| Required                                                                                                                                                   	|                                              	|
| name                  	| String    	| Name of Event            	| Required<br>min 1 char<br>max 50 char                                                                                                                      	| trimmed<br>to lower                          	|
| date_time_range       	| String    	| Date Time Range of Event 	| Required<br>Format: MM/DD/YYYY HH:MM - MM/DD/YYYY HH:MM<br>Start Date in future<br>End Date >= Start Date<br>If Start Date = End Date EndTime > Start Time 	|                                              	|
| activity              	| ObjectId  	| Activity Id              	| Required                                                                                                                                                   	|                                              	|
| details               	| String    	| Event Details            	| Required<br>min 1 char<br>max 500 char                                                                                                                     	| trim                                         	|
| age_limit             	| Array     	| Ages allowed in event    	| Required<br>1 or more choices                                                                                                                              	| If No-limit in array<br>only upload no-limit 	|
| price_for_non_members 	| String    	| Optional price           	| Optional<br>min 1 char<br>max 50 char                                                                                                                      	| trim                                         	|
| address               	| ObjectId  	| Address of event         	| Optional                                                                                                                                                   	|                                              	|
| max_attendees         	| Int32     	| Number of attendees      	| Required<br>min 1<br>max 1000                                                                                                                              	|                                              	|
| attendees             	| Array     	| array of users           	| Updated when user joins event                                                                                                                              	|                                              	|


- [x] Create
- [x] Read
- [x] Update
- [ ] Delete

Before an event is added to or updated, a uniqueness check is done to ensure the name and date/time combination is unique for events associated to the place. If the event already exists, the user is presented error messaging and routed back to the Events List Page or Update Events List Page.

The attendees list for an event is updated when a user interacts with the Join Event (Count Me In) functionality. First the Events database is read to determine if the max number of attendees has been met, and if not, the user is added to the attendee list.  

Due to the lack of user roles or permissions deletions of events do not happen. Events can be turned off via a soft delete by updating the share property. Ideally past events would be deleted and cleaned out of the databases if they have not been revised in a month to save space and reduce the number of records to keep the database efficient.

#### Metrics Clicks
The Metrics Clicks collection serves the purpose of tracking clicks by names related to the action the user is taking. Typically data-trigger attributes are set to buttons and links by a developer and handlers will then write to the database when the button or link is clicked through an ajax post. When a template is rendered, the app developer has to set the page value so the reporting will attribute the click the page.

| DB Key    	| Data Type 	|               Purpose              	| Form Validation            	| DB processing 	|
|-----------	|:---------:	|:----------------------------------:	|----------------------------	|---------------	|
| _id       	| ObjectId  	| unique identifier                  	| None                       	| n/a           	|
| link_name 	| String    	| reflects purpose of link or button 	| None, set by app developer 	| n/a           	|
| date      	| Date      	| track time of user click           	| None, auto generated       	| n/a           	|
| page      	| String    	| Page click initiated from          	| None, set by app developer 	| n/a           	|
| method    	| String    	| button or link                     	| None, set by app developer 	| n/a           	| 


- [x] Create
- [x] Read
- [ ] Update
- [ ] Delete

The metrics click data is read through an aggregated query to get counts by name and presented on the Metrics page. At a future point, funnels for joining events could be queried and analyzed to determine.

The design decisions around metrics can be found in the Clicks tab of this [google doc](https://docs.google.com/spreadsheets/d/1IRcafdaRZDiYhr5YtFVhcnb1w3mtcNLNPzOdSg6LiX4/edit?usp=sharing).

There are no updates or deletions to the metrics data. Ideally old data would be rolled up after a specific amount to save on disk space.

#### Metrics Page
The page metrics collection just holds page visited data:

| DB Key 	| Data Type 	|         Purpose        	| Form Validation            	| DB processing 	|
|--------	|:---------:	|:----------------------:	|----------------------------	|---------------	|
| _id    	| ObjectId  	| unique identifier      	| None                       	| n/a           	|
| name   	| String    	| Page click use visited 	| None, set by app developer 	| n/a           	|
| type   	| String    	| page or modal          	| None, set by app developer 	| n/a           	|

The metrics page data is read through an aggregated query to get counts of clicks by name and presented on the Metrics page. At a future point, it might be nice to see how more events are joined, initiated from the Places page or the Events page.

The design documentation around the pages metrics can be found in the Page tab of the [metrics spreadsheet](https://docs.google.com/spreadsheets/d/1IRcafdaRZDiYhr5YtFVhcnb1w3mtcNLNPzOdSg6LiX4/edit?usp=sharing).
#### Places
The places object is another major player in what2do2day and is built mostly by user input.

| DB Key      	| Data Type 	|                      Purpose                      	| Form Validation                       	| DB processing    	|
|-------------	|:---------:	|:-------------------------------------------------:	|---------------------------------------	|------------------	|
| _id         	| ObjectId  	| unique identifier                                 	| None                                  	| n/a              	|
| name        	| String    	| Name of place                                     	| Required<br>min 1 char<br>max 50 char 	| trim<br>to lower 	|
| address     	| ObjectId  	| Cross reference addresses table                   	| Optional                              	|                  	|
| user        	| ObjectId  	| Cross reference users table                       	| Required                              	|                  	|
| phone       	| String    	| Contact number of place                           	| Optional                              	|                  	|
| website     	| String    	| url of place                                      	| Optional                              	| trim             	|
| image_url   	| String    	| url of image on web                               	| Optional                              	| trim             	|
| share_place 	| Boolean   	| Used to hide places from list view<br>soft delete 	| Required                              	|                  	|
| activity    	| ObjectId  	| Cross reference activities table                  	| Required                              	|                  	|


- [x] Create
- [x] Read
- [x] Update
- [ ] Delete

While the user input from to collect a place gathers an email, an address, event and potentially another address and a review, the table only stores data related to the place object. 

Before a place is added or updated to the database, the Places database is ready to ensure the place's name and address (if one is present) is checked to be unique in the database. This allows franchises to co-exist in the system and prevents places from being updated to collide or stomp on other places in the system.

If the places is unique and the user is adding a place, then a new entry is written to the Places database.
If the user is updating a place, the uniqueness check is done as well. The name and or address can change and the place will be updated as long as it does not collide with another entry in the database.

Places are not deleted from the system. They can be updated to not be shared as a soft_delete. Ideally once business accounts are set up, then there would be admin functions to delete places that have been flagged as business in poor standing or who have not hosted an event in a specified amount of time or places. 

#### Reviews
Reviews are one of the simpler user objects on the site that requires user input for creation, but it's data structure is quite a bit more complex than the user entry form:

| DB Key   	| Data Type 	|                              Purpose                             	| Form Validation                       	| DB processing 	|
|----------	|:---------:	|:----------------------------------------------------------------:	|---------------------------------------	|---------------	|
| _id      	| ObjectId  	| unique identifier                                                	| None                                  	| n/a           	|
| place    	| ObjectId  	| cross references place                                           	| Required                              	| n/a           	|
| user     	| ObjectId  	| cross references user                                            	| Required                              	| n/a           	|
| rating   	| Int32     	| rating of place                                                  	| Required<br>Integer<br>min 1<br>Max 5 	| n/a           	|
| comments 	| String    	| User's opinion about the place                                   	| Required<br>min 1<br>max 500          	| trim          	|
| share    	| Boolean   	| Used to hide a review from the place's review list (soft delete) 	| Required                              	|               	|


- [x] Create
- [x] Read
- [ ] Update
- [ ] Delete

Before a review is added to the database, the user and the date and name are queried to ensure the user hasn't reviewed the place within the last week to avoid bloating of the aggregated rating for a given place.

Reviews are initiated from the Add Place form, by the add review button on the places list page.  Reviews cannot be updated at this time but would be part of a workflow before being shared in a future release.

At this time reviews are not removed from the database. Ideally there would be a workflow process defined to help delete profaine and robot generated reviews as well as reviews from dormant reviews or reviews associated with deleted places.

#### Users
The user is a very simplistic representation at this time. It's only the email. It's not verified, and it cannot be updated, and it dose not roles or permissions.

| DB Key 	| Data Type 	|                  Purpose                 	| Form Validation          	| DB processing               	|
|--------	|:---------:	|:----------------------------------------:	|--------------------------	|-----------------------------	|
| _id    	| ObjectId  	| unique identifier                        	| None                     	| n/a                         	|
| email  	| String    	| minimalistic view of a user, their email 	| Required<br>email format 	| to lower<br>unique in table 	|

- [x] Create
- [x] Read
- [ ] Update
- [ ] Delete

User are added to the database when adding a place, joining an event, or adding a review. 

Before a user is added to the Users database, the email is checked to see if it is already in the system or not. Users are aggregated into the review list seen on the places list page with the email. The user's ObjectId is added to reviews and the list of attendees for an event. The user's email is used a means to communicate event updates and joining via STMP mail.

The user is also cross referenced to a place as a creator. Ideally there would be an array of users that would have ownership and permissions to update a place.

Users cannot be updated or deleted at this time. 

### Skeleton
Having a rough data structure in hand, I knew what data fields I could present users managing the PLACES, EVENTS and REVIEW objects. I'm not a great artist but I find it easier start hand drawn markups before diving into a wireframing tool. I drafted out the home screen as well as the places list to kick start decisions concerning what data had a higher priority.
[view hand-drawn mockups](documentation/hand-drawn.md)

Once I had the Places list drawn out, I invested several hours to mockup and fine-tune the user experience using Balsamiq.
[view Balsamiq deck](documentation/balsamiq.md)

Taking the time to do more formal mockups exposed an issue with the crowding of edit buttons and delete buttons if I chose to clone the list pages and add buttons for updating and deleting. I decided that delete is really an update function since I am using a share attribute to hide or show items on the Places and Events pages.  The more formal mockups also allowed me to try several different layouts of the data for the main list pages. The mock-ups include layers for searching and in site adding of reviews. Search non-happy paths were also mocked up. 

Please note, the mockups were a guideline but not a hard design tool. Some aspects changed during development to make the site more user friendly and intuitive to use.

#### Content Considerations
Many UX decisions made had the target audience of 12 - 18 years in mind. The lack of maps on some pages was a conscious choice as the majority of users will be very familiar with the 1-5 mile radius around their home base. I wanted information spaced out with iconic/graphic identification so the users would know readily what interest the the most with limited reading required. 

## Design Choices
The application is aimed at users 12-18 in age. The intent is to provide a clean, intuitive design to users with engaging imagery and animation to spice up the views and keep users engaged. 

### Surface:
Below are the decisions and internal dialogs I had to help draw out what the end product will look like.

#### Color Choice
I have never taken a course in color theory and have been told my choices of red are more orange than red so picking colors is a bit of a touchy area for me and I'd much rather have a professional UX designer help me out.  Feel free to read about this [project's color journey](documentation/color_choices.md) if you want to hear more about my struggle.  In short, my final color choices are:
![Final Pallet](documentation/images/colors/final_colors.png)

The Green color is the dominate color on the site used to highlight cards, icons and buttons. The dark gray is used on accordions and as a text color,e the lighter gray is used to help delineate event dates. The red is an accent color for error messaging on forms. White is the background filler color but when the grays are used it becomes an icon or text color.

#### Typography
The target age group for this site is those that are young, bored at home whose parents desperately wish their kids would be outside interacting face to face with friends preferably doing something active.

To keep the site light and fun, I really wanted a cartoon feel to my headers that wouldn't have issues between uppercase i's and lower case L's. After some research I ended up choosing **Patrick Hand SC**:
>[![Patrick Hand SC](documentation/images/fonts/Patrick%20Hand%20SC.png "Patrick Hand SC Font")](https://fonts.google.com/specimen/Patrick+Hand+SC)

For my main content, I wanted a curvy flow to the font, but one that was easy to read without any i's and L's issues. I tested out a few fonts and decided on **Raleway**:
>[![Raleway](documentation/images/fonts/Raleway.png "Raleway Font")](https://fonts.google.com/specimen/Raleway)

Feel free to read about my [font choices](documentation/font_choices.md) if you want to know more about my decision process. 

#### Image Choice
This site's target audience is 12-18 years in age and they have a higher demand for imagery than older user groups do so I placed engaging imagery across the site:

##### Home Page 
To perpetuate the theme of Phineas and Ferb throughout the site, the cartoon's beginning image where Phineas and Ferb are in their back yard looking bored, chatting about what to do today is on the home page:

<img src="what2do2day/static/assets/images/were_gonna_build_a_rollercoaster_sm.jpg" width="300" height="auto" alt="Phineas and Ferb in backyard" />

##### Activity Icons
I wanted easily recognizable activities that users could quickly associate to events and places. I also wanted to give users a bit of self expression when creating events and places, so rather than allowing them to randomly load garish or naughty symbols, I decided to provide a broad set of icons to passively create activities from. I downloaded icons from [flaticon](https://www.flaticon.com/packs/outdoor-activities-32)
By having bold colorful icons, I am hoping to carry forward a cheerful and engaging website. Here are some example activity icons:

<img src="what2do2day/static/assets/images/icons/002-football-field.svg" width="50" height ="50" alt="football field icon"/> <img src="what2do2day/static/assets/images/icons/021-fishing.svg" width="50" height ="50" alt="fishing icon"/>  <img src="what2do2day/static/assets/images/icons/037-road-sign.svg" width="50" height ="50" alt="trail directions icon"/>

##### Input Icons
The site looked incredibly dull with wide full width entry fields, so I went back and broke it down into multiple columns and added slight splashes of color with icons relating to the input fields utilizing the primary site color and font awesome icons:  

<img src="documentation/images/form_fields.png" width="100%" height="auto" alt="form field image"/>

##### Header Image
The rest of the application's pages were not exciting compared to the home page, so I added in Perry the Platypus to my header with grass as seen in Phineas and Ferb's backyard. Perry's a character in Phineas and Ferb that goes from a boring pet to a super secret agent saver of the universe. By placing Perry at the top of every page except the home page, I am hoping to start the user off with a subconscious reminder to let your imagination be boundless before they start searching for something to do. 

<img src="what2do2day/static/assets/images/perry_the_platypus.png" width="50" height="auto" alt="perry the platypus" />

##### Modals and Errors
I wanted users to know through imagery that they had success or errors so I trolled the internet until I found a few Phineas and Ferb related images that would work.

 Phineas and Ferb giving each other a high five shows up on success layers: 
 
 <img src="/what2do2day/static/assets/images/success.png" width="100" height="auto" alt="success cheer image" />

Dr. Heinz Doofenshmirtz looking dumbfounded makes an appearance on user based failure layers: 

<img src="what2do2day/static/assets/images/oops.png" width="100" height="auto" alt="opps error image" />

Ferb wielding tools is on the application's catch all error page:  

<img src="/what2do2day/static/assets/images/fixit.png" width="100" height="auto" alt="fixit image" />

##### Loading Giff
I also added a loading gif for the maps in the event the API calls are a tad slow or if there are errors with google's API/configuration: 

<img src="what2do2day/static/assets/images/giphy_load.gif" width="100" height="auto" alt="opps error image" />


#### Design Elements
The formal wire-frame process identified the need for the following User Interface Components:

|               	|              	|                 	|
|---------------	|--------------	|-----------------	|
| top menu      	| sidebar menu 	| rating selector 	|
| modals/layers 	| accordions   	| textarea input  	|
| containers    	| pagination   	| icon selector   	|
| forms         	| maps         	| select choice   	|
| check boxes   	| buttons      	| date picker     	|
| switches      	| text input   	| drop downs      	|
 
 
 
 I did not want to invent all of the above, so I read [best css frameworks](https://www.creativebloq.com/features/best-css-frameworks) to make an informed decision on what framework to use. Foundation, Picnic, and Bulma made my short list as they appeared light weight and were frameworks I have not yet explored and I do want to get the most out of this course by picking up new technologies. After reading up a bit, I decided that [Bulma](https://bulma.io/) was the best fit for what I hoped to include in this project.
 
 I did end up modifying a few things from Bulma as there are errors with their calendar date picker and the default multi select was very ugly in appearance. I felt that customizing activity icon selections to display images greatly increased the user's willingness to interact with the app and was worth the struggle of learning flask macros. 

#### Animations & Transitions
I trolled [codrops](https://tympanus.net/codrops/) to look for some inspiration.  The following sites provided ideas that greatly altered my original wire-frames:
 - [expanding search option](https://tympanus.net/Tutorials/ExpandingSearchBar/) 
 - [grid icon expansion](https://tympanus.net/Tutorials/ThumbnailGridExpandingPreview/)
 - [expanding overlay](https://tympanus.net/Tutorials/ExpandingOverlayEffect/)
 - [fullscreen overly](https://tympanus.net/Development/FullscreenGridPortfolioTemplate/)

By seeing live examples, it dawned on me that I could and should have a small icon or minimal data in my lists instead of cramming all the information on the screen. I went back to my designs, reduced the amount of noise on the events and places lists pages. Parsing out some information and relying more heavily on imagery will hopefully induce more interaction with the app. On small devices the join an event layer expands out to a full screen detail layer. For desktop, the layer is nearly full screen with more of the data exposed. Both desktop and small device presentations attempt to have user input fields above the page fold so users do not have to hunt for input fields.

I was also told by a test subject (son number 4) that the lists were boring. So I added some animation to slide rows in from the left and right sides of the screen and added some color to keep it a bit more upbeat that a mainly white page.

For the Review Input, the stars have a wiggle animation on desktop as the user hovers over them and a shine to the selection if you rate something a 5 star. A one star is dull to reflect the glum outlook the reviewer has.

### User Stories:
This website serves 3 sets of users, thus the stories are broken down into 3 categories:

#### For kids looking for something free to do today in their neighborhood:
  - As a user, I'd like a list of events happening.
  - As a user, I want to filter events by age and activity so I can find something to do that matches my interests.
  - As a user, I want to sort events by a date range so I can find something to do in the future easily.
  - As a user, I want to join an event so I can be reminded when it happens.
  - As a user, I want to follow a place that hosts events so I can know when a new event is added immediately.
  - As a user, I want to read reviews about places that host events, so I know what to expect.
  - As a user, I want to write a review about a place so I can share my opinion.
  - As a user, I want to remove my review about a place so I can have a low profile online.
  - As a user, if I don't enter the form data correctly, I want to know how to fix it.

#### For places and organizations involved in building the community
  - As a user, I want to list my place so the community knows about it.
  - As a user, I want to have honest reviews about my place to build trust with the community.
  - As a user, I want to remove reviews about my place so that inappropriate comments are not associated with my place.
  - As a user, I want people to follow my place so they can know about events, and so I can compare my place to other places that host similar activities.
  - As a user, I want to add events to my place so the community knows about them.
  - As a user, I want people to join my events, so I can communicate with them if details change and plan for the right number of attendees.
  - As a user, I want to disable my events if the weather doesn't cooperate.
  - As a user, I want to disable my place if I decide to retire, go on vacation, or sell my place.
  - As a user, I want to know if I make any input errors easily so I can successfully update my form.

#### For site owners hosting a website to store community information
  - As a site owner, I want a Home page that communicates the purpose of the website.
  - As a site owner, I want the ability to track search criteria to better target ad spacing on my site.
  - As a site owner, I want the ability to track places users follow to negotiate offline conversion money from those places.
  - As a site owner, I want the ability to track events users join to negotiate offline conversion money and to better target ads.
  - As a site owner, I want the ability to track reviews uses write to better gauge community engagement.
  - As a site owner, I want the ability to track user's emails for research purposes in beta, potential marketing in the future.
  - As a site owner, I don't want hackers to mess with my data base, so I don't loose all the information my users have contributed.

## Features
To streamline the development process without the complexity of user roles and permissions, it was decided that the MVP consists of a beta product as a proof of concept for a small market. The beta features are those listed in the Implemented Features. If the project is taken to it's full potential, the Features Left to Implement would be tackled.

### Implemented Features
#### Structural
1. Navbar - the navbar stays collapsed on medium and small devices. The navbar contains brand logo and links to associated sections i.e. Home, Events, Places, Contribute Update. Bulma's navbar implementation was used.
1. Footer - contains disclaimer, copyrights information, links to github repository and developer's resume
#### Common Elements
1. Speech Bubble - used on home page to inform users what the site is about
1. Icon buttons - used to indicate adding events, adding places, adding reviews, following places, joining events
1. Switches - sharing and disabling events, places and reviews. The switch acts as a soft delete of items from main lists and allows users to turn them back to being shared.
1. Date Pickers - setting up time frames of events and filtering of the events list.
1. Rating Selector - star icon based radio button to record user ratings
1. Overlays - way to disable main page while getting user input for filtering results, joining an event, adding a review
1. Checkboxes - user friendly way to hide/show  sections on update and add forms such as the place address , place event, place review, event address.
1. Icon Selector - single choice, allow users to customize a place or event's activity by name and icon, 
1. Icon Selector - multiple choice, allows users to select more than one activity when searching for events.
1. Age Selector - allow a multiple select field for ages, in adding/updating events.
1. Accordion - collapse places' reviews and events, on the places list page, expands on click, expand/collapse filters on event list page.
#### Forms
1. Add Place - validation for required fields and proper data, unique Name check, also includes conditional validation of sub forms such as address, events and reviews.
1. Update Place - validation for required fields and proper data, uniqueness check
1. Add Event - validation for required fields and proper data, unique Name and Date check
1. Update Event - validation for required fields and proper data, uniqueness check
1. Count Me In - validation for unique email in list of attendees, check for max attendees limit
1. Filter Events - allow user to filter events by activities, date range and age, checks for validity of age input
1. Add Review - validation for required fields where author email can be conditionally required depending if added from place or add review button/add review navigation.

#### Database Operations
1. Aggregated Review - from all reviews of a given place, present an average rating for a place
1. Count of event joiners - When a unique email is entered, add them to the joiner list
1. Filter results for events based on updating vs reading (share field both on place and event), 
1. Create list of activities for filtering based on updating vs reading (share field both on place and event)
1. check for unique emails before adding a new user
1. check for unique place name before adding a new place or updating an existing place
1. check for unique event name /date and place combo before adding or updating an existing place
1. check for a unique user/place id and date within a week before adding a new review to a place
1. check for unique user before joining an event
1. check for max attendees not exceeded before joining an event
1. adjust the activities listed in the filters based on current items shown on the event list or update events page (meaning if you filter,  your list will get shorter)
#### API Integration
1. STMP Email -when a user joins an event, send agenda in email, when event is updated, email joiner list. Note the email includes json-ld for future google calendar integration
1. Google Maps - show map of event location, show map of place location
#### Metrics
1. track page and modal visits by date and type
1. present page metrics by counts with a bar chart, data will be sorted from highest count to lowest count
1. track user clicks by date and page. Record if a button or link was clicked
1. present click metrics by counts with a simple bar chart. Datat will be sorted from highest count to lowest count.
 
### Features Left to Implement
I overestimated my abilities when originally scoping this project. I didn't account for uncovering some core issues with Bulma's [datepicker functionality](https://github.com/Wikiki/bulma-calendar/issues/163#issuecomment-584172621), nor did I anticipate as much trouble understanding the routing and parameter passing in flask.  Understanding how to use WtForms and validation took a bit but was well worth the ability to have customized validation for my forms, especially with the date time range and conditional components of addresses, reviews and events when adding a place. I also spent too much time trying to figure out how to break out the controller, filtering, and utility functions from my run.py. Since this project required a greater learning curve than anticipated, some functionality had to be deferred in order to allow me to learn how to automate testing and to provide attention to cross browser/cross device validation.  
#### Features Deferred from original plan
1. Follow a place - I would not gain any skills taking this functionality on and I the UX being similar to the delivered Join Event feature I don't believe I'm loosing out on a learning opportunity by eliminating this functionality.
1. Filter Places - I tackled more complex filtering logic in the filter events layer and saw this list not getting nearly as long as the events list could be.
1. Pagination - By including a count of events or places found, the user has an idea of how many results they are seeing. Pagination isn't nearly as useful on smaller devices as the buttons are cumbersome for fingers and users are accustomed to scrolling down vs paging through results, thus pagination was differed
1. Update Review - updating and sharing reviews are tightly tied to various user roles. Since user roles were originally out of scope, it made sense to differ this functionality, especially since updating and soft delete powers have been exemplified in update events and update places.

#### User Roles & Permissions
In the long term once this concept proves viable, authentication would be enabled and five sets of roles would accessing the site: 

1. <strong>Place Administrators</strong> -  users who have permissions to manage the Place, Events and Activities.
1. <strong>External Users Adults</strong> - users who have permissions to grant minor external users  access to the site. Adult users would also have permissions to manage their profile and create, edit and delete their own reviews.
1. <strong>External Users Minors</strong> - users who must be granted permissions to the site by Adult External Users. Minor users can manage their profile with limited features to help ensure their safety (no images or location settings if and when those features are added to the site). Minor users can also create, edit and delete their own reviews.
1. <strong>Content Admins</strong> -  users who approve reviews for inappropriate content and bot induced batch reviews. Content admins would also be in charge of setting up ad campaigns.
1. <strong>Site Administrators</strong> - users who have permissions to create, update and delete all the data hosted on the site (Users, Places, Events, Reviews)
#### Place Administrator Dashboard
1. Limit number of attendees on events
1. Allow cloning of events
1. Allow set up of repeating events
1. Allow emailing to event joiners
1. Allow emailing to followers
1. Approve/Disapprove reviews
1. password management
1. place profile management
#### External User Adult Dashboard
1. Allow user to upload image to share along with review
1. Allow user to set proximity radius to parse down results to  1, 2, 5, 10 mi radius
1. Allow user to share location with other members
1. Allow user to manage minors reviews/places/events/profile
1. Allow user to opt into/out of minor's following and joining behavior
1. Allow user to see and manage all reviews they've made
1. Allow user to see and manage all places they have followed
1. Allow user to see and manage all events they have joined
1. password management
1. user profile management
#### External User Minor Dashboard
1. Allow user to chose avatar to share along with review/follow/join
1. Allow user to set proximity radius to parse down results to  1, 2, 5, 10 mi radius
1. Submit reviews/place following /event joining to supervising adult
1. Allow user to see and manage all reviews they've made
1. Allow user to see and manage all places they have followed
1. Allow user to see and manage all events they have joined
#### Content Admin Dashboard
1. Manage ad placement & campaigns
1. Follow up on disapproved reviews
1. Keep up with naughty word list identification
1. Manage abuse reports
#### Site Admin Dashboard
1. Pull metrics & manage dashboard graphics
1. Manage users & permissions/role groups
1. Password reset 
#### More Sophisticated Attendance Tracking ###
1. Allow users to enter how many in their group are attending an event min 1, max dynamic to max attendees allows - those already attending
1. Aggregate attendance count based on each attendee count instead of 1 to 1 ratio currently implemented
1. Real-Time attendance count - add backend wait time loops and javascript to show attendance adjustments made by other users instead of on checking attendance limit on submit only
1. Utilize a calendar API such as Google Calendars.
#### API Integrations
1. GoogleAds - ad placement, offline conversions, automatic bidding
1. GoogleMaps Sitepoint - get directions from current location
1. GoogleMaps Geolocation - share location with other members, narrow results of events and places by proximity/nearby functionality or postal code/address entry.
1. GoogleCalendar - manage events and email notifications instead of STMP emails.
#### Switch to Relational Database
1. MongoDB is not the correct data base, it was chosen because it has a free tier, but the aggregation to force joins is awkward and inefficient. As the dataset grows this will cripple the application's efficiency.
### Project Tracking
The scope of this project was larger than a typical milestone effort and I quickly felt overwhelmed when learning new skills such as Bulma, mongodb aggregated queries, Flask Filters, Flask Macros, Flask WTF Forms, Validators, Flask blueprints and routes. 
To ensure I kept on task and could feel a sense of accomplishment while taking the countless baby steps towards completion, I devised a [project tacking sheet](https://docs.google.com/spreadsheets/d/1Lnvt9zLgJj0oQFdpOIAs1V2JAN2lVGcBalIBHwXzqjY/edit?usp=sharing). It helped me prioritize what aspects I needed to accomplish first and also helped identify features to descope into future releases. 
I attempted to follow a rough Agile methodology where I prefixed discovery tasks in Feature 0 for sprint 0. Then I used the following numbers as a hierarchy of what to develop first:

 | Epic Task Number 	|                         Tasks                        	|                                                                     Deliverables                                                                    	|
|:----------------:	|:----------------------------------------------------:	|:---------------------------------------------------------------------------------------------------------------------------------------------------:	|
|         0        	| Discovery & Design                                   	| Wire-frames<br>Colors<br>Fonts<br>Initial Data Model<br>List of Features                                                                            	|
|         1        	| UI Decisions                                         	| Identify Design Elements<br>Choose CSS Framework<br>Images<br>Base Layout<br>Navigation<br>Footer                                                   	|
|         2        	| Build UI Components                                  	| Star Input Rating<br>Age Multi Selector<br>Check Boxes<br>Date Picker<br>Icon Selector<br>Switches<br>Form Inputs<br>Deploy to Local                	|
|         3        	| Accept User Inputs<br>DB Interaction                 	| Address Collection<br>Event Collection<br>Place Collection<br>Review Collection<br>Write to mongodb<br>Read from mongodb<br>Deploy to Heroku        	|
|         4        	| Rough list Places<br>List Events<br>Join Event Layer 	| Maps<br>Update mongodb<br>Email<br>aggregated mongo queries<br>google calendar                                                                      	|
|         5        	| Filter Events                                        	| aggregated find queries<br>flask routes with parameters                                                                                             	|
|         6        	| Edit Events                                          	| Flask route<br>reusable code - macros<br>reusable code - filters                                                                                    	|
|         7        	| Update Event                                         	| Flask Route<br>Form Pre-population<br>add conditionals to db query                                                                                  	|
|         8        	| List Places                                          	| Accordions<br>aggregated star rating<br>Google Maps<br>tooltips<br>merge events, reviews                                                            	|
|         9        	| Add Review                                           	| Review Form<br>Refactor Code for Blueprint<br>Success/Fail modals                                                                                   	|
|        10        	| Testing                                              	| Identify Types of Testing<br>Write Test Cases<br>Execute Test Case<br>Automate Tests                                                                	|
|        11        	| Metrics                                              	| Devise Tracking Scheme<br>Hook up DB<br>Implement Click Tracking<br>Implement Page Tracking<br>Ajax Post Clicks<br>Routing<br>Rough Display of Data 	|
|        12        	| Documentation                                        	| Clean up Sections<br>Refactor into Smaller Files<br>Explain Decisions<br>Check Links<br>Check Images                                                	|
|        13        	| Finalize UI                                          	| Final Footer<br>Final Nav<br>Execute Cross Browser Tests<br>Execute Accessibility Tests                                                             	|
|        14        	| Refactor                                             	| Identify Reuse<br>Clean up unused files<br>Restructure Directories<br>Test Deployment Instructions                                                  	|
|        15        	| Demo                                                 	| Peer Review<br>Mentor Meeting                                                                                                                       	|
 
 If you sort the Project Tracking sheet by Complete Date, you can see that I would finish about 80-90% of an epic task and then start working on another feature. This goes hand in hand with the agile development cycle where epic features are all intermingled due to the interdependency of the UI components.  It is definitely nice to see the completed count diminish.

## Technologies Used
### Programming languages
- [CSS3](https://www.w3schools.com/w3css/default.asp) - used to define DOM appearance. 
- [HTML5](https://www.w3schools.com/html/default.asp) -  used to define DOM elements. 
- [JQuery](https://jquery.com) - used to initialize elements of Bulma framework: check boxes, date pickers, menu toggles.
- [JavaScript](https://www.javascript.com/)  -  used to format dates and pull data from element attributes.
- [Python](https://www.python.org/) the project back-end functions are written using Python. Flask and Python is used to build route functions
- [Markdown](https://www.markdownguide.org/) Documentation within the readme was generated using markdown
### Framework & Extensions
- [Bulma](https://bulma.io/) - a mobile first, free, open source CSS framework based on Flex-box. Using this framework provides many nice top design elements such as navigation menu bar for desktop, side nav bar for mobile, modals/layers, containers and forms.
- [Bulma Extensions](https://wikiki.github.io/) extends Bluma by adding more complex design features such as: accordions, pagination, datetime pickers, checkradios, and switches.
- [mongodb](https://www.mongodb.com/cloud/atlas)- a fully-managed cloud database used to store manage and query data sets
- [Flask](https://flask-doc.readthedocs.io/en/latest/) - python based templating language. I used Flask for:
  - routing - passing database queries to templates for page specific presentations
  - layouts - extensions of templates for common layouts with prescribed blocks that can be customized
  - common elements - inclusion of HTML templates for common design elements like the navigation, footer, various forms
  - macros - to generate common HTML with variable dependent settings
- [WTForms](https://wtforms.readthedocs.io/en/stable/csrf.html#example) - form validation & form level cross-site request forgery protection
- [Flask-WTF](https://flask-wtf.readthedocs.io/en/stable/index.html)- extended form validation and global cross-site request forgery protection
- [Pygal](http://www.pygal.org/en/stable/documentation/) - charting for metrics dashboard
- [unittest](https://docs.python.org/3/library/unittest.html) - testing database CRUD functions, flask routing
- [google sheets & drive](https://drive.google.com/drive/folders/1mYY4M0jXf6sPWesmP9Q-wFvjpgT1v8IU?usp=sharing) - Used to create testing documents and project plan (feature to do list) 
### Fonts
- [FontAwesome]() - for icons associated with buttons and inputs
- [Patrick Hand SC](https://fonts.google.com/specimen/Patrick+Hand+SC) - Google Font's Patrick Hand font was used for headers and home page dialog
- [Raleway](https://fonts.google.com/specimen/Raleway) - Google's Raleway font was used as the main font
### Tools
- [draw.io](https://about.draw.io/features/) - used to create Entity Relationship diagrams.
- [balsamiq](https://balsamiq.com/) - used to create professional looking wire frames.
- [markdown table generator](https://www.tablesgenerator.com/markdown_tables) - used to help with documentation table formatting
- [icon generator](https://favicon.io/favicon-generator/) - free site to help in website icon generation
- [regex101.com](https://regex101.com/) - used to help fine tune some regular expression based validation
- [github](https://github.com/) - used for version control of project files
- [heroku](https://www.heroku.com/) - runs the what2do2day application in the cloud
- [color contrast](https://webaim.org/resourceshttps://webaim.org/resources/contrastchecker//contrastchecker/) Tool was used to adjust colors on fonts flagged as needing a higher contrast ratio from google's lighthouse audit tool.
- [lighthouse audit](https://developers.google.com/web/tools/lighthouse) Google's open source automated too to help improve the quality of your website. Specifically paid attention to Accessibility  and best practices aiming for scores above 80.
### APIs
- [stmp](https://github.com/python/cpython/blob/3.8/Lib/smtplib.py) - Send user notices when an event is joined or when an event they have joined has been updated.
- [Google Maps Javascript API](https://developers-dot-devsite-v2-prod.appspot.com/maps/documentation/javascript/examples/) - Customized Map of event and places

## Testing
Constant integration testing was preformed to ensure no console/javascript errors were present. Beyond that, unit testing, validation testing, cross browser testing, accessibility testing, and regression testing were manually performed. I also explored automated testing of custom filters that I created. Ideally mocked up database functionality tests would be automated as well, but I have not yet found the time to learn how to mock database data.

### Validation Testing
I used the following validation websites to test the code:
- [CSS Validator](https://jigsaw.w3.org/css-validator/) Note, any error associated with root: color variables were ignored. Vendor extension warnings were also ignored. Bulma extension CSS errors concerning SVG and text area visibility were ignored too.
- [HTML Validator](https://validator.w3.org/)  - validation of HTML with FLASK is pretty useless as all {{}} bracketed values raise errors. I ran only a few files through the validator and instead relyed heavily upon pycharm's IDE to identify mismatched tags and closing Flask directives.
- [JSON Validator](https://jsonlint.com/) Used to validate roughed in json-ld for future google calendar integration. It is part of the user send invite email currently, but does not seem to be picked up by gmail. Note: warnings were ignored.
- [JavaScript Validator](http://beautifytools.com/javascript-validator.php) Note any errors for let, variables set in other .js files, and constants were ignored. I also used a more [ES6 friendly checker](https://www.piliapp.com/syntax-check/es6/) and there were no errors for main.js

### Unit Testing
To ensure core functionality and features were delivered and working I created a series of manual tests in a [google doc](https://docs.google.com/spreadsheets/d/1p1aoEQsVZUAZN50AQLZbaerS9UVVQkHG--XoiNccaC0/edit?usp=sharing)
These manual unit test cases focus on testing the core functionality in a desktop browser only and examining the console for errors. Ideally the core functionality would be verified using mocked database inputs to the controller functions for specific views.

### Cross Browser/ Cross Device Verification
To verify that the application is functional and looks pleasant  across various operating systems and device sizes I devised another suite of manual tests in the cross browser tab of my [testing workheet](https://docs.google.com/spreadsheets/d/1p1aoEQsVZUAZN50AQLZbaerS9UVVQkHG--XoiNccaC0/edit?usp=sharing).
These tests are lighter on the functionality with more attention being paid to the layout and console logs.
The matrix for the browsers, operating systems and screen sizes is as follows:

|       TOOL      	|    DEVICE    	| BROWSER 	|    OS   	|   SCREEN WIDTH  	|
|:---------------:	|:------------:	|:-------:	|:-------:	|:---------------:	|
|       N/A       	|    motog6    	|  chrome 	| android 	| XS 360px & less 	|
|  browser stack  	|   iphone5s   	|  safari 	|   iOs   	| XS 360px & less 	|
| chrome emulator 	|    pixel 2   	| firefox 	| android 	|    M 361-576    	|
|   browserstack  	|  iPhone 10x  	|  Chrome 	|   iOs   	|    M 361-576    	|
|   browserstack  	|     nexus    	|  Chrome 	| android 	|  T-vert 571-768 	|
|       N/A       	|   ipad mini  	|  safari 	|   iOs   	|  T-vert 571-768 	|
|   browserstack  	|    galaxy    	| firefox 	| android 	|  T-hor 769-1024 	|
| chrome emulator 	|     ipad     	|  safari 	|   iOs   	|  T-hor 769-1024 	|
|   browserstack  	|       ?      	|  Chrome 	| windows 	|   HD 125-1240   	|
|       N/A       	| mac book pro 	|  safari 	|  Mohave 	|   HD 125-1240   	|
|   browserstack  	|       ?      	| firefox 	| windows 	|   HD 125-1240   	|
|   browserstack  	|       ?      	| IE Edge 	| windows 	|   HD 125-1240   	|

Another part of my cross browser testing was hitting each page in each view port with the chrome emulator for a smaller phone and copying the following javascript  into the developer's tools console screen. 
```javascript
var docWidth = document.documentElement.offsetWidth;
[].forEach.call(document.querySelectorAll('*'),function(el){if(el.offsetWidth > docWidth){console.log(el);}});
```
This snippet grabs all elements in the DOM and outputs offending elements that exceed the width of the screen to the console. If the output is "undefined", then I can be 99% certain that users will not experience any odd horizontal scrolls on their devices. Running this helped me identify and fix margin issues on small devices for the modals and the icon picker for the update event flow.

### Cross Site Scripting and Forgery
During my unit testing I encountered the CSRF errors many times myself when I left the CSRF token off pages or update my routes to use blueprint and mistyped paths. This got me wondering what I can do to try to test my application proactively so I read [veracodes' XSS article](https://www.veracode.com/security/xss) article to figure out ways to manually test for XSS and CSRF.
Based on my findings I added a Security worksheet to my [testing doc](https://docs.google.com/spreadsheets/d/1p1aoEQsVZUAZN50AQLZbaerS9UVVQkHG--XoiNccaC0/edit?usp=sharing) And documented routes where url parameters are allowed as well as pages with text or text area entries and templating variables. I then attempted to inject scripting and forgeries into my website. 

### Accessibility Testing
I know a few people with physical handicaps which makes using a mouse nearly impossible as well as a couple severely visually impaired people I try to ensure I build websites that can be use by them. I make use of  [axe](https://chrome.google.com/webstore/detail/axe-web-accessibility-tes/lhdoppojpmngadmnindnejefpokejbdd?hl=en-US) and [google's lighthouse audi](https://developers.google.com/web/tools/lighthouse) tool to help ensure that the application meets accessibility standards.

 
### Regression Testing
No one wants to keep running a large suite of unit tests and cross browser tests again and again. Due to my ineptitude at writing interactive tests with a database, (I tried but learning how to mock data was not something I had planned on doing)I reduced the unit testing and cross site browsing testing to a smaller suite once the core development was 70% done. These tests are on the Regression Tests Tab of my [testing doc](https://docs.google.com/spreadsheets/d/1p1aoEQsVZUAZN50AQLZbaerS9UVVQkHG--XoiNccaC0/edit?usp=sharing). While I really want to mock some database interaction, I do not have the bandwidth to take on that additional learning at this time. 

### Automated Testing
I did install unittest and put tests around the custom filters I wrote as I do not want them breaking. Doing such pointed out several type flaws in my logic that I shored up specifically around data type and none type errors.

These tests are in the [/tests/test_filters.py](https://github.com/maliahavlicek/what2do2day/blob/master/tests/test_filters.py) file.
From a terminal window you can execute this suite of test using the following command:
 ````$ python -m unittest tests/test_filters.py -v````
 
### Defect Tracking
Once I finished the initial layout of my file structure and had roughed in the base html, I began tracking [defects](https://docs.google.com/spreadsheets/d/161VXfe9ELN-CZMsHYaJfk8WoItRxhoAkscJhY_fMjdc/edit?usp=sharing) in a google sheet. They ranged from severely horrible coding errors, to the realization that my features were not 100% defined and I could make the user experience better.

#### Noteworthy Bugs
1. **500 CSRF** -One of the most intriguing bugs I encountered was a 500 error when I introduced page and click metrics. It took me a while to figure out how to restructure my ajax call through an onReady function out of base.html so I could easily access my CSRF_token and set it in the headers within the beforeSend function. Originally my ajax call was housed in my main.js file. That solution fixed 90% of the 500 errors I had seen, but I quickly discovered that my newer pages without forms lacked the setting of the csrf_token in a hidden form. It's easy to forget key steps if you take them early in the development process and forget about them a month later.
1. **flex block madness** Another odd bug was how my custom icon picker and multi picker for ages had mismatched heights. It took me a bit to discover a display flex on an outer div from 
1. **Bulma Date Picker** The most bamboozling issue I encountered was with Bulma's datepicker and form errors. The darned thing never preselected the date I previously had and had the wrong times. I trolled the internet and found that this is an exasperating issue for many hopeful bulma users. I ended up getting a have way working work around by modifying the calendar.js a bit and adding to my binding functions in main.js. This is the [official thread](https://github.com/Wikiki/bulma-calendar/issues/163#issuecomment-584172621) that I added my findings to in hopes of getting to a resolution. I tried switching my input field to a date but then it picked up some browser specific console logs so I switched it back to a datetime range.
1. **500 CSP google API** When testing with browser stack using safari iPhone6s I saw the following errors:
```
The source list for Content Security Policy directive 'script-src' contains an invalid source: ''strict-dynamic''. It will be ignored.
The source list for Content Security Policy directive 'script-src' contains an invalid source: ''report-sample''. It will be ignored.
```
Reading up on stack overflow it looks like google API wants you to have Content Security Policy directives. I tried append such to my flask app but that didn't work too well so I ended up adding many values to my base.html header and having to set a nuance value to my inline script. Learning so many things about web security.

#### Outstanding Defects
1. Bulma's calendar is the bane of my existence. If you have a user error on a form with a datetime picker, the date time for the end time gets dropped, so the next submit will error. 
2. Safari and google.api's (pages where maps are used (places list page) Safari is not yet compliant with CSP 3.0, so when you raise strict policies on script-src  you will see errors in the console about  ```javascript
The source list for Content Security Policy directive 'script-src' contains an invalid source: ''strict-dynamic''. It will be ignored
The source list for Content Security Policy directive 'script-src' contains an invalid source: ''report-sample''. It will be ignored ```
The site seems to function in safari but it's crowded with console errors.
Here's a google-api-javascrpt git hub thread about the issue:
https://github.com/google/google-api-javascript-client/issues/397

3. The icon pickers have different heights for same rows on T-Hor device widths (769-1024). Running out of time and it doesn't look as terrible as it did on desktop so leaving this issue in place for now.



## Deployment
This site was developed using PyCharm's IDE. To keep records of different versions of all project files, git version control was used. This project is hosted using Heroku deployed from the master branch.

### GitHub
https://github.com/maliahavlicek/what2do2day

#### Requires
 - [Jinja](https://github.com/pallets/jinja) 
 ```$ pip install -U Jinja2```
 - [Flask-PyMongo](https://flask-pymongo.readthedocs.io/en/latest/) 
 ```$ pip install Flask-PyMongo```
 - MongoDB instance [downloaded and installed](https://docs.mongodb.com/manual/installation/)
 - MongoDB Atlas Cloud [URI connection string](https://docs.atlas.mongodb.com/driver-connection/) 
 ```mongodb+srv://user_name:password@cluster-pielp.mongodb.net/db_name?retryWrites=true&w=majority?```
 - [Flask-WTF](https://flask-wtf.readthedocs.io/en/stable/install.html) 
 ```$ pip install Flask-WTF```
 - A google api key [get here](https://developers.google.com/maps/documentation/javascript/get-api-key)
 - [flask-googlemaps](https://github.com/flask-extensions/Flask-GoogleMaps/blob/master/README.md) 
 ```$ pip install flask-googlemaps```
 - a [gmail accoount](https://accounts.google.com/signup) with less secure app access turned on use [this link](https://myaccount.google.com/lesssecureapps?pli=1) after you are signed into the gmail account

#### Running Locally
1. Get the code base from git hub by running this command in the terminal of your IDE: 
```$ git clone https://github.com/maliahavlicek/what2do2day.git```

2. [set environmental variables](https://www.twilio.com/blog/2017/01/how-to-set-environment-variables.html) with your own values for: 
> - MONGO_URI_WHAT2DO2DAY [URI connection string](https://docs.atlas.mongodb.com/driver-connection/) 
> - GOOGLE_MAP_KEY [get here](https://developers.google.com/maps/documentation/javascript/get-api-key)
> - SECRET_KEY - a long random string of bytes. For example, copy the output of this to your config:
                ```$ python -c 'import os; print(os.urandom(16))'```
> - WTF_CSRF_SECRET_KEY another long random string of bytes to help protect against cross site request forgery.  You can copy the output of this to your config:
                ```$ python -c 'import os; print(os.urandom(24))'```
> - EMAIL - a [gmail accoount](https://accounts.google.com/signup) once you have an account and are signed in you need to make sure it has less secure app access turned on use [this link](https://myaccount.google.com/lesssecureapps?pli=1)
> - EMAIL_PASS - the password to the email account

3. start your server by typing 
```$ python run.py```
4. load up the countries db from the helper file:
```$ python helpers/upload_countries.py ```
4. access your local version of the application at http://0.0.0.0:5000/home

### Heroku
Heroku can be used to run this site in a cloud environment to allow visibility to external users.
#### Deployment To Shared Environment
1. Get the code base from git hub by running this command in the terminal of your IDE: 
```bash
   $ git clone https://github.com/maliahavlicek/what2do2day.git
   ```
1. Login to Heroku and set up a new app
1. Under the **Settings** tab, click **Reveal Config Vars**
1. Set the following variables
> |        Variable       	|   Setting  	|
>|:---------------------:	|:----------:	|
>| IP                    	| 0.0.0.0    	|
>| PORT                  	| 5000       	|
>| MONGO_URI_WHAT2DO2DAY 	| YOUR_KEY  	|
>| SECRET_KEY            	| YOUR_KEY  	|
>| WTF_CSRF_SECRET_KE    	| YOUR_KEY  	|
>| GOOGLE_MAP_KEY        	| YOUR_KEY   	|
>| EMAIL                	| YOUR_KEY   	|
>| EMAIL_PASS            	| YOUR_KEY   	|

5. Go back to your IDE's terminal window and connect to heroku ```bash heroku login``` and enter your credentials
5. Clone the heroku repository (exact command can be found on the Deployment tab for the app you just created in heroku) ```bash heroku git:clone -a 'your_app_name'```
5. make a slight change to a file, say the readme.md file
5. add the files, commit and push to heroku master:
```bash
$ git add .
$ git commit -am "initial heroku commit" 
$ git push heroku master
```
You should be able to access the application at your heroku via the url provided in the terminal window, or the open app button from your heroku app dashboard.
Ex) https://what2do2day.herokuapp.com/

## Credits
- [Icons made by Freepik from www.flaticon.com](https://www.flaticon.com/packs/outdoor-activities-32)
- [tables in markdown](https://www.tablesgenerator.com/markdown_tables#)
- [star rating input](https://codepen.io/jexordexan/pen/yyYEJa) - Thanks Jordan-Simonds
- [toggle switch](https://www.w3schools.com/howto/tryit.asp?filename=tryhow_css_switch)
- [star rating display](https://codepen.io/FredGenkin/pen/eaXYGV) - Thanks Fred Genkin

### Content
- [Avanti Music](https://advantimusic.org) description and imagery

### Media
The photos used in this site were obtained from:

- [Aage icons](https://images.app.goo.gl/aed22uFkaURNm9we6) - baby, preschoolers, middle schoolers, high schoolers
- [More Age iIcons](https://images.app.goo.gl/kUcThrqJ6hLJHsBk9) - elementary, young adult, 21+
- [Activity Icons](https://www.flaticon.com/packs/outdoor-activities-32) made by Freepik and hosted at www.flaticon.com
- [Perry the Platypus](https://images.app.goo.gl/AbcvfgihqBk83TCu6) - secret agent platypus image used on list pages
- [Phineas and Ferb](https://images.app.goo.gl/upEMCarxtGChgSh5A) - used as background image on home page
- [grass](https://images.app.goo.gl/be322rrT66jYjYmq9) - cropped out a section of a backyard png, to have grass to underline title hero objects on pages
- [loading gif](https://images.app.goo.gl/WLbJdQc2PPEjFAaM7)- used to hold maps while they are retrieved from google API
- [success](https://images.app.goo.gl/ieQJ64nMJXXt7EMP9) - Phineas and Ferb jumping for joy image used on successful follow place, join event screens
- [opps](https://images.app.goo.gl/dtquPurPUkehqTGHA) - Doofensmirtz oooh image used for already joined, already followed, place already exists, event already exists screens
- [fixit](https://images.app.goo.gl/EVtxLRwobhduoVe66) - Ferb with tools used for 404, 500 errors where the page request doesn't exist or weird routing issues

### Acknowledgements
The wonderful results of the google search engine helped me tremendously in completing this project.
- [uniwebsidad.com](https://uniwebsidad.com/libros/explore-flask/chapter-8) - Provides documentation on more advanced features of flask
  - macros and include them from an external file 
  - how to make custom filters
- [speech bubbles](https://auralinna.blog/post/2017/how-to-make-a-css-speech-bubble-with-borders-and-drop-shadow) The home page dialog bubbles were adopted from this post by Tero Auralinna.
- [CSS tricks](https://css-tricks.com) has an assortment of helpful ways to use CSS to accomplish tasks. 
  - [image centering]((https://css-tricks.com/perfect-full-page-background-image/)) how to center the home page background image across device sizes
  -  [styling scrollbars](https://css-tricks.com/the-current-state-of-styling-scrollbars/) to conserve vertical space, I put the icon choices into a scrolling area but wanted to show the scrollbars in an intuitive manner rather than relying on inconsistent default browser styles
- [Kyle Marek-Spartz](https://kyle.marek-spartz.org/posts/2014-04-04-setting-wtforms-selection-fields-dynamically.html) - Setting WTForms Selection Fields Dynamically
- [mcelhennyi](https://gist.github.com/devxoul/7638142) - Required If validation used in address, event, and review form entries
- [api_mongodb](https://api.mongodb.com/python/current/migrate-to-pymongo3.html) -  Help in overcoming and understanding write concern errors I encountered with MongoDB
- [mongo reference](https://docs.mongodb.com/manual/reference/) - Learning how to manipulate dates, strings, perform lookups, sorting, and merges on data
- [javascript dates](https://www.aspsnippets.com/Articles/JavaScript-Display-Current-Time-in-12-hour-format-AM-PM-and-24-hour-format-with-Hours-Minutes-and-Seconds-hhmmss.aspx) to clean up date formatting in the initial count me in layer
- [Pretty Printed](https://www.youtube.com/watch?v=kWncnBBxoJ4&feature=youtu.be)This video shows how to integrate google maps to a python flask application.
- [aezel](https://stackoverflow.com/users/64266/aezell) for [posting](https://stackoverflow.com/users/64266/aezell) a good way to separate flask filters from run.py
- [Todd Birchard](https://hackersandslackers.com/flask-blueprints/) For a most useful example about blueprints to make a larger flask application's directory structure manageable
- [Dan Badar](https://dbader.org/blog/python-send-email)- how to send emails via python and a google account
- **the G-men** A special thanks goes out to my family for allowing me to ignore them for the past two months as I dove deep into unknown waters. I hope the new skills I'm gaining from this program can pay for us all to go visit the grandparents again. Hawaii or Croatia... tough decisions.
<img src="documentation/images/IMG_20190717_213729_096.jpg" width="300" height="auto" alt="picture of Malia's boys"/>
