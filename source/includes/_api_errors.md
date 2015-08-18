## Errors

The **nousrassemble** API uses the following error codes:

Code | Meaning  | Example
---------- | ---------- | ----------
400 | **Bad Request** |
401 | **Unauthorized** | Happen generally when Authorization header is not sent and then request is anonymous
403 | **Forbidden** | Can happen when user is not granted to access an object or when a tenant is not yet available (has a curtain)
404 | **Not Found** | An object does not exist 
406 | **Not Acceptable** | You try to do perform a forbidden action as unliking on a tenant which has disable negative votes
409 | **Conflict** | An object has been updated before your update or you try to vote for a proposal on the 
410 | **Gone** | An object is no more available. It can happen when a tenant is not available on API
422 | **Unprocessable** | Occurs when you reset a password and new password is not well-formed for example 
429 | **Too Many Requests** | You're requesting too many things! Slow down!
500 | **Internal Server Error** | We had a problem with our server. Try again later.
503 | **Service Unavailable** | We're down for maintenance. Please try again later.
