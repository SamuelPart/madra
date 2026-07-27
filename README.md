# MandraPro (madra)

Proyecto Android (Kotlin + Android Gradle Plugin).

## Requisitos

- JDK 17
- Android SDK con API 34 instalada
- Gradle: no hace falta instalarlo, el proyecto usa el wrapper (`./gradlew`)

## Configuracion inicial

`local.properties` **no** se versiona (contiene rutas propias de cada maquina).
Al abrir el proyecto, Android Studio lo genera solo. Si compilas por linea de
comandos, crealo a mano en la raiz:

```properties
sdk.dir=/ruta/a/tu/Android/Sdk
```

O define la variable de entorno `ANDROID_HOME`.

## Compilar

```bash
./gradlew assembleDebug        # APK debug -> app/build/outputs/apk/debug/
./gradlew testDebugUnitTest    # tests unitarios
./gradlew lintDebug            # analisis estatico
```

En Windows usa `gradlew.bat` en lugar de `./gradlew`.

## Versiones

| Componente            | Version |
|-----------------------|---------|
| Android Gradle Plugin | 8.5.2   |
| Gradle                | 8.7     |
| Kotlin                | 1.9.24  |
| compileSdk / target   | 34      |
| minSdk                | 21      |
| JVM target            | 17      |

AGP 8.5.2 requiere Gradle 8.7; si actualizas uno, actualiza el otro.

## Estructura

```
madra/
├── app/                        # modulo de aplicacion
│   ├── build.gradle.kts
│   └── src/
│       ├── main/
│       │   ├── AndroidManifest.xml
│       │   ├── java/com/mandrapro/madra/MainActivity.kt
│       │   └── res/
│       └── test/               # tests unitarios
├── gradle/wrapper/             # wrapper: DEBE estar versionado
├── ci/android-ci.yml           # workflow de CI (ver ci/README.md)
├── build.gradle.kts
└── settings.gradle.kts
```

## Integracion continua

El workflow de GitHub Actions esta en `ci/android-ci.yml` y todavia no esta
activo. Ver [`ci/README.md`](ci/README.md) para activarlo.
