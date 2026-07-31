---
description: Toon de openstaande debiteuren uit AFAS Profit
argument-hint: "[administratie]"
allowed-tools: ["mcp__plugin_afas-ai-connect_afas__get_started", "mcp__plugin_afas-ai-connect_afas__read_operation", "mcp__plugin_afas-ai-connect_afas__search_endpoints", "mcp__plugin_afas-ai-connect_afas__select_administration"]
---
Roep eerst `get_started` aan om te authenticeren en de omgeving te kiezen.
Haal de openstaande debiteuren (openstaande posten) op via `read_operation`.
Welke GetConnector daarvoor bestaat verschilt per omgeving: zoek hem met
`search_endpoints`. Vat samen als tabel: klant, factuurnummer, bedrag,
vervaldatum, dagen open. Optioneel argument (administratie): $ARGUMENTS
