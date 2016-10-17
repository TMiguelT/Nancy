
## Going crazy with routes

Below are some samples of what routes in Nancy can look like. They cover some of the possible usages, but not all of them.

```c#
// would capture routes like /hello/nancy sent as a GET request
Get["/hello/{name}"] = parameters => {
    return "Hello " + parameters.name;
};

// would capture routes like /favoriteNumber/1234, but not /favoriteNumber/asdf as a GET request
Get["/favoriteNumber/{value:int}"] = parameters => {
    return "So your favorite number is " + parameters.value + "?";
};

// would capture routes like /products/1034 sent as a DELETE request
Delete[@"/products/(?<id>[\d]{1,7})"] = parameters => {
    return 200;
};

// would capture routes like /users/192/add/moderator sent as a POST request
Post["/users/{id}/add/{category}"] = parameters => {
    return HttpStatusCode.OK;
};
```
