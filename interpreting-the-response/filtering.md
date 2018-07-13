# Filtering

Some requests (mostly requests that return collections and/or take pagination requests) may also accept a filter argument. The structure of this filter will be an object with the key’s being what needs to be filtered, and the value will be the content of the filter.

There are a number of options that may modify the filter behaviour. These are appended to the end of the key to filter. The accepted modifiers are:

-	__CONTAINS: Return the results that contain the value.
-	__NOTCONTAINS: Return the results that do not contain the value.
-	__BEGINS: Return the results that start with the value.
-	__ENDS: Return the results that end with the value.
-	__LESSTHAN: Return the results that are less than or equal to the value.
-	__GREATERTHAN: Return the results that are greater than or equal to the value.
-	__NOT: Return the results that are not equal to the value.
-	__EMPTY: Returns results that are empty

If you want to search for ‘Null’ values, you can use the special value ‘__ISNULL__’ for the filter value.

**Example: Filter all the results where the firstName = Bob**

`{"filter":{"firstName":"Bob"}}`

**Example: Filter all results where the firstName starts with ‘M’**

`{"filter":{"firstName__BEGINS":"M"}}`

**Example: Filter all results where the birthDay has not been set**

`{"filter":{"firstName":"__ISNULL__"}}`
