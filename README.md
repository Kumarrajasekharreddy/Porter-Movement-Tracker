# 🚶‍♂️ Porter Movement Dashboard

A real-time analytics dashboard to visualize porter movements across hospital departments using timeline, heatmap, and Sankey diagram.

---

## 🧹 What Was Processed?

- **Input**: Excel file (`nfdk.xlsx.xls`) with columns:  
  `PORTER`, `START TIME`, `END TIME`, `FROM`, `TO`, `FROM_LAT`, `FROM_LON`, `TO_LAT`, `TO_LON`
- **Cleaning**:
  - Converted `START TIME` & `END TIME` to datetime using `pd.to_datetime(..., errors='coerce')`
  - Filtered porters by name (case-insensitive)
  - Applied dynamic date-range filtering
- **Output**: Interactive views showing movement paths, duration, and frequency

---

## 🛠️ What Was Used?

| Category       | Tools & Libraries |
|----------------|-------------------|
| **Core**       | Python, Pandas    |
| **Dashboard**  | Dash, Plotly      |
| **Visuals**    | Gantt Timeline, Heatmap, Sankey Diagram, Scatter Mapbox |
| **UI**         | `dcc.Input`, `dcc.DatePickerRange`, `dash_table.DataTable` |
| **Map**        | OpenStreetMap (no API key needed) |

---

## 💡 Key Code Snippets (Just the Magic)

### Dynamic Filtering
```python
porter_df = df[df['PORTER'].str.contains(porter_name, case=False, na=False)]
porter_df = porter_df[(porter_df['START TIME'] >= start_date) & (porter_df['END TIME'] <= end_date)]
