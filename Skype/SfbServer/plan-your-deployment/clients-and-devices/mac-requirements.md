---
title: Skype para empresas sobre los requisitos del cliente Mac
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: 790d3e89-2b68-411b-b282-38de5d34dd10
description: Lea este tema para obtener información sobre hardware, software y los requisitos de infraestructura para ejecutar Skype para el negocio en un MAC.
ms.openlocfilehash: 1b5fa68a9618126ab69f4ca78f13e65f1ab3ee4b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="skype-for-business-on-mac-client-requirements"></a>Skype para empresas sobre los requisitos del cliente Mac
 
Lea este tema para obtener información sobre hardware, software y los requisitos de infraestructura para ejecutar Skype para el negocio en un MAC.
  
El [Skype para el negocio en el cliente de Mac](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-3#Mac) está disponible para descarga.
  
## <a name="hardware-and-software-requirements-for-skype-for-business-on-the-mac"></a>Requisitos de hardware y software para Skype Empresarial para Mac

El Skype para el negocio en el cliente de Mac requiere Mac OS X El capitán y superiores y utiliza al menos 100MB de espacio en disco. Se admite el uso de todos los dispositivos de audio y vídeo integrados. Dispositivos externos deben estar en la [lista de dispositivos calificados para su uso con Lync](https://go.microsoft.com/fwlink/p/?LinkId=798223). 
  
> [!NOTE]
> Esta lista es preliminar y pueden ser calificados para Lync algunos dispositivos, pero no se admite en Skype para los negocios en el Mac. > Consulte los [requisitos del sistema](https://products.office.com/en-us/office-system-requirements) para el hardware mínimo necesario.
  
### <a name="legacy-mac-clients"></a>Clientes heredados de Mac

Skype para el año 2015 de Business Server también admite a los siguientes clientes heredados en equipos que ejecutan Mac OS 10.5.8 o el service pack más reciente o liberar (Intel) sistemas operativos (sistema operativo de Mac OS 10.9 incompatible). Para obtener más información acerca de las características admitidas, vea [comparación de características de cliente de escritorio de Skype para el negocio](desktop-feature-comparison.md).
  
- Microsoft Lync para Mac 2011 (consulte [Lync para Mac 2011 Guía de implementación](https://go.microsoft.com/fwlink/p/?LinkId=268786))
    
- Microsoft Communicator para Mac 2011 (vea [Communicator para Mac 2011 Guía de implementación](https://go.microsoft.com/fwlink/p/?LinkId=268787))
    
## <a name="infrastructure-requirements-for-skype-for-business-on-the-mac"></a>Requisitos de infraestructura de Skype Empresarial para Mac
<a name="Infrastructure"> </a>

El Skype para el negocio en el cliente de Mac aprovecha la plataforma de administración de comunicaciones unificadas (UCMP) así como el Unified Communications Web API (UCWA) que utilizan nuestros clientes de movilidad.
  
El cliente tiene los mismos requisitos que nuestros clientes de movilidad en cuanto a que debe tener un Servidor perimetral de acceso y un proxy inverso implementados en una configuración compatible. Además, la cuenta debe estar habilitada para la movilidad.
  
### <a name="authentication"></a>Autenticación

El Skype para el negocio en el cliente de Mac es compatible con la autenticación NTLM. Además, el cliente es compatible con Microsoft Modern Authentication y Multi-Factor Authentication cuando se implementa y se habilita.
  
> [!NOTE]
> Debido a una limitación actual, las credenciales del usuario Exchange deben ser igual a su Skype para credenciales de negocios. 
  
### <a name="certificates"></a>Certificados

Los certificados en uso en los servidores perimetral de acceso, proxy inverso y front-end no deben utilizar el algoritmo hash SHA-512.
  
La lista de revocación de certificados HTTP debe definirse y ser accesible para el cliente. Por ejemplo, no admiten una entrada LDAP en el certificado como la lista de revocaciones de certificados.
  
### <a name="dns"></a>DNS

Movilidad debe implementarse correctamente para el Skype para el negocio en el cliente de Mac para funcionar correctamente. Un error común es que las siguientes entradas DNS se puedan resolver en la red interna:
  
- lyncdiscoverinternal. \<sipdomain\>
    
- lyncdiscover. \<sipdomain\>
    
Para obtener más información, consulte: [Implementación de movilidad 2013 de Lync Server](https://go.microsoft.com/fwlink/p/?LinkId=798224)y la [Guía de movilidad de Microsoft Lync Server 2010](https://go.microsoft.com/fwlink//p/?LinkId=798226).
  
## <a name="see-also"></a>Vea también
<a name="Infrastructure"> </a>

#### 

[Requisitos de DNS para Skype para Business Server 2015](../../plan-your-deployment/network-requirements/dns.md)
#### 

[Preguntas más frecuentes](https://go.microsoft.com/fwlink/p/?LinkId=798227)
  
[Problemas conocidos](https://go.microsoft.com/fwlink/p/?LinkId=798228)

