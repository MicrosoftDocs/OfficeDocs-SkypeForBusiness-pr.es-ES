---
title: Requisitos de cliente de Skype Empresarial en Mac
ms.author: v-cichur
author: cichur
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 790d3e89-2b68-411b-b282-38de5d34dd10
description: Lea este tema para obtener información sobre los requisitos de hardware, software e infraestructura para ejecutar Skype Empresarial en un Mac.
ms.openlocfilehash: 866eda0cc5e82db1da1b69bee3eb4bf26df6d7b2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51109286"
---
# <a name="skype-for-business-on-mac-client-requirements"></a>Requisitos de cliente de Skype Empresarial en Mac
 
Lea este tema para obtener información sobre los requisitos de hardware, software e infraestructura para ejecutar Skype Empresarial en un Mac.
  
Skype [Empresarial en mac Client](https://products.office.com/skype-for-business/download-app?tab=tabs-3#Mac) está disponible para su descarga.
  
## <a name="hardware-and-software-requirements-for-skype-for-business-on-mac"></a>Requisitos de hardware y software para Skype Empresarial en Mac

El cliente de Skype Empresarial en Mac requiere Mac OS X El Capitan y superior, y usa al menos 100 MB de espacio en disco. Se admite el uso de todos los dispositivos de audio y vídeo integrados. Los dispositivos externos deben estar en el [Catálogo de soluciones de Skype Empresarial.](https://partnersolutions.skypeforbusiness.com/solutionscatalog) 
  
> [!NOTE]
> Esta lista es preliminar y algunos dispositivos pueden estar calificados para Lync, pero no son compatibles con Skype Empresarial en Mac. Consulte los [requisitos del sistema](https://products.office.com/office-system-requirements) para el hardware mínimo necesario.
  
### <a name="legacy-mac-clients"></a>Clientes mac heredados

Skype Empresarial Server 2015 también admite los siguientes clientes heredados en equipos que ejecutan Mac OS 10.5.8 o los sistemas operativos service pack o release más recientes (basados en Intel) (el sistema operativo Mac OS 10.9 no es compatible actualmente). Para obtener más información sobre las características admitidas, vea Comparación de características [de cliente de escritorio para Skype Empresarial.](desktop-feature-comparison.md)
  
- Microsoft Lync para Mac 2011 (consulte Guía de implementación de [Lync para Mac 2011](/previous-versions/office/office-for-mac-2011/jj984275(v=office.14)))
    
- Microsoft Communicator para Mac 2011 (consulte [Communicator para Mac 2011 Deployment Guide](/previous-versions/office/office-for-mac-2011/jj984270(v=office.14)))
 
Skype Empresarial Server 2019 no admite estos clientes.
   
## <a name="infrastructure-requirements-for-skype-for-business-on-mac"></a>Requisitos de infraestructura para Skype Empresarial en Mac
<a name="Infrastructure"> </a>

El cliente de Skype Empresarial en Mac aprovecha tanto la Plataforma de administración de comunicaciones unificadas (UCMP) como la API web de comunicaciones unificadas (UCWA) que usan nuestros clientes de movilidad.
  
El cliente tiene los mismos requisitos que nuestros clientes de movilidad, ya que debe tener un servidor perimetral de acceso y un proxy inverso implementados en una configuración compatible. 
  
### <a name="authentication"></a>Autenticación

El cliente de Skype Empresarial en Mac admite la autenticación basada en certificados, la autenticación moderna de Microsoft y la autenticación multifactor cuando se implementan y habilitan.
  
> [!NOTE]
> Debido a una limitación actual, las credenciales de Exchange del usuario deben ser las mismas que sus credenciales de Skype Empresarial. 
  
### <a name="certificates"></a>Certificados

Los certificados que se usan en los servidores perimetrales de acceso, proxy inverso y front-end no deben usar el algoritmo hash SHA-512.
  
El cliente debe definir y tener acceso a la lista de revocación de certificados HTTP. Por ejemplo, no se admite una entrada LDAP en el certificado como lista de revocación de certificados.
  
### <a name="dns"></a>DNS

La movilidad debe implementarse correctamente para que Skype Empresarial en el cliente Mac funcione correctamente. Un escenario de error común es que ambas entradas DNS se puedan resolver en la red interna:
  
- lyncdiscoverinternal.\<sipdomain\>
    
- lyncdiscover.\<sipdomain\>
    
Para obtener más información, consulte: Implementación de movilidad [en Lync Server 2013](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-mobility)y la Guía de movilidad de [Microsoft Lync Server 2010](https://go.microsoft.com/fwlink//p/?LinkId=798226).
  
## <a name="see-also"></a>Ver también
<a name="Infrastructure"> </a>

[Requisitos dns para Skype Empresarial Server](../../plan-your-deployment/network-requirements/dns.md)

[Preguntas más frecuentes](https://go.microsoft.com/fwlink/p/?LinkId=798227)
  
[Problemas conocidos](https://go.microsoft.com/fwlink/p/?LinkId=798228)