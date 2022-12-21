--- 

title: Swagger Petstore - OpenAPI 3.0 

language_tabs: 
   - shell 

toc_footers: 
   - <a href='#'>Sign Up for a Developer Key</a> 
   - <a href='https://github.com/lavkumarv'>Documentation Powered by lav</a> 

includes: 
   - errors 

search: true 

--- 

# Introduction 

This is a sample Pet Store Server based on the OpenAPI 3.0 specification.  You can find out more about
Swagger at [https://swagger.io](https://swagger.io). In the third iteration of the pet store, we've switched to the design first approach!
You can now help us improve the API whether it's by making changes to the definition itself or to the code.
That way, with time, we can improve the API in general, and expose some of the new features in OAS3.

_If you're looking for the Swagger 2.0/OAS 2.0 version of Petstore, then click [here](https://editor.swagger.io/?url=https://petstore.swagger.io/v2/swagger.yaml). Alternatively, you can load via the `Edit > Load Petstore OAS 2.0` menu option!_

Some useful links:
- [The Pet Store repository](https://github.com/swagger-api/swagger-petstore)
- [The source API definition for the Pet Store](https://github.com/swagger-api/swagger-petstore/blob/master/src/main/resources/openapi.yaml) 

**Version:** 1.0.11 

[Find out more about Swagger](http://swagger.io) 

# /PET
## ***PUT*** 

**Summary:** Update an existing pet

**Description:** Update an existing pet by Id

### HTTP Request 
`***PUT*** /pet` 

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Successful operation |
| 400 | Invalid ID supplied |
| 404 | Pet not found |
| 405 | Validation exception |

## ***POST*** 

**Summary:** Add a new pet to the store

**Description:** Add a new pet to the store

### HTTP Request 
`***POST*** /pet` 

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Successful operation |
| 405 | Invalid input |

# /PET/FINDBYSTATUS
## ***GET*** 

**Summary:** Finds Pets by status

**Description:** Multiple status values can be provided with comma separated strings

### HTTP Request 
`***GET*** /pet/findByStatus` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| status | query | Status values that need to be considered for filter | No |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | successful operation |
| 400 | Invalid status value |

# /PET/FINDBYTAGS
## ***GET*** 

**Summary:** Finds Pets by tags

**Description:** Multiple tags can be provided with comma separated strings. Use tag1, tag2, tag3 for testing.

### HTTP Request 
`***GET*** /pet/findByTags` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| tags | query | Tags to filter by | No |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | successful operation |
| 400 | Invalid tag value |

# /PET/{PETID}
## ***GET*** 

**Summary:** Find pet by ID

**Description:** Returns a single pet

### HTTP Request 
`***GET*** /pet/{petId}` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| petId | path | ID of pet to return | Yes |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | successful operation |
| 400 | Invalid ID supplied |
| 404 | Pet not found |

## ***POST*** 

**Summary:** Updates a pet in the store with form data

**Description:** 

### HTTP Request 
`***POST*** /pet/{petId}` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| petId | path | ID of pet that needs to be updated | Yes |  |
| name | query | Name of pet that needs to be updated | No |  |
| status | query | Status of pet that needs to be updated | No |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 405 | Invalid input |

## ***DELETE*** 

**Summary:** Deletes a pet

**Description:** delete a pet

### HTTP Request 
`***DELETE*** /pet/{petId}` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| api_key | header |  | No |  |
| petId | path | Pet id to delete | Yes |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 400 | Invalid pet value |

# /PET/{PETID}/UPLOADIMAGE
## ***POST*** 

**Summary:** uploads an image

**Description:** 

### HTTP Request 
`***POST*** /pet/{petId}/uploadImage` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| petId | path | ID of pet to update | Yes |  |
| additionalMetadata | query | Additional Metadata | No |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | successful operation |

# /STORE/INVENTORY
## ***GET*** 

**Summary:** Returns pet inventories by status

**Description:** Returns a map of status codes to quantities

### HTTP Request 
`***GET*** /store/inventory` 

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | successful operation |

# /STORE/ORDER
## ***POST*** 

**Summary:** Place an order for a pet

**Description:** Place a new order in the store

### HTTP Request 
`***POST*** /store/order` 

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | successful operation |
| 405 | Invalid input |

# /STORE/ORDER/{ORDERID}
## ***GET*** 

**Summary:** Find purchase order by ID

**Description:** For valid response try integer IDs with value <= 5 or > 10. Other values will generate exceptions.

### HTTP Request 
`***GET*** /store/order/{orderId}` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| orderId | path | ID of order that needs to be fetched | Yes |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | successful operation |
| 400 | Invalid ID supplied |
| 404 | Order not found |

## ***DELETE*** 

**Summary:** Delete purchase order by ID

**Description:** For valid response try integer IDs with value < 1000. Anything above 1000 or nonintegers will generate API errors

### HTTP Request 
`***DELETE*** /store/order/{orderId}` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| orderId | path | ID of the order that needs to be deleted | Yes |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 400 | Invalid ID supplied |
| 404 | Order not found |

# /USER
## ***POST*** 

**Summary:** Create user

**Description:** This can only be done by the logged in user.

### HTTP Request 
`***POST*** /user` 

**Responses**

| Code | Description |
| ---- | ----------- |
| default | successful operation |

# /USER/CREATEWITHLIST
## ***POST*** 

**Summary:** Creates list of users with given input array

**Description:** Creates list of users with given input array

### HTTP Request 
`***POST*** /user/createWithList` 

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Successful operation |
| default | successful operation |

# /USER/LOGIN
## ***GET*** 

**Summary:** Logs user into the system

**Description:** 

### HTTP Request 
`***GET*** /user/login` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| username | query | The user name for login | No |  |
| password | query | The password for login in clear text | No |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | successful operation |
| 400 | Invalid username/password supplied |

# /USER/LOGOUT
## ***GET*** 

**Summary:** Logs out current logged in user session

**Description:** 

### HTTP Request 
`***GET*** /user/logout` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |

**Responses**

| Code | Description |
| ---- | ----------- |
| default | successful operation |

# /USER/{USERNAME}
## ***GET*** 

**Summary:** Get user by user name

**Description:** 

### HTTP Request 
`***GET*** /user/{username}` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| username | path | The name that needs to be fetched. Use user1 for testing.  | Yes |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | successful operation |
| 400 | Invalid username supplied |
| 404 | User not found |

## ***PUT*** 

**Summary:** Update user

**Description:** This can only be done by the logged in user.

### HTTP Request 
`***PUT*** /user/{username}` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| username | path | name that need to be deleted | Yes |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| default | successful operation |

## ***DELETE*** 

**Summary:** Delete user

**Description:** This can only be done by the logged in user.

### HTTP Request 
`***DELETE*** /user/{username}` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| username | path | The name that needs to be deleted | Yes |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 400 | Invalid username supplied |
| 404 | User not found |

<!-- Converted with the swagger-to-slate https://github.com/lavkumarv/swagger-to-slate -->
