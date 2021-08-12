---
title: Configurar la federación para un proveedor de audioconferencia en la implementación híbrida
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
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
ms.custom: ''
description: 'Resumen: obtenga información sobre cómo configurar la federación para un proveedor de audioconferencia en Skype Empresarial Online.'
ms.openlocfilehash: 3e01615c65777508c2adead26dd15ca85afbb102e04d8ba57492826942f86672
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54301826"
---
# <a name="configure-federation-for-an-audio-conferencing-provider-in-your-hybrid-deployment"></a>Configurar la federación para un proveedor de audioconferencia en la implementación híbrida

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]


**Resumen:** Obtenga información sobre cómo configurar la federación para un proveedor de audioconferencia en Skype Empresarial Online.

Si desea usar un proveedor de audioconferencia (ACP) en la implementación híbrida (local con en línea), debe configurar la federación entre la implementación local y el partner ACP como un servidor de partners permitido. Puede configurar la federación agregando el dominio de socio ACP y el servidor perimetral (esto también se puede llamar proxy de acceso) a la lista Dominios federados para la implementación local. A continuación, el socio ACP debe agregar el FQDN del grupo de servidores perimetrales local a su lista de dominios federados permitidos. Póngase en contacto con su proveedor de ACP para obtener más información. A continuación, el socio ACP debe agregar el FQDN del grupo de servidores perimetrales local a su lista de dominios federados permitidos.

- **Agregar el dominio ACP y el servidor perimetral como un dominio federado permitido**

    Para agregar el dominio ACP como un servidor asociado permitido (dominio federado permitido), siga los pasos descritos en Configurar la compatibilidad con [dominios externos permitidos](/previous-versions/office/lync-server-2013/lync-server-2013-configure-support-for-allowed-external-domains). Para el servidor perimetral, agregue el FQDN del servidor perimetral del socio ACP. Es posible que deba ponerse en contacto con su partner ACP para obtener el FQDN de su servidor perimetral, al que también puede hacer referencia su ACP como su proxy de acceso.

- **Proporcionar el FQDN del grupo de servidores perimetrales al socio ACP**

    El partner ACP debe configurar la federación para agregar el dominio local como un servidor de partners permitido agregando el FQDN del grupo de servidores perimetrales como un dominio federado permitido.