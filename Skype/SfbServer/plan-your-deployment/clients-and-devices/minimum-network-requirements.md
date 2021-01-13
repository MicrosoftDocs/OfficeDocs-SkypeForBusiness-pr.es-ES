---
title: Requisitos de red mínimos de la aplicación Reuniones de Skype
ms.author: v-cichur
author: cichur
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
description: 'Resumen: información para organizaciones que no usan Microsoft 365 u Office 365 y necesitan acceder a reuniones hospedadas por organizaciones que sí lo usan.'
ms.openlocfilehash: d5e6b838ceddb4ea1195694eb0ad11a1d029a1bb
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816310"
---
# <a name="skype-meetings-app-minimum-network-requirements"></a>Requisitos de red mínimos de la aplicación Reuniones de Skype
 
**Resumen:**  Información para organizaciones que no usan Microsoft 365 u Office 365 y necesitan acceder a reuniones hospedadas por organizaciones que sí lo hacen. Este artículo no está pensado para los usuarios de estas aplicaciones.
  
Para permitir que los usuarios usen la aplicación Reuniones de Skype para asistir a reuniones hospedadas en Skype Empresarial Online, los administradores de red de organizaciones que no usan Microsoft 365 u Office 365 deben permitir o hacer disponibles los FQDN, ip y puertos mencionados a continuación.

## <a name="requirements-for-skype-meetings-app-connectivity"></a>Requisitos para la conectividad de la aplicación Reuniones de Skype

La información que se muestra aquí es un subconjunto de direcciones IP y URL de [Office 365,](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)que proporciona más profundidad y siempre será la más actualizada.
                    
 
|Aplicación |FQDN de destino  |Direcciones IP  |Puertos  |
|---|---------|---------|---------|
|**Aplicación Reuniones de Skype** | \*.lync.com <br/>\*.infra.lync.com<br/>\*.pipe.aria.microsoft.com<br/>\*.sfbassets.com<br/>\*.msecnd.net<br/>\*broadcast <span></span> .officeapps.live.com <br/>\*powerpoint <span></span> .officeapps.live.com <br/>\*.office.live.com<br/>\*.cdn.office.net<br/>*.s-microsoft.com<br/>        |   Estas direcciones IP se actualizan con frecuencia.  Vea [los intervalos IP de Skype](https://support.office.com/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip) Empresarial, así como los [intervalos IP de Office](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)         |TCP: 80 &amp; 443<br/>UDP: 3478-3481<br/>
|**Teams**    | \*<span></span>.microsoft.com <br/>\*<span></span>.skype.com | Estas direcciones IP se actualizan con frecuencia.  Vea [los intervalos IP de Skype](https://support.office.com/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip) Empresarial, así como los [intervalos IP de Office](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)      |TCP: 443 <br/> UDP: 3478-3481

## <a name="see-also"></a>Ver también
<a name="BKMK_Conferencing"> </a>

[Planeación de clientes de reuniones (aplicación web y aplicación de reuniones)](meetings-clients.md)

[Implementar clientes web descargables en Skype Empresarial Server](../../deploy/deploy-clients/deploy-web-downloadable-clients.md)

[Plataformas admitidas para la aplicación Reuniones de Skype](https://support.office.com/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)
