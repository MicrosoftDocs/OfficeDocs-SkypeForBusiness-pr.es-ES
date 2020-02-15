---
title: Requisitos de red mínimos para la aplicación reuniones de Skype
ms.author: v-lanac
author: lanachin
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 6/4/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d9666787-e72b-41e1-ba37-aec5fb849a10
description: 'Resumen: información para organizaciones que no usan Office 365 y necesitan acceder a reuniones hospedadas por organizaciones que sí lo hacen.'
ms.openlocfilehash: 162d05f9786f02258afa080e630c85d4b513db4e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42033194"
---
# <a name="skype-meetings-app-minimum-network-requirements"></a>Requisitos de red mínimos para la aplicación reuniones de Skype
 
**Resumen:**  Información para organizaciones que no usan Office 365 y necesitan acceder a reuniones hospedadas por organizaciones que sí lo hacen. Este artículo no está destinado a los usuarios de estas aplicaciones.
  
Para permitir que los usuarios usen la aplicación reuniones de Skype para asistir a reuniones hospedadas en Skype empresarial online, los administradores de red de las organizaciones que no usan Office 365 deberían tener la lista blanca o hacer que estén disponibles los FQDN, las direcciones IP y los puertos que se mencionan a continuación.

## <a name="requirements-for-skype-meetings-app-connectivity"></a>Requisitos para la conectividad de la aplicación reuniones de Skype

La información que se muestra aquí es un subconjunto de los [intervalos de direcciones IP y URL de Office 365](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US), lo que proporciona más profundidad y siempre será la más actualizada.
                    
 
|Aplicación |FQDN de destino  |Direcciones IP  |Puertos  |
|---|---------|---------|---------|
|**Aplicación Reuniones de Skype** | \*. lync.com <br/>\*. infra.lync.com<br/>\*. pipe.aria.microsoft.com<br/>\*. sfbassets.com<br/>\*. msecnd.net<br/>\*Broadcast<span></span>. officeapps.Live.com <br/>\*PowerPoint<span></span>. officeapps.Live.com <br/>\*. office.live.com<br/>\*. cdn.office.net<br/>*. s-microsoft.com<br/>        |   Estas direcciones IP se actualizan con frecuencia.  Ver los [rangos de IP de Skype empresarial](https://support.office.com/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip) , así como los [intervalos IP de Office](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)         |TCP: 80 &amp; 443<br/>UDP: 3478-3481<br/>
|**Teams**    | \*<span></span>. microsoft.com <br/>\*<span></span>. skype.com | Estas direcciones IP se actualizan con frecuencia.  Ver los [rangos de IP de Skype empresarial](https://support.office.com/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip) , así como los [intervalos IP de Office](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)      |TCP: 443 <br/> UDP: 3478-3481

## <a name="see-also"></a>Consulte también
<a name="BKMK_Conferencing"> </a>

[Planeación de clientes de reuniones (aplicación web y aplicación de reuniones)](meetings-clients.md)

[Implementar clientes Web descargables en Skype empresarial Server](../../deploy/deploy-clients/deploy-web-downloadable-clients.md)

[Plataformas compatibles con la aplicación reuniones de Skype](https://support.office.com/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)
