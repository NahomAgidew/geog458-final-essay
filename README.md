# Mapping Crimes Against Rohingya

![Screenshot of the project's homepage](imgs/home.png)
## Introduction
The project was done by the Amnesty International to map the experience of the Rohingya villagers in an effort to report the war crimes done by
the Myanmar's military.
First, a short background on the situation: according to news outlets, the Arakan Rohingya Salvation Army (ARSA) launched military operations against the Myanmar security force in one of Myanmar's state known as Rakhine State. The attack was a form of protest to voice issues faced by the Rohingya Muslim minority in the country. In order to retaliate, the security forces started a widespread campaign of violence against the entire Rohingya population in the region. In the following 10 months, they expelled more than 702,000 Rohingya people into the neighboring country Bangladesh. According to Amnesty International, the violence includes "widespread illegal detainment, torture, sexual violence, starvation and village burning." Almost all of the eleven crimes against humanity listed in the Rome Statute of the International Criminal Court were committed in that 10-month period.

The project combined evidences from maps, satellite images, photographs, drone footage, testimonial videos, and animations to deliver an unprecedented level of visibility and clarity into these crimes. The platform provides an interactive timeline of events to recount how Myanmar’s military systematically destroyed Rohingya villages. In addition, the platform enables users to engage directly with the exhaustive documentation that Amnesty has gathered on the case as they move through the sequential animated timeline. The satellite imagery is especially important as it shows the before and after comparison in order to create a spatial narrative to show village burnings and infrastructure destructions. This reminds of one of the week 7 readings on "Affective Geovisualisations" about how one can use animations to evoke a certain emotion on the map viewer. The map authors did a really great job of utilizing modern techniques to get their point across.

## Architecture
The frontend elements of the web application can be categorized into three parts: an embedded map on the left, details section on the right, and timeline at the bottom. The website is structured as a slideshow that one can navigate through by clicking the arrows on the opposite end of the screen or by using the left and right arrow keys on the keyboard or by clicking on the little square boxes in the timeline.

As you go the homepage, you are greeted with a looping background video of the Rohingya villagers and overlaid on top of that is the project title and a button instructing the user to start the report. It is at this stage that the auxiliary libraries such as the Mapbox JavaScript library and normalize.css are loaded. This is a great way to greet the user as the necessary data is loaded in the background. The user would have something to do / look at instead of a generic loading screen.

Regarding loading data, another clever optimization the authors used was the web application only loads the first slide initially. This, again, saves loading time and network bandwidth as you do not need everything at once. Instead, the application loads the rest of the slides on-demand. As the user navigates the slideshow by using one of the three options listed above, the client issues a GET request and subsequent data is fetched from the server. Looking at Google Chrome's inspector, the data is hosted on the same domain (so no cross-origin request) and the data format they used was GeoJSON. As we learned in the class, GeoJSON is a great way to store spatial data as it allows us to express complicated spatial structures in an easy-to-parse format. This data is used by the embedded Mapbox view and Mapbox is responsible for parsing the GeoJSON data and visualizing it. Using Mapbox removes a lot of overhead for the application developers as they don't have to worry about all the complexities that comes with spatial visualization.

## UI/UX
As the web application was made by Amnesty International, we expect a high level of professionalism and standard in terms of the user interface and user experience. They met this high expectation. It had a great color combination, the website loaded fast, the text was readable, and the animation was smooth. In addition, the website was also responsive to different screen sizes.
The highlight of the experience were three things. First, they provided multiple ways to navigate the slide (clicking the arrows on the opposite end of the screen, using the left and right arrow keys on the keyboard, and clicking on the little square boxes in the timeline). This made the user experience a delight as one can use any of the options and figure out how to navigate. Second, the timeline at the bottom communicate that the web application is in a slideshow format so that is another clever way communicating without necessarily using words. Third, the way they combined the satellite imagery with the color and zooming animations was amazing.

A couple of minor critiques are: they could have expanded up on the timeline design by incorporating the actual period of the events. Since this is a report of an event that occurred over the span of 10 months, it would have been great to show the date so users can skip to a specific time. Another minor improvement is to include a brief tutorial on the first slide show what you can do on the web application. Even though this is obvious to most people, it is possible that not everyone can figure out what is going on.

## Reflection
They provide different ways to navigate.