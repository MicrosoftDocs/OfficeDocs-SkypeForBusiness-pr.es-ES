---
title: Migrar dispositivos analógicos
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Skype para Business Server proporciona compatibilidad con dispositivos analógicos. Específicamente, los dispositivos analógicos compatibles son teléfonos audioconferencias analógicos y equipos de fax analógicos. Puede configurar las puertas de enlace completa para admitir el uso de dispositivos analógicos en su Skype para el entorno de servidor empresarial. Después de migrar a Skype para Business Server 2019, también debe migrar los objetos de contacto asociados con los dispositivos analógicos. Usar Skype para Shell de administración de servidor empresarial para todos los recuperar primero objetos asociados con los dispositivos analógicos heredados de contacto y, a continuación, mover los objetos a la Skype para el grupo de servidores de Business Server 2019.
ms.openlocfilehash: 25de46ce2d0b6a86553b78d591f35f9d881fb55e
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "25030416"
---
# <a name="migrate-analog-devices"></a>Migrar dispositivos analógicos

Skype para Business Server proporciona compatibilidad con dispositivos analógicos. Específicamente, los dispositivos analógicos compatibles son teléfonos audioconferencias analógicos y equipos de fax analógicos. Puede configurar las puertas de enlace completa para admitir el uso de dispositivos analógicos en su Skype para el entorno de servidor empresarial. Después de migrar a Skype para Business Server 2019, también debe migrar los objetos de contacto asociados con los dispositivos analógicos. Usar Skype para Shell de administración de servidor empresarial para todos los recuperar primero objetos asociados con los dispositivos analógicos heredados de contacto y, a continuación, mover los objetos a la Skype para el grupo de servidores de Business Server 2019.
  
### <a name="to-migrate-analog-devices"></a>Para migrar dispositivos analógicos

1. Iniciar el Skype para Shell de administración de negocio Server: haga clic en **Inicio**, haga clic en **Todos los programas**, haga clic en **Microsoft Skype para Business Server 2019**y, a continuación, haga clic en **Skype para Shell de administración de servidor empresarial**.
    
2. En la línea de comandos, escriba lo siguiente:
    
  ```
  Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsAnalogDevice -Target pool02.contoso.net
  
  ```

3. Compruebe que todos los objetos de contacto se han movido a la Skype para el grupo de servidores de Business Server 2019. En la línea de comandos, escriba lo siguiente:
    
  ```
  Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool02.contoso.net"}
  ```

4. Compruebe que todos los objetos de contacto están ahora asociadas con el Skype para el grupo de servidores de Business Server 2019.
    

