---
title: Configurar la federación para un proveedor de conferencias de audio en su implementación híbrida
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 12/8/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 08dedcce-0d3f-45da-8282-cf2634a41665
description: 'Resumen: Obtenga información sobre cómo configurar la federación para un proveedor de conferencias de audio en Skype para profesionales en línea.'
ms.openlocfilehash: 95ca4e369e42bf265d243842067f531907e26531
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="configure-federation-for-an-audio-conferencing-provider-in-your-hybrid-deployment"></a>Configurar la federación para un proveedor de conferencias de audio en su implementación híbrida
 
**Resumen:** Obtenga información sobre cómo configurar la federación para un proveedor de conferencias de audio en Skype para profesionales en línea.
  
Si desea usar un proveedor de audioconferencia (ACP) para la implementación híbrida (local con en línea), tiene que configurar la federación entre la implementación local y el asociado del ACP como servidor del asociado permitido. Para configurar la federación, agregue el dominio del asociado del ACP y el servidor perimetral (también se puede denominar servidor proxy de acceso) a la lista de dominios federados para la implementación local. Luego, su asociado del ACP tendrá que agregar el FQDN de su grupo de servidores perimetrales local a su lista de dominios federados permitidos. Póngase en contacto con su proveedor del ACP para más detalles. Su asociado del ACP tendrá que agregar el FQDN de su grupo de servidores perimetrales local a su lista de dominios federados permitidos.
  
- **Cómo agregar el dominio del ACP y el servidor perimetral como un dominio federado permitido**
    
    Para agregar el dominio ACP como un servidor de socio permitido (permitido dominio federado), siga los pasos de [Configuración de compatibilidad con dominios externos permitidos](http://technet.microsoft.com/library/3ee6e175-986d-4c33-b03a-b9f93083dca6.aspx). Para el servidor perimetral, agregue el FQDN del servidor perimetral del socio ACP. Puede que tenga que contactar con el asociado del ACP para obtener el FQDN del servidor perimetral, que el ACP también puede denominar servidor proxy de acceso.
    
- **Proporcionar el FQDN de su grupo de servidores perimetrales al asociado del ACP**
    
    El asociado del ACP tiene que configurar la federación para agregar su dominio local como un servidor de asociado permitido agregando el FQDN de su grupo de servidores perimetrales como un dominio federado permitido.
    

