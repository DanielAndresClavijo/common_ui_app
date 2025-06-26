# Common UI Package

Este repositorio contiene el código para `common_ui`, un paquete de Flutter compartido que proporciona componentes de interfaz de usuario, temas, constantes y utilidades para toda la ecosistema de la "Super App".

## Descripción General

El propósito de `common_ui` es centralizar todos los elementos visuales y de comportamiento comunes para garantizar una experiencia de usuario consistente en la aplicación principal y en todas las microaplicaciones.

Al tener una única fuente de verdad para la UI, evitamos la duplicación de código, facilitamos el mantenimiento y aseguramos que cualquier cambio de marca o estilo se aplique de manera uniforme en todo el proyecto.

## Contenido del Paquete

Este paquete puede exportar una variedad de elementos, tales como:

- **Temas:** Definiciones de `ThemeData` para los modos claro y oscuro (`CommonUITheme`).
- **Paleta de Colores:** Clases con colores de la marca definidos como constantes estáticas (`AppColors`).
- **Estilos de Texto:** Estilos de tipografía predefinidos (`AppTextStyles`).
- **Widgets Personalizados:** Componentes reutilizables como botones, campos de texto, tarjetas, etc. (`CustomButton`, `StyledCard`).
- **Recursos (Assets):** Fuentes personalizadas, iconos o imágenes que se usan en múltiples lugares.
- **Utilidades de UI:** Funciones de ayuda, mixins o extensiones relacionadas con la UI.

## Repositorios relacionados

- [parent-app](https://github.com/DanielAndresClavijo/parent-app)
- [micro_app_one](https://github.com/DanielAndresClavijo/micro_app_one)

## Cómo Usar

Para utilizar este paquete en cualquier otra aplicación o microaplicación, añade la siguiente dependencia a su archivo `pubspec.yaml`:

```yaml
dependencies:
  common_ui:
    git:
      url: https://github.com/example/common_ui.git # URL de este repositorio
      ref: main
```

Luego, puedes importar y usar sus componentes:

```dart
import 'package:common_ui/common_ui.dart';
import 'package:flutter/material.dart';

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'My App',
      theme: CommonUITheme.lightTheme, // Usando el tema compartido
      home: MyScreen(),
    );
  }
}

class MyScreen extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      body: Center(
        // Usando un widget y colores compartidos
        child: CustomButton(
          label: 'Hola Mundo',
          backgroundColor: AppColors.primary,
          onPressed: () {},
        ),
      ),
    );
  }
}
```

## Desarrollo y Pruebas

Este es un paquete de Flutter estándar. Para trabajar en él de forma aislada:

1.  **Clona el Repositorio:**

    ```sh
    git clone https://github.com/example/common_ui.git
    cd common_ui
    ```

2.  **Instala las Dependencias:**
    ```sh
    flutter pub get
    ```
