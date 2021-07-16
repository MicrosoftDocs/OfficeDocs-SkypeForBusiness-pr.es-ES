---
title: Administrar entradas DNS al retirar el entorno local
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: Instrucciones para administrar las entradas DNS al retirar el entorno Skype Empresarial local.
ms.openlocfilehash: bd8f3873ab28ef8e0b7ade86ffc95b4d5bb4e4cb
ms.sourcegitcommit: 405b22cfd94e50d651f4c3f73fb46780cd8a6d06
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/15/2021
ms.locfileid: "53459009"
---
# <a name="update-dns-entries-to-enable-your-organization-to-be-all-teams-only"></a>Actualizar entradas DNS para permitir que la organización sea Teams solo

Las organizaciones que anteriormente tenían implementaciones locales de Skype Empresarial Server o Lync Server aún pueden tener entradas DNS que apunten a una implementación Skype Empresarial local. Estos registros son necesarios si su organización incluye usuarios Skype Empresarial local. Sin embargo, una vez que la organización ya no tiene usuarios locales Skype Empresarial o Lync Server, estos registros ya no son necesarios. De hecho, como parte de completar la migración de local a Teams, estos registros deben actualizarse para que apunten a Microsoft 365 o quitar. Microsoft no puede realizar este paso por usted.

Al intentar conceder TeamsOnly a todo el inquilino, Teams comprobará DNS para determinar si existe alguno de estos registros DNS para su organización. Si se encuentra algún registro y apunta a algo que no sea Microsoft 365, el intento de cambiar el modo de coexistencia del espacio empresarial a TeamsOnly producirá un error por diseño. Este diseño es para impedir que las organizaciones híbridas con usuarios locales apliquen por error el modo TeamsOnly al inquilino, ya que al hacerlo se rompería la federación para los usuarios de Skype Empresarial locales (ya sea mediante Teams o Skype Empresarial).

Además, estos registros deben actualizarse para que pueda conceder TeamsOnly a todo el inquilino.

> [!Note] 
> En raras ocasiones, cambiar DNS de apuntar localmente a Microsoft 365 para su organización puede provocar que la federación con otras organizaciones deje de funcionar hasta que otra organización actualice su configuración de federación:
>
> - Las organizaciones federadas que usan el modelo de federación directa anterior (también conocido como Servidor de partners permitidos) tendrán que actualizar las entradas de dominio permitidas para su organización para quitar el FQDN de proxy. Este modelo de federación heredado no se basa en registros SRV de DNS, por lo que dicha configuración se desatendrán una vez que la organización se mueva a la nube.
> 
> - Cualquier organización federada que no tenga un proveedor de hospedaje habilitado para sipfed.online.lync. <span> com tendrá que actualizar su configuración para habilitarlo. Esta situación solo es posible si la organización federada es puramente local y nunca se ha federado con ningún inquilino híbrido o en línea. En tal caso, la federación con estas organizaciones no funcionará hasta que habiliten su proveedor de hospedaje.
>
> Si sospecha que alguno de sus socios federados puede estar usando Direct Federation o no haber federado con ninguna organización híbrida o en línea, le sugerimos que envíe una comunicación al respecto mientras se prepara para completar la migración a la nube.

## <a name="how-to-identify-stale-dns-records"></a>Cómo identificar registros DNS obsoletos

Para identificar los registros DNS que impiden que su organización se convierta en Teams Solo, puede usar el Centro de administración de Teams para cambiar el modo de coexistencia a TeamsOnly. Vaya a **Configuración de toda la** organización Teams  ->  **Actualizar**. Los registros DNS que impidan que la organización se convierta en Teams Solo se incluirán en el mensaje de error.  En el caso de que no se encuentra ningún registro DNS, el modo de coexistencia de la organización se cambiará a TeamsOnly. 

## <a name="how-to-remove-stale-dns-records"></a>Cómo quitar registros DNS obsoletos

Si su organización ya no tiene usuarios locales Skype Empresarial Server o Lync Server, debe hacer lo siguiente:

- Actualice Skype Empresarial DNS para que apunten a Microsoft 365 (en lugar de la implementación local).

- Quite Skype Empresarial DNS si ya no se usa el dominio SIP. 

En cada dominio en el que encuentre cualquiera de los siguientes registros, actualíguelos de la siguiente manera:

| Tipo de registro | Nombre | TTL | Prioridad | Peso | Puerto | Valor |
| :-----| :-----| :---- | :-----| :-----| :-----| :-----|
| SRV | _sipfederationtls.tcp | 3600 |  100 | 1 | 5061  | sipfed.online.lync.com |
| SRV | _sip.tls | 3600  | 100 |    1   | 443   | sipdir.online.lync.com |
| CNAME | lyncdiscover |    3600 |  N/D |   N/D |   N/D |   webdir.online.lync.com |
| CNAME |   sip | 3600 |    N/D |   N/D  | N/D |    sipdir.online.lync.com |
|||||||




