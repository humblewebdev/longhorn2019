# Diving into Guzzle: Getting the Most from Your Requests

> Steven Wade

## HTTP Requests are Hard

- URLs
- Headers
- Method
- Status Codes
- Sending / Parsing response

- cURL does not throw exceptions. You have to use `curl_errno($handler)`.

## Guzzle

- Supports cURL, Streams, and parallel executions
- Middleware:
  - Provides Error handling by default
  - Redirects
  - Cookies
  - Prepare Body
  - Extendable with `HandlerStack::create()`
  - Tap: `GuzzleHttp\Middleware::tap($before, $after)`
    - Callback events for both before and after a request is made.
    - Keeping track of stats maybe
  - Log: `GuzzleHttp\Middleware::log($logger, $messageFormatter)`
    - Particularly useful for failure back-tracking
  - Retry: `GuzzleHttp\Middleware::retry($decider, $delay)`
  - Custom Middleware
    - Allows for modifying outgoing requests before they are sent and responses before they are returned from the client.
  - Custom listeners
    - Particularly good for logging events and other things where one would want to know that something happened.
    
## Asynchronicity

- We can drastically speed up most applications by making our requests asynchronous. Requires `cURL` for this.
- Instead of `get()` or `post()`, it's just `getAsync()` or `postAsync()`.
- We can resolve all promises with helper methods like `all()` and `settle()`. `all()` fails if any fail, while `settle()` will not.
    
## Testing

- Supports a mock handler so that no real requests are made out to the network. Otherwise everything works exactly as it does in production.
- Supports both normal synchronous and asynchronous handling.
- Adam plugged Guzzler, which the speaker had not heard of yet.
