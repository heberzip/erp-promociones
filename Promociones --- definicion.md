Promocion E/R
---
```ts
PROMOCION (contenedores de CODIGO) {
    string id
    string nombre
    string descripcion
    enum TIPO_PROMO ("genérica", "específica")
    enum TIPO_FRECUENCIA ("uso único", "multi-uso")
    enum TIPO_APLICACION_FECHA ("por compra", "por traslado")
    date fecha_inicio
    date fecha_fin
    boolean sin_limite
    float importe (si específica)
    boolean activa
  }
```

```ts
CODIGO (dentro de PROMOCIONES) {
    string id
    string codigo
    float monto (si genérica)
    date fecha_creacion
    date fecha_validez
    date? fecha_uso
    string? cliente
    string? reserva
    float? total_pagado
    boolean activo (solo multi-uso)
  }
```

```ts
RAZON (tabla maestra) {
    string id
    string descripcion
  }
```

```ts
AREA_OPERACION (en las que aplican las promo) {
    string id
    string nombre
  }
```

```mermaid
erDiagram
  PROMOCION ||--o{ CODIGO : contiene
  PROMOCION }|--|| RAZON : tiene
  PROMOCION }|--o{ AREA_OPERACION : aplica_en
  CODIGO }|--o{ AREA_OPERACION : aplica_en

  PROMOCION {
    string id
    string nombre
    string descripcion
    enum TIPO_PROMO ("genérica" o "específica")
    enum TIPO_FRECUENCIA ("uso único" o "multi-uso")
    string tipo_aplicacion_fecha
    date fecha_inicio
    date fecha_fin
    boolean sin_limite
    float importe (si específica)
    boolean activa
  }

  CODIGO {
    string id
    string codigo
    float monto (si genérica)
    date fecha_creacion
    date fecha_validez
    date? fecha_uso
    string? cliente
    string? reserva
    float? total_pagado
    boolean activo (solo multi-uso)
  }

  RAZON {
    string id
    string descripcion
  }

  AREA_OPERACION {
    string id
    string nombre
  }
```
