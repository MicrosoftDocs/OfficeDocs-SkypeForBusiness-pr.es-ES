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
ms.localizationpriority: medium
description: Skype Empresarial Server admite dispositivos analógicos. En concreto, los dispositivos analógicos compatibles son teléfonos de audio analógico y máquinas de fax analógico. Puede configurar las puertas de enlace calificadas para admitir el uso de dispositivos analógicos en el entorno Skype Empresarial Server usuario. Después de migrar a Skype Empresarial Server 2019, también debe migrar los objetos de contacto asociados con los dispositivos analógicos. Use Skype Empresarial Server Shell de administración para recuperar primero todos los objetos de contacto asociados con los dispositivos analógicos heredados y, a continuación, mover esos objetos al grupo de servidores de Skype Empresarial Server 2019.
ms.openlocfilehash: d64552a53b5cb37187a25febe5ce6171d1c64ec9
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "58599695"
---
# <a name="migrate-analog-devices"></a>Migrar dispositivos analógicos

Skype Empresarial Server admite dispositivos analógicos. En concreto, los dispositivos analógicos compatibles son teléfonos de audio analógico y máquinas de fax analógico. Puede configurar las puertas de enlace calificadas para admitir el uso de dispositivos analógicos en el entorno Skype Empresarial Server usuario. Después de migrar a Skype Empresarial Server 2019, también debe migrar los objetos de contacto asociados con los dispositivos analógicos. Use Skype Empresarial Server Shell de administración para recuperar primero todos los objetos de contacto asociados con los dispositivos analógicos heredados y, a continuación, mover esos objetos al grupo de servidores de Skype Empresarial Server 2019.

### <a name="to-migrate-analog-devices"></a>Para migrar dispositivos analógicos

1. Inicie el Shell Skype Empresarial Server administración: haga clic en Inicio **,** en Todos los **programas,** en **Microsoft Skype Empresarial Server 2019** y, a continuación, haga clic en **Skype Empresarial Server Shell de administración**.

2. En la línea de comandos, escriba lo siguiente:

   ```PowerShell
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsAnalogDevice -Target pool02.contoso.net
   ```

3. Compruebe que todos los objetos de contacto se hayan movido al grupo Skype Empresarial Server 2019. En la línea de comandos, escriba lo siguiente:

   ```PowerShell
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

4. Compruebe que todos los objetos de contacto están asociados al grupo Skype Empresarial Server 2019.


