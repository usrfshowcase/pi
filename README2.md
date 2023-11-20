# Tabelas

## Section

#### Button Object

| **CAMPO** | **TIPO** | **DESCRIÇÃO**             |
|-----------|----------|---------------------------|
| text      | string   | texto contido no botão    |
| href      | string   | link relacionado ao botão |

#### Section Object

Representa uma seção ou bloco de conteúdo na página.

| **CAMPO**          | **TIPO**                                  | **DESCRIÇÃO**                                                                                                                                      |
|--------------------|-------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------|
| id                 | string                                    | identificador único de uma seção                                                                                                                   |
| position           | integer                                   | a posição da seção em relação com as outras seções                                                                                                 |
| title              | string                                    | representa o titulo de um texto. Trechos envoltos por aspas francesas "<>" devem ser renderizandos como texto em gradiente, como está no wireframe |
| text               | string                                    | o texto da seção                                                                                                                                   |
| button             | [button](#button-object) object *ou* null | botao contido na seção                                                                                                                             |
| imageFileName      | string *ou* null                          | o nome do arquivo da imagem dessa seção                                                                                                            |
| reversed           | boolean                                   | se a seção deve ser mostrada de forma invertida                                                                                                    |
| centered           | boolean                                   | se a seção deve ser mostrada de forma centralizada                                                                                                 |
| backgroundColorHex | string                                    | a cor de fundo da seção em código hex                                                                                                              |

#### Exemplo de Seção

```json
{
  "id": "a6636c75-8455-4c9f-9784-a6f5ed2225be",
  "position": 0,
  "title": "O <equilíbrio> perfeito entre vida e trabalho",
  "text": "Descubra a fórmula para alcançar o equilíbrio perfeito entre vida e trabalho e viva uma experiência extraordinária em todas as áreas da sua vida.",
  "button": null,
  "imageFileName": "multitasking.svg",
  "reversed": false,
  "centered": false,
  "backgroundColorHex": "#ffff"
}
```

#### Carousel Section

| **CAMPO**     | **TIPO**                                  | **DESCRIÇÃO**                                                                                                                                      |
|---------------|-------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------|
| id            | string                                    | identificador único de uma seção                                                                                                                   |
| position      | integer                                   | a posição da seção em relação com as outras seções                                                                                                 |
| title         | string                                    | representa o titulo de um texto.                                                                                                                   |
| text          | string                                    | o texto da seção                                                                                                                                   |
| imageFileName | string *ou* null                          | o nome do arquivo da imagem dessa seção                                                                                                            |
| reversed      | boolean                                   | se a seção deve ser mostrada de forma invertida                                                                                                    |
| centered      | boolean                                   | se a seção deve ser mostrada de forma centralizada                                                                                                 |

---

# Endpoints

## Criar Seção
#### POST /sections

Cria uma nova seção. Retorna um [section](#section-object) object em caso de sucesso.

#### Parâmetros de Body JSON

| **CAMPO**          | **TIPO**                                  | **DESCRIÇÃO**                                                                                                                                      |
|--------------------|-------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------|
| position           | integer                                   | a posição da seção em relação com as outras seções                                                                                                 |
| title              | string                                    | representa o titulo de um texto. Trechos envoltos por aspas francesas "<>" devem ser renderizandos como texto em gradiente, como está no wireframe |
| text               | string                                    | o texto da seção                                                                                                                                   |
| button             | [button](#button-object) object *ou* null | botao contido na seção                                                                                                                             |
| imageFileName      | string *ou* null                          | o nome do arquivo da imagem dessa seção                                                                                                            |
| reversed           | boolean                                   | se a seção deve ser mostrada de forma invertida                                                                                                    |
| centered           | boolean                                   | se a seção deve ser mostrada de forma centralizada                                                                                                 |
| backgroundColorHex | string                                    | a cor de fundo da seção em código hex                                                                                                              |


#### Respostas

|  **CÓDIGO**     | **TIPO**                          | **DESCRIÇÃO**                                       |
|-----------------|-----------------------------------|-----------------------------------------------------|
| 201 Created     | [section](#section-object) object | a seção que foi criada                              |
| 400 Bad Request | ValidationError                   | algum campo da requisição tem um tipo inesperado    |
| 403 Forbidden   | NotAllowedError                   | o cliente não tem permissão para acessar essa rota  |
| 409 Conflict    | PositionAlreadyOccupiedError      | a posição informada já está ocupada por outra seção |

---

## Buscar Seções
#### GET /sections

Busca as seções em ordem de posição. Retorna um array de [section](#section-object) objects em caso de sucesso.

#### Respostas

|  **CÓDIGO** | **TIPO**                                    | **DESCRIÇÃO**                   |
|-------------|---------------------------------------------|---------------------------------|
| 200 Ok      | array de [section](#section-object) objects | as seções ordenadas por posição |

---

## Editar Seção
#### PATCH /sections/{id}

Edita uma seção existente. Retorna o [section](#section-object) object editado em caso de sucesso.

#### Parâmetros de Body JSON

| **CAMPO**          | **TIPO**                                   | **DESCRIÇÃO**                                                                                                                                      |
|--------------------|--------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------|
| position           | ?integer                                   | a posição da seção em relação com as outras seções                                                                                                 |
| title              | ?string                                    | representa o titulo de um texto. Trechos envoltos por aspas francesas "<>" devem ser renderizandos como texto em gradiente, como está no wireframe |
| text               | ?string                                    | o texto da seção                                                                                                                                   |
| button             | ?[button](#button-object) object *ou* null | botao contido na seção                                                                                                                             |
| imageFileName      | ?string *ou* null                          | o nome do arquivo da imagem dessa seção                                                                                                            |
| reversed           | ?boolean                                   | se a seção deve ser mostrada de forma invertida                                                                                                    |
| centered           | ?boolean                                   | se a seção deve ser mostrada de forma centralizada                                                                                                 |
| backgroundColorHex | ?string                                    | a cor de fundo da seção em código hex                                                                                                              |

#### Respostas

|  **CÓDIGO**     | **TIPO**                          | **DESCRIÇÃO**                                       |
|-----------------|-----------------------------------|-----------------------------------------------------|
| 200 Ok          | [section](#section-object) object | a seção que foi editada                             |
| 400 Bad Request | ValidationError                   | algum campo da requisição tem um tipo inesperado    |
| 403 Forbidden   | NotAllowedError                   | o cliente não tem permissão para acessar essa rota  |
| 404 Not Found   | SectionNotFoundError              | não existe uma seção com o id informado             |
| 409 Conflict    | PositionAlreadyOccupiedError      | a posição informada já está ocupada por outra seção |

---

## Criar Seção de Carousel
#### POST /carousel-sections

Cria uma nova seção de carousel. Retorna um [carousel section](#carousel-section-object) object em caso de sucesso.

#### Parâmetros de Body JSON

| **CAMPO**     | **TIPO**                                  | **DESCRIÇÃO**                                                  |
|---------------|-------------------------------------------|----------------------------------------------------------------|
| position      | integer                                   | a posição da seção de carousel em relação com as outras seções |
| title         | string                                    | representa o titulo de um texto.                               |
| text          | string                                    | o texto da seção de carousel                                   |
| imageFileName | string *ou* null                          | o nome do arquivo da imagem dessa seção de carousel            |
| reversed      | boolean                                   | se a seção de carousel deve ser mostrada de forma invertida    |
| centered      | boolean                                   | se a seção de carousel deve ser mostrada de forma centralizada |

#### Respostas

|  **CÓDIGO**     | **TIPO**                                            | **DESCRIÇÃO**                                                   |
|-----------------|-----------------------------------------------------|-----------------------------------------------------------------|
| 201 Created     | [carousel section](#carousel-section-object) object | a seção de carousel que foi criada                              |
| 400 Bad Request | ValidationError                                     | algum campo da requisição tem um tipo inesperado                |
| 403 Forbidden   | NotAllowedError                                     | o cliente não tem permissão para acessar essa rota              |
| 409 Conflict    | PositionAlreadyOccupiedError                        | a posição informada já está ocupada por outra seção de carousel |

---

## Buscar Seções de Carousel
#### GET /carousel-sections

Busca as seções de carousel em ordem de posição. Retorna um array de [carousel section](#carousel-section-object) objects em caso de sucesso.

#### Respostas

|  **CÓDIGO** | **TIPO**                                                      | **DESCRIÇÃO**                               |
|-------------|---------------------------------------------------------------|---------------------------------------------|
| 200 Ok      | array de [carousel section](#carousel-section-object) objects | as seções de carousel ordenadas por posição |

---

## Editar Seção de Carousel
#### PATCH /carousel-sections/{id}

Editar uma seção de carousel existente. Retorna o [carousel section](#carousel-section-object) object editado em caso de sucesso.

#### Parâmetros de Body JSON

| **CAMPO**     | **TIPO**                                   | **DESCRIÇÃO**                                                  |
|---------------|--------------------------------------------|----------------------------------------------------------------|
| position      | ?integer                                   | a posição da seção de carousel em relação com as outras seções |
| title         | ?string                                    | representa o titulo de um texto.                               |
| text          | ?string                                    | o texto da seção de carousel                                   |
| imageFileName | ?string *ou* null                          | o nome do arquivo da imagem dessa seção                        |
| reversed      | ?boolean                                   | se a seção de carousel deve ser mostrada de forma invertida    |
| centered      | ?boolean                                   | se a seção de carousel deve ser mostrada de forma centralizada |

#### Respostas

|  **CÓDIGO**     | **TIPO**                                            | **DESCRIÇÃO**                                                   |
|-----------------|-----------------------------------------------------|-----------------------------------------------------------------|
| 200 Ok          | [carousel section](#carousel-section-object) object | a seção de carousel que foi editada                             |
| 400 Bad Request | ValidationError                                     | algum campo da requisição tem um tipo inesperado                |
| 403 Forbidden   | NotAllowedError                                     | o cliente não tem permissão para acessar essa rota              |
| 404 Not Found   | CarouselSectionNotFoundError                        | não existe uma seção de carousel com o id informado             |
| 409 Conflict    | PositionAlreadyOccupiedError                        | a posição informada já está ocupada por outra seção de carousel |
