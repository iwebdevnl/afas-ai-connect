---
description: Omzet per klant per maand uit AFAS Profit
argument-hint: "[jaar]"
allowed-tools: ["mcp__plugin_afas-ai-connect_afas__get_started", "mcp__plugin_afas-ai-connect_afas__read_operation", "mcp__plugin_afas-ai-connect_afas__analyze_data", "mcp__plugin_afas-ai-connect_afas__list_available_tables"]
---
Roep eerst `get_started` aan. Bepaal de omzet per klant per maand. Gebruik bij
grote datasets of aggregaties `analyze_data` op de gesynchroniseerde
`profit_*`-tabellen (Analytics-plan of trial); `list_available_tables` toont wat
beschikbaar is. Is dat niet beschikbaar, val dan terug op `read_operation` op de
GetConnector en pagineer. Bevat de omgeving meerdere administraties, groepeer dan
op de administratie (kolom `unit` of `unit_id`). Toon de top-resultaten als
tabel. Optioneel argument (jaar): $ARGUMENTS
