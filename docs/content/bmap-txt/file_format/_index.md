## Description of each line

Every map created via the map editor of Boring Man - OTSC is composed of 5 lines:

1. The title of the map
2. Whether the map is a climb map.
   - 1 means it is a climb map
   - 0 means it is not a climb map
3. The Steam workshop ID of the map.
   - If the ID is -1, it means it is not on the workshop.
4. A JSON containing all the objects of the map and the configuration of the map.
   - This JSON will always contain a `Config` key, even if the map is empty.
5. A JSON containing the MD5 file checksums for each image used in the map.
   - This JSON can be empty (`{}`) if no tiles is put on the map.

## Map objects and map configuration

The JSON of the 4th line are the map objects and the map configuration.

```
{"OBJ0": {...}, "Config": { ... }, "OBJ12": { ... }}
```

### Map configuration

The map configuration is always found via the key `Config` in the JSON.

[**Full documentation about map configuration entry here.**](./map_config)

### Map objects

All map objects have keys called `OBJ[number]`.

[**Full documentation about map objects entries here.**](./map_objects)
