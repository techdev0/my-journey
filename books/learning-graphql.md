## Chapter 1

Remote Procedure Calls
1. Invented in the 1960's
2. Used for communication between clients/servers

Simple Object Access Protocol (SOAP)
1. Emereged at Microsoft in the late 1990's.
2. Used XML to encode messages via HTTP
3. Shortcomings: caused frustrations because SOAP implementations were fairly complex

REST
1. Initially, REST was used with XML, which created a painful step for developers (having to parse it before being able to use the data)
2. JSON was developed by Douglas Crockford who also wrote *JavaScript: The Good Parts*, in which he mentions that JSON was one fo the good parts.

REST Drawbacks
1. Overfetching
2. Underfetching
3. Slower user experience

REST Complaints:
1. Lack of flexibility: endpoints can begin to multiply quickly
2. Development speed can be slow (frontend/backend teams have to communicate more)

GraphQL Benefits
1. We get the data in the shape that we need it, nothing more, nothing less.
2. More declarative queries
3. Faster results (no extraneous data)
4. Typical architecture involves a single endpoint
    - A single endpoint can be a gateway to multiple data sources
    - Easier organization of data

Incremental adaption
1. Use GraphQL to fetch data from REST endpoints

In the Real World
1. Github's API version 4 uses GraphQL
2. Other users:
   - New York TImes, IBM, Twitter, Yelp

GraphQL Clients
1. Leaders:
   - Relay (http://relay.dev)
      - Works with React/Native
   - Apollo (https://apollographql.com)
      - Developed by Meteor Development Group

Links:
- GraphQL Server Libraries - https://graphql.org/code
- Data Fetching in React - https://www.youtube.com/watch?v=9sc8Pyc51uU
- A Gentle Intro to Graph Theory - https://dev.to/vaidehijoshi/a-gentle-introduction-to-graph-theory

## Chapter 4: Designing a Schema
1. schema first
    - Schema Definition Language (SDL)
    - Schema documents
      - define the types available in an application
      - used to validate GraphQL requests (backend and frontend)
2. scalar types: Int, Float, String, Boolean,ID
3. custom scalar types
    1. `scalar DateTime`
    2. graphql-custom-types npm package
        - commonly used custom scalar types
4. enumaration (enum) types
    - limits the values (strings) allowed for a particular field

## Chapter 5: Creating a GraphQL API
1. GraphQL.js: reference implementation by Fb
2. express-graphql
    - simple way to create a GraphQL server with Express
    - first library
3. Apollo server
4. schema
    - defines the operations clients are allowed
    - how different types are related
5. resolver
    - function that returns data for a particular field
