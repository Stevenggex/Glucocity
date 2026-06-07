# Glucocity

Aplicación para el control y registro de niveles de glucosa en sangre. Permite a tutores gestionar dependientes, llevar un historial de mediciones y administrar medicamentos.

## Estructura del proyecto

```
Glucocity/
├── .github/workflows/
│   ├── staging.yml        # Auto-deploy a staging (rama develop)
│   └── production.yml     # Auto-deploy a producción (rama main)
├── backend/               # API en Python + FastAPI
│   ├── main.py            # Punto de entrada de la API
│   ├── requirements.txt   # Dependencias del backend
│   ├── .env.example       # Variables de entorno de ejemplo
│   └── venv/              # Entorno virtual (ignorado)
├── fronted/               # Frontend en Vue 3 + Vite
│   ├── src/               # Código fuente Vue
│   ├── public/            # Archivos públicos estáticos
│   ├── index.html         # HTML principal
│   ├── vite.config.js     # Configuración de Vite
│   └── package.json       # Dependencias del frontend
├── .gitignore             # Reglas de ignorado globales
└── README.md              # Este archivo
```

## Requisitos

- Node.js 20+
- Python 3.12+
- pip (gestor de paquetes de Python)

## Correr el frontend (local)

```bash
cd fronted
npm install
npm run dev
```

El servidor de desarrollo se levanta en `http://localhost:5173`.

## Correr el backend (local)

```bash
cd backend
python -m venv venv
source venv/bin/activate  # En Windows: venv\Scripts\activate
pip install -r requirements.txt
cp .env.example .env      # Completar las variables de entorno
uvicorn main:app --reload
```

La API se levanta en `http://localhost:8000`.

## Ramas

| Rama      | Entorno   | Descripción                        |
|-----------|-----------|------------------------------------|
| `main`    | Producción| Código estable en producción       |
| `develop` | Staging   | Integración y pruebas pre-producción|
