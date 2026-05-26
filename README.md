# Bajaj Finserv Health - Qualifier 1 (Java)

Spring Boot REST API for the Bajaj Finserv Health hiring challenge.

**Student:** Shivan Singh Yadav  
**Reg No:** 0827AL231121  
**Email:** shivansingh231254@acropolis.in

---

## Tech Stack

- Java 17
- Spring Boot 3.2.5
- Maven

---

## API Endpoint

### POST /bfhl

Accepts an array of mixed strings and categorises them.

**Request:**
```json
{
  "data": ["1", "2", "A", "b", "3", "!"]
}
```

**Response:**
```json
{
  "is_success": true,
  "user_id": "shivan_singh_yadav_0827al231121",
  "email": "shivansingh231254@acropolis.in",
  "roll_number": "0827AL231121",
  "numbers": ["1", "2", "3"],
  "alphabets": ["A", "B"],
  "highest_lowercase_alphabet": ["b"],
  "is_prime_found": false,
  "sum": "6",
  "concat_string": "...",
  "even_numbers": ["2"],
  "odd_numbers": ["1", "3"],
  "special_characters": ["!"]
}
```

### GET /bfhl/health

Health check endpoint — returns `200 OK`.

---

## Run Locally

```bash
./mvnw clean package -DskipTests
java -jar target/qualifier-1.0.0.jar
```

Then test:
```bash
curl -X POST http://localhost:8080/bfhl \
  -H "Content-Type: application/json" \
  -d '{"data": ["1","2","A","b","3"]}'
```

---

## Deploy on Railway

1. Connect this GitHub repo to [Railway](https://railway.app)
2. Railway auto-detects `railway.toml` and builds with Maven
3. The app starts on the `PORT` env variable automatically
4. Health check: `GET /bfhl/health`

---

## Environment Variables

| Variable | Default | Description |
|----------|---------|-------------|
| `PORT`   | `8080`  | Server port (set automatically by Railway) |
