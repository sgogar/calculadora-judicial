# Calculadora de Plazos Judiciales · Argentina

Calculadora de días hábiles judiciales por jurisdicción, con ferias y feriados nacionales y locales.

---

## Cómo actualizar las fechas de feria cada año

Solo hay que editar `ferias.json`. No hay que tocar el HTML.

### Estructura de cada entrada

```json
"PBA": {
  "nombre": "Provincia de Buenos Aires (SCBA)",
  "2025": {
    "verano":   { "desde": "2025-01-02", "hasta": "2025-01-31" },
    "invierno": { "desde": "2025-07-21", "hasta": "2025-08-01" },
    "extras": [
      { "fecha": "2025-12-24", "descripcion": "Asueto Res. 1565 SCBA" }
    ],
    "fuente": "Acuerdo SCBA 4183/2025"
  },
  "2026": {
    ...
  }
}
```

### Para agregar el año 2027 en una jurisdicción

1. Abrir `ferias.json`
2. Buscar la jurisdicción (ej. `"PBA"`)
3. Copiar el bloque de 2026 y pegarlo como 2027, actualizando fechas y fuente
4. Guardar y subir a GitHub (el sitio se actualiza solo en segundos)

### Cómo editar en GitHub sin bajar los archivos

1. En el repo, click en `ferias.json`
2. Click en el ícono del lápiz (✏️ Edit this file)
3. Hacer los cambios
4. Click en **Commit changes**

Listo. El sitio se actualiza automáticamente.

---

## Fuentes oficiales para verificar ferias

| Jurisdicción | URL |
|---|---|
| CABA Nac./Fed. | https://www.csjn.gov.ar |
| CABA local | https://www.tsjbaires.gov.ar |
| Prov. Buenos Aires | https://www.scba.gov.ar/actualidad.asp |
| Córdoba | https://www.justiciacordoba.gob.ar |
| Santa Fe | https://www.justiciasantafe.gov.ar |
| Mendoza | https://jusmendoza.gob.ar |
| Neuquén | https://www.jusneuquen.gov.ar |
| Tucumán | https://www.justucuman.gov.ar |
| Salta | https://www.justiciasalta.gov.ar |
| Río Negro | https://www.jusrionegro.gov.ar |
| Entre Ríos | https://www.jusentrerios.gov.ar |

Las ferias de invierno suelen publicarse en **mayo/junio** de cada año.  
Las ferias de verano suelen publicarse en **noviembre/diciembre** del año anterior.

---

## Notas importantes

- **Feriados nacionales** se calculan automáticamente (Pascua, Carnaval, fijos): no hay que cargarlos en el JSON.
- **Feriados locales** (fundación de municipio, patrono de localidad, etc.) los declara cada Cámara o la Corte provincial por resolución. Se agregan al array `extras`.
- **Mendoza** fija la feria de invierno como "10 días hábiles" desde una fecha, no como rango fijo. Calcular y convertir a rango de fechas al actualizar.
- Este cálculo es **orientativo**. Siempre verificar con el calendario oficial de cada jurisdicción antes de tomar decisiones procesales.
