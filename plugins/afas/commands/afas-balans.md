---
description: Balans / grootboeksaldi uit AFAS Profit
argument-hint: "[periode]"
allowed-tools: ["mcp__plugin_afas-ai-connect_afas__get_started", "mcp__plugin_afas-ai-connect_afas__read_operation", "mcp__plugin_afas-ai-connect_afas__search_endpoints", "mcp__plugin_afas-ai-connect_afas__get_entity_schema"]
---
Roep eerst `get_started` aan. Vraag de balans (grootboeksaldi) op via
`read_operation` en toon per grootboekrekening het saldo, gegroepeerd naar
balanspost. Welke GetConnectors beschikbaar zijn verschilt per AFAS-omgeving:
gebruik `search_endpoints` en `get_entity_schema` om de juiste connector en
veldnamen te vinden. Bevat de omgeving meerdere administraties, groepeer of
filter dan op de administratie (het Unit-veld) en tel saldi van verschillende
administraties nooit blind bij elkaar op.
Optioneel argument (periode): $ARGUMENTS
