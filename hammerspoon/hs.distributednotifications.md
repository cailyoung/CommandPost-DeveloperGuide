# Hammerspoon docs: hs.distributednotifications

Interact with NSDistributedNotificationCenter
There are many notifications posted by parts of OS X, and third party apps, which may be interesting to react to using this module.

You can discover the notifications that are being posted on your system with some code like this:
```
foo = hs.distributednotifications.new(function(name, object, userInfo) print(string.format("name: %s\nobject: %s\nuserInfo: %s\n", name, object, hs.inspect(userInfo))) end)
foo:start()
```

Note that distributed notifications are expensive - they involve lots of IPC. Also note that they are not guaranteed to be delivered, particularly if the system is very busy.

## API Overview
* Functions - API calls offered directly by the extension</li>
  * post
* Constructors - API calls which return an object, typically one that offers API methods</li>
  * new
* Methods - API calls which can only be made on an object returned by a constructor</li>
  * start
  * stop

## API Documentation

### Functions

#### post
  * Signature: hs.distributednotifications.post(name[, sender[, userInfo]])
  * Type: Function
  * Description: Sends a distributed notification
  Paramters:
     * name - A string containing the name of the notification
     * sender - An optional string containing the name of the sender of the notification (in the form `com.domain.application.foo`). Defaults to nil.
     * userInfo - An optional table containing additional information to post with the notification. Defaults to nil.

### Constructors

#### new
  * Signature: hs.distributednotifications.new(callback[, name[, object]]) -> object
  * Type: Constructor
  * Description: Creates a new NSDistributedNotificationCenter watcher
  * Parameters:
     * callback - A function to be called when a matching notification arrives. The function should accept one argument:
      * notificationName - A string containing the name of the notification
     * name - An optional string containing the name of notifications to watch for. A value of `nil` will cause all notifications to be watched. Defaults to `nil`.
     * object - An optional string containing the name of sending objects to watch for. A value of `nil` will cause all sending objects to be watched. Defaults to `nil`.
  * Returns:
     * An `hs.distributednotifications` object

### Methods

#### start
  * Signature: hs.distributednotifications:start() -> object
  * Type: Method
  * Description: Starts a NSDistributedNotificationCenter watcher
  * Parameters:
     * None
  * Returns:
     * The `hs.distributednotifications` object

#### stop
  * Signature: hs.distributednotifications:stop() -> object
  * Type: Method
  * Description: Stops a NSDistributedNotificationCenter watcher
  * Parameters:
     * None
  * Returns:
     * The `hs.distributednotifications` object