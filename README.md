# AI Scripts and Utilities for Perfect Tower II
This is my collection of AI scripts. I focus on low-RAM scripts (i.e. 14 actions or less), so that they'll be usable by everyone who has unlocked the AI.

All of these also work under `turbo exec` (https://github.com/Xenos6666/TPT2_scripts/tree/modular_V2/common/execution_stack), although with some quirks - for instance, the autominer will cause noticable lag on entering the mine, and mine everything before you can see it happen!

## Auto mining script
This pair of scripts mines across all tabs, at 16x speed (i.e. all squares simultaneously). It takes ~3 seconds to mine 10 layers * 12 tabs at the default 120 FPS (with vsync disabled). The max actions required is __7__, which should be accessible to everyone.

```
DiggerMaster 1 0 7
DiggerHead 0 0 6

Drag-select both lines to copy everything at once, or triple-click to copy and import an individual script.

DERpZ2dlck1hc3RlcgEAAAAJb3Blbi5taW5lAAAAAAcAAAAOZ2xvYmFsLmludC5zZXQIY29uc3RhbnQECGRyaWxscG9zCGNvbnN0YW50AgAAAAAPZ2VuZXJpYy5leGVjdXRlCGNvbnN0YW50BApEaWdnZXJIZWFkEWdlbmVyaWMud2FpdHVudGlsDmNvbXBhcmlzb24uaW50Dmdsb2JhbC5pbnQuZ2V0CGNvbnN0YW50BAhkcmlsbHBvcwhjb25zdGFudAQCPT0IY29uc3RhbnQCEQAAAA1sb2NhbC5pbnQuc2V0CGNvbnN0YW50BAN0YWIOYXJpdGhtZXRpYy5pbnQNbG9jYWwuaW50LmdldAhjb25zdGFudAQDdGFiCGNvbnN0YW50BAErCGNvbnN0YW50AgEAAAAIbWluZS50YWINbG9jYWwuaW50LmdldAhjb25zdGFudAQDdGFiDW1pbmUubmV3bGF5ZXIMZ2VuZXJpYy5nb3RvC3Rlcm5hcnkuaW50Dm1pbmUuaGFzTGF5ZXJzCGNvbnN0YW50AgYAAAALdGVybmFyeS5pbnQOY29tcGFyaXNvbi5pbnQNbG9jYWwuaW50LmdldAhjb25zdGFudAQDdGFiCGNvbnN0YW50BAE8CGNvbnN0YW50Ag0AAAAIY29uc3RhbnQCBAAAAAhjb25zdGFudAJjAAAA
;CkRpZ2dlckhlYWQAAAAAAAAAAAYAAAAOZ2xvYmFsLmludC5zZXQIY29uc3RhbnQECGRyaWxscG9zDmFyaXRobWV0aWMuaW50Dmdsb2JhbC5pbnQuZ2V0CGNvbnN0YW50BAhkcmlsbHBvcwhjb25zdGFudAQBKwhjb25zdGFudAIBAAAAD2dlbmVyaWMuZXhlY3V0ZQ50ZXJuYXJ5LnN0cmluZw5jb21wYXJpc29uLmludA5nbG9iYWwuaW50LmdldAhjb25zdGFudAQIZHJpbGxwb3MIY29uc3RhbnQEATwIY29uc3RhbnQCEQAAAAhjb25zdGFudAQKRGlnZ2VySGVhZAhjb25zdGFudAQADWxvY2FsLmludC5zZXQIY29uc3RhbnQEA3Bvcw5hcml0aG1ldGljLmludA5nbG9iYWwuaW50LmdldAhjb25zdGFudAQIZHJpbGxwb3MIY29uc3RhbnQEAS0IY29uc3RhbnQCAgAAAAhtaW5lLmRpZw5hcml0aG1ldGljLmludA1sb2NhbC5pbnQuZ2V0CGNvbnN0YW50BANwb3MIY29uc3RhbnQEA21vZAhjb25zdGFudAIEAAAADmFyaXRobWV0aWMuaW50DWxvY2FsLmludC5nZXQIY29uc3RhbnQEA3Bvcwhjb25zdGFudAQBLwhjb25zdGFudAIEAAAADmdlbmVyaWMuZ290b2lmCGNvbnN0YW50AgQAAAASdG93bi53aW5kb3cuaXNvcGVuCGNvbnN0YW50BARtaW5lDGdsb2JhbC51bnNldAhjb25zdGFudAQIZHJpbGxwb3M=

```

## Factory management scripts
The first one is a <s>simple</s> ore crushing/dust up-tiering combo. This works stand-alone, but pairs nicely with other factory automation that expects dust to be available. At __10__ actions, this should also work for everyone. It tries to crush any un-crushed ores, and up-tiers dust while trying to make the dust distribution match its built-in target ratios.
```
D0S.DustManager 1 0 10

D0QwUy5EdXN0TWFuYWdlcgEAAAAMb3Blbi5mYWN0b3J5AAAAAAoAAAAQbG9jYWwuc3RyaW5nLnNldAhjb25zdGFudAQQZHVzdF9tdWx0aXBsaWVycwhjb25zdGFudAQVMSAxIC42MjUgLjUgLjEgLjEgLjA1EGxvY2FsLmRvdWJsZS5zZXQOdGVybmFyeS5zdHJpbmcPY29tcGFyaXNvbi5ib29sDmNvbXBhcmlzb24uaW50DmFyaXRobWV0aWMuaW50DWxvY2FsLmludC5nZXQIY29uc3RhbnQEAWkIY29uc3RhbnQEA21vZAhjb25zdGFudALoAwAACGNvbnN0YW50BAI+PQ1zdHJpbmcubGVuZ3RoEGxvY2FsLnN0cmluZy5nZXQIY29uc3RhbnQEEGR1c3RfbXVsdGlwbGllcnMIY29uc3RhbnQEAXwRY29tcGFyaXNvbi5zdHJpbmcJc3Vic3RyaW5nEGxvY2FsLnN0cmluZy5nZXQIY29uc3RhbnQEEGR1c3RfbXVsdGlwbGllcnMOYXJpdGhtZXRpYy5pbnQNbG9jYWwuaW50LmdldAhjb25zdGFudAQBaQhjb25zdGFudAQDbW9kCGNvbnN0YW50AugDAAAIY29uc3RhbnQCAQAAAAhjb25zdGFudAQCPT0IY29uc3RhbnQEASAGY29uY2F0CGNvbnN0YW50BAZidWZmZXIDaTJzDmFyaXRobWV0aWMuaW50DmFyaXRobWV0aWMuaW50DmFyaXRobWV0aWMuaW50DWxvY2FsLmludC5nZXQIY29uc3RhbnQEAWkIY29uc3RhbnQEAS8IY29uc3RhbnQC6AMAAAhjb25zdGFudAQDbW9kCGNvbnN0YW50AmQAAAAIY29uc3RhbnQEASsIY29uc3RhbnQCAQAAAAhjb25zdGFudAQDYWNjDnRlcm5hcnkuZG91YmxlD2NvbXBhcmlzb24uYm9vbA5jb21wYXJpc29uLmludA5hcml0aG1ldGljLmludA1sb2NhbC5pbnQuZ2V0CGNvbnN0YW50BAFpCGNvbnN0YW50BANtb2QIY29uc3RhbnQC6AMAAAhjb25zdGFudAQCPj0Nc3RyaW5nLmxlbmd0aBBsb2NhbC5zdHJpbmcuZ2V0CGNvbnN0YW50BBBkdXN0X211bHRpcGxpZXJzCGNvbnN0YW50BAF8EWNvbXBhcmlzb24uc3RyaW5nCXN1YnN0cmluZxBsb2NhbC5zdHJpbmcuZ2V0CGNvbnN0YW50BBBkdXN0X211bHRpcGxpZXJzDmFyaXRobWV0aWMuaW50DWxvY2FsLmludC5nZXQIY29uc3RhbnQEAWkIY29uc3RhbnQEA21vZAhjb25zdGFudALoAwAACGNvbnN0YW50AgEAAAAIY29uc3RhbnQEAj09CGNvbnN0YW50BAEgEGxvY2FsLmRvdWJsZS5nZXQIY29uc3RhbnQEA2FjYxFhcml0aG1ldGljLmRvdWJsZRFhcml0aG1ldGljLmRvdWJsZRFhcml0aG1ldGljLmRvdWJsZRBsb2NhbC5kb3VibGUuZ2V0CGNvbnN0YW50BANhY2MIY29uc3RhbnQEASoOdGVybmFyeS5kb3VibGUPY29tcGFyaXNvbi5ib29sEWNvbXBhcmlzb24uc3RyaW5nCXN1YnN0cmluZxBsb2NhbC5zdHJpbmcuZ2V0CGNvbnN0YW50BBBkdXN0X211bHRpcGxpZXJzDmFyaXRobWV0aWMuaW50DmFyaXRobWV0aWMuaW50DWxvY2FsLmludC5nZXQIY29uc3RhbnQEAWkIY29uc3RhbnQEA21vZAhjb25zdGFudALoAwAACGNvbnN0YW50BAEtCGNvbnN0YW50AgEAAAAIY29uc3RhbnQCAQAAAAhjb25zdGFudAQCPT0IY29uc3RhbnQEASAIY29uc3RhbnQEAXwOY29tcGFyaXNvbi5pbnQOYXJpdGhtZXRpYy5pbnQNbG9jYWwuaW50LmdldAhjb25zdGFudAQBaQhjb25zdGFudAQDbW9kCGNvbnN0YW50AugDAAAIY29uc3RhbnQEAj09CGNvbnN0YW50AgAAAAAIY29uc3RhbnQDAAAAAAAAAAAOdGVybmFyeS5kb3VibGURY29tcGFyaXNvbi5zdHJpbmcJc3Vic3RyaW5nEGxvY2FsLnN0cmluZy5nZXQIY29uc3RhbnQEEGR1c3RfbXVsdGlwbGllcnMOYXJpdGhtZXRpYy5pbnQNbG9jYWwuaW50LmdldAhjb25zdGFudAQBaQhjb25zdGFudAQDbW9kCGNvbnN0YW50AugDAAAIY29uc3RhbnQCAQAAAAhjb25zdGFudAQCPT0IY29uc3RhbnQEAS4IY29uc3RhbnQDAAAAAAAA8D8IY29uc3RhbnQDAAAAAAAAJEAIY29uc3RhbnQEASsOdGVybmFyeS5kb3VibGURY29tcGFyaXNvbi5zdHJpbmcJc3Vic3RyaW5nEGxvY2FsLnN0cmluZy5nZXQIY29uc3RhbnQEEGR1c3RfbXVsdGlwbGllcnMOYXJpdGhtZXRpYy5pbnQNbG9jYWwuaW50LmdldAhjb25zdGFudAQBaQhjb25zdGFudAQDbW9kCGNvbnN0YW50AugDAAAIY29uc3RhbnQCAQAAAAhjb25zdGFudAQCPT0IY29uc3RhbnQEATEIY29uc3RhbnQDAAAAAAAA8D8OdGVybmFyeS5kb3VibGURY29tcGFyaXNvbi5zdHJpbmcJc3Vic3RyaW5nEGxvY2FsLnN0cmluZy5nZXQIY29uc3RhbnQEEGR1c3RfbXVsdGlwbGllcnMOYXJpdGhtZXRpYy5pbnQNbG9jYWwuaW50LmdldAhjb25zdGFudAQBaQhjb25zdGFudAQDbW9kCGNvbnN0YW50AugDAAAIY29uc3RhbnQCAQAAAAhjb25zdGFudAQCPT0IY29uc3RhbnQEATIIY29uc3RhbnQDAAAAAAAAAEAOdGVybmFyeS5kb3VibGURY29tcGFyaXNvbi5zdHJpbmcJc3Vic3RyaW5nEGxvY2FsLnN0cmluZy5nZXQIY29uc3RhbnQEEGR1c3RfbXVsdGlwbGllcnMOYXJpdGhtZXRpYy5pbnQNbG9jYWwuaW50LmdldAhjb25zdGFudAQBaQhjb25zdGFudAQDbW9kCGNvbnN0YW50AugDAAAIY29uc3RhbnQCAQAAAAhjb25zdGFudAQCPT0IY29uc3RhbnQEATMIY29uc3RhbnQDAAAAAAAACEAOdGVybmFyeS5kb3VibGURY29tcGFyaXNvbi5zdHJpbmcJc3Vic3RyaW5nEGxvY2FsLnN0cmluZy5nZXQIY29uc3RhbnQEEGR1c3RfbXVsdGlwbGllcnMOYXJpdGhtZXRpYy5pbnQNbG9jYWwuaW50LmdldAhjb25zdGFudAQBaQhjb25zdGFudAQDbW9kCGNvbnN0YW50AugDAAAIY29uc3RhbnQCAQAAAAhjb25zdGFudAQCPT0IY29uc3RhbnQEATQIY29uc3RhbnQDAAAAAAAAEEAOdGVybmFyeS5kb3VibGURY29tcGFyaXNvbi5zdHJpbmcJc3Vic3RyaW5nEGxvY2FsLnN0cmluZy5nZXQIY29uc3RhbnQEEGR1c3RfbXVsdGlwbGllcnMOYXJpdGhtZXRpYy5pbnQNbG9jYWwuaW50LmdldAhjb25zdGFudAQBaQhjb25zdGFudAQDbW9kCGNvbnN0YW50AugDAAAIY29uc3RhbnQCAQAAAAhjb25zdGFudAQCPT0IY29uc3RhbnQEATUIY29uc3RhbnQDAAAAAAAAFEAOdGVybmFyeS5kb3VibGURY29tcGFyaXNvbi5zdHJpbmcJc3Vic3RyaW5nEGxvY2FsLnN0cmluZy5nZXQIY29uc3RhbnQEEGR1c3RfbXVsdGlwbGllcnMOYXJpdGhtZXRpYy5pbnQNbG9jYWwuaW50LmdldAhjb25zdGFudAQBaQhjb25zdGFudAQDbW9kCGNvbnN0YW50AugDAAAIY29uc3RhbnQCAQAAAAhjb25zdGFudAQCPT0IY29uc3RhbnQEATYIY29uc3RhbnQDAAAAAAAAGEAOdGVybmFyeS5kb3VibGURY29tcGFyaXNvbi5zdHJpbmcJc3Vic3RyaW5nEGxvY2FsLnN0cmluZy5nZXQIY29uc3RhbnQEEGR1c3RfbXVsdGlwbGllcnMOYXJpdGhtZXRpYy5pbnQNbG9jYWwuaW50LmdldAhjb25zdGFudAQBaQhjb25zdGFudAQDbW9kCGNvbnN0YW50AugDAAAIY29uc3RhbnQCAQAAAAhjb25zdGFudAQCPT0IY29uc3RhbnQEATcIY29uc3RhbnQDAAAAAAAAHEAOdGVybmFyeS5kb3VibGURY29tcGFyaXNvbi5zdHJpbmcJc3Vic3RyaW5nEGxvY2FsLnN0cmluZy5nZXQIY29uc3RhbnQEEGR1c3RfbXVsdGlwbGllcnMOYXJpdGhtZXRpYy5pbnQNbG9jYWwuaW50LmdldAhjb25zdGFudAQBaQhjb25zdGFudAQDbW9kCGNvbnN0YW50AugDAAAIY29uc3RhbnQCAQAAAAhjb25zdGFudAQCPT0IY29uc3RhbnQEATgIY29uc3RhbnQDAAAAAAAAIEAOdGVybmFyeS5kb3VibGURY29tcGFyaXNvbi5zdHJpbmcJc3Vic3RyaW5nEGxvY2FsLnN0cmluZy5nZXQIY29uc3RhbnQEEGR1c3RfbXVsdGlwbGllcnMOYXJpdGhtZXRpYy5pbnQNbG9jYWwuaW50LmdldAhjb25zdGFudAQBaQhjb25zdGFudAQDbW9kCGNvbnN0YW50AugDAAAIY29uc3RhbnQCAQAAAAhjb25zdGFudAQCPT0IY29uc3RhbnQEATkIY29uc3RhbnQDAAAAAAAAIkAIY29uc3RhbnQDAAAAAAAAAAAIY29uc3RhbnQEASoOdGVybmFyeS5kb3VibGUPY29tcGFyaXNvbi5ib29sD2NvbXBhcmlzb24uYm9vbBFjb21wYXJpc29uLnN0cmluZwlzdWJzdHJpbmcQbG9jYWwuc3RyaW5nLmdldAhjb25zdGFudAQQZHVzdF9tdWx0aXBsaWVycw5hcml0aG1ldGljLmludA5hcml0aG1ldGljLmludA1sb2NhbC5pbnQuZ2V0CGNvbnN0YW50BAFpCGNvbnN0YW50BANtb2QIY29uc3RhbnQC6AMAAAhjb25zdGFudAQBKwhjb25zdGFudAIBAAAACGNvbnN0YW50AgEAAAAIY29uc3RhbnQEAiE9CGNvbnN0YW50BAEgCGNvbnN0YW50BAEmDmNvbXBhcmlzb24uaW50DmFyaXRobWV0aWMuaW50DmFyaXRobWV0aWMuaW50DWxvY2FsLmludC5nZXQIY29uc3RhbnQEAWkIY29uc3RhbnQEA21vZAhjb25zdGFudALoAwAACGNvbnN0YW50BAErCGNvbnN0YW50AgEAAAAIY29uc3RhbnQEAiE9DXN0cmluZy5sZW5ndGgQbG9jYWwuc3RyaW5nLmdldAhjb25zdGFudAQQZHVzdF9tdWx0aXBsaWVycwhjb25zdGFudAQBfA5jb21wYXJpc29uLmludA5hcml0aG1ldGljLmludA1sb2NhbC5pbnQuZ2V0CGNvbnN0YW50BAFpCGNvbnN0YW50BAEvCGNvbnN0YW50AqCGAQAIY29uc3RhbnQEAj09CGNvbnN0YW50AgAAAAAIY29uc3RhbnQDAAAAAAAA8D8RYXJpdGhtZXRpYy5kb3VibGUIY29uc3RhbnQDmpmZmZmZuT8IY29uc3RhbnQEA3BvdwNpMmQOYXJpdGhtZXRpYy5pbnQOYXJpdGhtZXRpYy5pbnQOYXJpdGhtZXRpYy5pbnQNbG9jYWwuaW50LmdldAhjb25zdGFudAQBaQhjb25zdGFudAQDbW9kCGNvbnN0YW50AugDAAAIY29uc3RhbnQEASsIY29uc3RhbnQCAQAAAAhjb25zdGFudAQBLQ5hcml0aG1ldGljLmludA1sb2NhbC5pbnQuZ2V0CGNvbnN0YW50BAFpCGNvbnN0YW50BAEvCGNvbnN0YW50AqCGAQANbG9jYWwuaW50LnNldAhjb25zdGFudAQBaQ5hcml0aG1ldGljLmludA5hcml0aG1ldGljLmludA5hcml0aG1ldGljLmludA5hcml0aG1ldGljLmludA1sb2NhbC5pbnQuZ2V0CGNvbnN0YW50BAFpCGNvbnN0YW50BANtb2QIY29uc3RhbnQC6AMAAAhjb25zdGFudAQBKwhjb25zdGFudAIBAAAACGNvbnN0YW50BAErDmFyaXRobWV0aWMuaW50DmFyaXRobWV0aWMuaW50DmFyaXRobWV0aWMuaW50DmFyaXRobWV0aWMuaW50DWxvY2FsLmludC5nZXQIY29uc3RhbnQEAWkIY29uc3RhbnQEAS8IY29uc3RhbnQC6AMAAAhjb25zdGFudAQDbW9kCGNvbnN0YW50AmQAAAAIY29uc3RhbnQEASsLdGVybmFyeS5pbnQPY29tcGFyaXNvbi5ib29sD2NvbXBhcmlzb24uYm9vbA5jb21wYXJpc29uLmludA5hcml0aG1ldGljLmludA1sb2NhbC5pbnQuZ2V0CGNvbnN0YW50BAFpCGNvbnN0YW50BANtb2QIY29uc3RhbnQC6AMAAAhjb25zdGFudAQCPj0Nc3RyaW5nLmxlbmd0aBBsb2NhbC5zdHJpbmcuZ2V0CGNvbnN0YW50BBBkdXN0X211bHRpcGxpZXJzCGNvbnN0YW50BAF8EWNvbXBhcmlzb24uc3RyaW5nCXN1YnN0cmluZxBsb2NhbC5zdHJpbmcuZ2V0CGNvbnN0YW50BBBkdXN0X211bHRpcGxpZXJzDmFyaXRobWV0aWMuaW50DWxvY2FsLmludC5nZXQIY29uc3RhbnQEAWkIY29uc3RhbnQEA21vZAhjb25zdGFudALoAwAACGNvbnN0YW50AgEAAAAIY29uc3RhbnQEAj09CGNvbnN0YW50BAEgCGNvbnN0YW50BAEmEWNvbXBhcmlzb24uc3RyaW5nCXN1YnN0cmluZxBsb2NhbC5zdHJpbmcuZ2V0CGNvbnN0YW50BBBkdXN0X211bHRpcGxpZXJzDmFyaXRobWV0aWMuaW50DmFyaXRobWV0aWMuaW50DWxvY2FsLmludC5nZXQIY29uc3RhbnQEAWkIY29uc3RhbnQEA21vZAhjb25zdGFudALoAwAACGNvbnN0YW50BAErCGNvbnN0YW50AgEAAAAIY29uc3RhbnQCAQAAAAhjb25zdGFudAQCIT0IY29uc3RhbnQEASAIY29uc3RhbnQCAQAAAAhjb25zdGFudAIAAAAACGNvbnN0YW50BAEqCGNvbnN0YW50AugDAAAIY29uc3RhbnQEASsOYXJpdGhtZXRpYy5pbnQLdGVybmFyeS5pbnQPY29tcGFyaXNvbi5ib29sDmNvbXBhcmlzb24uaW50DmFyaXRobWV0aWMuaW50DWxvY2FsLmludC5nZXQIY29uc3RhbnQEAWkIY29uc3RhbnQEA21vZAhjb25zdGFudALoAwAACGNvbnN0YW50BAI+PQ1zdHJpbmcubGVuZ3RoEGxvY2FsLnN0cmluZy5nZXQIY29uc3RhbnQEEGR1c3RfbXVsdGlwbGllcnMIY29uc3RhbnQEAXwRY29tcGFyaXNvbi5zdHJpbmcJc3Vic3RyaW5nEGxvY2FsLnN0cmluZy5nZXQIY29uc3RhbnQEEGR1c3RfbXVsdGlwbGllcnMOYXJpdGhtZXRpYy5pbnQNbG9jYWwuaW50LmdldAhjb25zdGFudAQBaQhjb25zdGFudAQDbW9kCGNvbnN0YW50AugDAAAIY29uc3RhbnQCAQAAAAhjb25zdGFudAQCPT0IY29uc3RhbnQEASAIY29uc3RhbnQCAAAAAAt0ZXJuYXJ5LmludBFjb21wYXJpc29uLnN0cmluZwlzdWJzdHJpbmcQbG9jYWwuc3RyaW5nLmdldAhjb25zdGFudAQQZHVzdF9tdWx0aXBsaWVycw5hcml0aG1ldGljLmludA1sb2NhbC5pbnQuZ2V0CGNvbnN0YW50BAFpCGNvbnN0YW50BANtb2QIY29uc3RhbnQC6AMAAAhjb25zdGFudAIBAAAACGNvbnN0YW50BAI9PQhjb25zdGFudAQBLg5hcml0aG1ldGljLmludA5hcml0aG1ldGljLmludA1sb2NhbC5pbnQuZ2V0CGNvbnN0YW50BAFpCGNvbnN0YW50BANtb2QIY29uc3RhbnQC6AMAAAhjb25zdGFudAQBKwhjb25zdGFudAIBAAAADmFyaXRobWV0aWMuaW50DWxvY2FsLmludC5nZXQIY29uc3RhbnQEAWkIY29uc3RhbnQEAS8IY29uc3RhbnQCoIYBAAhjb25zdGFudAQBKghjb25zdGFudAKghgEADmdlbmVyaWMuZ290b2lmCGNvbnN0YW50AgIAAAAOY29tcGFyaXNvbi5pbnQOYXJpdGhtZXRpYy5pbnQOYXJpdGhtZXRpYy5pbnQNbG9jYWwuaW50LmdldAhjb25zdGFudAQBaQhjb25zdGFudAQBLwhjb25zdGFudALoAwAACGNvbnN0YW50BANtb2QIY29uc3RhbnQCZAAAAAhjb25zdGFudAQCPD0IY29uc3RhbnQCCQAAABFnbG9iYWwuZG91YmxlLnNldAhjb25zdGFudAQJZHVzdF9kYXRhDnRlcm5hcnkuZG91YmxlD2NvbXBhcmlzb24uYm9vbBFjb21wYXJpc29uLmRvdWJsZRFnbG9iYWwuZG91YmxlLmdldAhjb25zdGFudAQJZHVzdF9kYXRhCGNvbnN0YW50BAE+CGNvbnN0YW50AwAAAAAAAAAACGNvbnN0YW50BAEmD2NvbXBhcmlzb24uYm9vbBZmYWN0b3J5Lm1hY2hpbmUuYWN0aXZlCGNvbnN0YW50BAVtaXhlcghjb25zdGFudAQBfA9jb21wYXJpc29uLmJvb2wSdG93bi53aW5kb3cuaXNvcGVuCGNvbnN0YW50BAdmYWN0b3J5CGNvbnN0YW50BAI9PQhjb25zdGFudAEAEWdsb2JhbC5kb3VibGUuZ2V0CGNvbnN0YW50BAlkdXN0X2RhdGERYXJpdGhtZXRpYy5kb3VibGURYXJpdGhtZXRpYy5kb3VibGUKZG91YmxlLm1pbhNmYWN0b3J5Lml0ZW1zLmNvdW50CGNvbnN0YW50BARkdXN0DmFyaXRobWV0aWMuaW50A2QyaRFhcml0aG1ldGljLmRvdWJsZQ50ZXJuYXJ5LmRvdWJsZRFjb21wYXJpc29uLmRvdWJsZRFnbG9iYWwuZG91YmxlLmdldAhjb25zdGFudAQJZHVzdF9kYXRhCGNvbnN0YW50BAI9PQhjb25zdGFudAMAAAAAAAAAAAhjb25zdGFudAMAAAAAAAAAABFhcml0aG1ldGljLmRvdWJsZRFnbG9iYWwuZG91YmxlLmdldAhjb25zdGFudAQJZHVzdF9kYXRhCGNvbnN0YW50BAErCGNvbnN0YW50AwAAAAAAAPA/CGNvbnN0YW50BANtb2QIY29uc3RhbnQDAAAAAAAAIkAIY29uc3RhbnQEASsIY29uc3RhbnQCAgAAAAhjb25zdGFudAMQx3Ecx3EMQwhjb25zdGFudAQBKghjb25zdGFudAMAAAAAAAAiQAhjb25zdGFudAQBKxFhcml0aG1ldGljLmRvdWJsZQ50ZXJuYXJ5LmRvdWJsZRFjb21wYXJpc29uLmRvdWJsZRFnbG9iYWwuZG91YmxlLmdldAhjb25zdGFudAQJZHVzdF9kYXRhCGNvbnN0YW50BAI9PQhjb25zdGFudAMAAAAAAAAAAAhjb25zdGFudAMAAAAAAAAAABFhcml0aG1ldGljLmRvdWJsZRFnbG9iYWwuZG91YmxlLmdldAhjb25zdGFudAQJZHVzdF9kYXRhCGNvbnN0YW50BAErCGNvbnN0YW50AwAAAAAAAPA/CGNvbnN0YW50BANtb2QIY29uc3RhbnQDAAAAAAAAIkAPZmFjdG9yeS5wcm9kdWNlCGNvbnN0YW50BANvcmUOYXJpdGhtZXRpYy5pbnQNbG9jYWwuaW50LmdldAhjb25zdGFudAQIb3JlX3RpZXIIY29uc3RhbnQEASsIY29uc3RhbnQCCgAAABNmYWN0b3J5Lml0ZW1zLmNvdW50CGNvbnN0YW50BANvcmUOYXJpdGhtZXRpYy5pbnQNbG9jYWwuaW50LmdldAhjb25zdGFudAQIb3JlX3RpZXIIY29uc3RhbnQEASsIY29uc3RhbnQCCgAAAAhjb25zdGFudAQHY3J1c2hlcg1sb2NhbC5pbnQuc2V0CGNvbnN0YW50BAhvcmVfdGllcgt0ZXJuYXJ5LmludBZmYWN0b3J5Lm1hY2hpbmUuYWN0aXZlCGNvbnN0YW50BAdjcnVzaGVyDWxvY2FsLmludC5nZXQIY29uc3RhbnQECG9yZV90aWVyC3Rlcm5hcnkuaW50DmNvbXBhcmlzb24uaW50DWxvY2FsLmludC5nZXQIY29uc3RhbnQECG9yZV90aWVyCGNvbnN0YW50BAE+CGNvbnN0YW50Avf///8OYXJpdGhtZXRpYy5pbnQNbG9jYWwuaW50LmdldAhjb25zdGFudAQIb3JlX3RpZXIIY29uc3RhbnQEAS0IY29uc3RhbnQCAQAAAAhjb25zdGFudAIAAAAADWZhY3RvcnkuY3JhZnQIY29uc3RhbnQEBGx1bXADZDJpEWFyaXRobWV0aWMuZG91YmxlEWFyaXRobWV0aWMuZG91YmxlEWdsb2JhbC5kb3VibGUuZ2V0CGNvbnN0YW50BAlkdXN0X2RhdGEIY29uc3RhbnQEA21vZAhjb25zdGFudAMAAAAAAAAiQAhjb25zdGFudAQBKwhjb25zdGFudAMAAAAAAADwPwpkb3VibGUubWluEWFyaXRobWV0aWMuZG91YmxlE2ZhY3RvcnkuaXRlbXMuY291bnQIY29uc3RhbnQEBGR1c3QOYXJpdGhtZXRpYy5pbnQDZDJpEWFyaXRobWV0aWMuZG91YmxlEWFyaXRobWV0aWMuZG91YmxlEWdsb2JhbC5kb3VibGUuZ2V0CGNvbnN0YW50BAlkdXN0X2RhdGEIY29uc3RhbnQEA21vZAhjb25zdGFudAMAAAAAAAAiQAhjb25zdGFudAQBKwhjb25zdGFudAMAAAAAAADwPwhjb25zdGFudAQBKwhjb25zdGFudAIBAAAACGNvbnN0YW50BAEtCmRvdWJsZS5tYXgIY29uc3RhbnQDAAAAAAAA8D8KZG91YmxlLm1pbhFhcml0aG1ldGljLmRvdWJsZRFhcml0aG1ldGljLmRvdWJsZRBsb2NhbC5kb3VibGUuZ2V0BmNvbmNhdAhjb25zdGFudAQGYnVmZmVyA2kycw5hcml0aG1ldGljLmludANkMmkRYXJpdGhtZXRpYy5kb3VibGURYXJpdGhtZXRpYy5kb3VibGURZ2xvYmFsLmRvdWJsZS5nZXQIY29uc3RhbnQECWR1c3RfZGF0YQhjb25zdGFudAQDbW9kCGNvbnN0YW50AwAAAAAAACJACGNvbnN0YW50BAErCGNvbnN0YW50AwAAAAAAAPA/CGNvbnN0YW50BAErCGNvbnN0YW50AgEAAAAIY29uc3RhbnQEASoRYXJpdGhtZXRpYy5kb3VibGUTZmFjdG9yeS5pdGVtcy5jb3VudAhjb25zdGFudAQEZHVzdAhjb25zdGFudAIBAAAACGNvbnN0YW50BAErEWFyaXRobWV0aWMuZG91YmxlCGNvbnN0YW50AwAAAAAAABBACGNvbnN0YW50BAEqEWFyaXRobWV0aWMuZG91YmxlE2ZhY3RvcnkuaXRlbXMuY291bnQIY29uc3RhbnQEBGR1c3QIY29uc3RhbnQCAgAAAAhjb25zdGFudAQBKxFhcml0aG1ldGljLmRvdWJsZQhjb25zdGFudAMAAAAAAAAQQAhjb25zdGFudAQBKhFhcml0aG1ldGljLmRvdWJsZRNmYWN0b3J5Lml0ZW1zLmNvdW50CGNvbnN0YW50BARkdXN0CGNvbnN0YW50AgMAAAAIY29uc3RhbnQEASsRYXJpdGhtZXRpYy5kb3VibGUIY29uc3RhbnQDAAAAAAAAEEAIY29uc3RhbnQEASoRYXJpdGhtZXRpYy5kb3VibGUTZmFjdG9yeS5pdGVtcy5jb3VudAhjb25zdGFudAQEZHVzdAhjb25zdGFudAIEAAAACGNvbnN0YW50BAErEWFyaXRobWV0aWMuZG91YmxlCGNvbnN0YW50AwAAAAAAABBACGNvbnN0YW50BAEqEWFyaXRobWV0aWMuZG91YmxlE2ZhY3RvcnkuaXRlbXMuY291bnQIY29uc3RhbnQEBGR1c3QIY29uc3RhbnQCBQAAAAhjb25zdGFudAQBKxFhcml0aG1ldGljLmRvdWJsZQhjb25zdGFudAMAAAAAAAAQQAhjb25zdGFudAQBKhFhcml0aG1ldGljLmRvdWJsZRNmYWN0b3J5Lml0ZW1zLmNvdW50CGNvbnN0YW50BARkdXN0CGNvbnN0YW50AgYAAAAIY29uc3RhbnQEASsRYXJpdGhtZXRpYy5kb3VibGUIY29uc3RhbnQDAAAAAAAAEEAIY29uc3RhbnQEASoRYXJpdGhtZXRpYy5kb3VibGUTZmFjdG9yeS5pdGVtcy5jb3VudAhjb25zdGFudAQEZHVzdAhjb25zdGFudAIHAAAACGNvbnN0YW50BAErEWFyaXRobWV0aWMuZG91YmxlCGNvbnN0YW50AwAAAAAAABBACGNvbnN0YW50BAEqEWFyaXRobWV0aWMuZG91YmxlE2ZhY3RvcnkuaXRlbXMuY291bnQIY29uc3RhbnQEBGR1c3QIY29uc3RhbnQCCAAAAAhjb25zdGFudAQBKxFhcml0aG1ldGljLmRvdWJsZQhjb25zdGFudAMAAAAAAAAQQAhjb25zdGFudAQBKhFhcml0aG1ldGljLmRvdWJsZRNmYWN0b3J5Lml0ZW1zLmNvdW50CGNvbnN0YW50BARkdXN0CGNvbnN0YW50AgkAAAAIY29uc3RhbnQEASsRYXJpdGhtZXRpYy5kb3VibGUIY29uc3RhbnQDAAAAAAAAEEAIY29uc3RhbnQEASoTZmFjdG9yeS5pdGVtcy5jb3VudAhjb25zdGFudAQEZHVzdAhjb25zdGFudAIKAAAACGNvbnN0YW50BAEvEWFyaXRobWV0aWMuZG91YmxlEGxvY2FsLmRvdWJsZS5nZXQIY29uc3RhbnQEB2J1ZmZlcjEIY29uc3RhbnQEASsRYXJpdGhtZXRpYy5kb3VibGUOdGVybmFyeS5kb3VibGURY29tcGFyaXNvbi5kb3VibGUTZmFjdG9yeS5pdGVtcy5jb3VudAhjb25zdGFudAQEZHVzdAhjb25zdGFudAICAAAACGNvbnN0YW50BAI9PQhjb25zdGFudAMAAAAAAAAAAAhjb25zdGFudAMAAAAAAAAAAAhjb25zdGFudAMAAAAAAAAQQAhjb25zdGFudAQBKhFhcml0aG1ldGljLmRvdWJsZRBsb2NhbC5kb3VibGUuZ2V0CGNvbnN0YW50BAdidWZmZXIyCGNvbnN0YW50BAErEWFyaXRobWV0aWMuZG91YmxlDnRlcm5hcnkuZG91YmxlEWNvbXBhcmlzb24uZG91YmxlE2ZhY3RvcnkuaXRlbXMuY291bnQIY29uc3RhbnQEBGR1c3QIY29uc3RhbnQCAwAAAAhjb25zdGFudAQCPT0IY29uc3RhbnQDAAAAAAAAAAAIY29uc3RhbnQDAAAAAAAAAAAIY29uc3RhbnQDAAAAAAAAEEAIY29uc3RhbnQEASoRYXJpdGhtZXRpYy5kb3VibGUQbG9jYWwuZG91YmxlLmdldAhjb25zdGFudAQHYnVmZmVyMwhjb25zdGFudAQBKxFhcml0aG1ldGljLmRvdWJsZQ50ZXJuYXJ5LmRvdWJsZRFjb21wYXJpc29uLmRvdWJsZRNmYWN0b3J5Lml0ZW1zLmNvdW50CGNvbnN0YW50BARkdXN0CGNvbnN0YW50AgQAAAAIY29uc3RhbnQEAj09CGNvbnN0YW50AwAAAAAAAAAACGNvbnN0YW50AwAAAAAAAAAACGNvbnN0YW50AwAAAAAAABBACGNvbnN0YW50BAEqEWFyaXRobWV0aWMuZG91YmxlEGxvY2FsLmRvdWJsZS5nZXQIY29uc3RhbnQEB2J1ZmZlcjQIY29uc3RhbnQEASsRYXJpdGhtZXRpYy5kb3VibGUOdGVybmFyeS5kb3VibGURY29tcGFyaXNvbi5kb3VibGUTZmFjdG9yeS5pdGVtcy5jb3VudAhjb25zdGFudAQEZHVzdAhjb25zdGFudAIFAAAACGNvbnN0YW50BAI9PQhjb25zdGFudAMAAAAAAAAAAAhjb25zdGFudAMAAAAAAAAAAAhjb25zdGFudAMAAAAAAAAQQAhjb25zdGFudAQBKhFhcml0aG1ldGljLmRvdWJsZRBsb2NhbC5kb3VibGUuZ2V0CGNvbnN0YW50BAdidWZmZXI1CGNvbnN0YW50BAErEWFyaXRobWV0aWMuZG91YmxlDnRlcm5hcnkuZG91YmxlEWNvbXBhcmlzb24uZG91YmxlE2ZhY3RvcnkuaXRlbXMuY291bnQIY29uc3RhbnQEBGR1c3QIY29uc3RhbnQCBgAAAAhjb25zdGFudAQCPT0IY29uc3RhbnQDAAAAAAAAAAAIY29uc3RhbnQDAAAAAAAAAAAIY29uc3RhbnQDAAAAAAAAEEAIY29uc3RhbnQEASoRYXJpdGhtZXRpYy5kb3VibGUQbG9jYWwuZG91YmxlLmdldAhjb25zdGFudAQHYnVmZmVyNghjb25zdGFudAQBKxFhcml0aG1ldGljLmRvdWJsZQ50ZXJuYXJ5LmRvdWJsZRFjb21wYXJpc29uLmRvdWJsZRNmYWN0b3J5Lml0ZW1zLmNvdW50CGNvbnN0YW50BARkdXN0CGNvbnN0YW50AgcAAAAIY29uc3RhbnQEAj09CGNvbnN0YW50AwAAAAAAAAAACGNvbnN0YW50AwAAAAAAAAAACGNvbnN0YW50AwAAAAAAABBACGNvbnN0YW50BAEqEWFyaXRobWV0aWMuZG91YmxlEGxvY2FsLmRvdWJsZS5nZXQIY29uc3RhbnQEB2J1ZmZlcjcIY29uc3RhbnQEASsRYXJpdGhtZXRpYy5kb3VibGUOdGVybmFyeS5kb3VibGURY29tcGFyaXNvbi5kb3VibGUTZmFjdG9yeS5pdGVtcy5jb3VudAhjb25zdGFudAQEZHVzdAhjb25zdGFudAIIAAAACGNvbnN0YW50BAI9PQhjb25zdGFudAMAAAAAAAAAAAhjb25zdGFudAMAAAAAAAAAAAhjb25zdGFudAMAAAAAAAAQQAhjb25zdGFudAQBKhFhcml0aG1ldGljLmRvdWJsZRBsb2NhbC5kb3VibGUuZ2V0CGNvbnN0YW50BAdidWZmZXI4CGNvbnN0YW50BAErEWFyaXRobWV0aWMuZG91YmxlDnRlcm5hcnkuZG91YmxlEWNvbXBhcmlzb24uZG91YmxlE2ZhY3RvcnkuaXRlbXMuY291bnQIY29uc3RhbnQEBGR1c3QIY29uc3RhbnQCCQAAAAhjb25zdGFudAQCPT0IY29uc3RhbnQDAAAAAAAAAAAIY29uc3RhbnQDAAAAAAAAAAAIY29uc3RhbnQDAAAAAAAAEEAIY29uc3RhbnQEASoRYXJpdGhtZXRpYy5kb3VibGUQbG9jYWwuZG91YmxlLmdldAhjb25zdGFudAQHYnVmZmVyOQhjb25zdGFudAQBKxFhcml0aG1ldGljLmRvdWJsZQ50ZXJuYXJ5LmRvdWJsZRFjb21wYXJpc29uLmRvdWJsZRNmYWN0b3J5Lml0ZW1zLmNvdW50CGNvbnN0YW50BARkdXN0CGNvbnN0YW50AgoAAAAIY29uc3RhbnQEAj09CGNvbnN0YW50AwAAAAAAAAAACGNvbnN0YW50AwAAAAAAAAAACGNvbnN0YW50AwAAAAAAABBACGNvbnN0YW50BAEqEGxvY2FsLmRvdWJsZS5nZXQIY29uc3RhbnQECGJ1ZmZlcjEwEWFyaXRobWV0aWMuZG91YmxlDGRvdWJsZS5mbG9vchFhcml0aG1ldGljLmRvdWJsZRFnbG9iYWwuZG91YmxlLmdldAhjb25zdGFudAQJZHVzdF9kYXRhCGNvbnN0YW50BAEvCGNvbnN0YW50AwAAAAAAACJACGNvbnN0YW50BAEtCGNvbnN0YW50AwAAAAAAACRAEWFyaXRobWV0aWMuZG91YmxlEWFyaXRobWV0aWMuZG91YmxlE2ZhY3RvcnkuaXRlbXMuY291bnQIY29uc3RhbnQEBGR1c3QDZDJpEWFyaXRobWV0aWMuZG91YmxlEWFyaXRobWV0aWMuZG91YmxlEWdsb2JhbC5kb3VibGUuZ2V0CGNvbnN0YW50BAlkdXN0X2RhdGEIY29uc3RhbnQEA21vZAhjb25zdGFudAMAAAAAAAAiQAhjb25zdGFudAQBKwhjb25zdGFudAMAAAAAAADwPwhjb25zdGFudAQBLQpkb3VibGUubWF4EWFyaXRobWV0aWMuZG91YmxlEWFyaXRobWV0aWMuZG91YmxlEWFyaXRobWV0aWMuZG91YmxlEGxvY2FsLmRvdWJsZS5nZXQGY29uY2F0CGNvbnN0YW50BAZidWZmZXIDaTJzA2QyaRFhcml0aG1ldGljLmRvdWJsZRFhcml0aG1ldGljLmRvdWJsZRFnbG9iYWwuZG91YmxlLmdldAhjb25zdGFudAQJZHVzdF9kYXRhCGNvbnN0YW50BANtb2QIY29uc3RhbnQDAAAAAAAAIkAIY29uc3RhbnQEASsIY29uc3RhbnQDAAAAAAAA8D8IY29uc3RhbnQEASoRYXJpdGhtZXRpYy5kb3VibGUTZmFjdG9yeS5pdGVtcy5jb3VudAhjb25zdGFudAQEZHVzdAhjb25zdGFudAIBAAAACGNvbnN0YW50BAErEWFyaXRobWV0aWMuZG91YmxlCGNvbnN0YW50AwAAAAAAABBACGNvbnN0YW50BAEqEWFyaXRobWV0aWMuZG91YmxlE2ZhY3RvcnkuaXRlbXMuY291bnQIY29uc3RhbnQEBGR1c3QIY29uc3RhbnQCAgAAAAhjb25zdGFudAQBKxFhcml0aG1ldGljLmRvdWJsZQhjb25zdGFudAMAAAAAAAAQQAhjb25zdGFudAQBKhFhcml0aG1ldGljLmRvdWJsZRNmYWN0b3J5Lml0ZW1zLmNvdW50CGNvbnN0YW50BARkdXN0CGNvbnN0YW50AgMAAAAIY29uc3RhbnQEASsRYXJpdGhtZXRpYy5kb3VibGUIY29uc3RhbnQDAAAAAAAAEEAIY29uc3RhbnQEASoRYXJpdGhtZXRpYy5kb3VibGUTZmFjdG9yeS5pdGVtcy5jb3VudAhjb25zdGFudAQEZHVzdAhjb25zdGFudAIEAAAACGNvbnN0YW50BAErEWFyaXRobWV0aWMuZG91YmxlCGNvbnN0YW50AwAAAAAAABBACGNvbnN0YW50BAEqEWFyaXRobWV0aWMuZG91YmxlE2ZhY3RvcnkuaXRlbXMuY291bnQIY29uc3RhbnQEBGR1c3QIY29uc3RhbnQCBQAAAAhjb25zdGFudAQBKxFhcml0aG1ldGljLmRvdWJsZQhjb25zdGFudAMAAAAAAAAQQAhjb25zdGFudAQBKhFhcml0aG1ldGljLmRvdWJsZRNmYWN0b3J5Lml0ZW1zLmNvdW50CGNvbnN0YW50BARkdXN0CGNvbnN0YW50AgYAAAAIY29uc3RhbnQEASsRYXJpdGhtZXRpYy5kb3VibGUIY29uc3RhbnQDAAAAAAAAEEAIY29uc3RhbnQEASoRYXJpdGhtZXRpYy5kb3VibGUTZmFjdG9yeS5pdGVtcy5jb3VudAhjb25zdGFudAQEZHVzdAhjb25zdGFudAIHAAAACGNvbnN0YW50BAErEWFyaXRobWV0aWMuZG91YmxlCGNvbnN0YW50AwAAAAAAABBACGNvbnN0YW50BAEqEWFyaXRobWV0aWMuZG91YmxlE2ZhY3RvcnkuaXRlbXMuY291bnQIY29uc3RhbnQEBGR1c3QIY29uc3RhbnQCCAAAAAhjb25zdGFudAQBKxFhcml0aG1ldGljLmRvdWJsZQhjb25zdGFudAMAAAAAAAAQQAhjb25zdGFudAQBKhFhcml0aG1ldGljLmRvdWJsZRNmYWN0b3J5Lml0ZW1zLmNvdW50CGNvbnN0YW50BARkdXN0CGNvbnN0YW50AgkAAAAIY29uc3RhbnQEASsRYXJpdGhtZXRpYy5kb3VibGUIY29uc3RhbnQDAAAAAAAAEEAIY29uc3RhbnQEASoTZmFjdG9yeS5pdGVtcy5jb3VudAhjb25zdGFudAQEZHVzdAhjb25zdGFudAIKAAAACGNvbnN0YW50BAEvEWFyaXRobWV0aWMuZG91YmxlEGxvY2FsLmRvdWJsZS5nZXQIY29uc3RhbnQEB2J1ZmZlcjEIY29uc3RhbnQEASsRYXJpdGhtZXRpYy5kb3VibGUOdGVybmFyeS5kb3VibGURY29tcGFyaXNvbi5kb3VibGUTZmFjdG9yeS5pdGVtcy5jb3VudAhjb25zdGFudAQEZHVzdAhjb25zdGFudAICAAAACGNvbnN0YW50BAI9PQhjb25zdGFudAMAAAAAAAAAAAhjb25zdGFudAMAAAAAAAAAAAhjb25zdGFudAMAAAAAAAAQQAhjb25zdGFudAQBKhFhcml0aG1ldGljLmRvdWJsZRBsb2NhbC5kb3VibGUuZ2V0CGNvbnN0YW50BAdidWZmZXIyCGNvbnN0YW50BAErEWFyaXRobWV0aWMuZG91YmxlDnRlcm5hcnkuZG91YmxlEWNvbXBhcmlzb24uZG91YmxlE2ZhY3RvcnkuaXRlbXMuY291bnQIY29uc3RhbnQEBGR1c3QIY29uc3RhbnQCAwAAAAhjb25zdGFudAQCPT0IY29uc3RhbnQDAAAAAAAAAAAIY29uc3RhbnQDAAAAAAAAAAAIY29uc3RhbnQDAAAAAAAAEEAIY29uc3RhbnQEASoRYXJpdGhtZXRpYy5kb3VibGUQbG9jYWwuZG91YmxlLmdldAhjb25zdGFudAQHYnVmZmVyMwhjb25zdGFudAQBKxFhcml0aG1ldGljLmRvdWJsZQ50ZXJuYXJ5LmRvdWJsZRFjb21wYXJpc29uLmRvdWJsZRNmYWN0b3J5Lml0ZW1zLmNvdW50CGNvbnN0YW50BARkdXN0CGNvbnN0YW50AgQAAAAIY29uc3RhbnQEAj09CGNvbnN0YW50AwAAAAAAAAAACGNvbnN0YW50AwAAAAAAAAAACGNvbnN0YW50AwAAAAAAABBACGNvbnN0YW50BAEqEWFyaXRobWV0aWMuZG91YmxlEGxvY2FsLmRvdWJsZS5nZXQIY29uc3RhbnQEB2J1ZmZlcjQIY29uc3RhbnQEASsRYXJpdGhtZXRpYy5kb3VibGUOdGVybmFyeS5kb3VibGURY29tcGFyaXNvbi5kb3VibGUTZmFjdG9yeS5pdGVtcy5jb3VudAhjb25zdGFudAQEZHVzdAhjb25zdGFudAIFAAAACGNvbnN0YW50BAI9PQhjb25zdGFudAMAAAAAAAAAAAhjb25zdGFudAMAAAAAAAAAAAhjb25zdGFudAMAAAAAAAAQQAhjb25zdGFudAQBKhFhcml0aG1ldGljLmRvdWJsZRBsb2NhbC5kb3VibGUuZ2V0CGNvbnN0YW50BAdidWZmZXI1CGNvbnN0YW50BAErEWFyaXRobWV0aWMuZG91YmxlDnRlcm5hcnkuZG91YmxlEWNvbXBhcmlzb24uZG91YmxlE2ZhY3RvcnkuaXRlbXMuY291bnQIY29uc3RhbnQEBGR1c3QIY29uc3RhbnQCBgAAAAhjb25zdGFudAQCPT0IY29uc3RhbnQDAAAAAAAAAAAIY29uc3RhbnQDAAAAAAAAAAAIY29uc3RhbnQDAAAAAAAAEEAIY29uc3RhbnQEASoRYXJpdGhtZXRpYy5kb3VibGUQbG9jYWwuZG91YmxlLmdldAhjb25zdGFudAQHYnVmZmVyNghjb25zdGFudAQBKxFhcml0aG1ldGljLmRvdWJsZQ50ZXJuYXJ5LmRvdWJsZRFjb21wYXJpc29uLmRvdWJsZRNmYWN0b3J5Lml0ZW1zLmNvdW50CGNvbnN0YW50BARkdXN0CGNvbnN0YW50AgcAAAAIY29uc3RhbnQEAj09CGNvbnN0YW50AwAAAAAAAAAACGNvbnN0YW50AwAAAAAAAAAACGNvbnN0YW50AwAAAAAAABBACGNvbnN0YW50BAEqEWFyaXRobWV0aWMuZG91YmxlEGxvY2FsLmRvdWJsZS5nZXQIY29uc3RhbnQEB2J1ZmZlcjcIY29uc3RhbnQEASsRYXJpdGhtZXRpYy5kb3VibGUOdGVybmFyeS5kb3VibGURY29tcGFyaXNvbi5kb3VibGUTZmFjdG9yeS5pdGVtcy5jb3VudAhjb25zdGFudAQEZHVzdAhjb25zdGFudAIIAAAACGNvbnN0YW50BAI9PQhjb25zdGFudAMAAAAAAAAAAAhjb25zdGFudAMAAAAAAAAAAAhjb25zdGFudAMAAAAAAAAQQAhjb25zdGFudAQBKhFhcml0aG1ldGljLmRvdWJsZRBsb2NhbC5kb3VibGUuZ2V0CGNvbnN0YW50BAdidWZmZXI4CGNvbnN0YW50BAErEWFyaXRobWV0aWMuZG91YmxlDnRlcm5hcnkuZG91YmxlEWNvbXBhcmlzb24uZG91YmxlE2ZhY3RvcnkuaXRlbXMuY291bnQIY29uc3RhbnQEBGR1c3QIY29uc3RhbnQCCQAAAAhjb25zdGFudAQCPT0IY29uc3RhbnQDAAAAAAAAAAAIY29uc3RhbnQDAAAAAAAAAAAIY29uc3RhbnQDAAAAAAAAEEAIY29uc3RhbnQEASoRYXJpdGhtZXRpYy5kb3VibGUQbG9jYWwuZG91YmxlLmdldAhjb25zdGFudAQHYnVmZmVyOQhjb25zdGFudAQBKxFhcml0aG1ldGljLmRvdWJsZQ50ZXJuYXJ5LmRvdWJsZRFjb21wYXJpc29uLmRvdWJsZRNmYWN0b3J5Lml0ZW1zLmNvdW50CGNvbnN0YW50BARkdXN0CGNvbnN0YW50AgoAAAAIY29uc3RhbnQEAj09CGNvbnN0YW50AwAAAAAAAAAACGNvbnN0YW50AwAAAAAAAAAACGNvbnN0YW50AwAAAAAAABBACGNvbnN0YW50BAEqEGxvY2FsLmRvdWJsZS5nZXQIY29uc3RhbnQECGJ1ZmZlcjEwCGNvbnN0YW50BAEtCGNvbnN0YW50AwAAAAAAABBACGNvbnN0YW50AwAAAAAAAPA/CGNvbnN0YW50BAEvCGNvbnN0YW50AwAAAAAAACBAD2ZhY3RvcnkucHJvZHVjZQhjb25zdGFudAQEbHVtcANkMmkRYXJpdGhtZXRpYy5kb3VibGURYXJpdGhtZXRpYy5kb3VibGURZ2xvYmFsLmRvdWJsZS5nZXQIY29uc3RhbnQECWR1c3RfZGF0YQhjb25zdGFudAQDbW9kCGNvbnN0YW50AwAAAAAAACJACGNvbnN0YW50BAErCGNvbnN0YW50AwAAAAAAAPA/E2ZhY3RvcnkuaXRlbXMuY291bnQIY29uc3RhbnQEBGx1bXADZDJpEWFyaXRobWV0aWMuZG91YmxlEWFyaXRobWV0aWMuZG91YmxlEWdsb2JhbC5kb3VibGUuZ2V0CGNvbnN0YW50BAlkdXN0X2RhdGEIY29uc3RhbnQEA21vZAhjb25zdGFudAMAAAAAAAAiQAhjb25zdGFudAQBKwhjb25zdGFudAMAAAAAAADwPwhjb25zdGFudAQFbWl4ZXIOZ2VuZXJpYy5nb3RvaWYIY29uc3RhbnQCBQAAABJ0b3duLndpbmRvdy5pc29wZW4IY29uc3RhbnQEB2ZhY3Rvcnk=

```
### Details

Edit the first line which sets the variable "dust_multipliers" to customize; this sets the shape of the target distribution as a space-separated list. Each number is a multiple of the T1 dust amount, so the first entry should be 1. The default of "1 1 .625 .5 .1 .1 .05 .05 .05 .05" is based on making high-level producers and should reasonable for everyone.

![The script in action](https://raw.githubusercontent.com/d0sboots/PerfectTower/main/crushing_in_progress.png)
This shows what you can expect after the script has run for a while. There's only 2.75K of the low-tier dusts, but 138 of the higest-tier dusts. This matches the ratios above (138 is 1/20th of 2750.) When you first start it, you might have millions of T1 dust - don't be alarmed if it drops this to just a few thousand.

You also might notice that when you first get a new tier (say, the first time you get T10 dust), your dust levels will drop suddenly. This is expected: the script cuts off the tiers you don't have (since you can't uptier to them yet), and once you gain access to a new tier the rebalancing will give you a bunch more dust of the new, higest tier, but ~1/4 as much dust in the other tiers.

This works equally well with or without Chemical Lumps, but if you don't have Lumps it will undershoot the buffer by 4 dust (but it will never consume the last dust, no matter what).

If you want to manually change what the factory is working on, you can repeatedly shift-right click to remove the current ore/lump from the machine. Due to a semi-intentional race condition, this will sometimes cause the script to advance to the next tier.

## Other Utilities
### Power Plant Optimizer/Calculator
https://www.desmos.com/calculator/ymjrbqrcve

Allows for fine-grained control of power-plant building counts to determine the optimal layout, accounting for Town Perks and what building is powered.

### Exotic Lab Simulator
https://d0sboots.github.io/PerfectTower/exotic_sim.html

A bit quick-and-dirty, this simulates the mechanics of the Exotic Lab. Mostly it just validates that the best strategy is to put one point into everything and then pump Time Factor exclusively. (But you can see how much time you're gaining for your gems...)
