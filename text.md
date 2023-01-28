1. Hello everyone
My name is Vlad and I am a junior frontend developer.
Today I will tell you about GraphQL technology: what it is, compare it with the REST API and see how it works

2. GraphQL is a query language for client and server interaction and also the execution environment for these requests

GraphQL was created in order to overcome the limitations of the REST architecture. It is suitable for applications that have a lot of data and they are stored in different databases.

The GraphQL approach is based on a simple idea — instead of creating endpoints for each object, it is enough to create one "smart" endpoint that will work with complex queries and return cumulative data to clients in the volume in which clients request them.

3. This programming language was created by Facebook developers in 2012
GraphQL is a replacement for REST
GraphQL uses a Query Language
Allows the client to specify exactly what data they need
Facilitates data aggregation from multiple sources
Uses a type system to describe data
All types of queries in GraphQL are sent via POST.

4. ADVANTAGES OVER REST API
One link for all requests
One request to many entities
In the answer ONLY the requested information
The request body defines the server response

5. Let's take an example
GraphQL was developed in big old Facebook, but even much simpler applications can run into the limitations of traditional REST APIs. For example, imagine you want to display a list of posts, and under each post a list of likes, including usernames and avatars. Actually, it's not hard, you just change the posts API to contain the likes array, which will contain the user objects.

6. But then, when developing a mobile application, it turned out that due to loading additional data the app is running slower. So you now need two endpoints, one one that returns posts with likes and one without them. Let's add one more factor: it turns out that posts are stored in a MySQL database, while likes in Redis! What to do now?! Here the REST API has reached its limit and GraphQL comes to the rescue.

7. GRAPHQL API IS BUILT ON THREE MAIN BUILDING BLOCKS:
Schema
Queries
Resolvers

8. GraphQL Schema is a description of your data types on the server, the relationships between them and the logic for obtaining this data

You have data on the server
There are methods for obtaining this data (resolve methods)
For these methods, you describe the data types of the input and output values (type declaration)
Take resolve methods and type descriptions, cleverly mix and get your GraphQL Schema

9. SCHEMA DEFINITION
You describe your data with a schema
Strongly Typed
Types can be a Scalar (boolean, string, ID, Float) or Object with fields
Schema can generate types in Typescript

10. Resolvers
Resolver is a function that returns data for a specific field. You can return only the data that is defined in the schema by the TypeDefs object. Recognizers can be asynchronous.
This is an example of a simple schema that defines how and what data the client will receive from the GraphQL server.

11. GraphQL Queries
The schema determines what data the client can receive. But to interact with it, you need to make the right queries. Here GraphQL also offers a thoughtful concept.

Example of a simple request:

The response to the request looks like this:
There are two fields in the request. The user field returned an object with the String type.

12. Arguments
In the request, you can point to a specific user using an argument. For example:
Here we want to get the age of the user with id = 2. Instead of id, name can be used as an argument if we know that the schema describes a function for processing such a value.
Multiple arguments can be used. For example, set a limit on the number of posts:

13. Aliases
For convenience, you can assign aliases — aliases to fields. Request example:
An alias will be specified in the response:
Aliases help to avoid conflicts when field names match.

14. Fragments
Fragments help to specify a structure with many fields. The concept is used when you need to divide complex queries into small parts. This is especially useful when you have to combine a large number of interface components with different fragments into one sample.
Example:

15. Variables
The values inside the query can be made dynamic using variables. Request example:
Here we create a named function. This can be useful in applications that run a lot of queries.
Example:

16. Directives
The concept of variables allows you to use directives that dynamically change the structure and form of queries depending on conditions. GraphQL uses two directives: @include and @skip.

Example of using @include:
Here we say to use the field if it is true. We see that $getFollowers has a false value, so the field is not included in the response.

Example of using @skip:
Here we say to skip the field if it is true. We see that $getFollowers has the value true, so the field is not included in the response.

17. A good way to try all this in practice is to use the GraphQL API Explorer from GitHub. For example, let's try the following query

18. Example with GraphQL API Explorer from GitHub

19. Mutations:
The mutation type adds data
This is an analogue of POST and PUT in REST
Can also specify return properties
Pass in variables

20. SUBSCRIPTION:
The subscription type allows you to listen to changes in the database in realtime. Subscriptions use websockets for this.

Example:

This request allows you to get a list of users with names and the number of likes each time the number of likes changes. Such functionality is used, for example, in the web interface to display user activity or voting results.

21. CLIENT-SERVER INTERACTION (SHORTLY):
The client sends a request to the GraphQL server to read or modify data. This request is made in accordance with a scheme approved in advance.
The GraphQL server recognizes the request by special functions — resolvers — and receives data on the requested fields.
The client receives a response with the requested data structure, usually in JSON format.

22. AS A RESULT, WHEN GRAPHQL CAN BE USEFUL:
Striving to minimize the number of client requests.
Refusal to denormalize data only to optimize work on the user interface.
The presence of multiple sources of information that multiple applications work with.
THE END
Thank you for your attention!

23. Thank for your attantion, good buy!