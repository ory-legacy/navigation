RESTful Navigation Service
==========

## API

### Models

```
container = {
  id:   int64,
  name: string,
  items: [{item},{item},...]
}

item = {
  id: int64,
  parameters: [{parameter},{parameter},{parameter},...],
  children: [{item},{item},{item},...]
}

parameter = {
  id: int64,
  key: string,
  value: string,
  children: [{parameter},{parameter},{parameter},...]
}
```

### Create a new container

`POST /navigation/container`

Parameters

| Parameter name | Type | Description |
|---|---|---|
| name | `string` | A unique name of that identifier | 

Result:
```
{
  error: nil|string,
  container: {container}
}
```

### Get all containers

`GET /navigation/container`

Result: 
```
[{container}, {container}, ...]
```

### Get a container

`GET /navigation/container/:name`

Parameters

| Parameter name | Type | Description |
|---|---|---|
| name | `string` | The containers name | 

Result: 
```
{container}
```

### Create an item

`PUT /navigation/container/:name/item`

Parameters

| Parameter name | Type | Description |
|---|---|---|
| name | `string` | The containers name | 
| parent | `int64\|null` | The items parent item | 

Result: 
```
{item}
{
  error: nil|string,
  item: {item}
}
```
