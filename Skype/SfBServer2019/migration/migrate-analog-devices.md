---
title: Migrar dispositivos analógicos
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Skype empresarial Server proporciona compatibilidad con dispositivos analógicos. Específicamente, los dispositivos analógicos compatibles son teléfonos de audio analógicos y equipos de fax analógico. Puede configurar las puertas de enlace calificadas para que admitan el uso de dispositivos analógicos en el entorno de Skype empresarial Server. Después de migrar a Skype empresarial Server 2019, también debe migrar los objetos de contacto asociados con los dispositivos analógicos. Use el shell de administración de Skype empresarial Server para recuperar primero todos los objetos de contacto asociados con los dispositivos analógicos heredados y, a continuación, mover esos objetos al grupo de servidores de Skype empresarial 2019.
ms.openlocfilehash: 7ca36c92270685709c479a1d164f60d0960c526c
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2020
ms.locfileid: "40990095"
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


