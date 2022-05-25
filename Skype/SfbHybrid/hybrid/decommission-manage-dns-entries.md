---
title: Administración de entradas DNS al retirar el entorno local
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: Instrucciones sobre cómo administrar las entradas DNS al retirar el entorno de Skype Empresarial local.
ms.openlocfilehash: c21a736c19ecec41ddc0458931675ca8ede34ed2
ms.sourcegitcommit: c53c22069b1babce7a2364de631057ff501ca1c0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/25/2022
ms.locfileid: "65671886"
---
# <a name="update-dns-entries-to-enable-your-organization-to-be-all-teams-only"></a>Actualizar las entradas DNS para permitir que la organización sea solo Teams

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Las organizaciones que anteriormente tenían implementaciones locales de Skype Empresarial Server o Lync Server pueden seguir teniendo entradas DNS que apunten a una implementación de Skype Empresarial local. Estos registros son necesarios si su organización incluye usuarios locales Skype Empresarial. Sin embargo, una vez que la organización ya no tiene ningún Skype Empresarial local o usuarios de Lync Server, estos registros originales ya no son necesarios para la implementación local y **estas entradas DNS deben actualizarse para que apunten a Microsoft 365 (o en algunos casos quitados)** como parte de la migración del entorno local a solo Teams. *Microsoft no puede actualizar estos registros DNS en su nombre.*

Al intentar conceder TeamsOnly a todo el inquilino, Teams comprobará DNS para determinar si existe alguno de estos registros DNS enumerados a continuación en cada uno de los dominios comprobados de Microsoft 365 de su organización. Si se encuentran registros y apuntan a algo distinto de Microsoft 365, el intento de cambiar el modo de coexistencia del inquilino a TeamsOnly producirá un error de diseño. Esto impide que las organizaciones híbridas con usuarios locales apliquen por error el modo TeamsOnly al inquilino, ya que hacerlo interrumpiría la federación de todos los usuarios locales Skype Empresarial de la organización (ya sea mediante Teams o Skype Empresarial).

## <a name="how-to-identify-stale-dns-records"></a>Identificación de registros DNS obsoletos

Para identificar los registros DNS que impiden que su organización se convierta en todo Teams Solo, puede usar el centro de administración de Teams para cambiar el modo de coexistencia a TeamsOnly. Vaya a **Teams** >  **Teams configuración de actualización**. Los registros DNS que impidan que la organización se convierta en Teams Solo se incluirán en el mensaje de error.  En caso de que no se encuentre ningún registro DNS, el modo de coexistencia de su organización se cambiará a TeamsOnly.

Como alternativa, puede usar Teams PowerShell para hacer lo mismo, como se muestra a continuación:

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Global
   ```

## <a name="dns-records-to-be-updated"></a>Registros DNS que se van a actualizar

Si su organización ya no tiene usuarios hospedados en Skype Empresarial Server local o Lync Server, debe hacer lo siguiente:

- Actualice la lista de registros DNS de Skype Empresarial siguiente para que apunte a Microsoft 365 (en lugar de la implementación local). Si tiene más de un dominio SIP, debe hacerlo para cada dominio SIP que sea un dominio Microsoft 365 comprobado.

- Quite Skype Empresarial registros DNS si ya no se usa el dominio SIP.

En cada dominio en el que encuentre cualquiera de los registros siguientes, actualícelos de la siguiente manera:

|Tipo de registro|Nombre|TTL|Prioridad|Peso|Puerto|Valor|
|---|---|---|---|---|---|---|
|SRV|_sipfederationtls._tcp|3600|100|1 |5061|sipfed.online.lync.com|
|SRV|_sip._tls|3600|100|1 |443|sipdir.online.lync.com|
|CNAME|lyncdiscover|3600|N/D|N/D|N/D|webdir.online.lync.com|
|CNAME|sip|3600|N/D|N/D|N/D|sipdir.online.lync.com|

Además, los registros CNAME para meet o dialin (si están presentes) se pueden eliminar. Por último, se deben quitar los registros DNS de Skype Empresarial en la red interna.

> [!NOTE]
> En raras ocasiones, el cambio de DNS de que apunte localmente a Microsoft 365 de su organización puede hacer que la federación con otras organizaciones deje de funcionar hasta que otra organización actualice su configuración de federación:
>
> - Todas las organizaciones federadas que usen el modelo anterior de federación directa (también conocido como Servidor de partners permitido) tendrán que actualizar sus entradas de dominio permitidas para que su organización quite el FQDN de proxy. Este modelo de federación heredado no se basa en registros SRV de DNS, por lo que dicha configuración dejará de estar actualizada una vez que la organización se mueva a la nube.
>
> - Cualquier organización federada que no tenga un proveedor de hospedaje habilitado para sipfed.online.lync.<span> com tendrá que actualizar su configuración para habilitarlo. Esta situación solo es posible si la organización federada es puramente local y nunca ha federado con ningún inquilino híbrido o en línea. En tal caso, la federación con estas organizaciones no funcionará hasta que habiliten su proveedor de hospedaje.
>
> Si sospecha que cualquiera de sus asociados federados puede usar federación directa o no ha federado con ninguna organización híbrida o en línea, le sugerimos que les envíe una comunicación al respecto mientras se prepara para completar la migración a la nube.
