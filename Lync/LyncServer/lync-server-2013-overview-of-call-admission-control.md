---
title: 'Lync Server 2013: información general sobre el control de admisión de llamadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of call admission control
ms:assetid: 6fda0195-4c89-4dea-82e8-624f03e3d062
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398529(v=OCS.15)
ms:contentKeyID: 48184474
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5cba1a83ce64fa575cf5de724d5dd215fcb459c7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825845"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-call-admission-control-in-lync-server-2013"></a>Información general sobre el control de admisión de llamadas en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-22_

Las comunicaciones en tiempo real son sensibles a la latencia y la pérdida de paquetes que se pueden producir en redes congestionadas. El control de admisión de llamadas (CAC) determina, en base al ancho de banda de la red disponible, si está permitido establecer sesiones de comunicación en tiempo real, como son las llamadas de voz o vídeo. El diseño CAC de Lync Server 2013 ofrece cuatro atributos principales:

  - Es fácil de implementar y administrar, y no requiere equipamiento adicional, como ocurre con los enrutadores especialmente configurados.

  - Está dirigido a casos de uso de comunicaciones unificadas críticas, como los escenarios con usuarios remotos o múltiples puntos de presencia. Las directivas del CAC se aplican de acuerdo con el lugar donde se ubica el extremo, no con el lugar donde se hospeda el usuario.

  - Además de las llamadas de voz, puede aplicarse a otro tráfico, como las videollamadas y las sesiones de conferencia de audio/vídeo.

  - Proporciona la flexibilidad necesaria para habilitar la representación de varios tipos de topologías de red. Para obtener ejemplos, vea [componentes y topologías de CAC en Lync Server 2013](lync-server-2013-components-and-topologies-for-cac.md).

Si una sesión de vídeo o voz nueva supera los límites de ancho de banda que se han establecido en un vínculo WAN, la sesión se bloquea o (solo para llamadas telefónicas) se desvía a la RTC.

El CAC controla el tráfico en tiempo real solo para voz y vídeo. No controla el tráfico de datos.

Los administradores definen las directivas de CAC, que se aplican mediante el servicio de directivas de ancho de banda instalado con cada grupo de servidores front-end. La configuración de CAC se propaga automáticamente a todos los servidores front-end de Lync Server de su red.

Para las llamadas en las que se produce un error debido a las directivas del CAC, el orden de prioridad para desviar la llamada es el siguiente:

1.  Internet

2.  RTC

3.  Correo de voz

Información de las capturas del registro de detalles de llamadas (CDR) sobre las llamadas que se desvían a la RTC o al correo de voz. El CDR no captura información sobre las llamadas que se desvían a Internet, ya que Internet se considera una ruta de acceso alternativa en lugar de una opción secundaria.

<div>


> [!NOTE]  
> Los depósitos de correo de voz no se denegarán por restricciones del ancho de banda.



</div>

El servicio de directivas de ancho de banda genera dos tipos de archivo de registro en formato de valores separados por comas (CSV). El archivo de registro de **errores de comprobación** captura información cuando se deniegan las solicitudes de ancho de banda. El archivo de registro de **uso de vínculos** captura una instantánea de la topología de red y del uso del ancho de banda del vínculo WAN. Estos dos archivos de registro pueden ayudarte a ajustar las directivas del CAC en función del uso.

<div>

## <a name="call-admission-control-considerations"></a>Consideraciones relacionadas con el servicio de control de admisión de llamadas

El administrador elige instalar el servicio de directiva de ancho de banda en el primer grupo configurado en la ubicación central. Dado que hay una única ubicación central por región de red, solo hay un servicio de directivas de ancho de banda en cada región de red, que administra la directiva de ancho de banda para dicha región, sus sitios asociados y los vínculos a esos sitios. El servicio de directivas de ancho de banda se ejecuta como parte de los servidores front-end y, por lo tanto, la alta disponibilidad está integrada en ese grupo. El servicio de directivas de ancho de banda que se ejecuta en cada servidor front-end se sincroniza cada 15 segundos. Si se produce un error en el grupo de servidores front end, ya no se aplican las directivas CAC para ese sitio hasta que el grupo de servidores front-end y, en consecuencia, el servicio de directivas de ancho de banda vuelva a estar operativo. Esto implica que todas las llamadas pasarán mientras el servicio de directivas de ancho de banda esté fuera de servicio. En consecuencia, existe la posibilidad de saturación del ancho de banda de los vínculos durante este período.

