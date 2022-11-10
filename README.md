# cs225-final-project

**Proposal**
Leading Question
The goal of this project is to analyze a data set of airport terminals and routes, using this dataset we will be able to use a variety of algorithms to find information like - the fastest way to get from terminal A to B, and all of the terminals that are within a certain distance from the input terminal. We believe that it will be relatively straightforward to visualize these interactions, allowing the nodes to be terminals and highlighting the path (edge) that you will be using to get from terminal to terminal. We will use the BFS to return a list of closest terminals that a user would be able to reach when given an input of a specific terminal, returning the end location and flight time and length. Next we would use a shortest path algorithm to find the fastest way to get from terminal A to terminal B, when inputting a starting location and end location. If we feel that this is not enough complexity for the project we have other ideas to expand and create more unique algorithms.

Dataset Acquisition
Dataset source: https://openflights.org/data.html From the above mentioned source, we plan to download airports.dat and routes.dat files. airports.dat contains data of 5888 airlines which includes the airline id, name, alias, 2 letter IATA code, 3 letter ICAO code, airline’s callsign, country where airport is located and its active status. routes.dat contains information on 67663 routes between 3321 airports on 548 airlines which includes information about the airlines, source and destination airports, number of layovers and other categories. Both these files have data stored in UTF-8 encoding. Using python, we will open each file as a csv and parse each file and trim the data and use a subset of the entire dataset in another csv file.

Data Format and Data Correction
airports_formatted.csv: This file will be created by trimming unwanted data from airports.dat such as airline id, alias and callsign. After formatting the data and only including data which have active airports and airports whose IATA codes weren’t reported as NULL, the formatted file will contain data of the airport and location (latitude and longitude). routes_formatted.csv: This file will be created by trimming unwanted data from routes.dat such as airline, equipment, and codeshare information. After this, we will go through the data and further format it by removing duplicate routes. This file will contain data of the source airport, destination airport and number of stops. Basically, the aim of this formatting is to have data of only unique routes and routes with the IATA codes stored in the airports_fprmatted.csv only.

Data Storage
Our project will only use this subset of data stored in both these formatted files. We propose to store this formatted data into directed graphs where each node is the airport, and the weight of each edge is the flight time. The weights would be calculated by first parsing through the airports_formatted.csv file and calculating the distance between each airport (assuming the flight travels the shortest distance). We will create this graph using an adjacency matrix and the time complexity to create this would be O(V+E) where V is the number of vertex (airports) and E is the number of edges(routes). The space complexity would be O(V) as we will use a queue to keep track of the visited nodes.

Algorithm
We plan on creating a graph that stores nodes that each contain airport terminal data. We expect it to take O(n^2) time to create this graph using the information from our database. The connections between these nodes/airports will be the connecting routes between the airports. Given an input of any given airport, we plan on using a breadth-first search on the graph of airport nodes to find all of the possible destinations that are 1 flight away from that given airport. We expect this breadth first search to take O(m + n) time where n is the number of nodes and m is the number of edges in the graph. Furthermore, if given two airports by the user, we plan on using Djikstra’s shortest path algorithm to find the shortest possible number of route(s) between those two airports and provide information of each of the following flights that they could take to make it to their destination. This should take O(n^2) where n is the number of nodes in the graph. We also plan on visualizing this breadth first search for the user, using dots to represent nodes and a line to represent the connecting flights. However, we are not yet sure what library we can use to do this and/or how long it will take. We may also try and implement something visual for the user with Djikstra’s shortest path algorithm by turning the airports involved in the shortest path green so that the user can better understand how our algorithm works behind the scenes.

Timeline
Our timeline will be roughly split up by week. In the first week, we will attempt to parse and process our data and get it into a usable format. This section may take a little more than a week as we are not experienced in data managing with python. After that, we will attempt to implement and test our BFS algorithm. This is core to the function of our project, so this will be the most important piece to implement. Next, we will implement our shortest path algorithm which will calculate the fastest way to get from one airport to another. Our next algorithm, the visualization, will build off of this function so it is critical that we implement it first. Then, in week 4, we will implement the graph visualization which will provide an image to show the user the shortest path as calculated. We will use the last week or so to fine tune the project, and if needed add some additional functionality.


**Team Contract**
Communication
Team Meetings

We will meet whenever is required to meet our project goals. This may be between 1 and 4 times a week. Each meeting should last about an hour or enough time for each member to get on the same page. We will ideally meet in person but if that is not possible we will meet on zoom. We will taking notes on our meetings.

Assistance

Our team has a groupchat designated for the project that will allow us to respond quickly. Each member will check this chat at least twice a day and make a conscious effort to participate and respond accordingly.

Respect

We will make sure that everyone gets a chance to speak in every meeting. We will have a voting system to decide ideas. We will all make our best effort to respect the perspectives and opinions of others to make the group work as efficiently as possible.

Collaboration
Work Distribution
We will divide up the work evenly amongst ourselves. Once we have a finalized plan for our project we will more accueretly be able to assure that everyone is doing their part and contributing equally for their own individual strenghts.

Time Commitment
We are going to aim for 5 hours of work a week per person dedicated to this project. This means that over the next 4 weeks we will each contribute 20 hours towards developing our project. That's 80 hours total between all members. We all have other time commitments to other things of course, but we have all agreed to prioritize this project highly relative to our other assignments because it counts for a large portion of our grade in an important class. If a time conflict comes up, that person can put in more hours the next week to make up for their missed hours. Time conflicts will likely not occur though because we will be meeting together to work on the project, so we all have expectations for each other to show up.

Conflict Resolution
All conflicts within the team will be decided through voting diplomatically. In the event of a tie between the votes, we will sit and discuss all the alternates and solutions as a group and come to a consensus. If this doesn’t work either, we can consult the TA for guidance and clarity on a topic.

If any member is consistently late or hasn’t accomplished his tasks, then we will call a meeting and first understand his perspective and reason about why he hasn’t been able to do it and we can help him through whatever problem he is having. If the problem persists, we can involve the TA and about helping us with possible options about getting the specific team member in line.

Signatures
Jacob Poeschel - jacobop2 Michael Rheintgen - mar13 Dirgh Shah - dirghvs2 Branden Kooper - bkooper2
