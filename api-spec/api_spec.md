# API Spec
## Status Code
* 200 OK: the request was successful, such as update, get, action
* 201 Created: a new resource has been created
* 202 Accepted: the request has been received but has not completed, such as async delete
* 204 No Content: the request was successful, but no response body, such as delete
* 401 Unauthorized: Authentication information was not sent or is invalid
* 403 Forbidden: The authenticated user is not allowed access to the requested resource
* 404 Not Found: These are not the droids you are looking for
* 405 Method Not Allowed: The requested HTTP method is not allowed for this URL
* 409 Conflict: the requested operation conflicts with the current state
* 422 Unprocessable Entity: The request was well-formed (400) and in a supported format (415), but cannot be processed. Typically used for application-specific validation errors
* 500 Internal Server Error: A generic message for an error on the server
* 503 Service Unavailable: The request couldn't be handled due to maintenance or overload

## Resources
* Resource representations MUST have these attributes
  * type: A string that uniquely identifies the kind, or type, of resource this is

* SHOULD have, in almost all cases
  * id: A string which uniquely identifies this resource
  * links: A map with links
    * self: The location of the resource itself.

* And MAY have, when appropriate
  * links: child resources and collections
  
## Collections
Collections are a special kind of resource. They have a "data" array that contains an array of resources.

* Collection representations MUST have:
  * type: "collection"
  * resourceType: The id of the schema for the type of resource this collection holds.
  * data: An array containing resource representations, This MUST always be present and be an array, even if there are 0 or 1 entries in it.

* SHOULD have, in almost all cases
  * links: A map with links
    * self: The location of the resource itself  
    
* And MAY have, when appropriate
  * Additional links: entries for related resources and collections
  
## Errors
* Error responses MUST be a valid resource which gives more information about the error. At a minimum, they MUST include
  * type: "error"
  * Code: A short identifier for the error, suitable for identifying what specific kind of error this is within client code
  * Status: the HTTP status code of the response
  
* Errors SHOULD include:
  * message: A short description of the error suitable for a human developer to read.
  
## Links
Links provide a trail for the client to follow to get to related information that is not included in the response

* resource links:
  * self: resource support get method
  * collection: resource support get method for collection
  * update: resource support put method
  * remove: resource support delete method 
  * child: resource child resource link
  
* collection links:
  * self
  * resource links in data: has the same described as above

## Operations
|Operation|HTTP Method|Request URL|
|-|-|-|
|List|GET|https://base/v1/collection_name|
|Get|GET|https://base/v1/collection_name/resource_id|
|Create|POST|https://base/v1/collection_name|
|Update|PUT|https://base/v1/collection_name/resource_id|
|Delete|DELETE|https://base/v1/collection_name/resource_id|
|Action|POST|https://base/v1/collection_name/resource_id?action=action_name|

## Schemas API File
file describe resource, resource field, father-child relationship, method, action

* resourceType: resource name
* collectionName: resource collection name
* parentResources: all parents of resource
* supportAsyncDelete: if support async delete
* resourceFields: resource fields
  * type: bool, int, string, map, array, json, date, resource, enum
  * elemType: if type is array, type of array element
  * validValues: if type is enum, it is a valid values array
  * keyType, valueType: if type is map, key and value type for map
  * description: field description info, described as below:
    * readonly
    * required
    * isDomain
    * immutable  
* subResources: if resourceField type is resource, is nesting resource, need define sub-resource, format is the same with resourceFields
* resourceMethods: resource support method array
* collectionMethods: collection support method array
* resourceActions: resource support actions
  * name: action name
  * input: action input fields, format is the same with resourceFields
  * output: action output fields, format is the same with resourceFields

## Filtering
If service support filtering for list resources, The client performs a search by starting with the URL for a standard query request. If they've already done a query and want to filter the results, The client then adds on query string parameters for {filter name}{"_"+modifier}={value}

* The underscore and modifier are optional if the desired modifier is eq.
  * name_eq=a and name=a are equivalent.
* For example to search for filenames starting with "a" and greater than 1kb, the client would append:
  * name_prefix=a&size_gt=1024
* To search for non-image files, they could append:
  * name_notlike=%.jpg&name_notlike=%.png
* All special characters in filter values MUST be URL-encoded. Note: "%" characters are shown here for clarity, but would be "%25" in an actual request.
* There is no mechanism defined for OR-ing conditions. All filters are AND-ed together

the standard modifiers

|modifier|meaning|
|-|-|
|`"eq"`      | equal to<br/>(always available, the default if no modifier is specified)|
|`"ne"`      | not equal to|
|`"lt"`      | less than|
|`"lte"`     | less than or equal to|
|`"gt"`      | greater than|
|`"gte"`     | greater than or equal to|
|`"prefix"`  | starts with|
|`"like"`    | matches, as in SQL:<br/>&bull; underscore ("\_") for exactly one character<br/>&bull; percent ("%") for 0 or more characters<br/>&bull; "\_" for one underscore character<br/>&bull;"%" for one percent character.|
|`"notlike"` | does not match (as above)|
|`"null"`    | value is NULL|
|`"notnull"` | value is not NULL|









