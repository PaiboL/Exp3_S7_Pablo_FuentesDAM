# SeñalSegura - Experiencia 3, Semana 7

Aplicación Android accesible para apoyar la comunicación de personas con discapacidad auditiva en contextos cotidianos, laborales y de emergencia.

Esta versión continúa el proyecto de tema libre validado por el docente e integra el back end solicitado para la actividad formativa “Programando el back end de la aplicación móvil”. Conserva todo lo desarrollado entre las semanas 2 y 6.

## Funciones incluidas

- Inicio de sesión y registro mediante Firebase Authentication cuando existe configuración.
- Recuperación de contraseña por correo mediante Firebase Authentication.
- Respaldo local funcional cuando no se encuentra `google-services.json`.
- Persistencia de sesión y alto contraste mediante `SharedPreferences` y Android KTX.
- Mensajes escritos mostrados en tamaño grande.
- Reproducción del mensaje mediante texto a voz.
- Frases rápidas organizadas por categoría.
- Búsqueda y filtrado de frases mediante colecciones y ciclos de Kotlin.
- Análisis del mensaje: prioridad, cantidad de palabras y tiempo estimado de lectura.
- Alerta visual y respuesta háptica.
- Modo de alto contraste.
- Diseño adaptativo mediante una grilla de ancho flexible.
- Tabla reutilizable con prioridad, cantidad de palabras y tiempo de lectura.
- Navegación con NavController y NavHost.
- Estado de la pantalla principal administrado por `HomeViewModel`.
- Validaciones de correo y registro centralizadas.
- Pantalla con cinco alertas accesibles almacenadas en un `Array`.
- Alertas favoritas y contador de uso mediante colecciones `Set` y `Map`.
- Jerarquía de alertas con clase abstracta, subclases e interfaz.
- Búsqueda de alertas combinada con categoría y favoritas mediante una lambda retornada.
- Validación del mensaje visible con límite de 180 caracteres y retroalimentación comprensible.
- Resumen semántico de cada alerta para lectores de pantalla como TalkBack.
- Componentes `@Composable` reutilizables como equivalentes modernos de Views y Fragments.
- `Scaffold`, `Column`, `Row`, `Card` y `LazyVerticalGrid` como ViewGroups adaptativos.
- Catálogo y detalle de alertas, equivalentes funcionales de las vistas Minuta y Receta.
- `AlertContentProvider` de solo lectura registrado en el manifiesto.
- Consulta del proveedor mediante `ContentResolver` y extensiones KTX.
- Extracción real de colores con Android Palette desde una ilustración vectorial.
- Textos, tarjetas y botones personalizados con la paleta obtenida.
- Eventos de clic, edición, selección, pulsación prolongada y navegación.
- Widget Android instalable en la pantalla de inicio.
- Pantalla de administración de datos con estado de conexión visible.
- Sincronización en tiempo real de alertas mediante `ValueEventListener`.
- CRUD completo de alertas con `setValue`, `updateChildren` y `removeValue`.
- CRUD del perfil asociado al usuario autenticado.
- Reglas de Realtime Database que restringen cada ruta al `uid` autenticado.
- Modelos Firebase con constructor vacío compatible con `DataSnapshot`.

## Evidencia de Kotlin

- Variables inmutables y mutables con `val` y `var`.
- Tipos `String`, `Int`, `Boolean`, `List` y tipos anulables.
- Operadores aritméticos, de comparación y lógicos.
- Condicionales `if/else` y expresiones `when`.
- Ciclos `for` y uso de `continue`.
- Funciones reutilizables y colecciones tipadas.
- Seguridad nula mediante `String?`, operador `?.` y `orEmpty()`.

El detalle de cada evidencia se encuentra en `EVIDENCIA_KOTLIN.md`.

## Evidencia de programación orientada a objetos

- Clases, objetos, propiedades, métodos y constructores.
- Modificadores de visibilidad `private`, `protected` e `internal`.
- Herencia mediante `AccessibleAlert`, `EmergencyAlert` e `InformationAlert`.
- Interfaz `AccessibleContent` para el texto accesible.
- Colecciones `Array`, `List`, `Set` y `Map` aplicadas a funcionalidades reales.

El detalle se encuentra en `EVIDENCIA_POO_SEMANA4.md`.

