# Tabelas

## Section

#### Button Object

| **CAMPO** | **TIPO** | **DESCRIÇÃO**             |
|-----------|----------|---------------------------|
| text      | string   | texto contido no botão    |
| href      | string   | link relacionado ao botão |

#### Section Object

Representa uma seção ou bloco de conteúdo na página.

| **CAMPO**     | **TIPO**                                  | **DESCRIÇÃO**                                                                                                                                      |
|---------------|-------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------|
| id            | string                                    | identificador único de uma seção                                                                                                                   |
| position      | integer                                   | a posição da seção em relação com as outras seções                                                                                                 |
| title         | string                                    | representa o titulo de um texto. Trechos envoltos por aspas francesas "<>" devem ser renderizandos como texto em gradiente, como está no wireframe |
| text          | string                                    | o texto da seção                                                                                                                                   |
| button        | [button](#button-object) object *ou* null | botao contido na seção                                                                                                                             |
| imageFileName | string *ou* null                          | o nome do arquivo da imagem dessa seção                                                                                                            |
| reversed      | boolean                                   | se a seção deve ser mostrada de forma invertida                                                                                                    |
| centered      | boolean                                   | se a seção deve ser mostrada de forma centralizada                                                                                                 |

---

# Endpoints

## Criar Seção
#### POST /sections

Cria uma nova seção. Retorna um [section](#section-object) object em caso de sucesso.

#### Parâmetros de Body JSON

| **CAMPO**     | **TIPO**                                  | **DESCRIÇÃO**                                                                                                                                      |
|---------------|-------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------|
| position      | integer                                   | a posição da seção em relação com as outras seções                                                                                                 |
| title         | string                                    | representa o titulo de um texto. Trechos envoltos por aspas francesas "<>" devem ser renderizandos como texto em gradiente, como está no wireframe |
| text          | string                                    | o texto da seção                                                                                                                                   |
| button        | [button](#button-object) object *ou* null | botao contido na seção                                                                                                                             |
| imageFileName | string *ou* null                          | o nome do arquivo da imagem dessa seção                                                                                                            |
| reversed      | boolean                                   | se a seção deve ser mostrada de forma invertida                                                                                                    |
| centered      | boolean                                   | se a seção deve ser mostrada de forma centralizada                                                                                                 |

---

## Editar Seção
#### PATCH /sections/{id}

Edita uma seção existente. Retorna o [section](#section-object) object editado em caso de sucesso.

#### Parâmetros de Body JSON

| **CAMPO**     | **TIPO**                                   | **DESCRIÇÃO**                                                                                                                                      |
|---------------|--------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------|
| position      | ?integer                                   | a posição da seção em relação com as outras seções                                                                                                 |
| title         | ?string                                    | representa o titulo de um texto. Trechos envoltos por aspas francesas "<>" devem ser renderizandos como texto em gradiente, como está no wireframe |
| text          | ?string                                    | o texto da seção                                                                                                                                   |
| button        | ?[button](#button-object) object *ou* null | botao contido na seção                                                                                                                             |
| imageFileName | ?string *ou* null                          | o nome do arquivo da imagem dessa seção                                                                                                            |
| reversed      | ?boolean                                   | se a seção deve ser mostrada de forma invertida                                                                                                    |
| centered      | ?boolean                                   | se a seção deve ser mostrada de forma centralizada                                                                                                 |

