---
title: Directivas de control de aplicación de AppLocker en Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: rafarhi
search.appverid: MET150
description: Obtenga información sobre cómo habilitar la aplicación de cliente de escritorio de los equipos con directivas de control de aplicación de AppLocker.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 04379cad0ab224915a02475b010f908d486284cc
ms.sourcegitcommit: 85b135cf622c9e9eb1857ef953bc618dc2cdb51e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "34063216"
---
# <a name="applocker-application-control-policies-in-microsoft-teams"></a>Directivas de control de aplicación de AppLocker en Microsoft Teams

En este artículo se explica cómo habilitar la aplicación de cliente de escritorio de los equipos con directivas de control de aplicación de AppLocker. Uso de AppLocker está diseñada para restringir la ejecución de programa y secuencias de comandos por los usuarios que no sean administrativos. Para obtener más información y orientación sobre AppLocker, consulte [¿Qué es AppLocker?](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker).

El proceso para permitir a los equipos con AppLocker requiere la creación de las directivas de AppLocker-based lista blanca. Las directivas se crean con software de administración de directiva de grupo o el uso de cmdlets de Windows PowerShell para AppLocker (vea la [referencia técnica de AppLocker](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference) para obtener más información). La directiva de AppLocker se guarda en formato XML y se puede editar con cualquier editor de XML o de texto.

## <a name="teams-whitelisting-with-applocker"></a>Lista blanca de los equipos con AppLocker

Las reglas de AppLocker se organizan en colecciones de reglas. Las reglas de AppLocker se aplican a la aplicación de destino y que son los componentes que componen la directiva de AppLocker.  

Para los equipos de la lista blanca, se recomienda usar las [reglas de condición de publisher](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/understanding-the-publisher-rule-condition-in-applocker) ya que todos los archivos de aplicación de los equipos están firmados digitalmente.
  
No se recomienda el uso de las reglas de ruta de acceso porque el directorio de instalación de los equipos se puede escribir el usuario. También se no recomienda el uso de reglas de hash porque las reglas tendría que se actualizan cada vez que se actualiza la aplicación de los equipos cliente.

Dado que los archivos ejecutables de escritorio de los equipos están firmados digitalmente, la condición de publisher identifica un archivo de aplicación basado en los atributos de versión incrustado y su firma digital. La firma digital contiene información acerca de la compañía que creó el archivo de aplicación (el publicador). La información de versión, se obtiene desde el recurso binario, incluye el nombre del producto que el archivo forma parte de y el número de versión de archivo de la aplicación.

### <a name="example-of-publisher-condition-rules"></a>Ejemplo de las reglas de condición de publisher

Para la aplicación de cliente de los equipos (todos los archivos, todas las versiones):

```
Publisher: O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US
Product name: MICROSOFT TEAMS
```

## <a name="related-topics"></a>Temas relacionados
[¿Qué es AppLocker?](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker) 
 [Referencia técnica de AppLocker](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference)