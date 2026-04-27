# DockForge

DockForge is a local, modular platform for molecular design assisted by docking.

This repository starts with the Phase 0 skeleton from the blueprint:

- FastAPI backend
- React + TypeScript + Vite frontend
- SQLite persistence
- Initial entities: Project, Receptor and Ligand
- Modular packages for chemistry, docking, scoring, interactions and optimization
- A workbench UI prepared for a 3D molecular viewer, a 2D ligand editor and project panels

## Repository Layout

```text
dockforge/
  apps/
    api/      FastAPI backend
    web/      React/Vite frontend
  packages/
    chemcore/
    docking/
    scoring/
    optimizer/
    interactions/
  data/
    projects/
  docs/
  tests/
```

## Backend

Recommended from `dockforge/apps/api`:

```bash
conda env create -f environment.yml
conda activate dockforge-api
uvicorn app.main:app --reload --port 8000
```

Core endpoints:

- `GET /health`
- `POST /projects`
- `GET /projects`
- `GET /projects/{project_id}`
- `POST /receptors`
- `GET /receptors`
- `GET /receptors/{receptor_id}`
- `POST /ligands/from-smiles`
- `GET /ligands`
- `GET /ligands/{ligand_id}`

## Frontend

Recommended from `dockforge/apps/web` with Node `^20.19.0` or `>=22.12.0`:

```bash
npm install
npm run dev
```

The frontend expects the API at `http://localhost:8000` by default. Override with:

```bash
VITE_API_BASE_URL=http://localhost:8000 npm run dev
```

### Static Preview

If you only want to see the first workbench mockup without installing anything, open:

```text
apps/web/preview.html
```

This is a static preview. The real app is the React/Vite project in `apps/web/src`.

## First MVP Target

MVP-LeadEdit v0.1:

- hAChE 4EY7 receptor/complex
- donepezil co-crystallized ligand
- 3D visualization
- 2D ligand editing
- ligand validation and 3D generation
- Vina `score_only` and `minimize`
- local database persistence
- compare original vs modified ligand
- export SDF/CSV

## Current Status

This is the initial development baseline. Docking engines and chemistry tooling are represented by stable interfaces and placeholders, ready to be implemented without coupling the UI to engine-specific details.
# Docking_Forge
# Docking_Forge
# Docking_Forge
