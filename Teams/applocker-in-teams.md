---
title: Directivas de control de aplicaciones de AppLocker en Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: rafarhi
search.appverid: MET150
description: Aprenda a habilitar la aplicación cliente de escritorio de Teams con directivas de control de aplicaciones de AppLocker.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8d87eb5328f5200479f719dc22d9244c46af8944
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36244947"
---
# <a name="applocker-application-control-policies-in-microsoft-teams"></a>Directivas de control de aplicaciones de AppLocker en Microsoft Teams

En este artículo se explica cómo habilitar la aplicación cliente de escritorio de Teams con directivas de control de aplicaciones de AppLocker. El uso de AppLocker está diseñado para restringir la ejecución de programas y scripts por parte de usuarios no administrativos. Para obtener más información y orientación en AppLocker, consulte [¿Qué es AppLocker?](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker).

El proceso de habilitar equipos con AppLocker requiere la creación de políticas de listas blancas basadas en AppLocker. Las directivas se crean con el software de administración de directivas de grupo y/o el uso de cmdlets de Windows PowerShell para AppLocker (consulte la [referencia técnica de AppLocker](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference) para obtener más información). La Directiva de AppLocker se guarda en formato XML y puede editarse con cualquier editor de texto o XML.

## <a name="teams-whitelisting-with-applocker"></a>Listas blancas de equipos con AppLocker

Las reglas de AppLocker se organizan en colecciones de reglas. Las reglas de AppLocker se aplican a la aplicación de destino y son los componentes que conforman la Directiva de AppLocker.  

Para los equipos de la lista blanca, le recomendamos que use las [reglas de condición](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/understanding-the-publisher-rule-condition-in-applocker) de Publisher, ya que todos los archivos de la aplicación Teams están firmados digitalmente.
  
No recomendamos el uso de reglas de ruta de acceso porque el directorio de instalación de Teams es grabable para el usuario. Tampoco recomendamos el uso de Reglas Hash porque las reglas deberían actualizarse cada vez que se actualice la aplicación cliente de Teams.

Como los archivos ejecutables de escritorio de Teams están firmados digitalmente, la condición Publisher identifica un archivo de aplicación en función de sus atributos de firma digital y versión insertada. La firma digital contiene información sobre la empresa que creó el archivo de la aplicación (el publicador). La información de versión, que se obtiene del recurso binario, incluye el nombre del producto del que forma parte el archivo y el número de versión del archivo de la aplicación.

### <a name="example-of-publisher-condition-rules"></a>Ejemplo de reglas de condición de editor

Para la aplicación cliente de Teams (todos los archivos, todas las versiones):

```
Publisher: O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US
Product name: MICROSOFT TEAMS
```

## <a name="related-topics"></a>Temas relacionados
[¿Qué es AppLocker?](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker) 
 [Referencia técnica de AppLocker](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference)