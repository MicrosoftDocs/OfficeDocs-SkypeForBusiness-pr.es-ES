---
title: Migrar dispositivos analógicos
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
description: Skype empresarial Server proporciona compatibilidad con dispositivos analógicos. En concreto, los dispositivos analógicos compatibles son los teléfonos de audio analógicos y los equipos de fax analógicos. Puede configurar las puertas de enlace calificadas para que admitan el uso de dispositivos analógicos en su entorno de Skype empresarial Server. Después de migrar a Skype empresarial Server 2019, también debe migrar los objetos de contacto asociados con los dispositivos analógicos. Use el shell de administración de Skype empresarial Server para recuperar primero todos los objetos de contacto asociados con los dispositivos analógicos heredados y, a continuación, mover dichos objetos al grupo de servidores de Skype empresarial 2019.
ms.openlocfilehash: 7b90a52486725c2cf30856dc643660d569d698e2
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752832"
---
# <a name="migrate-analog-devices"></a>Migrar dispositivos analógicos

Skype empresarial Server proporciona compatibilidad con dispositivos analógicos. En concreto, los dispositivos analógicos compatibles son los teléfonos de audio analógicos y los equipos de fax analógicos. Puede configurar las puertas de enlace calificadas para que admitan el uso de dispositivos analógicos en su entorno de Skype empresarial Server. Después de migrar a Skype empresarial Server 2019, también debe migrar los objetos de contacto asociados con los dispositivos analógicos. Use el shell de administración de Skype empresarial Server para recuperar primero todos los objetos de contacto asociados con los dispositivos analógicos heredados y, a continuación, mover dichos objetos al grupo de servidores de Skype empresarial 2019.

### <a name="to-migrate-analog-devices"></a>Para migrar dispositivos analógicos

1. Inicie el shell de administración de Skype empresarial Server: haga clic en **Inicio**, **todos los programas**, **Microsoft Skype empresarial Server 2019**y, a continuación, haga clic en **Shell de administración de Skype empresarial Server**.

2. En la línea de comandos, escriba lo siguiente:

   ```PowerShell
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsAnalogDevice -Target pool02.contoso.net
   ```

3. Compruebe que todos los objetos de contacto se han movido al grupo de Skype empresarial Server 2019. En la línea de comandos, escriba lo siguiente:

   ```PowerShell
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

4. Compruebe que todos los objetos de contacto están ahora asociados con el grupo de Skype empresarial Server 2019.


