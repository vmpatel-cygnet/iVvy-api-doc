# Collections

Some results return collections of objects. E.g. event?action=getEventList. The resulting JSON response for these collections will be an object with the following properties.

-	meta: An object providing information about the result set. The following keys may exist
  -	totalResults: The number of results in the complete collection
  -	start: The starting index of the collection this result represents
  -	perPage: The number of items per page of results
  -	count: The number of objects included in this result. 
-	results: An array of objects
