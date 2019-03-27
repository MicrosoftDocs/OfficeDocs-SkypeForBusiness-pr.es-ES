---
title: Migrar dispositivos analógicos
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Skype para Business Server proporciona compatibilidad con dispositivos analógicos. Específicamente, los dispositivos analógicos compatibles son teléfonos audioconferencias analógicos y equipos de fax analógicos. Puede configurar las puertas de enlace completa para admitir el uso de dispositivos analógicos en su Skype para el entorno de servidor empresarial. Después de migrar a Skype para Business Server 2019, también debe migrar los objetos de contacto asociados con los dispositivos analógicos. Usar Skype para Shell de administración de servidor empresarial para todos los recuperar primero objetos asociados con los dispositivos analógicos heredados de contacto y, a continuación, mover los objetos a la Skype para el grupo de servidores de Business Server 2019.
ms.openlocfilehash: 80edf5b806ffd192d125bd5da27207a37f3074d1
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30889969"
---
# <a name="migrate-analog-devices"></a>Migrar dispositivos analógicos

Skype para Business Server proporciona compatibilidad con dispositivos analógicos. Específicamente, los dispositivos analógicos compatibles son teléfonos audioconferencias analógicos y equipos de fax analógicos. Puede configurar las puertas de enlace completa para admitir el uso de dispositivos analógicos en su Skype para el entorno de servidor empresarial. Después de migrar a Skype para Business Server 2019, también debe migrar los objetos de contacto asociados con los dispositivos analógicos. Usar Skype para Shell de administración de servidor empresarial para todos los recuperar primero objetos asociados con los dispositivos analógicos heredados de contacto y, a continuación, mover los objetos a la Skype para el grupo de servidores de Business Server 2019.

### <a name="to-migrate-analog-devices"></a>Para migrar dispositivos analógicos

1. Iniciar el Skype para Shell de administración de negocio Server: haga clic en **Inicio**, haga clic en **Todos los programas**, haga clic en **Microsoft Skype para Business Server 2019**y, a continuación, haga clic en **Skype para Shell de administración de servidor empresarial**.

2. En la línea de comandos, escriba:

   ```
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsAnalogDevice -Target pool02.contoso.net
   ```

3. Compruebe que todos los objetos de contacto se han movido a la Skype para el grupo de servidores de Business Server 2019. En la línea de comandos, escriba:

   ```
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

4. Compruebe que todos los objetos de contacto están ahora asociadas con el Skype para el grupo de servidores de Business Server 2019.


