# Cara Membuat Pesan Interaktif

Katalis.app memungkinkan Anda membuat jenis pesan interaktif seperti kartu dan formulir di dalam Web Widget Katalis.app menggunakan API. Anda bisa membuat pesan ini menggunakan New Message API.

## Contoh Payload

Gunakan contoh payload berikut sebagai nilai untuk membuat berbagai pesan interaktif.

### 1. Options

```json
{
    "content": "Select one of the items below",
    "content_type": "input_select",
    "content_attributes": {
        "items": [
            { "title": "Option1", "value": "Option 1" },
            { "title": "Option2", "value": "Option 2" }
        ]
    },
    "private": false
}
```

### 2. Form

```json
{
  "content": "form",
  "content_type": "form",
  "content_attributes": {
    "items": [
      {
        "name": "email",
        "placeholder": "Please enter your email",
        "type": "email",
        "label": "Email",
        "default": "[email protected]"
      },
      {
        "name": "text_area",
        "placeholder": "Please enter text",
        "type": "text_area",
        "label": "Large Text",
        "default": "Sample text"
      },
      {
        "name": "text",
        "placeholder": "Please enter text",
        "type": "text",
        "label": "text",
        "default": "sample input"
      },
      {
        "name": "select",
        "label": "Select Option",
        "type": "select",
        "options": [
          {
            "label": "🌯 Burito",
            "value": "Burito"
          },
          {
            "label": "🍝 Pasta",
            "value": "Pasta"
          }
        ]
      }
    ]
  },
  "private": false
}
```

### 3. Cards

```json
{
   "content": "card message",
   "content_type": "cards",
   "content_attributes": {
      "items": [
         {
            "media_url": "https://example.com/image.jpg",
            "title": "Nike Shoes 2.0",
            "description": "Running with Nike Shoe 2.0",
            "actions": [
               {
                  "type": "link",
                  "text": "View More",
                  "uri": "google.com"
               },
               {
                  "type": "postback",
                  "text": "Add to cart",
                  "payload": "ITEM_SELECTED"
               }
            ]
         }
      ]
   },
   "private": false
}
```

### 4. Articles

```json
{
    "content": "articles",
    "content_type": "article",
    "content_attributes": {
        "items": [
            { "title": "API start guide", "description": "A random start api guide", "link": "http://google.com" },
            { "title": "Development docs", "description": "Development docs and guidelines", "link": "http://google.com" }
        ]
    },
    "private": false
}
```
