---
title: Requisitos de red mínimos de la aplicación Reuniones de Skype
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 6/4/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d9666787-e72b-41e1-ba37-aec5fb849a10
description: 'Resumen: Información para las organizaciones que no utilizan Office 365 y necesita tener acceso a reuniones hospedadas por las organizaciones que realizan.'
ms.openlocfilehash: e186b08a09f52e8de2d3f28867a4a0a30cdb1732
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/05/2018
ms.locfileid: "19577039"
---
# <a name="skype-meetings-app-minimum-network-requirements"></a>Requisitos de red mínimos de la aplicación Reuniones de Skype
 
**Resumen:**  Información de las organizaciones que no utilizan Office 365 y necesita tener acceso a reuniones hospedadas por las organizaciones que realizan. En este artículo no está pensada para los usuarios de estas aplicaciones.
  
Para permitir a los usuarios a usar la aplicación de las reuniones de Skype para asistir a reuniones hospedadas en Skype para Online de negocio, los administradores de red de las organizaciones que no usan <token>nm-office-365-short</token> , deben lista blanca o en caso contrario, poner a disposición los FQDN, IP y los puertos que se mencionan a continuación.

## <a name="requirements-for-skype-meetings-app-connectivity"></a>Requisitos para la conectividad de la aplicación Reuniones de Skype

La información que se muestra aquí es un subconjunto de [los intervalos de direcciones IP y URL de Office 365](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US), que proporciona más profundidad y siempre será el más actualizado.
                    
 
|Aplicación |FQDN de destino  |Direcciones IP  |Puertos  |
|---|---------|---------|---------|
|**Aplicación de las reuniones de Skype** | \*. lync.com <br/>\*. infra.lync.com<br/>\*. pipe.aria.microsoft.com<br/>\*. sfbassets.com<br/>\*. msecnd.net<br/>\*difusión<span></span>. officeapps.live.com <br/>\*PowerPoint<span></span>. officeapps.live.com <br/>\*. office.live.com<br/>\*. cdn.office.net<br/>*.s microsoft.com<br/>        |   Estas direcciones IP se actualizan con frecuencia.  Vea [Skype para rangos IP empresarial](https://support.office.com/en-us/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip) , así como [Rangos de IP de Office Online](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)         |TCP: 80 &amp; 443<br/>UDP: 3478-3481<br/>
|**Teams**    | *. microsoft.com <br/> *. skype.com | Estas direcciones IP se actualizan con frecuencia.  Vea [Skype para rangos IP empresarial](https://support.office.com/en-us/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip) , así como [Rangos de IP de Office Online](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)      |TCP: 443 <br/> UDP: 3478-3481

## <a name="see-also"></a>Vea también
<a name="BKMK_Conferencing"> </a>

[Planeación de los clientes de las reuniones (Web App y aplicación de las reuniones)](meetings-clients.md)

[Implementar a los clientes que se pueden descargar de Web en Skype para Business Server 2015](../../deploy/deploy-clients/deploy-web-downloadable-clients.md)

[Plataformas admitidas para la aplicación de las reuniones de Skype](https://support.office.com/en-US/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)