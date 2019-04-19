# OData 4.01

OData Version 4.01 adds various new features and removes a few restrictions. These changes can be categorized into:

- Extended Query Language
- Simplified Syntax
- Simplified Payloads
- Easier partial adoption of OData in existing REST APIs

OData 4.01 is highly compatible, incremental release over OData 4.0. A compliant 4.01 OData Service fully supports OData 4.0 clients.

New OData 4.01 query features and simplified syntax can be supported as compatible extensions to OData 4.0 syntax.

Content negotiation is facilitated through the ODataVersion header to ensure OData 4.0 clients don't receive unexpected constructs in response payloads.

## Protocol

|FEATURE|ODL|WebAPI|
|:---|:--:|:--:|
||||||||||||||||
|**NEW**|
| Default Namespaces. [[Spec]]("http://docs.oasis-open.org/odata/new-in-odata/v4.01/cn02/new-in-odata-v4.01-cn02.html#_Toc495652484")                                                  |N|N|
| Schema Versioning. [[Spec]]("http://docs.oasis-open.org/odata/new-in-odata/v4.01/cn02/new-in-odata-v4.01-cn02.html#_Toc495652485")                                                   |N|N|
| Headers EntityId and Isolation without OData- prefix. [[Spec]]("http://docs.oasis-open.org/odata/new-in-odata/v4.01/cn02/new-in-odata-v4.01-cn02.html#_Toc495652486")                |N|N|
| Preference omit-values. [[Spec]]("http://docs.oasis-open.org/odata/new-in-odata/v4.01/cn02/new-in-odata-v4.01-cn02.html#_Toc495652487")                                              |Y|N|
| Response Header AsyncResult. [[Spec]]("http://docs.oasis-open.org/odata/new-in-odata/v4.01/cn02/new-in-odata-v4.01-cn02.html#_Toc495652488")                                         |N|N|
| System Query Option $compute. [[Spec]]("http://docs.oasis-open.org/odata/new-in-odata/v4.01/cn02/new-in-odata-v4.01-cn02.html#_Toc495652491")                                        |Y|N|
| Indexing into Ordered Collections and Positional Insert. [[Spec]]("http://docs.oasis-open.org/odata/new-in-odata/v4.01/cn02/new-in-odata-v4.01-cn02.html#_Toc495652536")             |N|N|
| Deep Update. [[Spec]]("http://docs.oasis-open.org/odata/new-in-odata/v4.01/cn02/new-in-odata-v4.01-cn02.html#_Toc495652537")                                                         |Y|N|
| Set-Based Operations. [[Spec]]("http://docs.oasis-open.org/odata/new-in-odata/v4.01/cn02/new-in-odata-v4.01-cn02.html#_Toc495652494")                                                |Y|Y|
| $expand and $select with POST and PATCH. [[Spec]]("http://docs.oasis-open.org/odata/new-in-odata/v4.01/cn02/new-in-odata-v4.01-cn02.html#_Toc495652495")                             |N/A|N|
| Invoking Functions with Implicit Parameter Aliases. [[Spec]]("http://docs.oasis-open.org/odata/new-in-odata/v4.01/cn02/new-in-odata-v4.01-cn02.html#_Toc495652496")                  |N|N|
| Referencing an ETag in a Batch Request. [[Spec]]("http://docs.oasis-open.org/odata/new-in-odata/v4.01/cn02/new-in-odata-v4.01-cn02.html#_Toc495652497")                              |N|N|
| Referencing across Change Sets in a Batch Request. [[Spec]]("http://docs.oasis-open.org/odata/new-in-odata/v4.01/cn02/new-in-odata-v4.01-cn02.html#_Toc495652498")                   |N|N|
| Referencing Nested Inserted Entities. [[Spec]]("http://docs.oasis-open.org/odata/new-in-odata/v4.01/cn02/new-in-odata-v4.01-cn02.html#_Toc495652499")                                |N|N|
| Referencing Values in Response Bodies. [[Spec]]("http://docs.oasis-open.org/odata/new-in-odata/v4.01/cn02/new-in-odata-v4.01-cn02.html#_Toc495652500")                               |N|N|
||
|**PRUNED**|
|Metadata Service [[Spec]](http://docs.oasis-open.org/odata/new-in-odata/v4.01/cn02/new-in-odata-v4.01-cn02.html#_Toc495652489) |N|N|
||
|**IMPROVED**|
|Case-Insensitive System Query Options without $ prefix. [[Spec]](http://docs.oasis-open.org/odata/new-in-odata/v4.01/cn02/new-in-odata-v4.01-cn02.html#_Toc)|Y|Y|

## URL Conventions

|FEATURE|ODL|WebAPI|
|:---|:--:|:--:|
||||||||||||||||
|**NEW**|
|Alternate Keys.[[Spec]](http://docs.oasis-open.org/odata/new-in-odata/v4.01/cn02/new-in-odata-v4.01-cn02.html#_Toc495652502) |N|N|
|Key-as-Segment Convention.[[Spec]](http://docs.oasis-open.org/odata/new-in-odata/v4.01/cn02/new-in-odata-v4.01-cn02.html#_Toc495652503) |Y|Y|
|Addressing Operations without Namespace or Alias.[[Spec]](http://docs.oasis-open.org/odata/new-in-odata/v4.01/cn02/new-in-odata-v4.01-cn02.html#_Toc495652504) |Y|Y|
|Addressing a Member of an Ordered Collection.[[Spec]](http://docs.oasis-open.org/odata/new-in-odata/v4.01/cn02/new-in-odata-v4.01-cn02.html#_Toc495652505) |N|N|
|Annotation values in expressions.[[Spec]](http://docs.oasis-open.org/odata/new-in-odata/v4.01/cn02/new-in-odata-v4.01-cn02.html#_Toc495652507) |N|N|
|Casting String Values to Primitive Values.[[Spec]](http://docs.oasis-open.org/odata/new-in-odata/v4.01/cn02/new-in-odata-v4.01-cn02.html#_Toc495652509) |N|N|
|in Operator.[[Spec]](http://docs.oasis-open.org/odata/new-in-odata/v4.01/cn02/new-in-odata-v4.01-cn02.html#_Toc495652512) |Y|N|
|divby Operator.[[Spec]](http://docs.oasis-open.org/odata/new-in-odata/v4.01/cn02/new-in-odata-v4.01-cn02.html#_Toc495652513) |N|N|
|hassubset and hassubsequence Collection Functions.[[Spec]](http://docs.oasis-open.org/odata/new-in-odata/v4.01/cn02/new-in-odata-v4.01-cn02.html#_Toc495652514) |N|N|
|$expand of Stream Properties and Media Resources.[[Spec]](http://docs.oasis-open.org/odata/new-in-odata/v4.01/cn02/new-in-odata-v4.01-cn02.html#_Toc495652518) |N|N|
|System Query Option $compute..[[Spec]](http://docs.oasis-open.org/odata/new-in-odata/v4.01/cn02/new-in-odata-v4.01-cn02.html#_Toc495652521) |Y|N|
|System Query Option $index..[[Spec]](http://docs.oasis-open.org/odata/new-in-odata/v4.01/cn02/new-in-odata-v4.01-cn02.html#_Toc495652522) |Y|N|
||
|**PRUNED**|
|Structural Casting to Arbitrary Structured Types. [[Spec]](http://docs.oasis-open.org/odata/new-in-odata/v4.01/cn02/new-in-odata-v4.01-cn02.html#_Toc495652510)|N|N|
||
|**IMPROVED**|
|EQ Comparison. [[Spec]](http://docs.oasis-open.org/odata/new-in-odata/v4.01/cn02/new-in-odata-v4.01-cn02.html#_Toc495652508)|N|N|
|Case-Insensitive Operators and Functions.  [[Spec]](http://docs.oasis-open.org/odata/new-in-odata/v4.01/cn02/new-in-odata-v4.01-cn02.html#_Toc495652506)|Y|Y|
|Enumeration and Duration Literals without Prefix.  [[Spec]](http://docs.oasis-open.org/odata/new-in-odata/v4.01/cn02/new-in-odata-v4.01-cn02.html#_Toc495652511)|N|N|
|Collection Overloads for Functions concat, contains, endswith, indexof, length,startswith, and substring    [[Spec]](http://docs.oasis-open.org/odata/new-in-odata/v4.01/cn02/new-in-odata-v4.01-cn02.html#_Toc495652515)|N|N|
|substring with Negative Start Index.  [[Spec]](http://docs.oasis-open.org/odata/new-in-odata/v4.01/cn02/new-in-odata-v4.01-cn02.html#_Toc495652516)|N|N|
|/$count..  [[Spec]](http://docs.oasis-open.org/odata/new-in-odata/v4.01/cn02/new-in-odata-v4.01-cn02.html#_Toc495652517)|N|N|
|System Query Option $search..  [[Spec]](http://docs.oasis-open.org/odata/new-in-odata/v4.01/cn02/new-in-odata-v4.01-cn02.html#_Toc495652519)|N|N|
|System Query Option $select..  [[Spec]](http://docs.oasis-open.org/odata/new-in-odata/v4.01/cn02/new-in-odata-v4.01-cn02.html#_Toc495652520)|N|N|

## CSDL changes (XML)

|FEATURE|ODL|WebAPI|
|:---|:--:|:--:|
||||||||||||||||
|**NEW**|
|Decimal with Floating Scale. [[Spec]](http://docs.oasis-open.org/odata/new-in-odata/v4.01/cn02/new-in-odata-v4.01-cn02.html#_Toc495652525) |N|N|
|Built-in Abstract Type Edm.Untyped.. [[Spec]](http://docs.oasis-open.org/odata/new-in-odata/v4.01/cn02/new-in-odata-v4.01-cn02.html#_Toc495652526) |Y|N|
|Built-in Types for Terms: Edm.AnyPropertyPath and Edm.ModelElementPath  [[Spec]](http://docs.oasis-open.org/odata/new-in-odata/v4.01/cn02/new-in-odata-v4.01-cn02.html#_Toc495652527) |N|N|
|Key-Less Entity Types. [[Spec]](http://docs.oasis-open.org/odata/new-in-odata/v4.01/cn02/new-in-odata-v4.01-cn02.html#_Toc495652529) |Y|Y|
|Terms applying to Collections. [[Spec]](http://docs.oasis-open.org/odata/new-in-odata/v4.01/cn02/new-in-odata-v4.01-cn02.html#_Toc495652533) |N|N|
|Annotations targeting Parameters and Return Types. [[Spec]](http://docs.oasis-open.org/odata/new-in-odata/v4.01/cn02/new-in-odata-v4.01-cn02.html#_Toc495652534) |Y|N|
|Inheriting Annotations. [[Spec]](http://docs.oasis-open.org/odata/new-in-odata/v4.01/cn02/new-in-odata-v4.01-cn02.html#_Toc495652535) |N|N|
|Absolute Paths in Annotations. [[Spec]](http://docs.oasis-open.org/odata/new-in-odata/v4.01/cn02/new-in-odata-v4.01-cn02.html#_Toc495652536) |N|N|
|Annotation Expressions Has, In, Add, Sub, Neg, Mul, Div, DivBy, and Mod.. [[Spec]](http://docs.oasis-open.org/odata/new-in-odata/v4.01/cn02/new-in-odata-v4.01-cn02.html#_Toc495652537) |N|N|
|Client-Side Function odata.matchesPattern.. [[Spec]](http://docs.oasis-open.org/odata/new-in-odata/v4.01/cn02/new-in-odata-v4.01-cn02.html#_Toc495652538) |N|N|
|All URL Functions as Client-Side Functions. [[Spec]](http://docs.oasis-open.org/odata/new-in-odata/v4.01/cn02/new-in-odata-v4.01-cn02.html#_Toc495652539) |N|N|
||
|**PRUNED**|
|Metadata Service. [[Spec]](http://docs.oasis-open.org/odata/new-in-odata/v4.01/cn02/new-in-odata-v4.01-cn02.html#_Toc495652540) |N|N|
||
|**IMPROVED**|
|Key Properties. [[Spec]](http://docs.oasis-open.org/odata/new-in-odata/v4.01/cn02/new-in-odata-v4.01-cn02.html#_Toc495652528) |N|N|
|Inheritance. [[Spec]](http://docs.oasis-open.org/odata/new-in-odata/v4.01/cn02/new-in-odata-v4.01-cn02.html#_Toc495652530) |N|N|
|Referential Constraints. [[Spec]](http://docs.oasis-open.org/odata/new-in-odata/v4.01/cn02/new-in-odata-v4.01-cn02.html#_Toc495652531) |N|N|
|Unicode Facet. [[Spec]](http://docs.oasis-open.org/odata/new-in-odata/v4.01/cn02/new-in-odata-v4.01-cn02.html#_Toc495652532) |N|N|

## OData JSON format

|FEATURE|ODL|WebAPI|
|:---|:--:|:--:|
||||||||||||||||
|**NEW**|
|Simplified representation of Delta with Expand. [[Spec]](http://docs.oasis-open.org/odata/new-in-odata/v4.01/cn02/new-in-odata-v4.01-cn02.html#_Toc495652547) |Y|Y|
|Advertise Actions/Functions on Collection-Valued Properties. [[Spec]](http://docs.oasis-open.org/odata/new-in-odata/v4.01/cn02/new-in-odata-v4.01-cn02.html#_Toc495652550) |N|N|
|Advertise Non-Availability of Actions/Functions. [[Spec]](http://docs.oasis-open.org/odata/new-in-odata/v4.01/cn02/new-in-odata-v4.01-cn02.html#_Toc495652551) |N|N|
|Batch Requests and Responses[[Spec]](http://docs.oasis-open.org/odata/new-in-odata/v4.01/cn02/new-in-odata-v4.01-cn02.html#_Toc495652553) |Y|N|
||
|**IMPROVED**|
|Exponential Notation for Decimals. [[Spec]](http://docs.oasis-open.org/odata/new-in-odata/v4.01/cn02/new-in-odata-v4.01-cn02.html#_Toc495652544) |N|N|
|Control Information without prefix odata... [[Spec]](http://docs.oasis-open.org/odata/new-in-odata/v4.01/cn02/new-in-odata-v4.01-cn02.html#_Toc495652545) |Y|N|
|@type for Built-In Primitive Types. [[Spec]](http://docs.oasis-open.org/odata/new-in-odata/v4.01/cn02/new-in-odata-v4.01-cn02.html#_Toc495652546) |Y|N|
|Representation of Deleted Entities.[[Spec]](http://docs.oasis-open.org/odata/new-in-odata/v4.01/cn02/new-in-odata-v4.01-cn02.html#_Toc495652548) |Y|N|
|Representation of Deleted Links. [[Spec]](http://docs.oasis-open.org/odata/new-in-odata/v4.01/cn02/new-in-odata-v4.01-cn02.html#_Toc495652549) |Y|Y|
|Invoke Parameterless Actions with Empty Request Body.[[Spec]](http://docs.oasis-open.org/odaclta/new-in-odata/v4.01/cn02/new-in-odata-v4.01-cn02.html#_Toc495652552) |N|N|