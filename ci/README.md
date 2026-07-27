# CI

`android-ci.yml` es el workflow de GitHub Actions que compila el APK debug,
ejecuta los tests unitarios y pasa lint.

No pudo commitearse directamente en `.github/workflows/` porque la integración
que abrió este cambio no tiene el permiso `workflows` de GitHub. Para activarlo,
muévelo tú a su ubicación definitiva:

```bash
mkdir -p .github/workflows
git mv ci/android-ci.yml .github/workflows/android.yml
git commit -m "ci: activar workflow de Android"
git push
```
