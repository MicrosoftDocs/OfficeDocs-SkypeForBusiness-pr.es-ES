---
title: Migrar teléfonos de área común
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Los teléfonos de área común son teléfonos IP que a menudo se encuentran en un espacio de trabajo compartido o un área común, como una sala de espera, cocina o una fábrica. No es necesario que los teléfonos de área común estén conectados a un equipo para proporcionar la funcionalidad de comunicaciones unificadas (UC) de Skype Empresarial Server. Después de migrar una implementación a Skype Empresarial Server 2019, también debe migrar los objetos de contacto asociados con el teléfono de área común heredado. Con el Shell de administración de Skype Empresarial Server, primero recuperará todos los objetos de contacto asociados con los teléfonos de área común heredados y, a continuación, moverá esos objetos al grupo de Skype Empresarial Server 2019.
ms.openlocfilehash: b9cf5a32614ac41ac3c82773af4f37907c16e6f2
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752712"
---
# <a name="migrate-common-area-phones"></a>Migrar teléfonos de área común

Los teléfonos de área común son teléfonos IP que a menudo se encuentran en un espacio de trabajo compartido o un área común, como una sala de espera, cocina o una fábrica. No es necesario que los teléfonos de área común estén conectados a un equipo para proporcionar la funcionalidad de comunicaciones unificadas (UC) de Skype Empresarial Server. Después de migrar una implementación a Skype Empresarial Server 2019, también debe migrar los objetos de contacto asociados con el teléfono de área común heredado. Con el Shell de administración de Skype Empresarial Server, primero recuperará todos los objetos de contacto asociados con los teléfonos de área común heredados y, a continuación, moverá esos objetos al grupo de Skype Empresarial Server 2019.
  
### <a name="migrate-common-area-phones"></a>Migrar teléfonos de área común

1. Desde el servidor front-end de Skype Empresarial Server 2019, abra el Shell de administración de Skype Empresarial Server.
    
2. En la línea de comandos, escriba lo siguiente:
    
   ```PowerShell
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsCommonAreaPhone -Target pool02.contoso.net
   ```

3. Para comprobar que todos los objetos de contacto se han movido al grupo de Skype Empresarial Server 2019, desde el Shell de administración de Skype Empresarial Server escriba lo siguiente:
    
   ```PowerShell
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

    Compruebe que todos los objetos de contacto están ahora asociados con el grupo de Skype Empresarial Server 2019.
    

