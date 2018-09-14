# RunApplication

-> www.runapp.eu

A web application that generates random cross-country and cycling routes

Create a web application that allows the user to automatically generate a random route after entering the following parameters
desired path length of given error tolerance
starting point, definable as any point on the globe
choice of activity as either running or biking
choice of difficulty level as either easy or hard
Introduction
Trajectory calculation in the web application is based on maps distributed by Google. Designed random points on the map from which all information about the route is retrieved (distance, height, coordinates). It allows the user to efficiently design cross-country, cycling routes with the appropriate route difficulty option. Web application is designed mainly for athletes, for families who want for instance set up bike tours also for organizers of sports events where the key factor is knowledge of length of the route and the height with all ascends and descends.

Description of Google Maps tool
Google Maps gives the users the ability to interact with locations around the world. The interaction could have many activities for instance: zooming, getting coordinates, checking what’s in the place. It also allows to create stretches between two or more points and dynamically change the distance of that stretch depending on the route you choose. The advantage of using this tool is fact, that it’s constantly being developed by one of the industry’s most respected companies.

Compares with the other applications
The created application can be compared to many other developed applications by companies and individuals, but its uniqueness distinguishes two features. One of them involves automating the route generation process. The user is accustomed to the application where he must manually lead the points creating trajectories, which can be time-consuming. My application which I created, allows you to perform all these movements automatically, saving time with not involving the user.
The second feature is the ability to choose a route due to its elevation. Existing applications on the market don’t provide this possibility, the concept of creating such an algorithm is very individual and complex, because the generated route for each individual might be different, easier or harder.

Choice of algorithms
The whole concept of web application activity is to generate random points that, when combined, will be close to the value of the distance entered by the user. What characterizes the generated points are:
● randomness
● fit to existing road

Two algorithms are used to draw points, one of which is responsible for generating the first point, the other for generating the second. They are so matched that when you combine points with each other they create a route that will avoid the situation overlap. It is unfortunately not possible to completely eliminate this situation. The second important feature is matching to an existing road. If a point is designated where there is no road, it automatically matches the nearest path that is at that point. This makes it easy to find routes and protects the user from situations where the algorithm could set a point for example in the center of the lake.

Selection of route evaluation criterium for difficulty level
In order to make the choice between the easy and the hard route, criteria should be applied that would clearly separate the two variants. Only one criterion was used in the created application due to limitations on program run time. This criterion consists of two parameters, which are analyzed after the generated route. The generated route is classified as difficult when:
● between the start of the runway and its end is a difference of at least 10 meters.
● The run is at an angle of at least 2.8º
● The route counts at least 3 ascents

Problems and restrictions
Presents problematic situations for the operation of the algorithm. These are represent hard to reach places with a rare road network. This causes an algorithm to work incorrectly, where the distance setpoint will almost never be realized.

Unfortunelly, ferry crossings are received as ordinary roads, which is what the algorithm chooses during its operation
Another problem that can’t be eliminated are natural obstacles such as rivers, lakes, forests. An ideal example of this problem is the City of Police, which is limited to the right by Lake Dąbie, the Szczecin Lagoon and the Oder River. If a user enters a distance of several kilometers and the first random point is generated to the right of these natural obstacles, then the route will never be found.

For the correct operation of the application, random points can be generated at 0.7 second intervals. Decreasing this value will cause the algorithm to loop and never find a user-specified trajectory.

To avoid this situation, choose one of two possible solutions to the problem.
● purchase subscription
● reduce the time to call the server polling function for a new point to generate.

As a result, the limit is the number of points generated. With a time limit of 0.7 seconds, unfortunately generating more points would result in a significant lengthening of the trajectory-generating application. For two generated points, the application can do a long time, and it all depends on whether the algorithm will quickly "hit" the point in the distance it is interested in or not. When you purchase a subscription, this limitation disappears as the point could be generated incomparably faster, which would result in one attempt to designate a point for free use of the API, with a hundred attempts for the paid user.

Conclusion
The created web application fulfills all assumptions about the correctness of the algorithms, including generating random points and combining them to create a route that the user will see. Free account issues are resolved by applying sufficiently long intervals between points to generate, slowing down the application, but the application continues to work efficiently and correctly. The application practically every time finds a route in the form of the generated trajectory, and the speed of finding it depends on the luck of drawing points that meets expectations. Error handling is implemented as well as how the algorithm is supposed to behave when points are not found, or the height criterion is not met. The user who uses the application has an error tolerance slider available, so that the smaller the value of this tolerance, the longer the algorithm will find the route. The great advantage of the application is the ability to develop it, attach additional modules, or implement it on another development platform. The built-in google maps tool allows to automatically generate trajectories so that the user only has to do is input the interface into the web page.
