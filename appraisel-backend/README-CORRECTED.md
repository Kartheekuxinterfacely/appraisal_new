# Appraisal Letter Backend — Setup

## Requirements
- Java 21
- MySQL 8.x

## 1. Create a fresh database
Run this in MySQL Workbench:
```sql
CREATE DATABASE IF NOT EXISTS appraisel_db;
```
You do not need to create the `appraisels` table manually. Hibernate creates/updates it from the `Appraisal` entity when the backend starts.

## 2. Start backend on Windows
Open PowerShell in this folder and run:
```powershell
.\run-backend.ps1
```
Enter the MySQL `root` password when prompted. The script passes it to Spring Boot only for that process and does not store it in the project.

If you use another database user, set `$env:DB_USERNAME` before running the script. You can also set `DB_URL`, `DB_USERNAME`, `DB_PASSWORD`, and `SERVER_PORT` as environment variables.

## 3. Verify
- Health: http://localhost:9090/api/appraisels/health
- Swagger UI: http://localhost:9090/swagger-ui/index.html
- List saved records: http://localhost:9090/api/appraisels

Keep the backend terminal open while testing. The frontend expects the API at `http://localhost:9090` by default.