## Evidencia de Kotlin avanzado

- Función de orden superior `buildAlertPredicate`, que retorna una lambda reutilizable.
- Función `inline` `executeAccessibleAction`, que recibe tres lambdas.
- Lambdas aplicadas a `filter`, `sortedBy`, `map`, `count` y callbacks de Compose.
- Función de extensión `String.toAccessibleMessage()`.
- Propiedades de extensión `String.wordCount` y `AccessibleAlert.accessibilitySummary`.
- Gestión específica de errores mediante `try/catch/finally` y `InvalidAccessibleMessageException`.

El detalle y la ruta de cada implementación se encuentran en `EVIDENCIA_KOTLIN_AVANZADO_SEMANA5.md`.

## Evidencia de front end y KTX

- `AlertContentProvider` comparte de forma estructurada las cinco alertas mediante URI.
- `AlertProviderClient` consulta los datos con `ContentResolver` y cierra el cursor con `use`.
- `String.toUri()` y `Cursor.getStringOrNull()` evidencian extensiones de Android KTX.
- `rememberAlertPaletteColors` convierte la ilustración vectorial a `Bitmap` y ejecuta `Palette.from(...).generate()`.
- `AccessibleAlertCard` y `PaletteHeader` son componentes visuales reutilizables.
- `AlertDetailScreen` separa el catálogo del detalle de una alerta.
- `SignalSafeWidgetProvider` implementa un widget real para la pantalla de inicio.

La trazabilidad completa está en `EVIDENCIA_FRONT_END_SEMANA6.md`.

## Evidencia de back end y persistencia

- `FirebaseAuthRepository` implementa registro, inicio de sesión, cierre y recuperación de contraseña.
- `FirebaseBackendRepository` administra perfiles y alertas en Realtime Database.
- `FirebaseAlertRecord` y `FirebaseUserProfile` representan los objetos persistentes.
- `BackendViewModel` separa la lógica de datos de la pantalla Compose.
- `BackendScreen` permite crear, consultar, modificar y eliminar registros.
- `SessionPreferences` conserva información de sesión y configuración mediante la extensión KTX `edit`.
- `firebase.database.rules.json` limita el acceso a los datos del usuario autenticado.
- El modo local permite revisar toda la interfaz sin exponer una configuración privada.

La correspondencia con la pauta se encuentra en `EVIDENCIA_BACK_END_SEMANA7.md` y la configuración detallada en `CONFIGURACION_FIREBASE_SEMANA7.md`.

## Acceso de demostración

- Correo: `pablo@duoc.cl`
- Contraseña: `1234`

Este acceso funciona en modo local. Cuando Firebase está configurado, se debe crear una cuenta desde la pantalla Registro.

## Configuración

- Android Studio con JDK 21 seleccionado como Gradle JDK.
- El archivo `gradle/gradle-daemon-jvm.properties` solicita el JDK 21 incluido en Android Studio.
- Gradle 9.5.0.
- Android Gradle Plugin 9.3.1.
- Compile SDK 37, siguiendo el proyecto de ejemplo de la sesión sincrónica.
- Dispositivo virtual recomendado: Android 15, API 35, x86_64.
- Firebase Android BoM 34.19.0.
- Firebase Authentication y Firebase Realtime Database.

Para conectar un proyecto real, seguir `CONFIGURACION_FIREBASE_SEMANA7.md`. El archivo `google-services.json` se descarga desde Firebase Console y se copia en `app/`.

El JDK 21 ejecuta Gradle. La aplicación conserva compatibilidad de bytecode Java 17, que es la configuración apropiada para Android.

## Verificación

Desde la carpeta principal del proyecto:

```bash
./gradlew testDebugUnitTest assembleDebug
```

En Windows también se puede ejecutar `gradlew.bat testDebugUnitTest assembleDebug`.

## Repositorio Git

El proyecto incluye la carpeta `.git` con los commits de las semanas 2, 3, 4, 5, 6 y 7. Para cumplir el requisito de colaboración, se debe publicar esta carpeta en GitHub y adjuntar expresamente su enlace en AVA.

Las instrucciones para comprobar autenticación, CRUD y sincronización están en `GUIA_VERIFICACION_SEMANA7.md`.
