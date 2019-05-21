---
title: Migrar teléfonos de área común
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Los teléfonos de área común son teléfonos IP que suelen residir en un área de trabajo compartida o en un área común, como un vestíbulo, una cocina o una fábrica. No es necesario que los teléfonos de área común estén conectados a un equipo para proporcionar la funcionalidad de comunicaciones unificadas (UC) de Skype empresarial Server. Después de migrar una implementación a Skype empresarial Server 2019, también debe migrar los objetos de contacto asociados con el teléfono de área común heredado. Usar el shell de administración de Skype empresarial Server primero recuperará todos los objetos de contacto asociados a los teléfonos de área común heredados y, a continuación, moverá esos objetos al grupo de servidores de Skype empresarial 2019.
ms.openlocfilehash: 915b0b86c4f0b1ac74e2575cdfcd65d0cbf23d31
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280822"
---
# <a name="migrate-common-area-phones"></a>Migrar teléfonos de área común

Los teléfonos de área común son teléfonos IP que suelen residir en un área de trabajo compartida o en un área común, como un vestíbulo, una cocina o una fábrica. No es necesario que los teléfonos de área común estén conectados a un equipo para proporcionar la funcionalidad de comunicaciones unificadas (UC) de Skype empresarial Server. Después de migrar una implementación a Skype empresarial Server 2019, también debe migrar los objetos de contacto asociados con el teléfono de área común heredado. Si usa el shell de administración de Skype empresarial Server, primero deberá recuperar todos los objetos de contacto asociados a los teléfonos de área común heredados y, a continuación, mover esos objetos al grupo de servidores de Skype empresarial 2019.
  
### <a name="migrate-common-area-phones"></a>Migrar teléfonos de área común

1. Desde el servidor front-end de Skype empresarial Server 2019, abra el shell de administración de Skype empresarial Server.
    
2. En la línea de comandos, escriba lo siguiente:
    
   ```
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsCommonAreaPhone -Target pool02.contoso.net
   ```

3. Para comprobar que todos los objetos de contacto se han movido al grupo de servidores de Skype empresarial 2019, en el shell de administración de Skype empresarial Server, escriba lo siguiente:
    
   ```
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

    Compruebe que todos los objetos de contacto ahora están asociados con el grupo de servidores de Skype empresarial 2019.
    

