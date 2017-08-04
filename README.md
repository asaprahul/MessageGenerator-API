# MessageGenerator API

API to generate welcome messages for your hotel guests.

API implementation of the [Message Generator Project](https://github.com/MessageGenerator)

## How it works: 

Send POST requests to ```https://vast-brook-82312.herokuapp.com/getMessage```

The body of the request should contain this object: 

``` 
form: {
      'guest': 3,       //1, 2, 3, 4, 5, or 6
      'hotel': 2,       //1, 2, 3, 4, or 5
      'template' : 2,   //1, 2 or 3
      'phone' : '+15038038316'  //Your phone number
    }
```

This triggers the API to generate a text message with the given details and send the text message to the phone number provided in the body of the form object.


#### Guests: 
 
``` 
1 for Candy Pace
2 for Morgan Porter
3 for Bridgett Richard
4 for Melissa Perston
5 for Latoya Herrera
6 for Hewitt Hopper
```
  
#### Hotels : 
``` 
1 for Hotel California
2 for The Grand Budapest Hotel
3 for The Heartbreak Hotel
4 for The Prancing Pony
5 for The Fawlty Towers
```
    
#### Templates : 
``` 
1 for a message like "Good evening Samantha, welcome to Hotel Panda Express. Your room number 127, have a great stay."
    
2 for a message like "Good afternoon Maggie, I'm Sandy, Manager for Hotel Panda Express. We are delighted to have you as our guest. You will be staying in room number 127."
   
3 for a message like "Welcome to Hotel Panda Express! Good afternoon Jacob, your room number is 127. Have a wonderful stay with us!" 

```
    
## Sample Node.js code to send POST requests :

``` 
var request = require('request');

// Set the headers
var headers = {
}

// Configure the request
var options = {
    url: 'https://vast-brook-82312.herokuapp.com/getMessage',
    method: 'POST',
    headers: headers,
    form: {
      'guest': 3,
      'hotel': 2,
      'template' : 2,
      'phone' : '+15038038316'
    }
}

// Start the request
request(options, function (error, response, body) {
    if (!error && response.statusCode == 200) {
        console.log(body)
    }
})

```
Note: 
If you are using the sample node.js code to send POST requests, install this dependency first: 
`npm install request`
    
