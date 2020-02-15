---
title: Requisitos del cliente de Skype empresarial en Mac
ms.author: v-lanac
author: lanachin
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
description: Lea este tema para obtener información sobre los requisitos de hardware, software y la infraestructura para ejecutar Skype empresarial en un equipo Mac.
ms.openlocfilehash: f4f62246a86dabeb628755d3c75a10bc285ede12
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42013463"
---
# <a name="skype-for-business-on-mac-client-requirements"></a>Requisitos del cliente de Skype empresarial en Mac
 
Lea este tema para obtener información sobre los requisitos de hardware, software y la infraestructura para ejecutar Skype empresarial en un equipo Mac.
  
El [cliente de Skype empresarial en Mac](https://products.office.com/skype-for-business/download-app?tab=tabs-3#Mac) está disponible para su descarga.
  
## <a name="hardware-and-software-requirements-for-skype-for-business-on-mac"></a>Requisitos de hardware y software para Skype empresarial en Mac

El cliente de Skype empresarial en Mac requiere Mac OS X el capitan y versiones posteriores, y usa al menos 100 MB de espacio en disco. Admitimos el uso de todos los dispositivos de audio y vídeo integrados. Los dispositivos externos deben encontrarse en el [Catálogo de soluciones de Skype empresarial](https://partnersolutions.skypeforbusiness.com/solutionscatalog). 
  
> [!NOTE]
> Esta lista es preliminar y algunos dispositivos pueden estar calificados para Lync, pero no son compatibles con Skype empresarial en Mac. Consulte los [requisitos del sistema para conocer](https://products.office.com/office-system-requirements) el hardware mínimo necesario.
  
### <a name="legacy-mac-clients"></a>Clientes Mac heredados

Skype empresarial Server 2015 también admite los siguientes clientes heredados en equipos que ejecutan Mac OS 10.5.8 o versiones más recientes de los sistemas operativos de Service Pack o versiones (basados en Intel) (no se admite actualmente el sistema operativo Mac OS 10,9). Para obtener más información sobre las características admitidas, consulte [comparación de características de cliente de escritorio para Skype empresarial](desktop-feature-comparison.md).
  
- Microsoft Lync para Mac 2011 (consulte la [Guía de implementación de Lync para mac 2011](https://go.microsoft.com/fwlink/p/?LinkId=268786))
    
- Microsoft Communicator para Mac 2011 (consulte la [Guía de implementación de Communicator para mac 2011](https://go.microsoft.com/fwlink/p/?LinkId=268787))
 
Skype empresarial Server 2019 no es compatible con estos clientes.
   
## <a name="infrastructure-requirements-for-skype-for-business-on-mac"></a>Requisitos de infraestructura para Skype empresarial en Mac
<a name="Infrastructure"> </a>

El cliente de Skype empresarial para Mac aprovecha tanto la plataforma de administración de comunicaciones unificadas (UCMP) como la API Web de comunicaciones unificadas (UCWA) que nuestros clientes de movilidad usan.
  
El cliente tiene los mismos requisitos que nuestros clientes de movilidad en cuanto a que debe tener un servidor perimetral de acceso y un proxy inverso implementados en una configuración admitida. 
  
### <a name="authentication"></a>Autenticación

El cliente de Skype empresarial para Mac admite la autenticación basada en certificados, la autenticación moderna de Microsoft y la autenticación multifactor cuando se implementan y habilitan.
  
> [!NOTE]
> Debido a una limitación actual, las credenciales de Exchange del usuario deben ser las mismas que las credenciales de Skype empresarial. 
  
### <a name="certificates"></a>Certificados

Los certificados en uso en los servidores perimetrales de acceso, proxy inverso y front-end no deben usar el algoritmo de hash SHA-512.
  
La lista de revocación de certificados HTTP debe estar definida y accesible para el cliente. Por ejemplo, no se admite una entrada LDAP en el certificado como la lista de revocación de certificados.
  
### <a name="dns"></a>DNS

La movilidad debe implementarse correctamente para que Skype empresarial en el cliente Mac funcione correctamente. Un escenario de error común es tener las siguientes entradas DNS que se puedan resolver en la red interna:
  
- lyncdiscoverinternal. \<sipdomain\>
    
- lyncdiscover. \<sipdomain\>
    
Para obtener más información, consulte: [Deploying Mobility in Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=798224)y la guía de [movilidad de Microsoft Lync Server 2010](https://go.microsoft.com/fwlink//p/?LinkId=798226).
  
## <a name="see-also"></a>Consulte también
<a name="Infrastructure"> </a>

[Requisitos de DNS para Skype empresarial Server](../../plan-your-deployment/network-requirements/dns.md)

[Preguntas más frecuentes](https://go.microsoft.com/fwlink/p/?LinkId=798227)
  
[Problemas conocidos](https://go.microsoft.com/fwlink/p/?LinkId=798228)
