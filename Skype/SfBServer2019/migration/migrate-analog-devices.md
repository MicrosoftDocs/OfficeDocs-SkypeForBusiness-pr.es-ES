---
title: Migrar dispositivos analógicos
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Skype empresarial Server proporciona compatibilidad con dispositivos analógicos. Específicamente, los dispositivos analógicos compatibles son teléfonos de audio analógicos y equipos de fax analógico. Puede configurar las puertas de enlace calificadas para que admitan el uso de dispositivos analógicos en el entorno de Skype empresarial Server. Después de migrar a Skype empresarial Server 2019, también debe migrar los objetos de contacto asociados con los dispositivos analógicos. Use el shell de administración de Skype empresarial Server para recuperar primero todos los objetos de contacto asociados con los dispositivos analógicos heredados y, a continuación, mover esos objetos al grupo de servidores de Skype empresarial 2019.
ms.openlocfilehash: b3b3cc1ebafa468a43043b202a01957c1cc06e87
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813598"
---
# <a name="migrate-analog-devices"></a>Migrar dispositivos analógicos

Skype empresarial Server proporciona compatibilidad con dispositivos analógicos. Específicamente, los dispositivos analógicos compatibles son teléfonos de audio analógicos y equipos de fax analógico. Puede configurar las puertas de enlace calificadas para que admitan el uso de dispositivos analógicos en el entorno de Skype empresarial Server. Después de migrar a Skype empresarial Server 2019, también debe migrar los objetos de contacto asociados con los dispositivos analógicos. Use el shell de administración de Skype empresarial Server para recuperar primero todos los objetos de contacto asociados con los dispositivos analógicos heredados y, a continuación, mover esos objetos al grupo de servidores de Skype empresarial 2019.

### <a name="to-migrate-analog-devices"></a>Para migrar dispositivos analógicos

1. Inicie el shell de administración de Skype empresarial Server: haga clic en **Inicio**, haga clic en **todos los programas**, haga clic en **Microsoft Skype empresarial Server 2019**y, a continuación, haga clic en **consola de administración de Skype empresarial Server**.

2. En la línea de comandos, escriba:

   ```PowerShell
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsAnalogDevice -Target pool02.contoso.net
   ```

3. Compruebe que todos los objetos de contacto se han movido al grupo de servidores de Skype empresarial 2019. En la línea de comandos, escriba:

   ```PowerShell
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

4. Compruebe que todos los objetos de contacto están asociados con el grupo de servidores de Skype empresarial 2019.


