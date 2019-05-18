# CAPFIN: Customer List
A demo to allow addition of customers and addresses to MongoDB whilst associating customers to respective addresses.

## Tech Stack
```
React JS
Node.js
MongoDB
```

## Installation

1. Clone the repository.

```
https://github.com/vanniekerkalex/capfin_customers.git
```

2. Make sure Node.js and NPM are installed on your computer. (NPM comes with Node.js)

```
https://nodejs.org/
```

3. Open a terminal window, go to the **./server** directory and run the following commands to install the necessary packages and start the server:

```
npm update
nodemon
```

4. Open a new (2nd) terminal window, go to the **./client** directory and run the following commands to install the necessary packages and start the react web app:

```
npm update
npm start
```

5. A tab in your browser should open up with the running web app.

## API Instructions

The API that handles the MongoDB requests has been created with GraphQL. You can access the API here:

```
http://localhost:4000/api
```
You can find more information on GraphQL here:
```
https://graphql.org/
```

## API Usage Demo
To view all the customers associated with a specific address.

### 1. Display all the addresses in DB with their information.

Input
```
{
 addresses {
  id
  street
  suburb
  code
 }
}
```
Output
```
{
  "data": {
    "addresses": [
      {
        "id": "5cdf38d600d45419cfc22fbe",
        "street": "5 Newlands",
        "suburb": "Claremont",
        "code": "7708"
      },
      {
        "id": "5cdfe879a57af354b7b6cd91",
        "street": "17 Highwick",
        "suburb": "Kenilworth",
        "code": "7780"
      },
      {
        "id": "5cdff83fa2d0515a24244b07",
        "street": "1 Industrie Street",
        "suburb": "Kuilsriver",
        "code": "7580"
      },
      {
        "id": "5ce004bb10a8996cab2a39ee",
        "street": "25 Protea Road",
        "suburb": "Newlands",
        "code": "7708"
      }
    ]
  }
}
```

### 2. Copy the ID of one of the addresses that you wish to get the customer list for, then do as follows:

Input
```
{
 address(id: "5cdfe879a57af354b7b6cd91") {
  customers{
    fname
    sname 
  }
 }
}
```
Output
```
{
  "data": {
    "address": {
      "customers": [
        {
          "fname": "Mike",
          "sname": "Zimbo"
        },
        {
          "fname": "Fred",
          "sname": "Hope"
        }
      ]
    }
  }
}
```
