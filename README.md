# AutoGrading

Autograding laten werken?

- Open project in Intellij
- In de folder `.github/workflows`
- Pas de inhoud van het bestand `classroom.yaml` aan naar:
```
name: GitHub Classroom Workflow

on: [push]

permissions:
  checks: write
  actions: read
  contents: read

jobs:
  build:
    name: Autograding
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - uses: actions/setup-java@v3
        with:
          distribution: 'temurin'
          java-version: '17'
      - uses: education/autograding@v1
