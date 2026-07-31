---
description: Ouderdomsanalyse openstaande posten uit AFAS Profit
argument-hint: "[peildatum]"
allowed-tools: ["mcp__plugin_afas-ai-connect_afas__get_started", "mcp__plugin_afas-ai-connect_afas__read_operation", "mcp__plugin_afas-ai-connect_afas__search_endpoints"]
---
Roep eerst `get_started` aan. Maak een ouderdomsanalyse van de openstaande
debiteuren: haal de openstaande posten op via `read_operation` (zoek de juiste
GetConnector met `search_endpoints`), groepeer de bedragen naar ouderdomsbucket
(0-30, 31-60, 61-90 en 90+ dagen) en toon per bucket het totaal.
Optioneel argument (peildatum): $ARGUMENTS
