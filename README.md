# Backbone Review

## Intention
Let's think about the types of applications that we have built using JavaScript thus far. Scrabble was a basic functional program, but didn't really have any front-end component that did DOM manipulation or eventing. Trek was a nice SPA that used AJAX to interact with an API and jQuery events to provide much of the functionality. These types of applications were fairly small with not a lot of features or components that were difficult to keep track of.

Let's say that Trek had 5 times as many features that were built with similar interactions with APIs and events. This would be much harder to keep track of utilizing the unstructured process we were using originally. **This is where we will see the greatest use-case for utilizing Backbone as our JS library.**

## Setup
This repo includes a completed Backbone application version of Trek that we will refer to for these activities.

You should **fork and clone this repository to follow along.**

***

## 1) Review Components
![Backbone JS Architecture from http://www.slideshare.net/ronreiter/writing-html5-web-apps-using-backbonejs-and-gae](backbonejs-architecture.jpg)

Below are the Backbone components we have focused on to build our single page applications. Each component has a brief explanation along with a link to it's documentation.

- [Model](#model)
- [Collection](#collection)
- [View](#view)
- [Events](#events)

### Model
Models are the component of our Backbone application which retrieves and populates the data. Models also contain our applications business logic.

### Collection
Collections handle a group of related models. When initially thinking about a collection, they may seem like simply a list, but they are much more powerful. Collections are useful because they can allow you to listen for (and act on) events that occur on any model within the collection.

### View
Views act as the HTML representation of your Backbone Models. Views have much more power than Views in our Rails applications. Views act as the broker between the data in our application and the HTML displayed to the user.

The two main purposes of views are:
- Templating (rendering HTML)
- Eventing (triggering and handling events)

##### Clarifications on Views
**Notes on `el` `$el` and `this.$`:**
- **`el`:** A View's `el` property is it's _DOM element_. Every view has **one** and by default, unless otherwise defined, it is a `div` element.
- **`$el`:** The _jQuery wrapper_ around the View's `el` property. It gives you easy access to jQuery methods like `show()`, `hide()` and `addClass()`.
- **`this.$`:** The jQuery selector function, [_scoped_](http://api.jquery.com/jquery/#selector-context) to only search within the children of the View's DOM element. This allows you to make selector calls and be certain that you're not affecting any parts of the page outside of your View's responsibility.

You should always design your Backbone Views so that they never modify DOM elements that aren't children of `el`. The easiest way to make sure that your Views hold to that design is to **only ever use `this.$` and `$el` to modify the page**.

Using the standard jQuery `$` is acceptable if you need to _read_ parts of the page, when you might need to get the content for a template.


### Events
Events are defined inside of your Views. We can utilize three different types of events to create a truly dynamic site.

**DOM Events**: These are events that are triggered within our `events: {}` or `on` code in the View. These events occur when there is something directly happening in the DOM.

**Custom Events**: These are events which we can create ourselves by extending `Backbone.Events`.

**Backbone Events**: These are _technically_ custom events which Backbone has created for us based on common things that we need to do in a Backbone application. These are things like `add`, `update`, and `remove` on models and collections.

#### Documentation
[Backbone.model Documentation](http://backbonejs.org/#Model)

[Backbone.collection Documentation](http://backbonejs.org/#Collection)

[Backbone.view Documentation](http://backbonejs.org/#View)

[Backbone.events Documentation](http://backbonejs.org/#Events)

[Backbone built-in events](http://backbonejs.org/#Events-catalog)

**Activity:**
Go through the Trek application and list out each individual component. Use the diagram above to help you label each component as Model, View or Collection.

***

## 2) How we have structured our Backbone applications
The point of backbone is to provide a very intentional structure to our front-end code, so that we know where to find the code that is handling the specific functionality of our application.

With Backbone being a less opinionated library/framework, it also has less rules and conventions on


### App.js


### Views
- **application_view** was the most arbitrary. Why is it there?
- **contact_view**
- **rolodex_view**


### Models

Right now our models have done very little. We have used them to set defaults.

Then can also...

We will utilize them a lot more with Tic-Tac-Toe, and that lesson will come on Monday.

### Collections


### That Other stuff
Because our Backbone application relies on a few other libraries to get it's gear'a'grinding, we have a json file that keeps track of those libraries and will include them into our project when we run `npm install`.

To add more libraries, or to see which ones are already included, open the `package.json` file and look under `"devDependencies": {}`

If this process sounds familiar, it's because it's basically the same as having a gem file in rails and running *'bundle install'*.

- **Webpack**

- **Underscore**

- **JQuery** Anytime you see that money sign, you're working with a Jquery object. That Jquery object is set by referring to a

***

## 3) Review How the Components Interact with Each Other
Each component is responsible for specific functionality of our application. These components rely on each other, which can quickly complicate how data flows through our application.

The below activities practice understanding how the components interact with each other.

- [Rendering Views](#rendering-views)
- [Tracing Events](#tracing-events)
- [Initial Page Load](#initial-page-load)

### Rendering Views

**The structure of our HTML has hierarchy** When an HTML element is nested inside of another element, the outer-most element has a higher hierarchy. That outer-element acts as a container for it's inner-elements.

Some backbone views will be responsible for other views and act as a container with hierarchy over the inner-elements that are generated from the views.

For example, in the Rolodex project, the Rolodex view was responsible for rendering many contact views


With our application, a single page will likely have many different Backbone views rendering as once.


**Activity:** Views Responsibility

With this activity, we will get more comfortable recognizing the code that is

Each of the following views should correspond to a color. ex: trip view is yellow, trip_lis view is blue and app view is red. Use that color to draw a square around all the code that corresponds to that view, including view files, html


- trip view
- trip_list view
- app view



### Tracing Events

**Activity:**
Use the worksheet that corresponds to all the
Cut out the squares and put the segments of code in order in which they are ran, based on that event happening

- When Button, 'See All Trips', is clicked
- When button, 'Make Reservation', is clicked

### Initial Page Load
When the page initially loads, there is a lot of code in various parts of our application that are depended on to make sure it all comes together.

- On page load


##4) Would this be a backbone app?


Soundcloud.com
HTML5zombo.com
