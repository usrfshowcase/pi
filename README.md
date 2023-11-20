# Main Content

## Main Content Object

| **FIELD**          | **TYPE** | **DESCRIPTION**                                                        |
|--------------------|----------|------------------------------------------------------------------------|
| id                 | string   | unique identifier for this [main content](#main-content-object) object |
| title              | string   | content title                                                          |
| subtitle           | string   | content subtitle                                                       |        
| data               | string   | content data                                                           |
| reversed           | boolean  | whether the content is reversed                                        |
| centered           | boolean  | whether the content is centered                                        |
| imageFileName      | string   | file name for this content's image                                     |
| backgroundColorHex | string   | hex code for content's background color                                |

---

# Carousel Content

## Carousel Content Object

| **FIELD**     | **TYPE** | **DESCRIPTION**                                                                |
|---------------|----------|--------------------------------------------------------------------------------|
| id            | string   | unique identifier for this [carousel content](#carousel-content-object) object |
| name          | string   | person's name                                                                  |
| description   | string   | person's description                                                           |
| imageFileName | string   | file name for person's image                                                   |

---

## Create Carousel Content
#### POST /caroulsel-contents/

Creates a new carousel content. Returns a [carousel content](#carousel-content-object) on success.

#### JSON Params

| **FIELD**     | **TYPE** | **DESCRIPTION**                                                                |
|---------------|----------|--------------------------------------------------------------------------------|
| name          | string   | person's name                                                                  |
| description   | string   | person's description                                                           |
| imageFileName | string   | file name for person's image                                                   |
