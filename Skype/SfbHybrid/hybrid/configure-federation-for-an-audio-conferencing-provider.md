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
description: 'Resumen: obtenga información sobre cómo configurar la federación para un proveedor de servicios de audioconferencia en Skype Empresarial Online.'
ms.openlocfilehash: a19704327d1cf5591a1ebb3f62aa23f46fe09d10
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726890"
---
# <a name="configure-federation-for-an-audio-conferencing-provider-in-your-hybrid-deployment"></a>Configurar la federación para un proveedor de audioconferencia en la implementación híbrida

**Resumen:** Obtenga información sobre cómo configurar la federación para un proveedor de audioconferencia en Skype Empresarial Online.

Si desea usar un proveedor de audioconferencia (ACP) en su implementación híbrida (local con conexión), debe configurar la federación entre la implementación local y el asociado acp como un servidor de asociado permitido. Puede configurar la federación agregando el dominio de socio ACP y el servidor perimetral (también denominado proxy de acceso) a la lista de dominios federados para la implementación local. A continuación, el asociado del ACP debe agregar el FQDN del grupo de servidores perimetrales local a su lista de dominios federados permitidos. Póngase en contacto con su proveedor de ACP para obtener más información. A continuación, el asociado del ACP debe agregar el FQDN del grupo de servidores perimetrales local a su lista de dominios federados permitidos.

- **Agregar el dominio ACP y el servidor perimetral como un dominio federado permitido**

    Para agregar el dominio ACP como un servidor de socio permitido (dominio federado permitido), siga los pasos descritos en Configurar compatibilidad para [dominios externos permitidos.](https://technet.microsoft.com/library/3ee6e175-986d-4c33-b03a-b9f93083dca6.aspx) Para el servidor perimetral, agregue el FQDN del servidor perimetral del socio ACP. Es posible que tenga que ponerse en contacto con su partner de ACP para obtener el FQDN de su servidor perimetral, al que también puede hacer referencia su ACP como su proxy de acceso.

- **Proporcionar el FQDN del grupo de servidores perimetrales al asociado del ACP**

    El socio ACP debe configurar la federación para agregar el dominio local como un servidor de asociado permitido agregando el FQDN del grupo de servidores perimetrales como un dominio federado permitido.


