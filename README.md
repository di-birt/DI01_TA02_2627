# DI01 – TA01 – Componentes Base, Navegación y Binding

**Módulo:** Desarrollo de Interfaces | **Curso:** 25/26  
**Alumno/a:** _(escribe tu nombre aquí)_  
**Fecha de entrega:** _(escribe la fecha aquí)_

---

## Descripción de la tarea

En esta tarea crearás una pequeña aplicación Ionic que aplique los conceptos de
los apartados **1, 2 y 3** de la teoría:

| Apartado | Tema                          | Puntos |
|----------|-------------------------------|--------|
| 1        | Componentes Base en el HTML   | 40 pts |
| 2        | Navegación                    | 30 pts |
| 3        | Angular Binding               | 30 pts |

> 📄 Consulta la teoría en `src/assets/pdf/Componentes de Ionic y Angular _ BIRTLH.pdf`

---

## Contexto de la aplicación

Desarrollarás una **app de gestión de una lista de elementos**.  
Puedes elegir el dominio libremente: películas, recetas, libros, países, juegos, etc.

La app tendrá **dos páginas**:
- `HomePage` (`/home`) – Lista principal con campo de búsqueda y botón de acción.
- `DetallePage` (`/detalle`) – Detalle del elemento seleccionado.

---

## Requisitos

### Apartado 1 – Componentes Base en el HTML _(40 pts)_

#### Página Principal `home.page.html`
- [ ] `<ion-header>` con `<ion-toolbar>` e `<ion-title>` (nombre de tu app)
- [ ] `<ion-content>` como contenedor principal del contenido
- [ ] Lista con **al menos 5 elementos** usando `<ion-list>`, `<ion-item>` e `<ion-label>`
  - Cada ítem debe mostrar al menos el **nombre** y una **descripción corta**
  - Al pulsar un ítem se navega a la página de detalle _(ver Apartado 2)_
- [ ] Un `<ion-button>` que al pulsarlo muestre un `ion-toast` con un mensaje
- [ ] `<ion-footer>` con `<ion-toolbar>` e `<ion-title>` con texto informativo

#### Página de Detalle `detalle.page.html`
- [ ] `<ion-header>` con `<ion-toolbar>` e `<ion-title>` (nombre del elemento)
- [ ] `<ion-content>` que muestre los datos del elemento seleccionado
- [ ] Usar `<ion-list>`, `<ion-item>` e `<ion-label>` para presentar los campos

---

### Apartado 2 – Navegación _(30 pts)_

- [ ] Las rutas están correctamente definidas en `app.routes.ts`
  - `/home` → `HomePage`
  - `/detalle` → `DetallePage`
- [ ] Al pulsar un ítem de la lista, **navegar a `/detalle`** pasando los datos del elemento
  - Usa `this.router.navigate(['/detalle'], { state: { elemento } })`
- [ ] La página de detalle incluye `<ion-back-button defaultHref="/home">` dentro de `<ion-buttons>`
- [ ] Al volver desde el detalle, se regresa correctamente a la lista

---

### Apartado 3 – Angular Binding _(30 pts)_

Implementa los **4 tipos de binding** de Angular:

| Tipo                       | Dónde aplicarlo                                                    |
|----------------------------|--------------------------------------------------------------------|
| **Interpolación `{{ }}`**  | Mostrar el nombre del elemento en el título o cuerpo del detalle   |
| **Property Binding `[ ]`** | `[disabled]` en el botón cuando no haya elementos en la lista      |
| **Event Binding `( )`**    | `(click)` en el botón para llamar a `mostrarToast()`               |
| **Two-way Binding `[()]`** | `[(ngModel)]="busqueda"` en el campo para filtrar la lista en tiempo real |

---

## Estructura del proyecto

```
src/app/
├── models/
│   └── elemento.model.ts        ← Interfaz compartida (puedes ampliarla)
├── home/
│   ├── home.page.ts             ← Lógica de la página principal
│   └── home.page.html           ← Plantilla de la página principal
├── detalle/
│   ├── detalle.page.ts          ← Lógica de la página de detalle
│   └── detalle.page.html        ← Plantilla de la página de detalle
└── app.routes.ts                ← Definición de rutas
```

---

## Cómo ejecutar el proyecto

```bash
npm install
ionic serve
```

---

## Criterios de evaluación

| Criterio                                           | Puntos |
|----------------------------------------------------|--------|
| Estructura HTML con componentes Ionic correctos    | 20 pts |
| Datos estáticos (≥ 5 elementos) y lista visible    | 20 pts |
| Navegación funcional (home ↔ detalle)              | 30 pts |
| Los 4 tipos de binding implementados y funcionales | 30 pts |
| **Total**                                          | **100 pts** |

---

## Recursos

- 📄 Teoría: `src/assets/pdf/Componentes de Ionic y Angular _ BIRTLH.pdf`
- 🔗 Documentación Ionic: https://ionicframework.com/docs/
- 🔗 Documentación Angular: https://angular.dev/
