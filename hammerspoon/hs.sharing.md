# Hammerspoon docs: hs.sharing

Share items with the macOS Sharing Services under the control of Hammerspoon.

This module will allow you to share Hammerspoon items with registered Sharing Services.  Some of the built-in sharing services include sharing through mail, Facebook, AirDrop, etc.  Other applications can add additional services as well.

For most sharing services (this has not been tested with all), the user will be prompted with the standard sharing dialog showing what is to be shared and offered a chance to submit or cancel.

This example prepares an email with a screenshot:
~~~lua
mailer = hs.sharing.newShare("com.apple.share.Mail.compose")
mailer:subject("Screenshot generated at " .. os.date()):recipients({ "user@address.com" })
mailer:shareItems({ [[
    Add any notes that you wish to add describing the screenshot here and click the Send icon when you are ready to send this

]], hs.screen.mainScreen():snapshot() })
~~~

Common item data types that can be shared with Sharing Services include (but are not necessarily limited to):
 * basic data types like strings and numbers
 * hs.image objects
 * hs.styledtext objects
 * web sites and other URLs through the use of the [hs.sharing.URL](#URL) function
 * local files through the use of file URLs created with the [hs.sharing.fileURL](#fileURL) function

## API Overview
* Constants - Useful values which cannot be changed</li>
  * builtinSharingServices[]
* Functions - API calls offered directly by the extension</li>
  * URL
  * fileURL
  * shareTypesFor
* Constructors - API calls which return an object, typically one that offers API methods</li>
  * newShare
* Methods - API calls which can only be made on an object returned by a constructor</li>
  * accountName
  * alternateImage
  * attachments
  * callback
  * canShareItems
  * image
  * messageBody
  * permanentLink
  * recipients
  * serviceName
  * shareItems
  * subject
  * title

## API Documentation

### Constants

#### builtinSharingServices[]
  * Signature: hs.sharing.builtinSharingServices[]
  * Type: Constant
  * Description: A table containing the predefined sharing service labels defined by Apple.
  This table contains the default sharing service identifiers as identified by Apple.  Depending upon the software you have installed on your system, not all of the identifiers included here may be available on your computer and other Applications may provide sharing services with identifiers not included here.  You can determine valid identifiers for specific data types by using the [hs.sharing.shareTypesFor](#shareTypesFor) function which will list all identifiers that will work for all of the specified items, even those which do not appear in this table.

### Functions

#### URL
  * Signature: hs.sharing.URL(URL, [fileURL]) -> table
  * Type: Function
  * Description: Returns a table representing the URL specified.
   * Because macOS requires URLs to be represented as a specific object type which has no exact equivalent in Lua, Hammerspoon uses a table with specific keys to allow proper identification of a URL when included as an argument or result type.  Use this function or the [hs.sharing.fileURL](#fileURL) wrapper function when specifying a URL to ensure that the proper keys are defined.
     * At present, the following keys are defined for a URL table (additional keys may be added in the future if future Hammerspoon modules require them to more completely utilize the macOS NSURL class, but these will not change):
       * url           - a string containing the URL with a proper schema and resource locator
       * __luaSkinType - a string specifying the macOS type this table represents when converted into an Objective-C type
  * Parameters:
     * URL     - a string or table specifying the URL.
     * fileURL - an optional boolean, default `false`, specifying whether or not the URL is supposed to represent a file on the local computer.
  * Returns:
     * a table containing the necessary labels for representing the specified URL as required by the macOS APIs.
  * Notes:
     * If the URL is specified as a table, it is expected to contain a `url` key with a string value specifying a proper schema and resource locator.

#### fileURL
  * Signature: hs.sharing.fileURL(path) -> table
  * Type: Function
  * Description: Returns a table representing a file URL for the path specified.
  * Parameters:
     * path - a string specifying a path to represent as a file URL.
  * Returns:
     * a table containing the necessary labels for converting the specified path into a URL as required by the macOS APIs.
  * Notes:
     * this function is a wrapper to [hs.sharing.URL](#URL) which sets the second argument to `true` for you.
     * see [hs.sharing.URL](#URL) for more information about the table format returned by this function.

#### shareTypesFor
  * Signature: hs.sharing.shareTypesFor(items) -> identifiersTable
  * Type: Function
  * Description: Returns a table containing the sharing service identifiers which can share the items specified.
  * Parameters:
     * items - an array (table) or list of items separated by commas which you wish to share with this module.
  * Returns:
     * an array (table) containing strings which identify sharing service identifiers which may be used by the [hs.sharing.newShare](#newShare) constructor to share the specified data.
  * Notes:
     * this function is intended to be used to determine the identifiers for sharing services available on your computer and that may not be included in the [hs.sharing.builtinSharingServices](#builtinSharingServices) table.

### Constructors

#### newShare
  * Signature: hs.sharing.newShare(type) -> sharingObject
  * Type: Constructor
  * Description: Creates a new sharing object of the type specified by the identifier provided.
  * Parameters:
     * type - a string specifying a sharing type identifier as listed in the [hs.sharing.builtinSharingServices](#builtinSharingServices) table or returned by the [hs.sharing.shareTypesFor](#shareTypesFor).
  * Returns:
     * a sharingObject or nil if the type identifier cannot be created on this system

### Methods

#### accountName
  * Signature: hs.sharing:accountName() -> string | nil
  * Type: Method
  * Description: The account name used by the sharing service when posting on Twitter or Sina Weibo.
  * Parameters:
     * None
  * Returns:
     * a string containing the account name used by the sharing service, or nil if the sharing service does not provide this.
  * Notes:
     * According to the Apple API documentation, only the Twitter and Sina Weibo sharing services will set this property, but this has not been fully tested.

#### alternateImage
  * Signature: hs.sharing:alternateImage() -> hs.image object | nil
  * Type: Method
  * Description: Returns an alternate image, if one exists, representing the sharing service provided by this sharing object.
  * Parameters:
     * None
  * Returns:
     * an hs.image object or nil, if no alternate image representation for the sharing service is defined.

#### attachments
  * Signature: hs.sharing:attachments() -> table | nil
  * Type: Method
  * Description: If the sharing service provides an array of the attachments included when the data was posted, this method will return an array of file URL tables of the attachments.
  * Parameters:
     * None
  * Returns:
     * an array (table) containing the attachment file URLs, or nil if the sharing service selected does not provide this.
  * Notes:
     * not all sharing services will set a value for this property.

#### callback
  * Signature: hs.sharing:callback(function | nil) -> sharingObject
  * Type: Method
  * Description: Set or clear the callback for the sharingObject.
  * Parameters:
     * a function, or nil, to set or remove the callback for the sharingObject
  * Returns:
     * the sharingObject
  * Notes:
     * the callback should expect 3 or 4 arguments and return no results.  The arguments will be as follows:
       * the sharingObject itself
       * the callback message, which will be a string equal to one of the following:
         * "didFail"   - an error occurred while attempting to share the items
         * "didShare"  - the sharing service has finished sharing the items
         * "willShare" - the sharing service is about to start sharing the items; occurs before sharing actually begins
       * an array (table) containing the items being shared; if the message is "didFail" or "didShare", the items may be in a different order or converted to a different internal type to facilitate sharing.
       * if the message is "didFail", the fourth argument will be a localized description of the error that occurred.

#### canShareItems
  * Signature: hs.sharing:canShareItems(items) -> boolean
  * Type: Method
  * Description: Returns a boolean specifying whether or not all of the items specified can be shared with the sharing service represented by the sharingObject.
  * Parameters:
     * items - an array (table) or list of items separated by commas which are to be shared by the sharing service
  * Returns:
     * a boolean value indicating whether or not all of the specified items can be shared with the sharing service represented by the sharingObject.

#### image
  * Signature: hs.sharing:image() -> hs.image object | nil
  * Type: Method
  * Description: Returns an image, if one exists, representing the sharing service provided by this sharing object.
  * Parameters:
     * None
  * Returns:
     * an hs.image object or nil, if no image representation for the sharing service is defined.

#### messageBody
  * Signature: hs.sharing:messageBody() -> string | nil
  * Type: Method
  * Description: If the sharing service provides the message body that was posted when sharing has completed, this method will return the message body as a string.
  * Parameters:
     * None
  * Returns:
     * a string containing the message body, or nil if the sharing service selected does not provide this.
  * Notes:
     * not all sharing services will set a value for this property.

#### permanentLink
  * Signature: hs.sharing:permanentLink() -> URL table | nil
  * Type: Method
  * Description: If the sharing service provides a permanent link to the post when sharing has completed, this method will return the corresponding URL.
  * Parameters:
     * None
  * Returns:
     * the URL for the permanent link, or nil if the sharing service selected does not provide this.
  * Notes:
     * not all sharing services will set a value for this property.

#### recipients
  * Signature: hs.sharing:recipients([recipients]) -> current value | sharingObject
  * Type: Method
  * Description: Get or set the subject to be used when the sharing service performs its sharing method.
  * Parameters:
     * recipients - an optional array (table) or list of recipient strings separated by commas which specify the recipients of the shared items.
  * Returns:
     * if an argument is provided, returns the sharingObject; otherwise returns the current value.
  * Notes:
     * not all sharing services will make use of the value set by this method.
     * the individual recipients should be specified as strings in the format expected by the sharing service; e.g. for items being shared in an email, the recipients should be email address, etc.

#### serviceName
  * Signature: hs.sharing:serviceName() -> string
  * Type: Method
  * Description: The service identifier for the sharing service represented by the sharingObject.
  * Parameters:
     * None
  * Returns:
     * a string containing the identifier for the sharing service.
  * Notes:
     * this string will match the identifier used to create the sharing service object with [hs.sharing.newShare](#newShare)

#### shareItems
  * Signature: hs.sharing:shareItems(items) -> sharingObject
  * Type: Method
  * Description: Shares the items specified with the sharing service represented by the sharingObject.
  * Parameters:
     * items - an array (table) or list of items separated by commas which are to be shared by the sharing service
  * Returns:
     * the sharingObject, or nil if one or more of the items cannot be shared with the sharing service represented by the sharingObject.
  * Notes:
     * You can check to see if all of your items can be shared with the [hs.sharing:canShareItems](#canShareItems) method.

#### subject
  * Signature: hs.sharing:subject([subject]) -> current value | sharingObject
  * Type: Method
  * Description: Get or set the subject to be used when the sharing service performs its sharing method.
  * Parameters:
     * subject - an optional string specifying the subject for the posting of the shared content
  * Returns:
     * if an argument is provided, returns the sharingObject; otherwise returns the current value.
  * Notes:
     * not all sharing services will make use of the value set by this method.

#### title
  * Signature: hs.sharing:title() -> string
  * Type: Method
  * Description: The title for the sharing service represented by the sharingObject.
  * Parameters:
     * None
  * Returns:
     * a string containing the title of the sharing service.
  * Notes:
     * this string differs from the identifier used to create the sharing service object with [hs.sharing.newShare](#newShare) and is intended to provide a more friendly label for the service if you need to list or refer to it elsewhere.