El servicio de directivas de ancho de banda proporciona alta disponibilidad dentro de un grupo de servidores front-end; sin embargo, no proporciona redundancia en los grupos de servidores front-end. El servicio de directivas de ancho de banda no puede realizar la conmutación por error de un grupo front-end a otro. Una vez que se restaura el servicio al grupo de servidores front-end, el servicio de directivas de ancho de banda se reanuda y puede aplicar de nuevo las comprobaciones de directiva de ancho de banda.

<div>

## <a name="network-considerations"></a>Consideraciones relacionadas con la red

Aunque el servicio de directivas de ancho de banda de Lync Server 2013 exige la restricción de ancho de banda para el audio y el vídeo, esta restricción no se aplica al enrutador de red (capa 2 y 3). Lync Server 2010 CAC no puede impedir que una aplicación de datos consuma todo el ancho de banda de la red en un vínculo de WAN, incluido el ancho de banda reservado para audio y vídeo por la Directiva CAC. Para proteger el ancho de banda necesario en la red, puedes implementar un protocolo de calidad de servicio (QoS) como, por ejemplo, los servicios diferenciados (DiffServ). Así pues, el procedimiento recomendado es coordinar las directivas de ancho de banda del CAC que definas con cualquier configuración de QoS que puedas implementar.

</div>

<div>

## <a name="media-and-signaling-paths-over-vpn"></a>Rutas de acceso de señalización y medios sobre VPN

Si tu empresa admite medios a través de VPN, asegúrate de que tanto la secuencia de medios como la secuencia de señalización pasen por la VPN o se redirijan a través de Internet. De forma predeterminada, las secuencias de medios y de señalización pasan por el túnel VPN.

</div>

<div>

## <a name="call-admission-control-of-outside-users"></a>Servicio de control de admisión de llamadas de usuarios externos

El control de admisión de llamadas no se aplica a los usuarios remotos cuando el tráfico de red fluye a través de Internet. Dado que el tráfico multimedia atraviesa Internet, que no está administrado por Lync Server, no se puede aplicar CAC. Sin embargo, se realizarán comprobaciones CACs en la parte de la llamada que fluye a través de la red empresarial.

</div>

<div>

## <a name="call-admission-control-of-pstn-connections"></a>Servicio de control de admisión de llamadas de conexiones RTC

El control de admisión de llamadas es obligatorio en el servidor de mediación, independientemente de si está conectado a un IP/PBX, una puerta de enlace RTC o un tronco de SIP. Debido a que el servidor de mediación es un agente de usuario inverso (B2BUA), finaliza los medios. Tiene dos lados de conexión: un lado que está conectado a Lync Server y un lado de puerta de enlace, que está conectado a puertas de enlace RTC, IP/PBX o a troncos de SIP. Para obtener más información acerca de las conexiones RTC, consulte [planificación de la conectividad RTC en Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md).

Se puede aplicar CAC a ambos lados del servidor de mediación, a menos que se habilite la omisión de medios. Si se habilita la omisión de multimedia, el tráfico multimedia no atraviesa el servidor de mediación, sino que se transmite directamente entre el cliente de Lync y la puerta de enlace. En este caso, el CAC no es necesario. Para obtener más información, consulte [planificación de la omisión de medios en Lync Server 2013](lync-server-2013-planning-for-media-bypass.md).

En la siguiente figura se muestra cómo se aplica el CAC a las conexiones RTC con la omisión de medios habilitada e inhabilitada.

**Cumplimiento del control de admisión de llamadas en conexiones al RTC**

![Aplicación de omisión multimedia de voz CAC] (images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "Aplicación de omisión multimedia de voz CAC")

</div>

<div>

## <a name="compatibility-of-call-admission-control-with-earlier-versions-of-office-communications-server"></a>Compatibilidad del control de admisión de llamadas con versiones anteriores de Office Communications Server

El control de admisión de llamadas solo se puede habilitar en los extremos habilitados para Lync Server 2010 y versiones posteriores.

El control de admisión de llamadas no se puede habilitar en los extremos que ejecutan Office Communicator 2007 R2 o versiones anteriores.

**Aplicación de CAC en diferentes versiones de Lync Server**

![Diagrama de comparación de versiones de voz CAC] (images/Gg398529.fdbfee7e-15fc-445b-949d-8d61e61ac350(OCS.15).jpg "Diagrama de comparación de versiones de voz CAC")

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

