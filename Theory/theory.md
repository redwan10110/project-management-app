# What is GraphQL

GraphQl is an open-source data query manipulation language  for apis and runtime for fulfilling queries with existing data.

IT is alternative to rest api, with some added benefits such as the ability to request the exact data that you want. 


# CRUD in GraphQL

+ Queries as GET
+ Mutation as PUT/ Delete 


# GraphQL Queries & Mutations

These are the GraphQL queries and mutations for the YouTube course.

## Get names of all clients
```
{
  clients {
    name
  }
}
```

## Get a single client name and email
```
{
  client(id: 1) {
    name
    email
  }
}
```

## Get name and status of all projects
```
{
  projects {
    name
    status
  }
}
```

## Get a single project name, description along with the client name and email
```
{
  project(id: 1) {
    name
    description,
    client {
      name
      email
    }
  }
}
```

## Create a new client and return all data
```
mutation {
  addClient(name: "Tony Stark", email: "ironman@gmail.com", phone: "955-365-3376") {
    id
    name
    email
    phone
  }
}
```

## Delete a client and return id
```
mutation {
  deleteClient(id: 1) {
    id
  }
}
```

## Create a new project and return name and description
```
mutation {
  addProject(name: "Mobile App", description: "This is the project description", status: "new", clientId: "1") {
   name
   description
  }
}