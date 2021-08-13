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
description: Los teléfonos de área común son teléfonos IP que a menudo se encuentran en un espacio de trabajo compartido o un área común, como una sala de espera, cocina o una fábrica. Los teléfonos de área común no necesitan conectarse a un equipo para proporcionar Skype Empresarial Server de comunicaciones unificadas (UC). Después de migrar una implementación a Skype Empresarial Server 2019, también debe migrar los objetos de contacto asociados con el área común heredada Teléfono. Con Skype Empresarial Server Shell de administración, primero recuperará todos los objetos de contacto asociados con los teléfonos de área común heredados y, a continuación, moverá esos objetos al grupo de servidores de Skype Empresarial Server 2019.
ms.openlocfilehash: 808e874216fac97b01face6efa7aae00e269b74ee0f009b106f872a33a6d6261
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54340436"
---
# <a name="migrate-common-area-phones"></a>Migrar teléfonos de área común

Los teléfonos de área común son teléfonos IP que a menudo se encuentran en un espacio de trabajo compartido o un área común, como una sala de espera, cocina o una fábrica. Los teléfonos de área común no necesitan conectarse a un equipo para proporcionar Skype Empresarial Server de comunicaciones unificadas (UC). Después de migrar una implementación a Skype Empresarial Server 2019, también debe migrar los objetos de contacto asociados con el área común heredada Teléfono. Con Skype Empresarial Server Shell de administración, primero recuperará todos los objetos de contacto asociados con los teléfonos de área común heredados y, a continuación, moverá esos objetos al grupo de servidores Skype Empresarial Server 2019.
  
### <a name="migrate-common-area-phones"></a>Migrar teléfonos de área común

1. Desde el Skype Empresarial Server front-end de 2019, abra Skype Empresarial Server Shell de administración.
    
2. En la línea de comandos, escriba lo siguiente:
    
   ```PowerShell
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsCommonAreaPhone -Target pool02.contoso.net
   ```

3. Para comprobar que todos los objetos de contacto se han movido al grupo de servidores de Skype Empresarial Server 2019, desde el shell de administración de Skype Empresarial Server escriba lo siguiente:
    
   ```PowerShell
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

    Compruebe que todos los objetos de contacto están asociados al grupo Skype Empresarial Server 2019.
    

