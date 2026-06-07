# 📚 Library Management System

A **full CRUD web application** for managing a book collection — built with vanilla HTML, CSS, and JavaScript. No frameworks, no build step, no server needed. Just open `index.html` and go.

🔗 **Live demo:** https://karobel.github.io/library/

---

## ✨ Features

| Feature | Details |
|---|---|
| **Create** | Add books with title, author, ISBN, genre, price, stock, and publish date |
| **Read** | Browse the full collection in a sortable table |
| **Search** | Real-time search across title, author, and genre |
| **Filter** | Filter by genre using the sidebar |
| **Update** | Edit any book with a pre-filled form |
| **Delete** | Remove a book with a confirmation dialog |
| **Persistence** | Data saved in `localStorage` — survives page refresh |
| **Validation** | Duplicate ISBN detection, required-field checks, type guards |

---

## 🏗️ Architecture

The app mirrors a **layered architecture** (the same pattern used in Java/Spring Boot):

```
index.html
│
├── Data Layer     loadData / saveData / createBook / readAll / updateBook / deleteBook
│                  → in-memory array + localStorage for persistence
│
├── Service Layer  validation logic inside saveBook()
│                  → duplicate ISBN, required fields, negative-value guards
│
└── UI Layer       render() + modal functions
                   → builds the DOM from data, handles user events
```

This structure maps directly to the Java version of the project:

| Web (JS)                  | Java equivalent              |
|---------------------------|------------------------------|
| `books[]` array           | `InMemoryBookRepository`     |
| `createBook / readAll …`  | `BookRepository` interface   |
| Validation in `saveBook`  | `BookService`                |
| `render()` + modals       | `ConsoleUI`                  |

---


## 🛠️ Tech Stack

| Technology | Purpose |
|---|---|
| HTML5 | Structure & semantic markup |
| CSS3 | Custom properties, grid, animations |
| Vanilla JavaScript (ES2020) | DOM, localStorage, business logic |
| Google Fonts | Playfair Display + DM Mono |

**Zero dependencies. Zero build tools. One file.**

---

## 🔮 Possible Extensions

- [ ] Connect to a REST API backend (Java Spring Boot / Node.js)
- [ ] Add a `Member` entity + `Loan` management (borrow / return)
- [ ] Export collection to CSV / PDF
- [ ] Add sorting on table columns
- [ ] Dark / light theme toggle
- [ ] Unit tests with Vitest or Jest

---

