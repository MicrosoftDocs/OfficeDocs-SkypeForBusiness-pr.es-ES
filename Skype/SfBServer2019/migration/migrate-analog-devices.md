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
description: Skype Empresarial Server proporciona compatibilidad con dispositivos analógicos. En concreto, los dispositivos analógicos compatibles son teléfonos de audio analógicos y faxes analógicos. Puede configurar las puertas de enlace cualificadas para admitir el uso de dispositivos analógicos en su entorno de Skype Empresarial Server. Después de migrar a Skype Empresarial Server 2019, también debe migrar los objetos de contacto asociados con los dispositivos analógicos. Use el Shell de administración de Skype Empresarial Server para recuperar primero todos los objetos de contacto asociados con los dispositivos analógicos heredados y, a continuación, mueva esos objetos al grupo de Skype Empresarial Server 2019.
ms.openlocfilehash: 7b90a52486725c2cf30856dc643660d569d698e2
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752832"
---
# <a name="migrate-analog-devices"></a>Migrar dispositivos analógicos

Skype Empresarial Server proporciona compatibilidad con dispositivos analógicos. En concreto, los dispositivos analógicos compatibles son teléfonos de audio analógicos y faxes analógicos. Puede configurar las puertas de enlace cualificadas para admitir el uso de dispositivos analógicos en su entorno de Skype Empresarial Server. Después de migrar a Skype Empresarial Server 2019, también debe migrar los objetos de contacto asociados con los dispositivos analógicos. Use el Shell de administración de Skype Empresarial Server para recuperar primero todos los objetos de contacto asociados con los dispositivos analógicos heredados y, a continuación, mueva esos objetos al grupo de Skype Empresarial Server 2019.

### <a name="to-migrate-analog-devices"></a>Para migrar dispositivos analógicos

1. Inicie el Shell de administración de Skype Empresarial Server: Haga clic en **Inicio,** en Todos los **programas,** en **Microsoft Skype Empresarial Server 2019** y, a continuación, en Shell de administración de Skype Empresarial **Server.**

2. En la línea de comandos, escriba lo siguiente:

   ```PowerShell
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsAnalogDevice -Target pool02.contoso.net
   ```

3. Compruebe que todos los objetos de contacto se hayan movido al grupo de Skype Empresarial Server 2019. En la línea de comandos, escriba lo siguiente:

   ```PowerShell
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

4. Compruebe que todos los objetos de contacto están ahora asociados con el grupo de Skype Empresarial Server 2019.


