# Test info

- Name: Envío baleiro do formulario
- Location: C:\xampp\htdocs\MAIO\tests\formulario.spec.js:15:1

# Error details

```
Error: page.goto: net::ERR_CONNECTION_REFUSED at http://localhost/MAIO/index.html
Call log:
  - navigating to "http://localhost/MAIO/index.html", waiting until "load"

    at C:\xampp\htdocs\MAIO\tests\formulario.spec.js:16:16
```

# Page snapshot

```yaml
- heading "No se puede acceder a este sitio web" [level=1]
- paragraph:
  - text: La página
  - strong: localhost
  - text: ha rechazado la conexión.
- paragraph: "Prueba a:"
- list:
  - listitem: Comprobar la conexión
  - listitem:
    - link "Comprobar el proxy y el cortafuegos":
      - /url: "#buttons"
- text: ERR_CONNECTION_REFUSED
- button "Volver a cargar"
- button "Detalles"
```

# Test source

```ts
   1 | const { test, expect } = require('@playwright/test');
   2 |
   3 | test('Envío válido do formulario', async ({ page }) => {
   4 |     await page.goto('http://localhost/MAIO/index.html');
   5 |
   6 |     await page.fill('input[name="nome"]', 'Ana');
   7 |     await page.fill('input[name="email"]', 'ana@example.com');
   8 |     await page.fill('textarea[name="mensaxe"]', 'Proba automatizada');
   9 |
  10 |     await page.click('button[type="submit"]');
  11 |
  12 |     await expect(page.locator('#confirmacion')).toContainText('Mensaxe enviada correctamente');
  13 | });
  14 |
  15 | test('Envío baleiro do formulario', async ({ page }) => {
> 16 |     await page.goto('http://localhost/MAIO/index.html');
     |                ^ Error: page.goto: net::ERR_CONNECTION_REFUSED at http://localhost/MAIO/index.html
  17 |
  18 |     // Forzar a eliminación de validación no cliente
  19 |     await page.evaluate(() => {
  20 |         const form = document.querySelector('form');
  21 |         form.removeAttribute('novalidate');
  22 |         form.noValidate = true;
  23 |     });
  24 |
  25 |     // Forzar envío aínda que os campos estean baleiros
  26 |     await page.$eval('form', form => form.submit());
  27 |
  28 |     // Agardar polos erros xerados polo servidor
  29 |     await expect(page.locator('.erro')).toBeVisible();
  30 | });
```