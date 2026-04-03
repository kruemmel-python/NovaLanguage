# Beispiele zum Nova Language Grundkurs

Dieser Ordner enthaelt die begleitenden Unterrichtsbeispiele fuer den Grundkurs in [NovaLanguage](H:\Nova-shell-main\NovaLanguage).

## Reihenfolge

1. `01_hallo_welt.ns`
2. `02_datasets_und_literale.ns`
3. `03_alias_und_datenfluss.ns`
4. `04_listen_maps_und_dictionaries.ns`
5. `05_state_und_events.ns`
6. `06_agent_und_tool.ns`
7. `07_system_service_package.ns`
8. `08_import_shared.ns`
9. `08_import_main.ns`
10. `09_python_bruecke.ns`
11. `10_objektmodell_und_komposition.ns`

## Nutzung

Graph validieren:

```powershell
python nova_shell.py -c "ns.graph .\NovaLanguage\Beispiele\01_hallo_welt.ns"
```

Direkt ausfuehren:

```powershell
ns.run .\NovaLanguage\Beispiele\05_state_und_events.ns
```

Mehrdatei-Beispiel pruefen:

```powershell
@'
from pathlib import Path
from nova.runtime.runtime import NovaRuntime
path = Path(r".\NovaLanguage\Beispiele\08_import_main.ns").resolve()
source = path.read_text(encoding="utf-8")
with NovaRuntime() as runtime:
    runtime.load(source, source_name=str(path), base_path=path.parent)
    print("Import-Beispiel erfolgreich geladen.")
'@ | python -
```

## Didaktischer Hinweis

Die Beispiele sind bewusst progressiv aufgebaut:

- zuerst lokal und ohne AI-Zwang
- danach mit strukturierten Daten und Transformation
- spaeter mit Zustand, Ereignissen, Agenten und Plattformobjekten
- das Import-Beispiel ist absichtlich als kleines Projekt und nicht nur als Einzeldatei modelliert
