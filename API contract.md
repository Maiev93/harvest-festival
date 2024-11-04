# API contract

#### Products entity
##### Request
- Endpoint: `baseUrl/products`
- query params: 
```
{
  page: number // non negative integer
  count: number // non negative integer
}
```
##### Response
```
[
  pageCount: integer // non negative integer
  {
    id: uuid
    image: string // image url
    name: string // max 50 symbols
    price: float // non negative float
    currency: integer
  }
]
```

#### Main banner entity
##### Request
- Endpoint: `baseUrl/main-banner`
##### Response
```
{
  id: uuid
  date: string // YYYY-MM-DDTHH:MM:SSZ
  title: string // max 50 symbols
  image: string // image url
  url: string
}
```

#### Side banner entity
##### Request
- Endpoint: `baseUrl/side-banner`
```
{
  id: uuid
  title: string // max 50 symbols
  description: string
  image: string // image url
  linkText: string // max 50 symbols
  url: string
}
```
