# Base de herramientas de escenarios — archivos de escenario para los editores

`scenario_tools_base` es una biblioteca compartida por los editores que leen o escriben archivos de escenario. No añade ventanas; llega junto con los editores que la necesitan.

## Quién la usa

El editor de escenarios, el editor de escenas, los editores de interactivos y de luces, y el editor de mapas RPG.

## Qué aporta

- **`ScenarioFileService`** — encuentra los archivos `.scenario` de todos los mods (`ScanScenarioFiles`), los lee y escribe (solo mods de carpeta), analiza la cabecera (escena, prioridad), extrae referencias (cambios de escena, claves de localización, misiones, fondos), crea un escenario nuevo para una escena (`CreateForScene`) y construye el grafo de escenas (`BuildSceneGraph`, los datos del grafo del editor de escenarios).
- **`ScenarioSyntaxService`** — el resaltado del lenguaje de escenarios para los textos de los editores (el editor de mapas RPG lo usa para los guiones de eventos) y un separador de líneas de comando; con él el editor de interactivos encuentra qué escenario añade un interactivo, y el editor de luces lee y reescribe la línea `light_set` con el servicio de archivos.

El lenguaje en sí viene del motor de diálogos (`dialog_base`); los servicios neutrales de archivos y escenas siguen en `tools_base`, así las herramientas que no tocan escenarios no arrastran el motor de diálogos.

## Dependencias

`tools_base`, `dialog_base`.
