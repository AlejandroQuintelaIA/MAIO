# MAIO
# Formulario de Contacto con Bootstrap

Este proyecto implementa un formulario de contacto responsive utilizando Bootstrap 5 con validación del lado del cliente.

## Características

- Validación en tiempo real
- Diseño responsive
- Mensajes de feedback para el usuario
- Validación de formato de email
- Control de longitud en el mensaje

## Estructura del Proyecto

```
formulario-bootstrap/
├── src/
│   ├── css/
│   │   └── styles.css
│   ├── js/
│   │   └── validation.js
│   └── index.html
└── README.md
```

## Cómo usar

1. Clona el repositorio
2. Coloca los archivos en tu servidor Apache local (ej: xampp/htdocs/)
3. Accede a través de localhost en tu navegador
4. Prueba el formulario completando los campos

## Importante ⚠️

Este formulario solo funciona correctamente cuando se ejecuta a través de:
- Servidor Apache
- Acceso mediante localhost
- No funcionará si se abre directamente el archivo HTML

## Validaciones

- Nombre: Campo obligatorio
- Email: Campo obligatorio y formato válido
- Mensaje: Entre 10 y 200 caracteres

## URLs del Proyecto

### URLs de Acceso
- **Clonar Repositorio**: `https://github.com/AlejandroQuintelaIA/MAIO.git`
- **Ver Código**: `https://github.com//AlejandroQuintelaIA/MAIO`
- **GitHub Pages**: `https://alejandroquintelaia.github.io/MAIO/`

## Tecnologías utilizadas

- HTML5
- CSS3
- JavaScript
- Bootstrap 5
- Apache Server

## Ejecución de Tests

Para ejecutar las pruebas automatizadas del formulario:

1. Instala las dependencias necesarias:
```bash
npm install
npm i -D @playwright/test
```

2. Instala los navegadores requeridos:
```bash
npx playwright install
```

3. Ejecuta los tests:
```bash
npx playwright test
```

Las pruebas verifican:
- Envío correcto del formulario con datos válidos
- Validación de campos vacíos
- Comportamiento del formulario con datos inválidos

### Requisitos previos
- Node.js instalado
- Servidor Apache ejecutándose (XAMPP)
- Proyecto ubicado en la carpeta htdocs