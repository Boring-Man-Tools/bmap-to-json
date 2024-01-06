---
title: "Map Configuration"
---

{{< toc >}}

## Full map configuration example

Example of a map configuration with all fields:

```
"Config": {
    // Map
    "Name": "The best map ever",
    "Author": "Shaigro",
    "MapWidth": "6528",
    "MapHeight": "2050",
    "Ambience": "9",

    // Worskhop
    "Preview": "thumbnail_of_the_year.png",
    "Workshop": "1818514910",

    // Sea
    "SeaLevel": "1920",
    "SeaType": "0",
    "SeaDepth": "2",

    // Background 1
    "Bkgd1File": "background2.png",
    "Bkgd1MD5": "92043a581db0c50efb7856aa840f885c",
    "Bkgd1Hspeed": "0",
    "Bkgd1Vspeed": "0",
    "Bkgd1HPara": "1",
    "Bkgd1VPara": "0",
    "Bkgd1XTile": "1",
    "Bkgd1YTile": "1",
    "Bkgd1XOff": "0",
    "Bkgd1YOff": "0",

    // Background 2
    "Bkgd2File": "",
    "Bkgd2MD5": "",
    "Bkgd2Hspeed": "0",
    "Bkgd2Vspeed": "0",
    "Bkgd2HPara": "0",
    "Bkgd2VPara": "0",
    "Bkgd2XTile": "1",
    "Bkgd2YTile": "1",
    "Bkgd2XOff": "0",
    "Bkgd2YOff": "0",

    // Foreground
    "Bkgd3File": "",
    "Bkgd3MD5": "",
    "Bkgd3Hspeed": "0",
    "Bkgd3Vspeed": "0",
    "Bkgd3HPara": "0",
    "Bkgd3VPara": "0",
    "Bkgd3XTile": "1",
    "Bkgd3YTile": "1",
    "Bkgd3XOff": "0",
    "Bkgd3YOff": "0",

    // Color background
    "BkgdColor1": "4982848",
    "BkgdColor2": "3666080",
    "Bkgd1AmbCol": "4210752",
    "Bkgd1Amb": "8",

    // Misc
    "Climb": "0",
    "DivChc": "25",
    "DecalDepth": "-200",
    "ShowPath": "0",
    "ShowCol": "0",
    "ShowLog": "0",

    // Other
    "TotalGates": "934",
}
```

## Properties

### Map properties

#### Name

**Description:** Name of the map.

**Value:** Any string. Default is "Boring Map". Unknown if there is a limit of characters.

#### Author

**Description:** Author of the map.

**Value:** Any string. Default is the current player name. Unknown if there is a limit of characters.

#### MapWidth

**Description:** Width of the map.

**Value:** `0 < map_width < ... `

#### MapHeight

**Description:** Height of the map.

**Value:** `0 < map_height < ... `

#### Ambience

**Description:** Ambience of the map.

**Value:** Possible values are:

- `0`: Silence
- `1`: Fields
- `2`: Evening
- `3`: City
- `4`: Desert
- `5`: Factory
- `6`: Ocean
- `7`: Cold
- `8`: Caves
- `9`: Rain
- `10`: Waterfall
- `11`: Strange
- `12`: Railroad
- `13`: Blizzard

### Workshop properties

#### Preview

**Description:** Filename of the preview of the map. The preview displays on Steam workshop when looking for the map. The image has to be a `.png` if it is defined.

**Value:**

- `*.png`: Preview is defined
- ` `: Preview is not defined

#### Workshop

**Description:** Workshop ID of the map.

**Value:** Possible values:

- `-1`: Not on the workshop.
- `0 < workshop_id `: On the workshop.

### Sea properties

#### SeaLevel

**Description:** Determines where the sea is rendered on the Y axis.

**Value:**

- `0 < sea_level < map_height`: The sea level is enabled.
- `sea_level <= 0 || map_height < sea_level`: The sea level is disabled.

#### SeaType

**Description:** Type of the sea.

**Value:**

- `0`: Water
- `1`: Lava

#### SeaDepth

**Description:** Depth of the layer the sea is on.

**Value:**

- `sea_depth <= 0`: Behind the player.
- `0 < sea_depth`: In front of the player.

### Background 1 properties

The background 1 is an image that can be put on a layer behind any assets, tiles or players.

The background 1 is always behind the background 2.

#### Bkgd1File

**Description:** Filename of the background 1 image. The image has to be a `.png` if it is defined.

- `*.png`: The background 1 is based on the provided image.
- ` `: There is no background 1.

#### Bkgd1MD5

