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

## Create Main Content
#### POST /main-contents

Creates a new main content. Returns the created [main content](#main-content-object) on success.

#### JSON Body Parameters

| **FIELD**          | **TYPE** | **DESCRIPTION**                                                        |
|--------------------|----------|------------------------------------------------------------------------|
| title              | string   | content title                                                          |
| subtitle           | string   | content subtitle                                                       |        
| data               | string   | content data                                                           |
| reversed           | boolean  | whether the content is reversed                                        |
| centered           | boolean  | whether the content is centered                                        |
| imageFileName      | string   | file name for this content's image                                     |
| backgroundColorHex | string   | hex code for content's background color                                |

---

## Edit Main Content
#### PATCH /main-contents/{id}

Edits a main content. Returns the editted [main content](#main-content-object) object on success.

#### JSON Body Parameters

| **FIELD**          | **TYPE**   | **DESCRIPTION**                                                        |
|--------------------|------------|------------------------------------------------------------------------|
| title              | ?string    | content title                                                          |
| subtitle           | ?string    | content subtitle                                                       |        
| data               | ?string    | content data                                                           |
| reversed           | ?boolean   | whether the content is reversed                                        |
| centered           | ?boolean   | whether the content is centered                                        |
| imageFileName      | ?string    | file name for this content's image                                     |
| backgroundColorHex | ?string    | hex code for content's background color                                |

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
#### POST /carousel-contents

Creates a new carousel content. Returns a [carousel content](#carousel-content-object) on success.

#### JSON Body Parameters

| **FIELD**     | **TYPE** | **DESCRIPTION**                                                                |
|---------------|----------|--------------------------------------------------------------------------------|
| name          | string   | person's name                                                                  |
| description   | string   | person's description                                                           |
| imageFileName | string   | file name for person's image                                                   |

---

## Edit Carousel Content
#### PATCH /carousel-contents/{id}

Edits a carousel content. Returns the editted [carousel content](#carousel-content-object) on success.

####  JSON Body Parameters

| **FIELD**     | **TYPE**  | **DESCRIPTION**                                                                |
|---------------|-----------|--------------------------------------------------------------------------------|
| name          | ?string   | person's name                                                                  |
| description   | ?string   | person's description                                                           |
| imageFileName | ?string   | file name for person's image                                                   |

