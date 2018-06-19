---
title: Skype para la empresa en los requisitos de cliente de Mac
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 790d3e89-2b68-411b-b282-38de5d34dd10
description: Leer este tema para obtener más información acerca de hardware, software y los requisitos de infraestructura para la ejecución de Skype para la empresa en un MAC.
ms.openlocfilehash: 9fd03dbc04937dc34145c97a3abd4fc561ae0270
ms.sourcegitcommit: b14cfca231b618ec28cf9f4efe11cb3e8aceb34b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2018
ms.locfileid: "19503959"
---
# <a name="skype-for-business-on-mac-client-requirements"></a>Skype para la empresa en los requisitos de cliente de Mac
 
Leer este tema para obtener más información acerca de hardware, software y los requisitos de infraestructura para la ejecución de Skype para la empresa en un MAC.
  
El [Skype para la empresa en el cliente de Mac](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-3#Mac) está disponible para su descarga.
  
## <a name="hardware-and-software-requirements-for-skype-for-business-on-the-mac"></a>Requisitos de hardware y software para Skype Empresarial para Mac

El Skype para la empresa en el cliente de Mac requiere Mac OS X El capitán y superior y usa al menos 100MB de espacio en disco. Se admite el uso de todos los dispositivos de audio y vídeo integrados. Los dispositivos externos deben estar en la [lista de dispositivos compatibles para su uso con Lync](https://go.microsoft.com/fwlink/p/?LinkId=798223). 
  
> [!NOTE]
> Esta lista es una versión preliminar y pueden ser compatibles con Lync algunos dispositivos, pero no se admiten en Skype para la empresa en Mac. > Hacer referencia a los [requisitos del sistema](https://products.office.com/en-us/office-system-requirements) para el hardware mínimo necesario.
  
### <a name="legacy-mac-clients"></a>Clientes heredados de Mac

Skype para Business Server 2015 también admite a los siguientes clientes heredados en equipos que ejecutan Mac OS 10.5.8 o el último service pack o la última versión (Intel) sistemas operativos (sistema operativo de Mac OS 10.9 actualmente no se admite). Para obtener información detallada acerca de las características admitidas, vea [comparación de características de cliente de escritorio de Skype para la empresa](desktop-feature-comparison.md).
  
- Microsoft Lync para Mac 2011 (consulte [Lync para Mac 2011 Deployment Guide](https://go.microsoft.com/fwlink/p/?LinkId=268786))
    
- Microsoft Communicator para Mac 2011 (vea [Communicator para Mac 2011 Deployment Guide](https://go.microsoft.com/fwlink/p/?LinkId=268787))
    
## <a name="infrastructure-requirements-for-skype-for-business-on-the-mac"></a>Requisitos de infraestructura de Skype Empresarial para Mac
<a name="Infrastructure"> </a>

El Skype para la empresa en el cliente de Mac aprovecha la plataforma de administración de comunicaciones unificadas (UCMP) así como la Unified Communications Web API (UCWA) que usan nuestros clientes de movilidad.
  
El cliente tiene los mismos requisitos que nuestros clientes de movilidad en cuanto a que debe tener un Servidor perimetral de acceso y un proxy inverso implementados en una configuración compatible. Además, la cuenta debe estar habilitada para la movilidad.
  
### <a name="authentication"></a>Autenticación

El Skype para la empresa en el cliente de Mac es compatible con la autenticación NTLM. Además, el cliente es compatible con Microsoft Modern Authentication y Multi-Factor Authentication cuando se implementa y se habilita.
  
> [!NOTE]
> Debido a una limitación actual, las credenciales del usuario Exchange deben ser el mismo que sus Skype para las credenciales de negocio. 
  
### <a name="certificates"></a>Certificados

Los certificados en uso en los servidores perimetral de acceso, proxy inverso y front-end no deben utilizar el algoritmo hash SHA-512.
  
La lista de revocación de certificados HTTP debe definirse y ser accesible para el cliente. Por ejemplo, no admite una entrada LDAP en el certificado como la lista de revocación de certificados.
  
### <a name="dns"></a>DNS

Movilidad debe estar implementado correctamente para el Skype para la empresa en el cliente de Mac funcione correctamente. Un error común es que las siguientes entradas DNS se puedan resolver en la red interna:
  
- lyncdiscoverinternal. \<sipdomain\>
    
- lyncdiscover. \<sipdomain\>
    
Para obtener más información, consulte: [Implementación de movilidad en Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=798224)y la [Guía de movilidad de Microsoft Lync Server 2010](https://go.microsoft.com/fwlink//p/?LinkId=798226).
  
## <a name="see-also"></a>Vea también
<a name="Infrastructure"> </a>

[Requisitos de DNS de Skype para Business Server 2015](../../plan-your-deployment/network-requirements/dns.md)

[Preguntas más frecuentes](https://go.microsoft.com/fwlink/p/?LinkId=798227)
  
[Problemas conocidos](https://go.microsoft.com/fwlink/p/?LinkId=798228)