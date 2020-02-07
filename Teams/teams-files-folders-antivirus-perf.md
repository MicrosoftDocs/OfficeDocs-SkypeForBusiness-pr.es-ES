---
title: Archivos y carpetas de Teams que se excluyen de la detección de virus
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ramesa
audience: admin
description: Mejore el rendimiento de los equipos al excluir determinados archivos y carpetas de la exploración antivirus normal.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2dbb4b31fc3cddd8c434eb5c94e4f8801ff0633b
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41837680"
---
<a name="teams-files-and-folders-to-exclude-from-antivirus-scanning"></a>Archivos y carpetas de Teams que se excluyen de la detección de virus
=================================

Puede mejorar el rendimiento general de la implementación de equipos impidiendo que los programas antivirus examinen determinados archivos y carpetas de Teams. Esto evitará el desembolso de los recursos del sistema al analizar archivos y carpetas que no es necesario analizar.

> [!NOTE]
> Cuando los usuarios descargan archivos o comparten archivos entre sí, no pasan por las ubicaciones que se muestran en la siguiente sección. Las ubicaciones donde los usuarios carguen, descarguen o compartan archivos seguirán siendo analizados regularmente por el programa antivirus.

## <a name="files-and-folders-to-add-to-your-antivirus-safe-lists"></a>Archivos y carpetas para agregar a las listas seguras con el antivirus

Use los procedimientos admitidos por el programa antivirus para agregar los siguientes archivos y carpetas a las listas seguras. Si lo hace, se ahorrarán recursos del sistema evitando la detección de antivirus de estas ubicaciones.

### <a name="programs"></a>Programas

Agregue los siguientes programas de Teams a la lista segura de antivirus.

**%localappdata%\Microsoft\Teams\current\Teams.exe**

**%localappdata%\Microsoft\Teams\Update.exe**

### <a name="folders"></a>Las

Agregue las siguientes carpetas de Teams a la lista segura de antivirus.

|Categoría  |Ubicación  |
|---------|---------|
|Archivos de programa  |%localappdata%\Microsoft\Teams|
|Archivos de datos     |%appdata%\Microsoft\Teams\|