**Description:** [MD5 checksum](/bmap-to-json/bmap-txt/glossary/#md5-checksum) of the image. It is used to verify that the image downloaded from the workshop is correct.

**Value:** `md5.length == 32`: It's always a 128-bit value.

#### Bkgd1Hspeed

**Description:** Determines how fast the image is moving on the X axis.

**Value:**

- `speed < 0`: The image moves from right to left.
- `speed == 0`: The image doesn't move.
- `0 < speed`: The image moves from left to right.

#### Bkgd1Vspeed

**Description:** Determines how fast the image is moving on the Y axis.

**Value:**

- `speed < 0`: The image moves from bottom to top.
- `speed == 0`: The image doesn't move.
- `0 < speed`: The image moves from top to bottom.

#### Bkgd1HPara

**Description:** Define how the [parallax](/bmap-to-json/bmap-txt/glossary/#parallax) work for the image on the X axis.

**Value:**

- `0`: Static
- `1`: Full-Parallax
- `2`: Half-Parallax
- `3`: Absolute

#### Bkgd1VPara

**Description:** Define how the [parallax](/bmap-to-json/bmap-txt/glossary/#parallax) work for the image on the Y axis.

**Value:**

- `0`: Static
- `1`: Full-Parallax
- `2`: Half-Parallax
- `3`: Absolute

#### Bkgd1XTile

**Description:** Determines whether the background 1 image should repeat itself on the X axis.

**Value:**

- `0`: Image does not repeat.
- `1`: Image does repeat.

#### Bkgd1YTile

**Description:** Determines whether the background 1 image should repeat itself on the Y axis.

**Value:**

- `0`: Image does not repeat.
- `1`: Image does repeat.

#### Bkgd1XOff

**Description:** Define what is the offset of the background 1 image on the X axis.

**Value:** Any integer. Unknown limit.

- `offset < 0`: Left of the image goes outside the map.
- `0 <= offset < map_width - width_of_image`: Image is fully visible in the map.
- `map_width - width_of_image <= offset`: Right of the image goes outside the map.

#### Bkgd1YOff

**Description:** Define what is the offset of the background 1 image on the Y axis.

**Value:** Any integer. Unknown limit.

- `offset < 0`: Top of the image goes outside the map.
- `0 <= offset < map_height - height_of_image`: Image is fully visible in the map.
- `map_height - height_of_image <= offset`: Bottom of the image goes outside the map.

### Background 2 properties

The background 2 is an image that can be put on a layer behind any assets, tiles or players.

The background 2 is always above the background 1.

#### Bkgd2File

**Description:** Filename of the background 2 image. The image has to be a `.png` if it is defined.

- `*.png`: The background 2 is based on the provided image.
- ` `: There is no background 2.

#### Bkgd2MD5

**Description:** [MD5 checksum](/bmap-to-json/bmap-txt/glossary/#md5-checksum) of the image. It is used to verify that the image downloaded from the workshop is correct.

**Value:** `md5.length == 32`: It's always a 128-bit value.

#### Bkgd2Hspeed

**Description:** Determines how fast the image is moving on the X axis.

**Value:**

- `speed < 0`: The image moves from right to left.
- `speed == 0`: The image doesn't move.
- `0 < speed`: The image moves from left to right.

#### Bkgd2Vspeed

**Description:** Determines how fast the image is moving on the Y axis.

**Value:**

- `speed < 0`: The image moves from bottom to top.
- `speed == 0`: The image doesn't move.
- `0 < speed`: The image moves from top to bottom.

#### Bkgd2HPara

**Description:** Define how the [parallax](/bmap-to-json/bmap-txt/glossary/#parallax) work for the image on the X axis.

**Value:**

- `0`: Static
- `1`: Full-Parallax
- `2`: Half-Parallax
- `3`: Absolute

#### Bkgd2VPara

**Description:** Define how the [parallax](/bmap-to-json/bmap-txt/glossary/#parallax) work for the image on the Y axis.

**Value:**

- `0`: Static
- `1`: Full-Parallax
- `2`: Half-Parallax
- `3`: Absolute

#### Bkgd2XTile

**Description:** Determines whether the background 2 image should repeat itself on the X axis.

**Value:**

- `0`: Image does not repeat.
- `1`: Image does repeat.

#### Bkgd2YTile

**Description:** Determines whether the background 2 image should repeat itself on the Y axis.

**Value:**

- `0`: Image does not repeat.
- `1`: Image does repeat.

#### Bkgd2XOff

**Description:** Define what is the offset of the background 2 image on the X axis.

**Value:** Any integer. Unknown limit.

- `offset < 0`: Left of the image goes outside the map.
- `0 <= offset < map_width - width_of_image`: Image is fully visible in the map.
- `map_width - width_of_image <= offset`: Right of the image goes outside the map.

#### Bkgd2YOff

**Description:** Define what is the offset of the background 2 image on the Y axis.

**Value:** Any integer. Unknown limit.

- `offset < 0`: Top of the image goes outside the map.
- `0 <= offset < map_height - height_of_image`: Image is fully visible in the map.
- `map_height - height_of_image <= offset`: Bottom of the image goes outside the map.

### Foreground properties

The foreground is an image that can be put on a layer above any assets, tiles or players.

#### Bkgd3File

**Description:** Filename of the foreground image. The image has to be a `.png` if it is defined.

**Value:**

- `*.png`: The foreground is based on the provided image.
- ` `: There is no foreground.

#### Bkgd3MD5

**Description:** [MD5 checksum](/bmap-to-json/bmap-txt/glossary/#md5-checksum) of the image. It is used to verify that the image downloaded from the workshop is correct.

**Value:** `md5.length == 32`: It's always a 128-bit value.

#### Bkgd3Hspeed

**Description:** Determines how fast the image is moving on the X axis.

**Value:**

- `speed < 0`: The image moves from right to left.
- `speed == 0`: The image doesn't move.
- `0 < speed`: The image moves from left to right.

#### Bkgd3Vspeed

**Description:** Determines how fast the image is moving on the Y axis.

**Value:**

- `speed < 0`: The image moves from bottom to top.
- `speed == 0`: The image doesn't move.
- `0 < speed`: The image moves from top to bottom.

#### Bkgd3HPara

**Description:** Define how the [parallax](/bmap-to-json/bmap-txt/glossary/#parallax) work for the image on the X axis.

**Value:**

- `0`: Static
- `1`: Full-Parallax
- `2`: Half-Parallax
- `3`: Absolute

#### Bkgd3VPara

**Description:** Define how the [parallax](/bmap-to-json/bmap-txt/glossary/#parallax) work for the image on the Y axis.

**Value:**

- `0`: Static
- `1`: Full-Parallax
- `2`: Half-Parallax
- `3`: Absolute

#### Bkgd3XTile

**Description:** Determines whether the foreground image should repeat itself on the X axis.

**Value:**

- `0`: Image does not repeat.
- `1`: Image does repeat.

#### Bkgd3YTile

**Description:** Determines whether the foreground image should repeat itself on the Y axis.

**Value:**

- `0`: Image does not repeat.
- `1`: Image does repeat.

#### Bkgd3XOff

**Description:** Define what is the offset of the foreground image on the X axis.

**Value:** Any integer. Unknown limit.

- `offset < 0`: Left of the image goes outside the map.
- `0 <= offset < map_width - width_of_image`: Image is fully visible in the map.
- `map_width - width_of_image <= offset`: Right of the image goes outside the map.

#### Bkgd3YOff

**Description:** Define what is the offset of the foreground image on the Y axis.

**Value:** Any integer. Unknown limit.

- `offset < 0`: Top of the image goes outside the map.
- `0 <= offset < map_height - height_of_image`: Image is fully visible in the map.
- `map_height - height_of_image <= offset`: Bottom of the image goes outside the map.

### Color Background properties

#### Gradient

##### BkgdColor1

**Description:** Defines the color at the top of the map to be used for the background gradient. The color is defined as a [GML color](/bmap-to-json/bmap-txt/glossary/#gml-colors).

**Value:** `0 <= color <= 16777215`

##### BkgdColor2

**Description:** Defines the color at the bottom of the map to be used for the background gradient. The color is defined as a [GML color](/bmap-to-json/bmap-txt/glossary/#gml-colors).

**Value:** `0 <= color <= 16777215`

#### Overlay

##### Bkgd1AmbCol

**Description:** Defines the color of the overlay that is on top of the gradient and the background 1 & 2. The color is defined as a [GML color](/bmap-to-json/bmap-txt/glossary/#gml-colors).

**Value:** `0 <= color <= 16777215`

##### Bkgd1Amb

**Description:** Determines the overlay opacity. The percentage is computed with the formula: `percentage = overlay * 10`.

**Value:** `0 <= overlay <= 10`

### Misc properties

#### Climb

**Description:** Determines if the map is a climb map.

**Value:**

- `1`: Is a climb map.
- `0`: Is not a climb map.

#### DivChc

**Description:** Defines the chance to divert AI for all "Waypoint Divert" asset. Usually, it is a multiple of 5.

**Value:** `0 <= chance <= 100`

#### DecalDepth

**Description:** Depth of the layer the [decals](/bmap-to-json/bmap-txt/glossary/#decals) are on.

**Value:** Any integer. Default is `-200`. Unknown limit.

#### ShowPath

**Description:** Determines if AI path is shown to the host of the map.

**Value:**

- `0`: Don't show AI path
- `1`: Show AI path

#### ShowCol

**Description:** Determines if collisions are shown to the host of the map.

**Value:**

- `0`: Don't show collisions
- `1`: Show collisions

#### ShowLog

**Description:** Determines if logic is shown to the host of the map.

**Value:**

- `0`: Don't show logic
- `1`: Show logic

#### TotalGates

**Description:** Represents the total number of gates that was ever created. Every time an asset or a tile is placed in the map, the count increase by 1.

**Value:** `0 <= total_gates`
