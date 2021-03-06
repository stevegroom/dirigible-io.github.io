---
layout: api
title: Repository Manager
icon: fa-check
---

{{ page.title }}
===

Repository Manager object gives access to the repository. It can be used for creating artifacts such as services and web pages programmatically.


Version 3.x
---

- Module: **repository/v3/manager**
- Alias: **repository/manager**
- Definition: [https://github.com/eclipse/dirigible/issues/377](https://github.com/eclipse/dirigible/issues/377)
- Source: [/repository/v3/manager.js](https://github.com/dirigiblelabs/api-v3-repository/blob/master/repository/v3/manager.js)
- Facade: [RepositoryFacade](https://github.com/eclipse/dirigible/blob/master/api/api-facade/api-repository/src/main/java/org/eclipse/dirigible/api/v3/repository/RepositoryFacade.java)
- Status: **alpha**


### Basic Usage

The service which list the available workspaces:

```javascript

var response = require("http/v3/response");
var repositoryManager = require("repository/v3/manager");

var resource = repositoryManager.getResource('/registry/public/repository/v3/manager.js');

response.println("Exists: " + resource.exists());
response.flush();
response.close();

```

### Definition

#### Functions

---

Function     | Description | Returns
------------ | ----------- | --------
**getResource(path)**   | Get Resource by path | *Resource*
**createResource(path, content, contentType)**   | Creates Resource programmatically | *Resource*
**updateResource(path, content)**   | Updates Resource content | *Resource*
**deleteResource(path)**   | Delete Resource by path | *-*
**getCollection(path)**   | Get Collection by path | *Collection*
**createCollection(path)**   | Creates Collection programmatically | *Collection*
**deleteCollection(path)**   | Delete Collection by path | *-*


#### Objects

---

##### Resource

Function     | Description | Returns
------------ | ----------- | --------
**getName()** | Gets the Resource name | *string*
**getPath()**   | Gets the Resource path | *string*
**getParent()** | Gets the Resource parent Collection | *Collection*
**getInformation()** | Get the Resource information | *EntityInformation*
**create()** | Create new Resource | *-*
**delete()** | Delete the Resource | *-*
**renameTo(name)** | Rename the Resource | *-*
**moveTo(path)** | Moves the Resource to a new location | *-*
**copyTo(path)** | Copy the Resource to a new location | *-*
**exists()** | Returns _true_ if the Resource exists | *boolean*
**isEmpty()** | Returns _true_ if the Resource is empty | *boolean*
**getContent()** | Returns the content of the Resource | *byte array*
**setContent(content)** | Sets the Resource content | *-*
**isBinary()** | Returns _true_ if the Resource content is binary | *boolean*
**getContentType()** | Returns the content type of the Resource | *string*

##### Collection

Function     | Description | Returns
------------ | ----------- | --------
**getName()** | Gets the Collection name | *string*
**getPath()**   | Gets the Collection path | *string*
**getParent()** | Gets the Collection parent Collection | *Collection*
**getInformation()** | Get the Collection information | *EntityInformation*
**create()** | Create new Collection | *-*
**delete()** | Delete the Collection | *-*
**renameTo(name)** | Rename the Collection | *-*
**moveTo(path)** | Moves the Collection to a new location | *-*
**copyTo(path)** | Copy the Collection to a new location | *-*
**exists()** | Returns _true_ if the Collection exists | *boolean*
**isEmpty()** | Returns _true_ if the Collection is empty | *boolean*
**getCollectionsNames()** | Gets the names of the Collections in this Collection | *array of strings*
**createCollection(name)** | Create new Collection | *Collection*
**getCollection(name)** | Get Collection by name | *Collection*
**removeCollection(name)** | Remove Collection by name | *-*
**getResourcesNames()** | Gets the names of the Resources in this Collection | *array of strings*
**getResource(name)** | Get Resource by name | *Resource*
**removeResource(name)** | Remove Resource by name | *-*
**createResource(name, content)** | Create new Resource | *Resource*


##### EntityInformation

Function     | Description | Returns
------------ | ----------- | --------
**getName()** | Gets the entity name | *string*
**getPath()**   | Gets the entity path | *string*
**getPermissions()**   | Gets the entity permissions | *string*
**getSize()**   | Gets the entity size | *string*
**getCreatedBy()**   | Gets the entity createdBy | *string*
**getCreatedAt()**   | Gets the entity createdAt | *string*
**getModifiedBy()**   | Gets the entity modifiedBy | *string*
**getModifiedAt()**   | Gets the entity modifiedAt | *string*


### Compatibility

Rhino | Nashorn | V8
----- | ------- | --------
 ✅  | ✅  | ✅


---

Version 2.x
---

See the old version [here](repository.html).
