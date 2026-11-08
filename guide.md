# CHITRA Setup & Deployment Guide (Spring Boot + Pure HTML/CSS/JS)

> **NITROUS ENGINE (CHITRA - Team NiTRO+)**  
> AI-powered automated content transformation platform.  
> Complete Spring Boot 3 Backend with a pure HTML5, CSS3, and JavaScript Frontend.

---

## 🛠️ Prerequisites

| Component | Minimum Requirement | Notes |
|---|---|---|
| **Operating System** | Windows 10/11, macOS, Linux | Any modern OS |
| **Java** | JDK 21+ | JDK 21 or JDK 22 recommended |
| **Build Tool** | Embedded Maven Wrapper (`mvnw` / `mvnw.cmd`) | Pre-packaged in the repository |
| **Node.js** | **NOT REQUIRED** | Pure HTML/CSS/JS requires zero npm packages! |

---

## 🚀 How to Run

### Single-Command Full-Stack Execution
The HTML, CSS, and JS frontend is bundled directly inside the Spring Boot backend (`src/main/resources/static`).

1. Open PowerShell / Command Prompt:
   ```powershell
   cd C:\Users\01abh\.gemini\antigravity\scratch\chitra\backend
   .\mvnw.cmd spring-boot:run
   ```

2. Open your web browser:
   ```
   http://localhost:8000
   ```

The application is completely loaded and fully functional!

---

## 💻 Standalone Frontend (Optional)
If you prefer editing the frontend in isolation:
- The `frontend/` folder contains standalone `index.html`, `styles.css`, and `app.js`.
- Simply double-click `frontend/index.html` to open it in Chrome/Edge/Firefox. It connects to the Spring Boot backend running on `http://localhost:8000`.
