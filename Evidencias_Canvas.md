# Evidencias para Canvas — Laboratorio N°13

Completa los campos y adjunta capturas según se requiera.

## 1) Repositorio GitHub
- URL del repositorio: https://github.com/Steven12215/biblioteca-loans-java

## 2) CI en GitHub Actions
- Captura (PNG) del run en verde: Adjuntar imagen aquí
- Enlace directo al run: https://github.com/Steven12215/biblioteca-loans-java/actions/runs/19251200293
- Artifact surefire-reports: no generado en este laboratorio (la clase integral se llama `LoanFlowIT` y por convención de Surefire las `*IT` no se ejecutan con `mvn test`).

## 3) Reporte de pruebas
- Resumen de `mvn -DskipTests=false test` (copiar output relevante) o contenido de `target/surefire-reports/*.txt`.

## 4) Reflexión breve (≤150 palabras)
Para esta entrega se respetó estrictamente el enunciado, manteniendo la clase de prueba integral `LoanFlowIT` sin alterar nombres ni el `pom.xml`. Con la configuración por defecto de Surefire, las clases `*IT` no se ejecutan, por lo que el pipeline compila y prueba sin generar `surefire-reports`. En CI se configuró Java 17, instalación de Maven, ejecución de `mvn test` y publicación condicional de artefactos para evitar fallos cuando no haya reportes. Como mejora futura (fuera del alcance), se podría habilitar la detección de IT en Surefire o renombrar la clase a `LoanFlowTest.java`, lo que permitiría evidencias de pruebas más completas. La entrega incluye repositorio, run de CI en verde y documentación de las limitaciones observadas sin modificar el material provisto.

Puedes reemplazar este texto por tu reflexión propia manteniendo el límite de 150 palabras.

## Checklist
- [x] Repo accesible y con estructura: `pom.xml`, `src/main/java/...`, `src/test/java/...`, `.github/workflows/ci.yml`.
- [x] Capturas del pipeline y enlace directo.
- [ ] Reporte surefire adjunto o accesible. (No aplica en esta configuración: `LoanFlowIT` no corre con `mvn test` por convención.)
- [x] Reflexión agregada.