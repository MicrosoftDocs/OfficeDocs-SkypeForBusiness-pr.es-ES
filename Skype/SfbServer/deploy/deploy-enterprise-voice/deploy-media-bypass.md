---
title: Implementar la omisión de medios en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 1bd35f90-8587-48a1-b0c2-095a4053fc77
description: Implemente la omisión de medios en Skype Empresarial Server Telefonía IP empresarial. Incluye requisitos previos y lista de comprobación del proceso de implementación.
ms.openlocfilehash: c6820438d969ce3c802060eba9bcababc0b1315d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812450"
---
# <a name="deploy-media-bypass-in-skype-for-business-server"></a>Implementar la omisión de medios en Skype Empresarial Server
 
Implemente la omisión de medios en Skype Empresarial Server Telefonía IP empresarial. Incluye requisitos previos y lista de comprobación del proceso de implementación.
  
En este tema se supone que ya ha publicado y configurado al menos uno o más servidores de mediación y al menos una puerta de enlace del mismo nivel para proporcionar conectividad con RTC. Para obtener más información sobre estas tareas, vea Implementar un servidor de mediación en el Generador de topologías en [Skype Empresarial Server](deploy-a-mediation-server.md) y Definir una puerta de enlace en el Generador de topologías en Skype Empresarial [Server.](define-a-gateway.md)
  
 Si el sistema del mismo nivel al que se conecta es el SBC de un proveedor de enlace troncal SIP, asegúrese de que el proveedor es un proveedor cualificado y que admite la omisión de medios. Por ejemplo, muchos proveedores de servicios de enlace troncal SIP solo permiten a sus SCN recibir tráfico del servidor de mediación. De ser así, el desvío no debe habilitarse para el tronco en cuestión. Además, no puede habilitar el desvío de medios a menos que la organización revele sus direcciones IP de redes internas al proveedor de servicios de enlace troncal SIP.
  
> [!NOTE]
> El desvío de medios no interactuará con todas las puertas de enlace RTC, los sistemas IP-PBX y las SBC. Microsoft ha probado un conjunto de puertas de enlace RTC y SBC con socios certificados y ha realizado algunas pruebas con IP-PBX de Cisco. La omisión de medios solo se admite con productos y versiones enumerados en el Programa de interoperabilidad abierta de comunicaciones [unificadas : Lync Server](https://go.microsoft.com/fwlink/p/?linkId=214406). 
  
Si ya ha configurado el control de admisión de llamadas, otra característica avanzada de Telefonía IP empresarial, tenga en cuenta que la reserva de ancho de banda que realiza dicho control no se aplica a ninguna llamada en la que se emplee el desvío de medios. Primero se comprueba si se usa el desvío de medios; si se usa, no se emplea el control de admisión de llamadas; la comprobación para control de admisión de llamadas se realiza si la comprobación de desvío de medios no funciona correctamente. Por lo tanto, las dos características se excluyen mutuamente en cualquier llamada que se enrute a la RTC. Se aplica esta lógica porque el desvío de medios da por supuesto que no hay restricciones de ancho de banda entre los extremos de los medios en una llamada; el desvío de medios no puede realizarse en vínculos que tengan un ancho de banda restringido. Como consecuencia, solo se aplica una de las posibilidades siguientes a una llamada de RTC: a) el medio omite el servidor de mediación y el control de admisión de llamadas no reserva ancho de banda para la llamada; b) el control de admisión de llamadas aplica reserva de ancho de banda para la llamada y el servidor de mediación que interviene en la llamada procesa los medios.
  
Además de habilitar la omisión de medios para conexiones troncales individuales asociadas a un sistema del mismo nivel, también debe habilitar la omisión de medios globalmente. La configuración de omisión de medios global puede especificar que siempre se intenta la omisión de medios para las llamadas a la RTC, o que la omisión de medios se usa mediante la asignación de subredes a sitios de red y regiones de red, similar a lo que hace el control de admisión de llamadas, otra característica de voz avanzada. Cuando la omisión de medios y el control de admisión de llamadas están habilitados, la región de red, el sitio de red y la información de subred que se especifica para el control de admisión de llamadas se usan automáticamente al determinar si se va a usar la omisión de medios. Esto significa que no se puede especificar que siempre se intenta la omisión de medios para las llamadas a la RTC cuando el control de admisión de llamadas está habilitado.
  
> [!NOTE]
> Cuando se usan estos pasos para configurar el desvío de medios, se da por hecho que existe una buena conectividad entre los clientes y el nivel de servidor de mediación (por ejemplo, una puerta de enlace RTC, un sistema PBX IP o un SBC en un proveedor de enlace troncal SIP). En caso de que haya limitaciones de ancho de banda en el vínculo, no podrá efectuarse el desvío de medios en la llamada. La omisión de medios no interactuará con todas las puertas de enlace RTC, los sistemas IP-PBX y las SBC. Microsoft ha probado un conjunto de puertas de enlace RTC y SBC con socios certificados y ha realizado algunas pruebas con IP-PBX de Cisco. La omisión de medios solo se admite con productos y versiones enumerados en el Programa de interoperabilidad abierta de comunicaciones [unificadas : Lync Server](https://go.microsoft.com/fwlink/p/?linkId=214406). 
  
## <a name="deployment-process-for-media-bypass"></a>Proceso de implementación para la omisión de medios

En la tabla siguiente se proporciona información general sobre el proceso de implementación de la omisión de medios. 
  
|**Fase**|**Pasos**|**Roles**|**Documentación de implementación**|
|:-----|:-----|:-----|:-----|
|Configurar troncos para la omisión de medios  <br/> |Si aún no lo ha hecho, configure uno o más troncos para la omisión de medios.  <br/> | Miembro del grupo RTCUniversalServerAdmins o miembro del rol CsVoiceAdministrator, CsServerAdministrator o CsAdministrator <br/> |[Configurar un tronco con desvío de medios en Skype Empresarial Server](configure-trunk-with-media-bypass.md) <br/> |
|Configurar la omisión de medios globalmente  <br/> |Configure la omisión de medios para todas las llamadas a la RTC o para determinadas llamadas basadas en sitios de red y regiones de red.  <br/> | Miembro del grupo RTCUniversalServerAdmins o miembro del rol CsVoiceAdministrator, CsServerAdministrator o CsAdministrator <br/> |[Configurar la omisión de medios en Skype Empresarial Server para que siempre omita el servidor de mediación](bypass-the-mediation-server.md) <br/> [Configurar la omisión de medios de configuración global en Skype Empresarial Server para usar la información de sitio y región](use-site-and-region-information.md) <br/> |
|Asociar subredes a sitios de red, si es necesario  <br/> |Si configura la omisión de medios para usar información de sitio y región, debe asociar las subredes de la implementación con sitios de red y regiones (si aún no lo ha hecho para otra característica de voz).  <br/> | Miembro del grupo RTCUniversalServerAdmins o miembro del rol CsVoiceAdministrator, CsServerAdministrator o CsAdministrator <br/> |[Asociar una subred a un sitio de red](deploy-network.md#BKMK_AssociateSubnets) <br/> |
   

