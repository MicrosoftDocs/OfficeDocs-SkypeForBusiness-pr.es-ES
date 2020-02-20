---
title: 'Lync Server 2013: opciones de implementación SIP directa'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Direct SIP deployment options
ms:assetid: 84691944-03f2-4a89-9f2b-1ab3d7f388cc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398672(v=OCS.15)
ms:contentKeyID: 48184692
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 03d3d51c8323ab448951255ac9f7cf8d284896ba
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147533"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="direct-sip-deployment-options-in-lync-server-2013"></a>Opciones de implementación SIP directa en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-21_

En este tema se proporcionan ejemplos de topologías para implementar conexiones SIP directas.

<div id="sectionSection0" class="section">

<span id="BKMK_CommunicationsServerStand_Alone"></span>

<div>

## <a name="lync-server-stand-alone"></a>Lync Server independiente

Si su organización usa una de las implementaciones descritas en esta sección, puede usar Lync Server 2013 como solución de telefonía única para una parte o la totalidad de una organización. En esta sección se describen las siguientes implementaciones en detalle:

  - **Implementación incremental:** Esta opción presupone que tiene una infraestructura existente de central de conmutación (PBX) y que pretende presentar la telefonía IP empresarial incrementalmente a grupos más pequeños o a equipos de su organización.

  - **Implementación de Lync Server con VoIP-only:** esta opción presupone que está pensando en implementar Enterprise Voice en un sitio que no tiene una infraestructura de telefonía tradicional.

<div>

## <a name="incremental-deployment"></a>Implementación incremental

En la implementación incremental, Lync Server 2013 es la única solución de telefonía para equipos o departamentos individuales, mientras que el resto de los usuarios de una organización siguen usando una PBX. Esta estrategia de implementación incremental proporciona una forma de introducir la telefonía IP en su empresa a través de programas piloto controlados. Los grupos de trabajo cuyas comunicaciones unificadas de Microsoft atienden mejor a las necesidades de comunicación se mueven a telefonía IP empresarial, mientras que otros usuarios permanecen en la PBX existente. Los grupos de trabajo adicionales se pueden migrar a la telefonía IP empresarial, según sea necesario.

Se recomienda usar la opción incremental si tiene definidos claramente los grupos de usuarios con requisitos de comunicación en común y que se presten a una administración centralizada. Esta opción también es efectiva si tiene equipos o departamentos que se propagan en áreas geográficas anchas, donde el ahorro en los gastos de larga distancia puede ser significativo. De hecho, esta opción es útil para crear equipos virtuales cuyos miembros pueden estar dispersos por todo el mundo. Puede crear, modificar o Disband estos equipos en una respuesta rápida para cambiar los requisitos empresariales.

En la siguiente figura se muestra la topología genérica para la implementación de telefonía IP empresarial detrás de una PBX. Esta es la topología recomendada para la implementación incremental.

**Opción de implementación incremental**

![Diagrama de opción de migración departamental](images/Gg398672.e951ecf4-7cd2-425a-9106-76977492d682(OCS.15).jpg "Diagrama de opción de migración departamental")

<div>


> [!NOTE]  
> Si va a conectar su implementación de Lync Server a un socio de SIP directo certificado, no se requiere una puerta de enlace de red telefónica conmutada (RTC) entre el servidor de mediación y la PBX. Para obtener una lista de asociados de SIP directos certificados, consulte el sitio web del programa de interoperabilidad abierta de comunicaciones unificadas de Microsoft en <A href="https://go.microsoft.com/fwlink/p/?linkid=203309">https://go.microsoft.com/fwlink/p/?linkId=203309</A>.



</div>

<div>


> [!NOTE]  
> La ruta de medios que se muestra en esta figura tiene habilitada la omisión de medios (la configuración recomendada). Si opta por deshabilitar la omisión de medios, la ruta de medios se redirige a través del servidor de mediación.



</div>

En esta topología, los departamentos o grupos de trabajo seleccionados están habilitados para telefonía IP empresarial. Una puerta de enlace RTC vincula el grupo de trabajo de voz sobre protocolo de Internet (VoIP) habilitado a la PBX. Los usuarios que están habilitados para telefonía IP empresarial, incluidos los trabajadores remotos, se comunican a través de la red IP. Las llamadas de los usuarios de Enterprise Voice a la RTC y a los compañeros de trabajo que no están habilitados para la telefonía IP empresarial se enrutan a la puerta de enlace RTC correspondiente. Las llamadas de compañeros que todavía están en el sistema PBX, o de las personas que llaman en la RTC, se enrutan a la puerta de enlace RTC, que reenvía las llamadas a Lync Server para el enrutamiento.

