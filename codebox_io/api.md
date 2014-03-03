---
layout: default
title: REST API
section: codebox_io/api
---

## Codebox REST API

Codebox is based on a very simple REST API which allow clients to create boxes from any applications.
You can also use a wrapper for the API in Python, Javascript or Ruby.

All the API methods use the header *Authorization* for authenticate the user.

#### Create a new box

```
$ curl -X POST https://api.codebox.io/api/boxes \
   -H "Authorization: <your api token>" \
   -d "name=Test" \
   -d "type=type1" \
   -d "stack=node"
```

Optional paramters are:

* *description*: (string) default is empty
* *git*: (string) default is empty
* *public*: (boolean) default is false

#### List Boxes

```
$ curl -X GET https://api.codebox.io/api/boxes \
   -H "Authorization: <your api token>"
```

#### Manage collaborators (for private boxes)

Get the list of collaborators emails:

```
$ curl -X GET https://api.codebox.io/api/box/<box>/collaborators \
   -H "Authorization: <your api token>"
```

Add a collaborator by email:

```
$ curl -X POST https://api.codebox.io/api/box/<box>/collaborators \
   -H "Authorization: <your api token>" \
   -d "email=youremail@mymail.com"
```

Remove a collaborator by email:

```
$ curl -X DELETE https://api.codebox.io/api/box/<box>/collaborators \
   -H "Authorization: <your api token>" \
   -d "email=youremail@mymail.com"
```

#### Manage a box

Get the information about a box:

```
$ curl -X GET https://api.codebox.io/api/box/<box> \
   -H "Authorization: <your api token>"
```

Remove a box:

```
$ curl -X DELETE https://api.codebox.io/api/box/<box> \
   -H "Authorization: <your api token>"
```

#### Content

Download content as a tar.gz file with a stream on:

```
$ curl -O https://api.codebox.io/api/box/<box>/content \
   -H "Authorization: <your api token>"
```

#### Events

List events for a boxes:

```
$ curl -X GET https://api.codebox.io/api/box/<box>/events \
   -H "Authorization: <your api token>"
```

#### Activity data

Get box activity:

```
$ curl -X GET https://api.codebox.io/api/box/<box>/activity \
   -H "Authorization: <your api token>"
```


## Using the node.js library

Create a client:

```javascript
var Codebox = require("codebox-io").Client;

var client = new Codebox({
	'token': "<api token>"
});
```

Create a box:

```javascript
client.create({
	'type': 'type1',
	'name': 'My Node Box',
   'stack': 'python'
}).then(function(box) {
	console.log(box.id," : ", box.name)
});
```

List boxes:

```javascript
client.boxes().then(function(boxes) {
	boxes.forEach(function(box) {
		console.log(box.id," : ", box.name)
	})
});
```

Get a box by its id:

```javascript
client.box("7546736a-621d-434f-9c10-ad7cd0773a06").then(function(box) {
	console.log(box.id," : ", box.name)
});
```

Download box content:

```javascript
box.content("./test.gz").then(function() {
    console.log("End!");
}, function(err) {
    console.log("Error:", err);
});
```

## Others librairies

* [Erlang](https://github.com/mawuli-ypa/codebox-erlang)
