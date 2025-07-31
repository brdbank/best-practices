# 🌐 API Endpoint Design Best Practices

## ✅ 1. Use Nouns, Not Verbs
Endpoints should represent **resources**, not actions.

- ✅ `GET /users`  
- ❌ `GET /getUsers`

---

## ✅ 2. Use Plural Nouns for Resources
Always use **plural form** for collections.

- ✅ `/users`
- ✅ `/products/123`

---

## ✅ 3. Use HTTP Methods to Represent Actions

| HTTP Method | Purpose        | Example              |
|-------------|----------------|----------------------|
| `GET`       | Retrieve       | `/users/1`           |
| `POST`      | Create         | `/users`             |
| `PUT`       | Replace        | `/users/1`           |
| `PATCH`     | Update Partial | `/users/1`           |
| `DELETE`    | Delete         | `/users/1`           |

---

## ✅ 4. Use Nested Routes for Logical Relationships
Use nesting to reflect parent-child relationships.

- ✅ `/users/1/posts` (Posts by user 1)
- ✅ `/orders/123/items`

---

## ⚠️ 5. Avoid Deep Nesting
Deeply nested URLs like:
- /companies/1/departments/5/projects/3/tasks/9

---

## 🔄 Summary


| Principle       | Good Practice                  |
| --------------- | ------------------------------ |
| Resource Naming | Use nouns, plural form         |
| Method Usage    | Use HTTP verbs correctly       |
| Hierarchies     | Limit to 1–2 levels of nesting |
| Querying        | Use query params for filtering |
| Versioning      | Prefix API version in the URL  |
