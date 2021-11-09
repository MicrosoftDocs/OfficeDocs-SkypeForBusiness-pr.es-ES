---
title: Skype Empresarial requisitos de cliente de Mac
ms.author: v-mahoffman
author: HowlinWolf-92
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 790d3e89-2b68-411b-b282-38de5d34dd10
description: Lea este tema para obtener información sobre los requisitos de hardware, software e infraestructura para ejecutar Skype Empresarial en un Mac.
ms.openlocfilehash: b7d3ce484ea3e333e85c2f8473cdcdaaebe44057
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/08/2021
ms.locfileid: "60847223"
---
# <a name="skype-for-business-on-mac-client-requirements"></a>Skype Empresarial requisitos de cliente de Mac
 
Lea este tema para obtener información sobre los requisitos de hardware, software e infraestructura para ejecutar Skype Empresarial en un Mac.
  
El [Skype Empresarial en Mac Client](https://products.office.com/skype-for-business/download-app?tab=tabs-3#Mac) está disponible para su descarga.
  
## <a name="hardware-and-software-requirements-for-skype-for-business-on-mac"></a>Requisitos de hardware y software para Skype Empresarial en Mac

El Skype Empresarial de Mac requiere Mac OS X El Capitan y superior, y usa al menos 100 MB de espacio en disco. Se admite el uso de todos los dispositivos de audio y vídeo integrados. Los dispositivos externos deben aparecer en [Microsoft Teams dispositivos](https://www.microsoft.com/microsoft-teams/across-devices/devices). 
  
> [!NOTE]
> Esta lista es preliminar y algunos dispositivos pueden estar calificados para Lync, pero no se admiten Skype Empresarial en mac. Consulte los [requisitos del sistema](https://products.office.com/office-system-requirements) para el hardware mínimo necesario.
  
### <a name="legacy-mac-clients"></a>Clientes mac heredados

Skype Empresarial Server 2015 también admite los siguientes clientes heredados en equipos que ejecutan Mac OS 10.5.8 o los sistemas operativos service pack o release más recientes (basados en Intel) (el sistema operativo Mac OS 10.9 no es compatible actualmente). Para obtener más información sobre las características admitidas, consulte Comparación de características [de cliente de escritorio para Skype Empresarial](desktop-feature-comparison.md).
  
- Microsoft Lync para Mac 2011 (consulte Guía de implementación de [Lync para Mac 2011](/previous-versions/office/office-for-mac-2011/jj984275(v=office.14)))
    
- Microsoft Communicator para Mac 2011 (vea [Communicator para Mac 2011 Deployment Guide](/previous-versions/office/office-for-mac-2011/jj984270(v=office.14)))
 
Estos clientes no son compatibles con Skype Empresarial Server 2019.
   
## <a name="infrastructure-requirements-for-skype-for-business-on-mac"></a>Requisitos de infraestructura para Skype Empresarial en Mac
<a name="Infrastructure"> </a>

El Skype Empresarial cliente de Mac aprovecha tanto la Plataforma de administración de comunicaciones unificadas (UCMP) como la API web de comunicaciones unificadas (UCWA) que usan nuestros clientes de movilidad.
  
El cliente tiene los mismos requisitos que nuestros clientes de movilidad, ya que debe tener un servidor perimetral de acceso y un proxy inverso implementados en una configuración compatible. 
  
### <a name="authentication"></a>Autenticación

El Skype Empresarial en Mac admite la autenticación basada en certificados, la autenticación moderna de Microsoft y la autenticación multifactor cuando se implementan y habilitan.
  
> [!NOTE]
> Debido a una limitación actual, las credenciales de Exchange del usuario deben ser las mismas que sus Skype Empresarial credenciales. 
  
### <a name="certificates"></a>Certificados

Los certificados que se usan en los servidores perimetrales de acceso, proxy inverso y front-end no deben usar el algoritmo hash SHA-512.
  
El cliente debe definir y tener acceso a la lista de revocación de certificados HTTP. Por ejemplo, no se admite una entrada LDAP en el certificado como lista de revocación de certificados.
  
### <a name="dns"></a>DNS

La movilidad debe implementarse correctamente para que el Skype Empresarial en el cliente Mac funcione correctamente. Un escenario de error común es que ambas entradas DNS se puedan resolver en la red interna:
  
- lyncdiscoverinternal.\<sipdomain\>
    
- lyncdiscover.\<sipdomain\>
    
Para obtener más información, consulte: Implementación de movilidad [en Lync Server 2013](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-mobility)y la Guía de movilidad de [Microsoft Lync Server 2010](https://go.microsoft.com/fwlink//p/?LinkId=798226).
  
## <a name="see-also"></a>Consulte también
<a name="Infrastructure"> </a>

[Requisitos dns para Skype Empresarial Server](../../plan-your-deployment/network-requirements/dns.md)

[Preguntas más frecuentes](https://go.microsoft.com/fwlink/p/?LinkId=798227)
  
[Problemas conocidos](https://go.microsoft.com/fwlink/p/?LinkId=798228)