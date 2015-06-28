<img src="http://www.grok-interactive.com/images/grok-logo.svg" alt="Grok Logo" style="margin-left: -165px; left: 50%; position: relative;">

# API Endpoints

## Getting a Collection of Questions for a Given Category

### Request

`GET http://trivia.grok.rocks/questions?category=Star_Wars?page=4`

### Response

```json
{
  "links": {
    "self": "http://trivia.grok.rocks/questions?category=Star_Wars?page=4",
    "first": "http://trivia.grok.rocks/questions?category=Star_Wars",
    "previous": "http://trivia.grok.rocks/questions?category=Star_Wars?page=3",
    "next": "http://trivia.grok.rocks/questions?category=Star_Wars?page=5",
    "last": "http://trivia.grok.rocks/questions?category=Star_Wars?page=10"
  },
  "data": [
    {
      "type": "question",
      "id": "67f03c54-1c0f-11e5-9a21-1697f925ec7b",
      "attributes": {
        "question": "Who said \"I suggest a new strategy, R2. Let the wookiee win.\"?",
        "correctAnswer": "C-3PO",
        "category": "Star Wars",
        "answers": [
          "C-3PO",
          "Obi-Wan Kenobi",
          "Han Solo",
          "Chewbacca"
        ]
      },
      "links": {
        "self": "http://trivia.grok.rocks/question/67f03c54-1c0f-11e5-9a21-1697f925ec7b"
      }
    },
    {
      "type": "question",
      "id": "5c4814e0-1dcb-11e5-9a21-1697f925ec7b",
      "attributes": {
        "question": "Who killed Jango Fett?",
        "category": "Star Wars",
        "correctAnswer": "C-3PO",
        "answers": [
          "Mace-Windu",
          "Obi-Wan Kenobi",
          "Anakin Skywalker",
          "Yoda"
        ]
      },
      "links": {
        "self": "http://trivia.grok.rocks/question/5c4814e0-1dcb-11e5-9a21-1697f925ec7b"
      }
    }
  ]
}
```

## Getting the List of Categories

### Request

`GET http://trivia.grok.rocks/categories`

### Response

```json
{
  "links": {
    "self": "http://trivia.grok.rocks/categories?page=4",
    "first": "http://trivia.grok.rocks/categories",
    "previous": "http://trivia.grok.rocks/categories?page=3",
    "next": "http://trivia.grok.rocks/categories?page=5",
    "last": "http://trivia.grok.rocks/categories?page=10"
  },
  "data": [
    {
      "type": "category",
      "id": "Star_Wars",
      "attributes": {
        "name": "Star Wars"
      },
      "links": {
        "self": "http://trivia.grok.rocks/category/Star_Wars",
        "questions": "http://trivia.grok.rocks/questions?cateogory=Star_Wars"
      }
    },
    {
      "type": "category",
      "id": "Legend_of_Zelda",
      "attributes": {
        "name": "Legend of Zelda"
      },
      "links": {
        "self": "http://trivia.grok.rocks/category/Legend_of_Zelda",
        "questions": "http://trivia.grok.rocks/questions?cateogory=Legend_of_Zelda"
      }
    }
  ]
}
```

## Answering a Question

### Request

`POST http://trivia.grok.rocks/question/67f03c54-1c0f-11e5-9a21-1697f925ec7b/answer`


```json
{
  "data": {
    "type": "answer",
    "attributes": {
      "value": "C-3PO"
    },
    "relationships": {
      "question": {
        "data": {
          "type": "question",
          "id": "67f03c54-1c0f-11e5-9a21-1697f925ec7b"
        }
      }
    }
  }
}
```

### Response (Answering Correctly)

`200 OK`

```json
{
  "data": {
    "type": "answer",
    "attributes": {
      "value": "C-3PO",
      "status": "correct"
    },
    "relationships": {
      "question": {
        "data": {
          "type": "question",
          "id": "67f03c54-1c0f-11e5-9a21-1697f925ec7b"
        }
      }
    }
  }
}
```


### Response (Answering Incorrectly)

`200 OK`

```json
{
  "data": {
    "type": "answer",
    "attributes": {
      "value": "Han Solo",
      "status": "incorrect"
    },
    "relationships": {
      "question": {
        "data": {
          "type": "question",
          "id": "67f03c54-1c0f-11e5-9a21-1697f925ec7b"
        }
      }
    }
  }
}
```
