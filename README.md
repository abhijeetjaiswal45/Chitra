# CHITRA - Content Transformation Platform (Spring Boot + Pure HTML/CSS/JS)

> **NITROUS ENGINE (CHITRA - Team NiTRO+)**  
> AI-powered automated content transformation platform (Raw PDFs, DOCX, Text Prompts $\rightarrow$ PowerPoint Decks, PDF Advisories, Infographics, Social Posts, and Executive Summaries).  
> **Enterprise-Grade Spring Boot 3 (Java 21/22)** Backend with a zero-dependency **Pure HTML5, CSS3, & Vanilla JavaScript** Frontend UI.

---

## 🏛️ Project Architecture

```
chitra/
├── backend/                             # Spring Boot 3 Java Backend
│   ├── pom.xml                          # Maven build dependencies
│   ├── mvnw / mvnw.cmd                  # Maven Wrapper (zero install required)
│   ├── .env.example                     # Environment template (Gemini / Ollama)
│   └── src/
│       ├── main/
│       │   ├── java/com/chitra/
│       │   │   ├── ChitraApplication.java       # Spring Boot Main Entry Point
│       │   │   ├── config/                      # CORS & WebMvc Configuration
│       │   │   ├── controller/                  # REST Controllers (/health, /transform, /download)
│       │   │   ├── dto/                         # Request/Response Jackson DTOs
│       │   │   └── service/                     # Business Logic & Engine Services
│       │   │       ├── DocumentParserService.java   # Apache PDFBox & Apache POI DOCX parsing
│       │   │       ├── VectorStoreService.java      # In-memory chunk retrieval & ranking
│       │   │       ├── LlmEngineService.java        # HybridBrain (Ollama + Google Gemini Fallback)
│       │   │       ├── PptxGeneratorService.java    # Apache POI 16:9 Widescreen Presentation generator
│       │   │       └── PdfGeneratorService.java     # OpenPDF Sovereign / CERT-In PDF Advisory generator
│       │   └── resources/
│       │       ├── application.properties       # Server port (8000), upload limits, LLM properties
│       │       └── static/                      # Bundled HTML/CSS/JS Frontend (Served on http://localhost:8000)
│       │           ├── index.html
│       │           ├── styles.css
│       │           ├── app.js
│       │           └── assets/
│       └── test/
├── frontend/                            # Standalone Pure HTML, CSS & Vanilla JavaScript UI
│   ├── index.html                       # Complete responsive layout & modals
│   ├── styles.css                       # Design tokens, themes, animations
│   ├── app.js                           # State machine, reactive UI, API integration
│   └── assets/                          # Static assets and icons
├── guide.md                             # Setup & deployment guide
├── Rules.md                             # Design & architecture rules
├── fact.md                              # Functional specifications
├── front.md                             # Frontend design system specifications
└── brain.md                             # Engine specifications & deliverable tracking
```

---

## 🚀 Quick Start (Zero Node.js Required!)

### 1. Prerequisites
- **Java:** JDK 21 or JDK 22 installed (`java -version`)
- *(Optional)* **Ollama:** For local offline air-gapped inference (`ollama run qwen3:8b`)
- *(Optional)* **Google Gemini API Key:** For cloud inference

---

### 2. Run the Spring Boot Server & UI Together

Because the HTML/CSS/JS frontend is bundled inside the Spring Boot backend (`src/main/resources/static`), **a single command runs the entire full-stack application!**

1. Open a terminal and navigate to `backend`:
   ```bash
   cd backend
   ```

2. Run the application using the included Maven wrapper:
   - **On Windows:**
     ```powershell
     .\mvnw.cmd spring-boot:run
     ```
   - **On Linux/macOS:**
     ```bash
     ./mvnw spring-boot:run
     ```

3. **Open in your browser:**  
   Navigate to:
   ```
   http://localhost:8000/
   ```
   The complete CHITRA UI and all backend APIs are live!

---

### 3. (Optional) Run the Standalone Frontend Folder

You can also run or open `frontend/index.html` directly in your browser or with any lightweight static server:
```bash
# Double-click or open in browser:
frontend/index.html

# Or with python/live-server if desired:
cd frontend
python -m http.server 3000
```
It automatically connects to the backend at `http://localhost:8000`.

---

## 🎨 Frontend Highlights (Pure HTML/CSS/JS)
- **100% Identical Visual Design:** Exact same `#FCE4E4` pastel canvas, `#7A3E48` rosewood headers and 2px borders, `#5E2E36` burgundy buttons, and `#FDF8F8` inner cards.
- **Zero Framework Bloat:** No `node_modules`, no npm dependencies, no build step. Instant loading in any modern browser.
- **Full Interactive Feature Parity:**
  - Dynamic drag-and-drop document upload with document grid cards and PDF badges.
  - Symmetrical mode switch: **Upload Documents** vs **Text Prompt**.
  - Circular expandable intake drawer.
  - Fine-grained **Parameters Drawer** (Deliverables multi-select, Tone, Audience, Classification).
  - Real-time **Pipeline Execution Tracker** with smooth progress meter and instant cancel button.
  - Interactive **Generated Deliverables Carousel** with dots and arrow navigation.
  - Interactive **16:9 Slide Deck Modal** with speaker notes and keyboard arrow navigation.
  - Formal **Compliance Advisory Modal** with IoC lists and mitigation steps.
  - Dynamic **SVG Vector Graphic** rendering with instant download.
  - One-click copy buttons with animated "Copied!" feedback.
  - Direct file downloads for generated `.pptx` and `.pdf` files.
