---
title: 'Lync Server 2013: Opciones de implementación SIP directa'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Direct SIP deployment options
ms:assetid: 84691944-03f2-4a89-9f2b-1ab3d7f388cc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398672(v=OCS.15)
ms:contentKeyID: 48184692
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 277b64346dc17815438f2ac34da58f36d2b150f2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835395"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="direct-sip-deployment-options-in-lync-server-2013"></a>Opciones de implementación SIP directa en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-21_

En este tema se proporcionan topologías de ejemplo para implementar conexiones SIP directas.

<div id="sectionSection0" class="section">

<span id="BKMK_CommunicationsServerStand_Alone"></span>

<div>

## <a name="lync-server-stand-alone"></a>Lync Server independiente

Si su organización usa una de las implementaciones descritas en esta sección, puede usar Lync Server 2013 como la única solución de telefonía para una parte o toda la organización. En esta sección se describen las siguientes implementaciones en detalle:

  - **Implementación incremental:** Esta opción supone que tiene una infraestructura de intercambio privado existente (PBX) y tiene previsto presentar la telefonía IP en forma incremental para grupos más pequeños o equipos de su organización.

  - **Implementación solo con VoIP de Lync Server:** esta opción supone que está considerando la posibilidad de implementar una telefonía IP empresarial en un sitio que no tiene una infraestructura de telefonía tradicional.

<div>

## <a name="incremental-deployment"></a>Implementación incremental

En la implementación incremental, Lync Server 2013 es la única solución de telefonía para equipos individuales o departamentos, mientras que el resto de los usuarios de una organización continúa usando un sistema PBX. Esta estrategia de implementación incremental proporciona una forma de introducir la telefonía IP en su empresa a través de programas piloto controlados. Los grupos de trabajo cuyas comunicaciones unificadas de Microsoft se sirven mejor a las comunicaciones unificadas de Microsoft se mueven a telefonía IP empresarial, mientras que otros usuarios permanecen en el PBX existente. Se pueden migrar grupos de trabajo adicionales a la telefonía IP empresarial, según sea necesario.

Se recomienda usar la opción incremental si tiene definidos claramente grupos de usuarios que tienen requisitos de comunicación en común y que se prestan a una administración centralizada. Esta opción también es eficaz si tiene equipos o departamentos que están dispersos en áreas geográficas amplias, donde el ahorro en los cargos de larga distancia puede ser significativo. De hecho, esta opción es útil para crear equipos virtuales cuyos miembros pueden estar dispersos por todo el mundo. Puede crear, modificar o desintegrar esos equipos con rapidez para desplazarse por los requisitos empresariales.

La siguiente ilustración muestra la topología genérica para la implementación de telefonía IP empresarial detrás de un sistema PBX. Esta es la topología recomendada para una implementación incremental.

**Opción de implementación incremental**

![Diagrama de opciones de migración a departamentos] (images/Gg398672.e951ecf4-7cd2-425a-9106-76977492d682(OCS.15).jpg "Diagrama de opciones de migración a departamentos")

<div>


> [!NOTE]  
> Si va a conectar su implementación de Lync Server a un socio certificado SIP certificado, una puerta de enlace de red telefónica conmutada (RTC) entre el servidor de mediación y la PBX no es necesaria. Para obtener una lista de socios de SIP directos certificados, consulte el sitio web del programa de interoperabilidad abierto de comunicaciones unificadas de Microsoft en <A href="http://go.microsoft.com/fwlink/p/?linkid=203309">http://go.microsoft.com/fwlink/p/?linkId=203309</A>.



</div>

<div>


> [!NOTE]  
> La ruta multimedia que se muestra en esta figura tiene habilitada la omisión de medios (configuración recomendada). Si opta por deshabilitar la omisión de medios, la ruta de medios se redirige a través del servidor de mediación.



</div>

En esta topología, los departamentos o grupos de trabajo seleccionados están habilitados para telefonía IP empresarial. Una puerta de enlace RTC vincula el grupo de trabajo habilitado para el protocolo de voz a través de Internet (VoIP) a la PBX. Los usuarios que están habilitados para telefonía IP empresarial, incluidos los trabajadores remotos, se comunican a través de la red IP. Las llamadas de los usuarios de Voice empresarial a la RTC y a los compañeros de trabajo que no están habilitados para telefonía IP empresarial se enrutan a la puerta de enlace PSTN correspondiente. Las llamadas de colegas que aún están en el sistema PBX, o de las personas que llaman en la RTC, se enrutan a la puerta de enlace PSTN, que reenvía las llamadas a Lync Server para su enrutamiento.

