
# 🧾 Transformaciones realizadas / Applied Transformations

## 1. Reordenación de columnas / Column reordering
**ES:** Se ha colocado la columna `Resuelto` entre `Actualizado` y `Cerrado` para reflejar la lógica temporal de una incidencia.  
**EN:** The `Resuelto` column was placed between `Actualizado` and `Cerrado` to follow the chronological order of incident resolution.

---

## 2. Homogeneización de categorías / Category homogenization
**ES:** Se ha sustituido "Diferida" por "Diferido" para evitar duplicidad en Power BI.  
**EN:** Replaced "Diferida" with "Diferido" to prevent duplicated values in Power BI reports.

---

## 3. Limpieza de `Actualizado` / Cleaning the `Actualizado` column
- Se calculó longitud de caracteres por fila.  
- Se filtraron valores con al menos 10 caracteres (`DD/MM/AAAA`).  
- Se extrajo el valor entre “/” para identificar el mes.  
- Se generó `Actualizado definitivo`, conservando valores válidos.

**EN:**  
- Character length was calculated per row.  
- Filtered values with 10+ characters to ensure correct format.  
- Extracted month from between slashes.  
- Created `Actualizado definitivo` only if the month was ≤ 12.

---

## 4. Limpieza de `Abierto` / Cleaning the `Abierto` column
Misma lógica que `Actualizado`. Se crea `Abierto definitivo` con validación de mes.  
**EN:** Same logic applied as with `Actualizado`, resulting in `Abierto definitivo`.

---

## 5. Limpieza de `Cerrado` / Cleaning the `Cerrado` column
Validación por longitud, extracción del mes, creación de `Cerrado definitivo`.  
Columnas auxiliares eliminadas.  
**EN:** Length check, month extraction, and generation of `Cerrado definitivo`.  
Auxiliary columns were removed for clarity.

---

## 6. Limpieza de `Resuelto` con nulos justificados / Handling `Resuelto` with justified nulls
**ES:** Se verificó que los nulos correspondían a estados como “Cancelado”. Se validaron y conservaron.  
**EN:** Confirmed that nulls were justified (e.g. “Cancelled” cases), and retained them.  
Se generó `Resuelto definitivo` con la misma lógica de mes válida.

---

## 7. Generación de mes alternativo / Alternative month column
**ES:** Se detectó que `Mes` tenía valores como "No aplica". Se creó una nueva columna `Mes desde Cerrado definitivo`, fiable y basada en fechas válidas.  
**EN:** Detected non-standard values in original `Mes`. Created new column based on valid dates: `Mes desde Cerrado definitivo`.

---

## 8. Revisión de `Horas Real` / Review of `Horas Real`
**ES:** Se detectó que el 89% de los valores eran nulos. No se imputaron, por considerarse opcionales.  
**EN:** 89% nulls found; field seems optional. Left unchanged as expected behavior.
