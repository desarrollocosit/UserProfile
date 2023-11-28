

## Requisitos previos
Para ejecutar este proyecto prediseñado, necesitará:

- [Android Studio Giraffe o superior](https://developer.android.com/studio)
- Dispositivo Android o emulador que ejecute API nivel 23 o superior
- SDK de Android instalado y configurado (> v.32.0.0)
- Herramientas de compilación de Android (> v.32.0.0)
- JDK 17 (ahora integrado en Android Studio)

### Instalación del marco Couchbase Lite

- Este proyecto ya contiene las adiciones apropiadas para descargar y utilizar el módulo de dependencia de Android Couchbase Lite. Sin embargo, en el futuro, para incluir compatibilidad con Couchbase Lite dentro de una aplicación de Android, agregue lo siguiente en el archivo de configuración de Gradle (src/gradle.settings)

```
dependenciaResoluciónManagement {
    repositoriosMode.set(RepositoriosMode.FAIL_ON_PROJECT_REPOS)
    repositorios {
        maven {url "https://mobile.maven.couchbase.com/maven2/dev/" } // << agregar este repositorio
        Google()
        expertoCentral()
    }
}
```

- A continuación, asegúrese de estar utilizando la versión más reciente de Couchbase Lite Mobile para Android. En el archivo de compilación del módulo (src/app/build.gradle), verifique esta línea para verificar que el número de versión sea correcto:

```
dependencias {
    ...

    implementación 'com.couchbase.lite:couchbase-lite-android-ee:3.1.2'
}
```

## Arquitectura de la aplicación

La aplicación de muestra sigue el [patrón MVP](https://en.wikipedia.org/wiki/Model%E2%80%93view%E2%80%93presenter), separando el modelo de datos interno, de una vista pasiva a través de un presentador. que maneja la lógica de nuestra aplicación y actúa como conducto entre el modelo y la vista.

## Pruébalo

* **Abre src/build.gradle usando Android Studio.**
* Construir y ejecutar el proyecto.
* Verifica que ves la pantalla de inicio de sesión.

## Conclusión

Configurar una aplicación básica de Android en Java con Couchbase Lite es bastante simple; cuando se ejecute este proyecto, el usuario podrá iniciar sesión, actualizar un perfil de usuario y guardar la información en la base de datos integrada.
