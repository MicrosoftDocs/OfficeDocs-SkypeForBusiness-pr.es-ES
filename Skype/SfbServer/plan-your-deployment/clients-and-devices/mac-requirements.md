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
description: Lea este tema para obtener información sobre los requisitos de hardware, software e infraestructura para ejecutar Skype Empresarial en un Equipo Mac.
ms.openlocfilehash: 5f967bab3a5dcc41a3419324c9fe09b48a8fb674
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832170"
---
# <a name="skype-for-business-on-mac-client-requirements"></a>Requisitos de cliente de Skype Empresarial en Mac
 
Lea este tema para obtener información sobre los requisitos de hardware, software e infraestructura para ejecutar Skype Empresarial en un Equipo Mac.
  
El [cliente de Skype Empresarial en Mac](https://products.office.com/skype-for-business/download-app?tab=tabs-3#Mac) está disponible para su descarga.
  
## <a name="hardware-and-software-requirements-for-skype-for-business-on-mac"></a>Requisitos de hardware y software para Skype Empresarial en Mac

El cliente de Skype Empresarial en Mac requiere Mac OS X El Seba y superior, y usa al menos 100 MB de espacio en disco. Se admite el uso de todos los dispositivos de audio y vídeo integrados. Los dispositivos externos deben estar en el [Catálogo de soluciones de Skype Empresarial.](https://partnersolutions.skypeforbusiness.com/solutionscatalog) 
  
> [!NOTE]
> Esta lista es preliminar y algunos dispositivos pueden estar calificados para Lync, pero no son compatibles con Skype Empresarial en Mac. Consulte los [requisitos del sistema](https://products.office.com/office-system-requirements) para el hardware mínimo necesario.
  
### <a name="legacy-mac-clients"></a>Clientes mac heredados

Skype Empresarial Server 2015 también admite los siguientes clientes heredados en equipos que ejecutan Mac OS 10.5.8 o los últimos sistemas operativos Service Pack o Release (basados en Intel) (actualmente no se admite el sistema operativo Mac OS 10.9). Para obtener más información sobre las características admitidas, vea la comparación de características [de cliente de escritorio para Skype Empresarial.](desktop-feature-comparison.md)
  
- Microsoft Lync para Mac 2011 (consulte Guía de implementación de [Lync para Mac 2011)](https://go.microsoft.com/fwlink/p/?LinkId=268786)
    
- Microsoft Communicator para Mac 2011 (vea Communicator guía de implementación para [Mac 2011)](https://go.microsoft.com/fwlink/p/?LinkId=268787)
 
Skype Empresarial Server 2019 no admite estos clientes.
   
## <a name="infrastructure-requirements-for-skype-for-business-on-mac"></a>Requisitos de infraestructura para Skype Empresarial en Mac
<a name="Infrastructure"> </a>

El cliente de Skype Empresarial en Mac aprovecha tanto la Plataforma de administración de comunicaciones unificadas (UCMP) como la API web de comunicaciones unificadas (UCWA) que usan nuestros clientes de movilidad.
  
El cliente tiene los mismos requisitos que nuestros clientes de movilidad en que debe tener un servidor perimetral de acceso y un proxy inverso implementados en una configuración compatible. 
  
### <a name="authentication"></a>Autenticación

El cliente de Skype Empresarial en Mac admite la autenticación basada en certificados, la autenticación moderna de Microsoft y la autenticación multifactor cuando se implementa y se habilita.
  
> [!NOTE]
> Debido a una limitación actual, las credenciales de Exchange del usuario deben ser las mismas que sus credenciales de Skype Empresarial. 
  
### <a name="certificates"></a>Certificados

Los certificados en uso en los servidores perimetrales de acceso, proxy inverso y front-end no deben usar el algoritmo hash SHA-512.
  
El cliente debe definir y tener acceso a la lista de revocación de certificados HTTP. Por ejemplo, no se admite una entrada LDAP en el certificado como lista de revocación de certificados.
  
### <a name="dns"></a>DNS

La movilidad debe implementarse correctamente para que Skype Empresarial en el cliente Mac funcione correctamente. Un escenario de error común es que las dos entradas DNS siguientes se puedan resolver en la red interna:
  
- lyncdiscoverinternal.\<sipdomain\>
    
- lyncdiscover.\<sipdomain\>
    
Para obtener más información, consulte: Implementar la movilidad en [Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=798224)y la Guía de movilidad de [Microsoft Lync Server 2010.](https://go.microsoft.com/fwlink//p/?LinkId=798226)
  
## <a name="see-also"></a>Ver también
<a name="Infrastructure"> </a>

[Requisitos de DNS para Skype Empresarial Server](../../plan-your-deployment/network-requirements/dns.md)

[Preguntas más frecuentes](https://go.microsoft.com/fwlink/p/?LinkId=798227)
  
[Problemas conocidos](https://go.microsoft.com/fwlink/p/?LinkId=798228)
