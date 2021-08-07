# PetProject — Task Management System

A web-based task management platform with role-based access control, queue processing, and email notifications. Built with Spring Boot.

## Features

- **Role-based access** — ADMIN, MODERATOR, PROGRAMMER, USER with distinct permissions
- **Task lifecycle** — ESTIMATED → WAITING_ACCEPT → QUEUED → IN_PROCESS → DONE / CANCELLED
- **File upload** — attach technical requirements (.doc, .docx, .pdf)
- **Queue management** — tasks are processed in FIFO order by available workers
- **Email notifications** — confirmation codes via Spring Mail on task submission
- **Admin panel** — user management, role assignment, ban/unban, sorting/filtering
- **Registration & auth** — sign-up with email confirmation, password reset flow
- **FreeMarker templates** — server-side rendered UI

## Tech Stack

| Layer | Technology |
|-------|-----------|
| Framework | Spring Boot 2.5 |
| Security | Spring Security |
| Persistence | Spring Data JPA / Hibernate |
| Database | PostgreSQL |
| Templating | Apache FreeMarker |
| Build | Maven |
| Java | JDK 8 |
| Utilities | Lombok, Guava |

## Getting Started

```bash
# Clone and run
git clone https://github.com/RomanNebelskyi/petProject.git
cd petProject
./mvnw spring-boot:run
```

Set the following environment variables:

```
MAIL_USERNAME=your-email
MAIL_PASSWORD=your-email-password
FILE_PATH=path/to/uploads
```

Configure `src/main/resources/application.properties` with your PostgreSQL credentials.

## Project Structure

```
src/main/java/com/example/petProject/
├── config/           — Security, MVC, Mail configuration
├── controller/       — Web controllers (Admin, Task, Auth, Cabinet)
├── model/            — JPA entities (User, Task, TaskQueue)
├── repo/             — Spring Data repositories
├── service/          — Business logic (Mail, File, Comparator)
└── Dto/              — Data transfer objects
```

## License

MIT
