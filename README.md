# irohub

Aplicación Android desarrollada por **@nautaii**.

## Características

- App ligera basada en WebView optimizado
- Sin banners ni diálogos invasivos
- Navegación fluida con soporte de gestos
- Tema oscuro moderno
- Soporte para Android 5.0 (API 22) y superior
- Compilación nativa para 32 y 64 bits (armeabi-v7a, arm64-v8a, x86, x86_64)

## Compilación

El proyecto se compila automáticamente mediante GitHub Actions. Cada push a `main` o cada tag `v*` dispara una compilación que produce APKs firmados para todas las arquitecturas soportadas.

Para compilar localmente:

```bash
./gradlew assembleRelease
```

Los APKs se generan en `app/build/outputs/apk/release/`.

## Firmas

Para que GitHub Actions firme los APKs automáticamente, configurar estos secrets en el repo:

- `SIGNING_KEY_BASE64`: keystore en base64 (`base64 -w0 keystore.jks`)
- `KEY_ALIAS`: alias de la clave
- `KEYSTORE_PASSWORD`: password del keystore
- `KEY_PASSWORD`: password de la clave

Si no se configuran, GitHub Actions no podrá firmar los APKs de release. Se puede usar `assembleDebug` como alternativa.

## Estructura

```
irohub/
├── app/
│   ├── build.gradle
│   ├── src/main/
│   │   ├── AndroidManifest.xml
│   │   ├── java/com/irohub/app/
│   │   │   ├── MainActivity.java
│   │   │   ├── AboutActivity.java
│   │   │   └── irohubApp.java
│   │   └── res/
│   │       ├── drawable/         (iconos adaptivos)
│   │       ├── layout/           (layouts XML)
│   │       ├── menu/             (menús)
│   │       ├── mipmap-*/         (iconos por densidad)
│   │       └── values/           (strings, colors, themes)
├── .github/workflows/build.yml   (CI/CD)
├── build.gradle
├── settings.gradle
└── gradle/wrapper/
```

## Créditos

- Desarrollador: **@nautaii**
- Icono: Diseño propio generado con Pillow (Python)
- Tema: Material 3 Dark con paleta violeta/naranja

## Licencia

Uso educativo. Todo el contenido cargado por la app pertenece a sus respectivos dueños.
