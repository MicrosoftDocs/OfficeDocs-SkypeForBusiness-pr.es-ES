---
title: Directivas de control de AppLocker
author: MSFTTracyP
ms.author: tracyp
manager: dansimp
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: rafarhi
search.appverid: MET150
f1.keywords:
- NOCSH
description: Obtenga información sobre cómo habilitar la aplicación Teams cliente de escritorio con directivas de control de aplicaciones de AppLocker.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: d6e6040956ba5e5469076b4fbbab337f58268c68
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120852"
---
# <a name="applocker-application-control-policies-in-microsoft-teams"></a>Directivas de control de aplicaciones de AppLocker en Microsoft Teams

En este artículo se explica cómo habilitar la Teams cliente de escritorio con directivas de control de aplicaciones de AppLocker. El uso de AppLocker está diseñado para restringir la ejecución de programas y scripts por usuarios no administrativos. Para obtener más información y instrucciones sobre AppLocker, vea [¿Qué es AppLocker?](/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker).

El proceso para habilitar Teams con AppLocker requiere la creación de directivas de descripción de permitidos basadas en AppLocker. Las directivas se crean con software de administración de directivas de grupo o con el uso de cmdlets de Windows PowerShell para AppLocker (consulte la referencia técnica de [AppLocker](/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference) para obtener más información). La directiva de AppLocker se guarda en formato XML y se puede editar con cualquier texto o editor XML.

## <a name="teams-allow-list-with-applocker"></a>Teams lista de permitidos con AppLocker

Las reglas de AppLocker se organizan en colecciones de reglas. Las reglas de AppLocker se aplican a la aplicación de destino y son los componentes que la directiva de AppLocker.  

Para permitir Teams, le recomendamos que [](/windows/security/threat-protection/windows-defender-application-control/applocker/understanding-the-publisher-rule-condition-in-applocker) use las reglas de condición del editor, ya que todos los Teams de la aplicación están firmados digitalmente.
  
No se recomienda el uso de reglas de ruta de acceso porque el Teams de instalación es fácil de escribir por el usuario. Tampoco recomendamos el uso de reglas hash, ya que las reglas tendrían que actualizarse cada vez que se actualiza Teams aplicación cliente.

Puesto Teams archivos ejecutables de escritorio están firmados digitalmente, la condición del editor identifica un archivo de aplicación en función de su firma digital y atributos de versión incrustados. La firma digital contiene información sobre la empresa que creó el archivo de aplicación (el editor). La información de versión, que se obtiene del recurso binario, incluye el nombre del producto del que forma parte el archivo y el número de versión del archivo de aplicación.

### <a name="example-of-publisher-condition-rules"></a>Ejemplo de reglas de condición del editor

Para la Teams cliente (todos los archivos, todas las versiones) agregue lo siguiente a las reglas ejecutables & reglas DLL:

```console
Publisher: O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US
Product name: MICROSOFT TEAMS
Product name: MICROSOFT TEAMS UPDATE
```

## <a name="related-topics"></a>Temas relacionados
[¿Qué es AppLocker?](/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker) 
 [Referencia técnica de AppLocker](/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference)