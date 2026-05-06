🌐 README.md — SecureProductApi (Cyberpunk Edition)
⚡ API sicura, containerizzata, scalabile. Costruita con ASP.NET Core 8, EF Core, SQL Server, Docker e pipeline DevSecOps.

🟣 SecureProductApi
API REST moderna e sicura per la gestione dei prodotti, progettata con architettura pulita, logging, middleware personalizzato, containerizzazione e pipeline CI con SAST.

Progetto ideale per portfolio Backend + DevSecOps.

🚀 Tecnologie principali
ASP.NET Core 8

Entity Framework Core

SQL Server (Docker)

Repository + Service Pattern

Middleware personalizzato

Swagger/OpenAPI

Dockerfile multi-stage

Docker Compose

GitHub Actions (CI + SAST)

Semgrep (SAST)

🧬 Architettura
Codice
          ┌──────────────────────────┐
          │      Products API        │
          │     ASP.NET Core 8       │
          ├─────────────┬────────────┤
          │ Controllers  │ Middleware │
          └──────┬──────┴──────┬─────┘
                 │             │
           ┌─────▼─────┐   ┌──▼────────┐
           │ Services   │   │ Error Mdw │
           └─────┬─────┘   └───────────┘
                 │
           ┌─────▼──────┐
           │ Repository  │
           └─────┬──────┘
                 │
           ┌─────▼────────┐
           │  DbContext    │
           └─────┬────────┘
                 │
           ┌─────▼──────────────┐
           │ SQL Server (Docker) │
           └─────────────────────┘
📁 Struttura del progetto
Codice
SecureProductApi/
│
├── src/
│   └── SecureProductApi/
│       ├── Controllers/
│       ├── Models/
│       ├── DTOs/
│       ├── Services/
│       ├── Repositories/
│       ├── Data/
│       ├── Middleware/
│       ├── appsettings.json
│       └── Program.cs
│
├── docker/
│   ├── Dockerfile
│   └── docker-compose.yml
│
├── .github/workflows/
│   └── ci.yml
│
└── README.md
🔌 Endpoint API
GET /api/products
Restituisce tutti i prodotti.

GET /api/products/{id}
Restituisce un prodotto specifico.

POST /api/products
Crea un nuovo prodotto.
Body:

json
{
  "name": "Laptop",
  "price": 1299.99
}
🐳 Esecuzione con Docker
Assicurati di essere nella cartella docker/.

Build + Run
bash
docker-compose up --build
Servizi esposti:
API → http://localhost:8080/swagger

SQL Server → localhost:1433

🧪 Esecuzione locale (senza Docker)
bash
cd src/SecureProductApi
dotnet restore
dotnet run
Swagger disponibile su:

Codice
https://localhost:5001/swagger
🔐 Sicurezza
Middleware globale per gestione errori

Validazione input tramite DTO

SQL Server con credenziali isolate

Pipeline CI con SAST (Semgrep)

Dockerfile multi-stage per ridurre superficie d’attacco

Immagini ufficiali Microsoft

🛠️ Pipeline CI (GitHub Actions)
La pipeline esegue:

Restore

Build

Test

SAST (Semgrep)

Preparazione per CD

File: .github/workflows/ci.yml

🧭 Roadmap
[ ] Aggiungere autenticazione JWT

[ ] Aggiungere ruoli e autorizzazioni

[ ] Aggiungere logging avanzato con Serilog + Elastic Stack

[ ] Aggiungere test di integrazione

[ ] Aggiungere scansione container (Trivy)

[ ] Deploy su Azure Container Apps

👨‍💻 Autore
Hamid Elharouachi  
Backend & DevSecOps Engineer
Milano, Italia
