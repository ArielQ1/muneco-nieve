# Documentación CSS Position - Muñeco de Nieve ⛄

## Información Académica
- **Materia:** Programación Web II
- **Docente:** Ph.D Marisol Téllez Ramírez
- **Auxiliar:** Univ. Ariel Quizaya Callisaya

---

## 📋 Descripción del Proyecto

Este proyecto implementa un muñeco de nieve usando únicamente HTML y CSS, con especial énfasis en el uso de la propiedad `position` para posicionar elementos de manera precisa. Es un ejemplo práctico de cómo los diferentes valores de positioning en CSS pueden crear diseños complejos.

---

## 🎯 La Propiedad CSS Position

La propiedad `position` en CSS controla cómo se posiciona un elemento en el documento. Es fundamental para crear layouts complejos y posicionar elementos de manera precisa.

### Valores de Position

#### 1. `static` (Por defecto)
- **Descripción:** Posicionamiento normal del flujo del documento
- **Características:** No se ve afectado por `top`, `right`, `bottom`, `left`
- **Uso:** Comportamiento estándar de elementos

```css
.elemento {
    position: static; /* Valor por defecto */
}
```

#### 2. `relative`
- **Descripción:** Se posiciona relativo a su posición original
- **Características:** Mantiene su espacio en el flujo del documento
- **Propiedades:** Acepta `top`, `right`, `bottom`, `left`

```css
.contenedor {
    position: relative; /* Crea un contexto de posicionamiento */
}
```

**Ejemplo en el proyecto:**
```css
.cuerpo {
    position: relative; /* Los elementos hijos absolute se posicionan respecto a este */
    background: #fff;
    border-radius: 50%;
}
```

#### 3. `absolute`
- **Descripción:** Se posiciona relativo al ancestro posicionado más cercano
- **Características:** Se saca del flujo normal del documento
- **Propiedades:** Usa `top`, `right`, `bottom`, `left` para posicionamiento exacto

**Ejemplos en el proyecto:**
```css
.brazos {
    position: absolute; /* Se posiciona respecto al .cuerpo (relative) */
    top: 60px;
    /* right: -16px; o left: -17px; según el brazo */
}

.ojos {
    position: absolute;
    top: 30px;
    /* left: 25px; o right: 25px; según el ojo */
}

.boca {
    position: absolute;
    top: 60px;
    left: 25px;
}
```

#### 4. `fixed`
- **Descripción:** Se posiciona relativo a la ventana del navegador
- **Características:** Se mantiene fijo al hacer scroll
- **Uso:** Barras de navegación, botones flotantes

```css
.navbar-fixed {
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
}
```

#### 5. `sticky`
- **Descripción:** Híbrido entre relative y fixed
- **Características:** Se comporta como relative hasta llegar a un punto, luego como fixed
- **Uso:** Headers que se "pegan" al hacer scroll

```css
.header-sticky {
    position: sticky;
    top: 0;
}
```

---

## 🔧 Implementación en el Muñeco de Nieve

### Estructura de Posicionamiento

1. **Contenedor Principal** (`.contenedor`)
   - Usa posicionamiento normal (static)
   - Centrado con `margin: auto`

2. **Partes del Cuerpo** (`.cuerpo`)
   - `position: relative` - Crea contexto para elementos hijos
   - Permite que ojos, boca y brazos se posicionen respecto a cada parte

3. **Elementos Detallados** (`.ojos`, `.boca`, `.brazos`)
   - `position: absolute` - Posicionamiento exacto
   - Coordenadas específicas con `top`, `left`, `right`

### Ejemplos Específicos del Código

#### Posicionamiento de Ojos
```css
.ojos {
    position: absolute; /* Se saca del flujo normal */
    top: 30px;         /* 30px desde arriba del contenedor padre */
}

.izquierdo {
    left: 25px;        /* 25px desde la izquierda */
}

.derecho {
    right: 25px;       /* 25px desde la derecha */
}
```

#### Posicionamiento de Brazos
```css
.brazos {
    position: absolute;
    top: 60px;         /* Altura específica en el cuerpo */
}

.centro > .derecho {
    right: -16px;      /* Sobresale del contenedor hacia la derecha */
    rotate: -20deg;    /* Rotación para efecto natural */
}

.centro > .izquierdo {
    left: -17px;       /* Sobresale del contenedor hacia la izquierda */
    rotate: 20deg;     /* Rotación opuesta */
}
```

---

## 📊 Ventajas y Consideraciones

### Ventajas de Position Absolute
- ✅ Control exacto de la posición
- ✅ Permite superposición de elementos
- ✅ Ideal para detalles precisos como ojos, botones
- ✅ No afecta la posición de otros elementos

### Consideraciones
- ⚠️ Los elementos absolute se sacan del flujo normal
- ⚠️ Puede crear problemas de responsive design
- ⚠️ Requiere un contenedor con position relative/absolute/fixed

---

## 🚀 Cómo Ejecutar el Proyecto

1. Clona o descarga el repositorio
2. Abre `index.html` en tu navegador
3. Observa cómo los elementos se posicionan usando CSS

## 📁 Estructura de Archivos

```
muneco-nieve/
├── index.html      # Estructura HTML del muñeco
├── style.css       # Estilos y posicionamiento CSS
└── README.md       # Esta documentación
```

---

## 🎨 Conceptos CSS Aplicados

- **Position (relative, absolute)**
- **Border-radius** (formas circulares)
- **Transform (rotate)** (rotación de brazos)
- **Flexbox/Centering** (centrado de elementos)
- **CSS Custom Properties** (variables CSS)

---

## 📚 Recursos Adicionales

- [MDN - CSS Position](https://developer.mozilla.org/es/docs/Web/CSS/position)
- [CSS Tricks - Position](https://css-tricks.com/almanac/properties/p/position/)
- [W3Schools - CSS Position](https://www.w3schools.com/css/css_positioning.asp)

---

*Proyecto desarrollado para la materia Programación Web II*