= Event Storming Workshop Cheat Sheet

Event storming is a rapid design technique for software systems involving both technical staff and domain experts / business analysts. It best fits in a Domain Driven Design context and leans towards / prepares for Event Sourcing and CQRS. The technique was first introduced by Alberto Brandolini and picked up by Vaughn Vernon in Domain Driven Design Distilled. It is also taught as part of his iDDD Workshop series.

This cheat sheet aims to provide a short opinionated summary of preparing and facilitating an Event Storming Workshop. It is not intended to give a complete introduction to the topic, prior knowledge on DDD and Event Storming is required to make responsible use of this document.

== Required Material

* *Paper rolls* to create the modeling surface. Available e.g. at IKEA (Mala, http://www.ikea.com/de/de/catalog/products/80324072/ or at Amazon https://www.amazon.de/gp/product/B005OBO1LO)
* *Sticky notes*. Vaughn Vernon recommends the 7,6 x 7,6 cm super sticky variety. You need the following colors: orange, light blue, pale yellow, green, pink, purple / red, lilac. I found the Post It collections Marrakesh (e.g. https://www.amazon.de/gp/product/B016OON3UO/) and Energy (e.g. https://www.amazon.de/gp/product/B006JCQJJY) put together work. Make sure you have plenty of them
* If you also want to sketch out UI Mocks, personas or acceptance test cases, you may add a larger variety of stickies as well.
* *Fine felt tip markers*. At least one per participant, but better to have two colors, e.g. black & blue. Do not use standard flipchart markers as they are too big for the selected sticky notes but rather a finer variety. I found Stabilo' GREENpoint L0.8 work well (https://www.amazon.de/dp/B004HV1N8Q/).
* *Bigger felt tip markers*. Standard flip chart markers work well. You can't go wrong with Neuland markers, e.g. https://de.neuland.com/marker-stifte/neuland-marker/neuland-no.one-keilspitze-2-6-mm-einzelfarben.html
* *Adhesive tape*. Use gaffer tape to put up the paper roll and probably crepe tape to put up additional notes.

== Preparation

Up front:

* Invite both domain experts and developers. Personally, I'd aim for no more than 8. But since the modelling space is big, discussion groups will emerge, so more people could work well, too.
* Schedule a session for no longer than 2 or 3 hours. Plan for follow-up sessions.

At the location:

* Remove chairs from the room. People should walk around. Seats are poisonous, as Alberto puts it.
* Prepare the legend in advance. Alternatively, for first time participants, create the legend iteratively as you go along as described in <<Execution>>. You can use pre-prepared link:cards.adoc[cards] like the ones attached to this document.
* Prepare the modeling space. Use paper rolls taped to a large wall. 1 m x 10 m should be considered the minimum size. Bigger is better. Be prepared for having to expand the space.
* Lay out sticky notes and markers.

== Execution

Below you find the order Vaughn Vernon recommends. It is fine to add additional artefacts in a later step, but it is important to roughly adhere to the Event -> Command -> Aggregate -> boundaries -> view order.

. Create or line out the legend so the semantics of the color notes / annotations is well understood by all participants.
. Storm out _Domain Events_ on _orange_ stickies and place them on the modeling space in business process (= time) order. The name is a noun/verb combination in the past tense, e.g. `ItemOrdered`.
. If _issues_ with the process or questions_ arise that are not immediately resolvable, mark them with _purple or red_ notes.
. Some Domain Events will cause a _business process_ to run. Note the name of the process on a _lilac_ note and draw an arrow from the Event process to the process.
.  When you feel you have captured most of the Domain Events, focus on the _Commands_ that create those Events. Put them on _light blue_ notes left to the Event they cause. Proceed from left to right on the timeline. The name is an action like `OrderItem`.
. If a specific _user role_ performs the Command, note that on a _yellow_ note left below the Command. I like to draw stick figures to distinguish them.
. When you think you have all Commands, note the _Aggregates_ on _yellow_ notes and place them a little higher between the Command that is executed on this Aggregate and the Events it causes. The name is a noun, like `Item`. If Aggregates are used multiple times, create copies and place them repeatedly on the timeline.
. Draw your _Bounded Contexts_ (solid lines) and _Subdomains_ (dashed lines) onto the modeling surface. You should do this only when you feel you have understood the boundaries well enough. Name the contexts using _pink_ notes.
. Draw arrows to show in which direction Events flow between your contexts.
. Identify _Views_ required for the user to carry out tasks in your system. Place them on _green_ stickies below the Aggregates the operate on.

Optional additions:

* UI Mock Ups along with the views
* Acceptance Test sketches for important tests
* User personas
* Read models

== Reference

The semantics of the various colors as mentioned in the text above are shown below for reference.

* *Domain Events* - orange
* *Commands* - light blue
* *Aggregates* - yellow
* *Issues* - red or purple
* *User Roles / Personas* - yellow with stick figure
* *Views* - green
* *Bounded contexts* - solid line, names on pink notes
* *Subdomains* - dashed lines
* *Event Flow* - arrows

== Further Information

* Vernon, Vaughn. “Ch. 7, Event Storming.” Domain-Driven Design Distilled, Addison-Wesley, 2016. - https://www.amazon.com/Domain-Driven-Design-Distilled-Vaughn-Vernon/dp/0134434420
* Brandolini, Alberto. Introducing EventStorming. Leanpub, to be released, eventstorming.com/ - https://leanpub.com/introducing_eventstorming
* Brandolini, Alberto. “Ziobrando's Lair.” Introducing Event Storming, Nov. 2013, ziobrando.blogspot.de/2013/11/introducing-event-storming.html.
* Brandolini, Alberto. Event Storming Recipes. SlideShare, 21 June 2014, de.slideshare.net/ziobrando/event-storming-recipes.
* Rayner, Paul. Event Storming. SlideShare, 26 May 2017, www.slideshare.net/AgileDenver/event-storming-76390807.
* Brandolini, Alberto. Model Storming. SlideShare, 19 Sept. 2013, www.slideshare.net/ziobrando/model-storming.

