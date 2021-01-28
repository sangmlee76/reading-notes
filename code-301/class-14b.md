# Read 14b - Notes: Project Ideas and APIs

## Idea 1: LMS for pre-K/K

1. Problem: Early learners or those who are not in a formal program still need to manage their work. Parents who homeschool or teachers of early learners need a LMS that cater to young learners that help develop individual capabilities and motivation in a fun way.  Think: Canvas for Kids!

2. Proposed solution: Basic LMS that allows both young kids to manage their work and parents to track what they are learning while giving/teaching them the responsibility to manage their own work.

3. App components:

- UI (front end): "Kid" (main) screen with kid-friendly UI that allows simple (colorful block style) icons that help them identify "to-do tasks" and "completed tasks"; add gamification (e.g. encouragement, animation, etc.) to cheer kids on when they complete a task (could be a household chore also -- not just academic). "Parent" screen that allows them to see what tasks their child has completed and what remains for the day. A detailed "analysis" page that looks at task completion over time (e.g. 1 week, 1 month, 3 months) to see patterns and to understand how their child is progressing.

- STRETCH GOAL: Parents can add educational content that they want their kids to learn form a library of educational material (e.g. from Khan Academy)

- backend: connect to LMS API (e.g. google learning/education), more interaction with front-end. Database to track each day's tasks and completed tasks to track child's progress and habits that can be pulled for analysis.

- STRETCH GOAL: the analysis can be a simple count for MVP but can be more dynamic and robust for the stretch goal to give parents more insight.

4. APIs needed: google education, K-12 LMS (e.g. Canvas, D2L, etc.), Khan Academy (for stretch goal),



## Idea 2: EWTSFP (Everyone wants the same freakin' picture)

1. Problem: Did you notice that everyone takes the same picture when they travel? (e.g. https://www.gettyimages.com/photos/leaning-tower-of-pisa?phrase=leaning%20tower%20of%20pisa&sort=mostpopular (Links to an external site.)) ... but, as they say, when in Rome (or Pisa...) -- you just can't leave a city you are visiting without that same freakin' shot. So, why fight it? We say, DON'T -- instead, double down.

2. Proposed solution: A mobile app that gives you the exact geolocation on a map of where to take the picture that everyone else is taking so you, too, can post it to your Instagram. If in the city, it gives you popular pictures that have been captured within that city and the geolocation on where to go. We also inspire you with some relevant quotes and some basic facts about the famous sight to make sure you are learning something cool during your travels.

3. App components:

- UI (front-end):

   + forms: type in the city name that returns images

   + Image detail page: provides geolocation on a map, gives fun or historical facts, gives relevant quote to inspire you, gives you relevant information nearby the sight so you can plan your trip accordingly (e.g. yelp for food, gift shops, etc.) -- this could be a separate page

   + STRETCH GOAL: user can select multiple sights/pictures or can "save" the sights -- creates an "itinerary" -- can make this smart by creating an optimal travel from sight to sight (ML?)

- backend: API calls to get the data; render text, images, geolocation on a map to front-end

- STRETCH GOAL: tie the quote dynamically based on the image selected (computer vision?)

4. APIs needed:
- Getty Images, mapping API, Wikipedia (or other facts based site), quotes, Yelp


## Additional Reference
+ [This repo](https://github.com/toddmotto/public-apis) for APIs you could use.

***
[<<< Back to Main](https://sangmlee76.github.io/reading-notes/)

