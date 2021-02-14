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
description: Obtenga información sobre cómo habilitar la aplicación cliente de escritorio de Teams con directivas de control de aplicaciones AppLocker.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 4e70fc4502851137494c316db9eff7faefc140d1
ms.sourcegitcommit: c573b0be535fcf927ae01d60a7eb8fbf1aec271d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2020
ms.locfileid: "46526696"
---
# <a name="applocker-application-control-policies-in-microsoft-teams"></a>Directivas de control de aplicaciones AppLocker en Microsoft Teams

En este artículo se explica cómo habilitar la aplicación cliente de escritorio de Teams con directivas de control de aplicaciones AppLocker. El uso de AppLocker está diseñado para restringir la ejecución de programas y scripts por usuarios no administrativos. Para obtener más información e instrucciones sobre AppLocker, consulta [¿Qué es AppLocker?](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker).

El proceso para habilitar Teams con AppLocker requiere la creación de directivas de descripción de permitidos basadas en AppLocker. Las directivas se crean con el software de administración de directivas de grupo o con el uso de Windows PowerShell cmdlets para AppLocker (consulte la referencia técnica de [AppLocker](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference) para obtener más información). La directiva de AppLocker se guarda en formato XML y se puede editar con cualquier editor de texto o XML.

## <a name="teams-allow-list-with-applocker"></a>Lista de equipos permitidos con AppLocker

Las reglas de AppLocker están organizadas en colecciones de reglas. Las reglas de AppLocker se aplican a la aplicación de destino y son los componentes que la directiva de AppLocker.  

Para permitir Teams, le recomendamos que use las reglas de condición de [Publisher,](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/understanding-the-publisher-rule-condition-in-applocker) ya que todos los archivos de la aplicación Teams están firmados digitalmente.
  
No se recomienda el uso de reglas de ruta porque el directorio de instalación de Teams se puede escribir por el usuario. Tampoco recomendamos el uso de reglas de hash, ya que estas tendrían que actualizarse cada vez que se actualice la aplicación cliente de Teams.

Puesto que los archivos ejecutables del escritorio de Teams están firmados digitalmente, la condición del editor identifica un archivo de la aplicación en función de su firma digital y atributos de versión incrustados. La firma digital contiene información sobre la compañía que creó el archivo de la aplicación (el editor). La información de la versión, que se obtiene del recurso binario, incluye el nombre del producto del que forma parte el archivo y el número de versión del archivo de la aplicación.

### <a name="example-of-publisher-condition-rules"></a>Ejemplo de reglas de condición de publisher

Para la aplicación cliente de Teams (todos los archivos, todas las versiones) agregue lo siguiente a las reglas ejecutables & de DLL:

```console
Publisher: O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US
Product name: MICROSOFT TEAMS
Product name: MICROSOFT TEAMS UPDATE
```

## <a name="related-topics"></a>Temas relacionados
[¿Qué es AppLocker?](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker) 
 [Referencia técnica de AppLocker](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference)