Hay dos configuraciones recomendadas para conectar telefonía IP empresarial a una infraestructura PBX existente para la interoperabilidad: telefonía IP empresarial detrás de PBX y telefonía IP empresarial delante de la PBX.

<div>

## <a name="enterprise-voice-behind-the-pbx"></a>Telefonía IP empresarial detrás del PBX

Cuando se implementa la telefonía IP empresarial tras la PBX, todas las llamadas de la RTC llegan a la PBX, que enruta las llamadas a los usuarios de Enterprise Voice a una puerta de enlace RTC y llama a los usuarios de PBX a la PBX.

</div>

<div>

## <a name="enterprise-voice-in-front-of-the-pbx"></a>Telefonía IP empresarial delante de la PBX

Cuando se implementa la telefonía IP empresarial delante de la PBX, todas las llamadas llegan a la puerta de enlace RTC, que enruta las llamadas de los usuarios de Enterprise Voice a Lync Server y llama a los usuarios de PBX a la PBX. Las llamadas a la RTC desde los usuarios de Enterprise Voice y PBX se enrutan a través de la red IP a la puerta de enlace RTC más rentable. En la siguiente tabla se muestran las ventajas y desventajas de esta configuración.

### <a name="advantages-and-disadvantages-of-deploying-enterprise-voice-in-front-of-pbx"></a>Ventajas y desventajas de la implementación de la telefonía IP empresarial en la parte frontal de la PBX

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Ventajas</th>
<th>Desventajas</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>PBX todavía da servicio a los usuarios que no están habilitados para telefonía IP empresarial.</p></td>
<td><p>Es posible que las puertas de enlace existentes no admitan las características o la capacidad que desee.</p></td>
</tr>
<tr class="even">
<td><p>PBX controla todos los dispositivos anteriores.</p></td>
<td><p>Requiere un tronco desde la puerta de enlace al PBX y desde la puerta de enlace al servidor de mediación. Es posible que necesite más troncos del proveedor de servicios.</p></td>
</tr>
<tr class="odd">
<td><p>Los usuarios de Enterprise Voice mantienen los mismos números de teléfono.</p></td>
<td><p> </p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="lync-server-voip-only-deployment"></a>Implementación de solo VoIP de Lync Server

La telefonía IP empresarial proporciona nuevas empresas y también nuevos sitios de Office para las empresas existentes, con la oportunidad de implementar una solución VoIP completa sin tener que preocuparse de la integración de PBX o incurrir en la implementación y el mantenimiento importantes. costos de una infraestructura de IP-PBX. Esta solución admite tanto a los trabajadores en el sitio como a los remotos.

En esta implementación, todas las llamadas se enrutan a través de la red IP. Las llamadas a la RTC se enrutan a la puerta de enlace RTC correspondiente. Lync 2013 o Lync Phone Edition sirve como softphone. El control remoto de llamadas no está disponible y no es necesario porque no hay teléfonos PBX para que los usuarios los controlen. Los servicios de correo de voz y de operador automático están disponibles a través de la implementación opcional de mensajería unificada (UM) de Exchange.

<div>


> [!NOTE]  
> Además de la infraestructura de red necesaria para admitir Lync Server 2013, una implementación de solo VoIP puede usar una puerta de enlace de uso reducido para admitir equipos de fax y dispositivos analógicos.



</div>

En la siguiente figura se muestra una topología típica para una implementación de solo VoIP.

**Opción de implementación de solo VoIP**

![Opción de implementación de en entorno virgen](images/Gg398672.820dc5fe-0e20-431b-ae4e-fefdf2221d3b(OCS.15).jpg "Opción de implementación de en entorno virgen")

<div>


> [!NOTE]  
> La ruta de medios que se muestra en esta figura tiene habilitada la omisión de medios (la configuración recomendada). Si opta por deshabilitar la omisión de medios, la ruta de medios se redirige a través del servidor de mediación.



</div>

</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

