**Habitual is a project focused in the field of productivity, allowing users add habits they want to improve and show them real-time progress and basic statistics for each habit as they progress.**

<h3>WIP - Design Documentation Below</h3>
<h4>Design Introduction</h4>
This design document includes an overall solution of how I plan to develop the app. This includes UI mockups, and the process flow of the app shown in the flowchart below. It is designed using MVC architecture because I believe it makes the most sense for the complexity of the app. Choosing this architecture leaves less room for error because of fewer moving parts and because this is my first experience building a fully functional app in Swift, room for error should be kept to a minimum.
<h4>Logical Solution Design:</h4>
![[Pasted image 20240117131528.png]]

<h4>Physical Solution Design:</h4>
![[Physical Diagram.png]]

<h3>Key Technical Design Decisions:</h3>
My core technical design decisions are utilizing Swift and the Swift UI, and Swift Charts frameworks. Additionally, I will use AWS to host my data through RDS to ensure reliable uptime and use GitHub for version control. I also plan on hosting the Express API if putting Habitual on the App Store becomes in-scope. Also, since the Express API will handle all communication with the database, it will act as a Data Access Object (DAO) for the business classes to directly communicate with, as shown in the logical diagram.

<h4>Database ER Diagram:</h4>
![[Pasted image 20240117144719.png]]

Each Habit object will entail details including a user_id which is used to link habits to a specific user. Each Record object will likewise be linked to a habit through a habit_id to ensure that users only see their own list of habits and expected records.

<h4>Flowchart Diagram:</h4>
![[Pasted image 20240117144855.png]]
The logical flow of the app as the user would see it. Green nodes indicate where the user will start.

<h4>Sitemap Diagram:</h4>
![[Pasted image 20240117144922.png]]
The sitemap shows the technical flow of the app at a high level.

<h3>User Interface Diagrams:</h3>
![[Pasted image 20240117145051.png]]
![[Pasted image 20240117145102.png]]

![[Pasted image 20240117145110.png]]
![[Pasted image 20240117145116.png]]
Users will tap the ‘+’ icon to the left of each habit once they’ve completed it. The results on the right side will add up accordingly to see a brief overview of their status. When a habit name is tapped on, the square becomes darkened and triggers the ‘Details View’ for that habit as seen below.

![[Pasted image 20240117145136.png]]
![[Pasted image 20240117145143.png]]
Statistics for each habit are compiled through a business class and displayed on the screen above. This is where a user can delete a habit from their account as well.

![[Pasted image 20240117145203.png]]
![[Pasted image 20240117145208.png]]
The ‘Add Habit Form’ page allows users to add new habits and includes all data needed to add a new habit row to the database.

The ‘Activity Page’ gives users a visual representation of their progress for a single or multiple habits over a 7-day period. Tapping on the greyed-out habits will show/hide their corresponding-colored line on the chart at the top.


<h4>Non-Functional Requirement (NFR):</h4>
An NFR for the app will restrict the iPhones that are supported to iPhones 12-15 with max counterparts and iOS 17+. The iOS requirement was chosen because of the possibility of adding a widget later on, which is only supported on iOS 17+. The design supports the different phone sizes since the choice of using Swift UI allows for an accurately simulated depiction of different phone models and sizes.

<h3>Operational Support Design:</h3>
Logging will be supported through the API and will log errors, stack traces and important events including user account activity.