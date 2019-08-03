---
title: Configurar la Federación para un proveedor de servicios de audioconferencia en su implementación híbrida
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
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
description: 'Resumen: Obtenga información sobre cómo configurar la Federación para un proveedor de servicios de audioconferencia en Skype empresarial online.'
ms.openlocfilehash: faeae07c0662bc252e07bbf66ec463355e439461
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "36160770"
---
# <a name="configure-federation-for-an-audio-conferencing-provider-in-your-hybrid-deployment"></a>Configurar la Federación para un proveedor de servicios de audioconferencia en su implementación híbrida

**Resumen:** Obtenga información sobre cómo configurar la Federación para un proveedor de servicios de audioconferencia en Skype empresarial online.

Si desea usar un proveedor de servicios de audioconferencia (ACP) en su implementación híbrida (local con online), debe configurar la Federación entre su implementación local y el socio de ACP como servidor asociado permitido. Puede configurar la Federación agregando el dominio del asociado del ACP y el servidor perimetral (esto también puede llamarse servidor proxy de acceso) a la lista de dominios federados para la implementación local. A continuación, su partner ACP debe agregar el FQDN de su grupo de servidores perimetrales local a su lista de dominios federados permitidos. Póngase en contacto con su proveedor de ACP para obtener más detalles. A continuación, su partner ACP debe agregar el FQDN de su grupo de servidores perimetrales local a su lista de dominios federados permitidos.

- **Adición del dominio ACP y el servidor perimetral como un dominio federado permitido**

    Para agregar el dominio ACP como servidor asociado permitido (dominio federado permitido), siga los pasos de [configurar la compatibilidad con dominios externos permitidos](https://technet.microsoft.com/library/3ee6e175-986d-4c33-b03a-b9f93083dca6.aspx). Para el servidor perimetral, agregue el FQDN del servidor perimetral del asociado del ACP. Es posible que deba ponerse en contacto con su partner de ACP para obtener el FQDN de su servidor perimetral, al que también puede hacer referencia su ACP como su proxy de acceso.

- **Suministro del FQDN de su grupo de servidores perimetrales al asociado del ACP**

    El socio de ACP debe configurar la Federación para agregar el dominio local como servidor asociado permitido agregando el FQDN de su grupo de servidores perimetrales como un dominio federado permitido.


