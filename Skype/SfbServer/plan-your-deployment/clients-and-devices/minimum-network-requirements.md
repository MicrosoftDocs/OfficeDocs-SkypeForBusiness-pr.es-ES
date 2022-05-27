---
title: Requisitos de red mínimos de la aplicación Reuniones de Skype
ms.author: serdars
author: SerdarSoysal
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 6/4/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d9666787-e72b-41e1-ba37-aec5fb849a10
description: 'Resumen: información para las organizaciones que no usan Microsoft 365 o Office 365 y necesitan acceder a las reuniones hospedadas por organizaciones que sí lo hacen.'
ms.openlocfilehash: bdc3c6a3fba4968dd679a2039064c19786bd4661
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/25/2022
ms.locfileid: "65674532"
---
# <a name="skype-meetings-app-minimum-network-requirements"></a>Requisitos de red mínimos de la aplicación Reuniones de Skype

**Resumen:** Información para las organizaciones que no usan Microsoft 365 o Office 365 y necesitan acceder a las reuniones hospedadas por las organizaciones que lo hacen. Este artículo no está pensado para Office 365 ni Microsoft 365 usuarios finales.

Es posible que los usuarios de la aplicación de reuniones de Skype en organizaciones que no usan Microsoft 365 o Office 365 necesiten asistir a reuniones hospedadas en Skype Empresarial Online. Para asistir a estas reuniones, los administradores de red deben permitir los siguientes FQDN, direcciones IP y puertos a través de su firewall.

## <a name="requirements-for-skype-meetings-app-connectivity"></a>Requisitos para la conectividad de Skype Meetings App

La información que se muestra aquí es un subconjunto de la información de [Office 365 direcciones URL e intervalos de direcciones IP](/microsoft-365/enterprise/urls-and-ip-address-ranges). Ese tema es mucho más detallado y siempre será actual.

|Aplicación|FQDN de destino|Direcciones IP|Puertos|
|---|---------|---------|---------|
|**Skype aplicación de reuniones**|\*.lync.com <br/>\*.infra.lync.com<br/>\*.pipe.aria.microsoft.com<br/>\*.sfbassets.com<br/>\*.msecnd.net<br/>\*broadcast.officeapps.live.com<span></span> <br/>\*powerpoint.officeapps.live.com<span></span> <br/>\*.office.live.com<br/>\*.cdn.office.net<br/>*.s-microsoft.com<br/>|Estas direcciones IP se actualizan con frecuencia. Consulte [los intervalos IP Skype Empresarial y Microsoft Teams](/microsoft-365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams), así como [los intervalos IP de Office](/microsoft-365/enterprise/urls-and-ip-address-ranges)|TCP: 80 & 443<br/>UDP: 3478-3481|
|**Teams**|\*<span></span>.microsoft.com <br/>\*<span></span>.skype.com|Estas direcciones IP se actualizan con frecuencia. Consulte [los intervalos IP Skype Empresarial y Microsoft Teams](/microsoft-365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams), así como [los intervalos IP de Office](/microsoft-365/enterprise/urls-and-ip-address-ranges)|TCP: 443 <br/> UDP: 3478-3481|

## <a name="see-also"></a>Vea también
<a name="BKMK_Conferencing"> </a>

[Planear clientes de reuniones (aplicación web y aplicación de reuniones)](meetings-clients.md)

[Implementación de clientes web descargables en Skype Empresarial Server](../../deploy/deploy-clients/deploy-web-downloadable-clients.md)

[Plataformas admitidas para Skype Aplicación de reuniones](https://support.office.com/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)
