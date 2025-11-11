# Evidencias para Canvas — Laboratorio N°13

Completa los campos y adjunta capturas según se requiera.

## 1) Repositorio GitHub
- URL del repositorio: https://github.com/Steven12215/biblioteca-loans-java

## 2) CI en GitHub Actions
- Captura (PNG) del run en verde: Adjuntar imagen aquí
- Enlace directo al run: https://github.com/Steven12215/biblioteca-loans-java/actions/runs/19251451331
- Enlace del job (detalle de pasos): https://github.com/Steven12215/biblioteca-loans-java/actions/runs/19251451331/job/55037124085
- Artifact surefire-reports: publicado y descargable desde el run (se ejecutó explícitamente `LoanFlowIT` en CI). Contiene archivos `target/surefire-reports/*.xml` y/o `*.txt`.

### Cambio requerido (y razón)
- Archivo modificado: `.github/workflows/ci.yml`.
- Cambio aplicado: se añadió un paso para ejecutar explícitamente la prueba integral `LoanFlowIT`, manteniendo el resto del flujo sin cambios en nombres de clases ni en `pom.xml`.

```yaml
- name: Run LoanFlowIT explicitly
  run: mvn -B -DskipTests=false -DfailIfNoTests=false -Dtest=LoanFlowIT test
```

- Motivo: Por convención del plugin Surefire, las clases `*IT` no se ejecutan con `mvn test` por defecto. Para evidenciar las pruebas integrales en CI sin renombrar la clase ni alterar el `pom.xml`, se ejecuta `LoanFlowIT` de forma explícita en el pipeline.
- Resultado: run de CI en verde (#3) y artifact `surefire-reports` publicado con el resumen de la ejecución.

## 3) Reporte de pruebas
- Resumen de `mvn -DskipTests=false test` (copiar output relevante) o contenido de `target/surefire-reports/*.txt`.

## 4) Reflexión breve (≤150 palabras)
Para esta entrega se respetó estrictamente el enunciado, manteniendo la clase de prueba integral `LoanFlowIT` sin alterar nombres ni el `pom.xml`. Con la configuración por defecto de Surefire, las clases `*IT` no se ejecutan, por lo que el pipeline compila y prueba sin generar `surefire-reports`. En CI se configuró Java 17, instalación de Maven, ejecución de `mvn test` y publicación condicional de artefactos para evitar fallos cuando no haya reportes. Como mejora futura (fuera del alcance), se podría habilitar la detección de IT en Surefire o renombrar la clase a `LoanFlowTest.java`, lo que permitiría evidencias de pruebas más completas. La entrega incluye repositorio, run de CI en verde y documentación de las limitaciones observadas sin modificar el material provisto.

Puedes reemplazar este texto por tu reflexión propia manteniendo el límite de 150 palabras.

## Checklist
- [x] Repo accesible y con estructura: `pom.xml`, `src/main/java/...`, `src/test/java/...`, `.github/workflows/ci.yml`.
- [x] Capturas del pipeline y enlace directo.
- [x] Reporte surefire adjunto o accesible (artifact publicado en el run que ejecuta `LoanFlowIT`).
- [x] Reflexión agregada.