Hay dos configuraciones recomendadas para conectar telefonía IP empresarial a una infraestructura PBX existente para la interoperabilidad: telefonía IP empresarial detrás de la PBX y la voz de empresa delante de la PBX.

<div>

## <a name="enterprise-voice-behind-the-pbx"></a>Telefonía IP empresarial detrás de la PBX

Cuando se implementa la telefonía IP empresarial tras la PBX, todas las llamadas de la RTC llegan a la PBX, que dirige las llamadas a los usuarios de telefonía de la empresa a una puerta de enlace RTC y llama a los usuarios de PBX a la PBX.

</div>

<div>

## <a name="enterprise-voice-in-front-of-the-pbx"></a>Voz empresarial delante de la PBX

Cuando se implementa la telefonía IP empresarial delante del sistema PBX, todas las llamadas llegan a la puerta de enlace PSTN, que dirige las llamadas de usuarios de telefonía de empresa a Lync Server y llama a los usuarios de PBX a la PBX. Las llamadas a la RTC desde los usuarios de Enterprise Voice y PBX se dirigen a través de la red IP a la puerta de enlace RTC más económica. En la tabla siguiente se muestran las ventajas y desventajas de esta configuración.

### <a name="advantages-and-disadvantages-of-deploying-enterprise-voice-in-front-of-pbx"></a>Ventajas y desventajas de implementar voz empresarial en la parte delantera de PBX

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Ofrece</th>
<th>Desventajas</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>PBX aún da servicio a los usuarios que no tienen habilitada la telefonía IP empresarial.</p></td>
<td><p>Es posible que las puertas de enlace existentes no admitan las características o la capacidad que usted desee.</p></td>
</tr>
<tr class="even">
<td><p>PBX controla todos los dispositivos anteriores.</p></td>
<td><p>Requiere un tronco desde la puerta de enlace a la PBX y desde la puerta de enlace hasta el servidor de mediación. Es posible que necesites más troncos del proveedor de servicios.</p></td>
</tr>
<tr class="odd">
<td><p>Los usuarios de voz empresarial conservan los mismos números de teléfono.</p></td>
<td><p> </p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="lync-server-voip-only-deployment"></a>Implementación solo con VoIP de Lync Server

Enterprise Voice ofrece nuevas empresas y también nuevos sitios de Office para empresas existentes, con la oportunidad de implementar una solución VoIP completa sin tener que preocuparse por la integración de PBX o incurrir en la implementación y el mantenimiento importantes. costos de una infraestructura IP-PBX. Esta solución es compatible tanto con trabajadores remotos como en el sitio.

En esta implementación, todas las llamadas se enrutan a través de la red IP. Las llamadas a la RTC se enrutan a la puerta de enlace PSTN adecuada. Lync 2013 o Lync Phone Edition funciona como softphone. El control remoto de llamadas no está disponible e innecesario porque no hay teléfonos PBX para que los usuarios puedan controlarlo. Los servicios de correo de voz y de operador automático están disponibles a través de la implementación opcional de mensajería unificada de Exchange (UM).

<div>


> [!NOTE]  
> Además de la infraestructura de red necesaria para admitir Lync Server 2013, una implementación de solo VoIP puede usar una pequeña y certificada puerta de enlace para admitir equipos de fax y dispositivos analógicos.



</div>

En la siguiente ilustración se muestra una topología típica para una implementación de solo VoIP.

**Opción de implementación solo de VoIP**

![Opción de implementación Greenfidle] (images/Gg398672.820dc5fe-0e20-431b-ae4e-fefdf2221d3b(OCS.15).jpg "Opción de implementación Greenfidle")

<div>


> [!NOTE]  
> La ruta multimedia que se muestra en esta figura tiene habilitada la omisión de medios (configuración recomendada). Si opta por deshabilitar la omisión de medios, la ruta de medios se redirige a través del servidor de mediación.



</div>

</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

