# 🧠 Developing and Testing an Asynchronous API with FastAPI and Pytest

This project documents my learning journey on how to **develop, containerize, and test an asynchronous REST API** built with **FastAPI**, **PostgreSQL**, and **Pytest**, using **Docker Compose** for orchestration.

---

## 📘 Project Overview

This FastAPI CRUD application manages **Notes** and demonstrates:

- Building an **asynchronous API** using FastAPI.
- Using **SQLAlchemy Core** and the **databases** library for async DB operations.
- Writing and running **Pytest test cases** for endpoint testing.
- Running the app and database with **Docker Compose**.
- Viewing and interacting with the **OpenAPI (Swagger UI)** documentation.

---

## 🧩 Tech Stack

| Tool | Purpose |
|------|----------|
| **FastAPI** | Framework for building the API |
| **PostgreSQL** | Database for storing notes |
| **Docker Compose** | Orchestrates app and DB containers |
| **Pytest** | Testing framework for endpoints |
| **Starlette TestClient** | Mocks API requests during tests |
| **HTTPie / curl** | For manual API testing |

---



🧾 Notes CRUD API
Method	Endpoint	Description
GET	/notes/	Read all notes
POST	/notes/	Create a new note
GET	/notes/{id}	Read a single note
PUT	/notes/{id}/	Update an existing note
DELETE	/notes/{id}/	Delete a note

🧪 Testing with Pytest
Run tests directly inside the Docker container:

bash
Copy code
docker-compose exec web pytest
Example Output:
<img width="1882" height="969" alt="Screenshot 2025-11-12 122704" src="https://github.com/user-attachments/assets/13c50de4-3a7b-4120-9b0a-721a6d9f3fca" />

<img width="1597" height="702" alt="Screenshot 2025-11-12 130205" src="https://github.com/user-attachments/assets/b2d6eecc-4ded-4af8-8a7a-6a3ea2fcc84a" />

<img width="1612" height="365" alt="Screenshot 2025-11-12 140708" src="https://github.com/user-attachments/assets/a70c0462-f372-4110-b0f0-eee8fee9d03d" />

<img width="1894" height="962" alt="Screenshot 2025-11-12 140855" src="https://github.com/user-attachments/assets/b8fd92a5-f507-49a5-9ab7-71b96b2a9879" />


🧠 Key Learnings
Defining asynchronous routes using async def.

Using Pytest fixtures and monkeypatch to mock DB operations.

Adding validation using Path(..., gt=0) for proper HTTP 422 errors.

Using Docker Compose to manage a multi-container environment.

Accessing interactive API documentation via Swagger UI.

🧰 Common Commands Reference
Action	Command
Build containers	docker compose up -d --build
Run tests	docker compose exec web pytest
Access PostgreSQL	docker compose exec db psql -U hello_fastapi -d hello_fastapi_dev
View Swagger Docs	http://localhost:8002/docs

🧾 Conclusion
This project demonstrates how to:

✅ Develop and test a fully asynchronous FastAPI application.
✅ Use Pytest to validate endpoints thoroughly.
✅ Manage Dockerized environments for consistency and reproducibility.

All tests passing ✅ and a working Swagger UI confirm that the FastAPI API and PostgreSQL database are integrated successfully.

