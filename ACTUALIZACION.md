# Actualización de los archivos de inversión en oro

## Cambios realizados:

### 1. gold-chart.html
- **Nuevo índice agregado**: SMIC (SMI con dividendos) en verde (#10b981)
- **Datos históricos**: SMIC desde 2000-2025 con valores que reflejan rendimiento con dividendos
- **Cálculo de impuestos (Suiza)**:
  - Oro: 0% de impuesto de ganancias de capital
  - Acciones (SMIC, S&P 500, DAX): ~12% en promedio sobre ingresos por dividendos
- **Nuevos controles de gráfico**:
  - "Nach Steuern (€)" - Valores después de impuestos
  - "Brutto-Werte (€)" - Valores antes de impuestos
  - "Nach Steuern (%)" - Cambio porcentual después de impuestos
  - "Brutto (%)" - Cambio porcentual antes de impuestos
- **Cálculo de rendimiento annualizado**:
  - Fórmula: (Valor Final / Valor Inicial)^(1/25) - 1
  - Aplicado después del cálculo de impuestos

**Resultados clave (después de impuestos, 25 años):**
- Gold: 7.42% p.a.
- SMIC: 5.41% p.a.
- S&P 500 TR: 4.87% p.a.
- DAX: 2.26% p.a.

### 2. gold-slideshow.html
- **Slide 3**: Actualizado con SMIC en la comparación gráfica
- **Slide 4**: Completamente rediseñado con:
  - Gráfico interactivo que incluye SMIC
  - Controles para mostrar valores antes/después de impuestos
  - Leyenda actualizada con valores después de impuestos
- **Slide 5**: Tabla de comparación detallada actualizada con:
  - Valores finales de cada índice
  - Rendimiento annualizado
  - Rendimiento annualizado después de impuestos suizo

### 3. CLAUDE.md
- Actualizado para documentar:
  - Los cuatro índices en comparación (Gold, SMIC, S&P 500 TR, DAX)
  - Metodología de cálculo de impuestos suizo
  - Nuevas funciones interactivas del gráfico

## Características técnicas:

### Función de cálculo de impuestos:
```javascript
function calculateAfterTax(values, taxRate) {
    return values.map((value, index) => {
        if (index === 0) return value;
        const gain = value - 10000;
        const tax = gain > 0 ? gain * taxRate : 0;
        return value - tax;
    });
}
```

### Datos SMIC (SMI mit Dividende):
- Representa el índice SMI con reinversión de dividendos
- Refleja mejor la rentabilidad total para inversores suizos
- Más conservador que el S&P 500 pero mejor que el DAX

## Contexto de impuestos suizos:
- No existe impuesto federal sobre ganancias de capital en Suiza
- Oro: Sin impuestos sobre ganancias (sin impuesto de patrimonio federal)
- Dividendos: ~10-15% depende del cantón (promedio 12% utilizado)

