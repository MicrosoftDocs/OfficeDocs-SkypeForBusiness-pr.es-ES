---
title: Implementar la omisión de medios en Skype Empresarial Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 1bd35f90-8587-48a1-b0c2-095a4053fc77
description: Implementar el desvío de medios en Skype para Business Server Enterprise Voice. Incluye los requisitos previos y una lista de comprobación del proceso de implementación.
ms.openlocfilehash: ffd026465b5ad4463b8df2c3184e39198bfe5045
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="deploy-media-bypass-in-skype-for-business-server-2015"></a>Implementar la omisión de medios en Skype Empresarial Server 2015
 
Implementar el desvío de medios en Skype para Business Server Enterprise Voice. Incluye los requisitos previos y una lista de comprobación del proceso de implementación.
  
En este tema se da por supuesto que ya ha publicado y ha configurado el mismo nivel de al menos una puerta de enlace y al menos uno o varios servidores de mediación para proporcionar conectividad con RTC. Para obtener más detalles sobre estas tareas, vea [implementar un servidor de mediación en el generador de Skype para Business Server 2015](deploy-a-mediation-server.md) y [definir una puerta de enlace en el generador de Skype para Business Server 2015](define-a-gateway.md).
  
 Si el equivalente al que se conecta es el SBC de un proveedor de servicios de enlace troncal SIP, asegúrese de que sea un proveedor cualificado y que admita la omisión de medios. Por ejemplo, muchos proveedores de servicios de enlace troncal SIP solo permiten a sus SBC recibir tráfico del servidor de mediación. De ser así, la omisión no debe habilitarse para el tronco en cuestión. Además, no puede habilitar la omisión de medios a menos que la organización revele sus direcciones IP de redes internas al proveedor de servicios de enlace troncal SIP.
  
> [!NOTE]
> La omisión de medios no interactuará con todas las puertas de enlace RTC, los sistemas IP-PBX y las SBC. Microsoft ha probado una serie de puertas de enlace RTC y SBC con socios certificados y ha realizado algunas pruebas con los IP-PBX de Cisco. Desvío de medios es compatible solo con productos y versiones que aparecen en [Unified Communications Open Interoperability Program - Lync Server](https://go.microsoft.com/fwlink/p/?linkId=214406). 
  
Si ya ha configurado el control de admisión de llamadas (CAC), otra característica avanzada de la Telefonía IP empresarial, tenga en cuenta que la reserva de ancho de banda que realiza dicho control no se aplica a ninguna llamada en la que se emplee la omisión de medios. Primero se comprueba si se usa la omisión de medios; si se usa, no se emplea el control de admisión de llamadas; la comprobación para control de admisión de llamadas se realiza únicamente si la comprobación de omisión de medios no funciona correctamente. Por lo tanto, las dos características se excluyen mutuamente en cualquier llamada que se enrute a la RTC. Se aplica esta lógica porque la omisión de medios da por supuesto que no hay restricciones de ancho de banda entre los extremos de los medios en una llamada; la omisión de medios no puede realizarse en vínculos que tengan un ancho de banda restringido. Como consecuencia, solo se aplica una de las posibilidades siguientes a una llamada de RTC: a) el medio omite el servidor de mediación y el control de admisión de llamadas no reserva ancho de banda para la llamada; o b) el control de admisión de llamadas aplica reserva de ancho de banda para la llamada y el servidor de mediación que interviene en la llamada procesa los medios.
  
Además de habilitar la omisión de medios para las conexiones de tronco individuales asociadas a un nivel, también deberá habilitar la omisión de medios de forma global. La configuración de la omisión de medios global puede establecer que se intente realizar siempre una omisión de medios de las llamadas a RTC, o bien que la omisión de medios se use con la asignación de subredes a sitios y regiones de red, algo similar a lo que lleva a cabo el control de admisión de llamadas, que es otra característica de voz avanzada. Cuando tanto la omisión de medios como el control de admisión de llamadas están habilitados, la información de región de red, sitio de red y subred especificada para el control de admisión de llamadas se usa automáticamente para determinar si ha de usarse o no la omisión de medios, lo cual quiere decir que no siempre se va a poder especificar que se intente omitir los medios a RTC siempre cuando el control de admisión de llamadas está habilitado.
  
> [!NOTE]
> Cuando se usan estos pasos para configurar la omisión de medios, se da por hecho que existe una buena conectividad entre los clientes y el nivel de servidor de mediación (por ejemplo, una puerta de enlace RTC, un sistema PBX IP o un SBC en un proveedor de enlace troncal SIP). En caso de que haya limitaciones de ancho de banda en el vínculo, no podrá efectuarse la omisión de medios en la llamada. La omisión de medios no interactuará con todas las puertas de enlace RTC, los sistemas IP-PBX y las SBC. Microsoft ha probado una serie de puertas de enlace RTC y SBC con socios certificados y ha realizado algunas pruebas con los IP-PBX de Cisco. Desvío de medios es compatible solo con productos y versiones que aparecen en [Unified Communications Open Interoperability Program - Lync Server](https://go.microsoft.com/fwlink/p/?linkId=214406). 
  
## <a name="deployment-process-for-media-bypass"></a>Proceso de implementación para la omisión de medios

En la siguiente tabla se proporciona información general sobre el proceso de implementación de servidores perimetrales. 
  
|**Fase**|**Pasos**|**Roles**|**Documentación de implementación**|
|:-----|:-----|:-----|:-----|
|Configurar troncos para omisión de medios  <br/> |Si aún no lo ha hecho, configurar uno o más troncos para la omisión de medios.  <br/> | Un miembro del grupo RTCUniversalServerAdmins o un miembro de la función CsVoiceAdministrator, CsServerAdministrator o CsAdministrator <br/> |[Configurar un tronco con desvío de medios en Skype para Business Server 2015](configure-trunk-with-media-bypass.md) <br/> |
|Configurar la omisión de medios globalmente  <br/> |Configure la omisión de medios para todas las llamadas a la RTC o bien algunas las llamadas basadas en sitios de red y regiones de red.  <br/> | Un miembro del grupo RTCUniversalServerAdmins o un miembro de la función CsVoiceAdministrator, CsServerAdministrator o CsAdministrator <br/> |[Configurar el desvío de medios en Skype para Business Server 2015 omitir siempre el servidor de mediación](bypass-the-mediation-server.md) <br/> [Configurar la configuración global de desvío de medios en Skype para Business Server 2015 utilizar la información de sitio y región](use-site-and-region-information.md) <br/> |
|Asociar subredes a sitios de red, si es necesario  <br/> |Si configura la omisión de medios para usar la información de sitio y de región, debe asociar las subredes de la implementación con sitios de red y regiones (si no lo ha hecho para otra característica de voz).  <br/> | Un miembro del grupo RTCUniversalServerAdmins o un miembro de la función CsVoiceAdministrator, CsServerAdministrator o CsAdministrator <br/> |[Associate a subnet with a network site](deploy-network.md#BKMK_AssociateSubnets) <br/> |
   

