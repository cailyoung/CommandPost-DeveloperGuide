# Hammerspoon docs: hs.usb.watcher

Watch for USB device connection/disconnection events

## API Overview
* Constructors - API calls which return an object, typically one that offers API methods</li>
  * new
* Methods - API calls which can only be made on an object returned by a constructor</li>
  * start
  * stop

## API Documentation

### Constructors

#### new
  * Signature: hs.usb.watcher.new(fn) -> watcher
  * Type: Constructor
  * Description: Creates a new watcher for USB device events
  * Parameters:
     * fn - A function that will be called when a USB device is inserted or removed. The function should accept a single parameter, which is a table containing the following keys:
      * eventType - A string containing either "added" or "removed" depending on whether the USB device was connected or disconnected
      * productName - A string containing the name of the device
      * vendorName - A string containing the name of the device vendor
      * vendorID - A number containing the Vendor ID of the device
      * productID - A number containing the Product ID of the device
  * Returns:
     * A `hs.usb.watcher` object

### Methods

#### start
  * Signature: hs.usb.watcher:start() -> watcher
  * Type: Method
  * Description: Starts the USB watcher
  * Parameters:
     * None
  * Returns:
     * The `hs.usb.watcher` object

#### stop
  * Signature: hs.usb.watcher:stop() -> watcher
  * Type: Method
  * Description: Stops the USB watcher
  * Parameters:
     * None
  * Returns:
     * The `hs.usb.watcher` object