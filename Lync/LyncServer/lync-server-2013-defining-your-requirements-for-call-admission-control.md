---
title: 'Lync Server 2013: definición de los requisitos para el control de admisión de llamadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your organization's requirements for call admission control
ms:assetid: 5122171a-a5b0-4059-b033-846caec10d1e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398334(v=OCS.15)
ms:contentKeyID: 48184104
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 13a06cfc55481fcfada5782fcbedbac52e6a7660
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504427"
---
# <a name="defining-your-requirements-for-call-admission-control-in-lync-server-2013"></a>Definición de los requisitos para el control de admisión de llamadas en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-10-28_

La planeación del servicio de control de admisión de llamadas (CAC) requiere información detallada sobre la topología de red de la empresa. Para obtener ayuda para planear las directivas del servicio de control de admisión de llamadas, siga estos pasos.

1.  Identifique los concentradores o redes troncales (denominadas *regiones de red*) dentro de la red de la empresa.

2.  Identifique las oficinas o ubicaciones (denominadas *sitios de red*) dentro de cada región de red.

3.  Determine la ruta de red entre cada par de regiones de red.

4.  Determine los límites de ancho de banda para cada vínculo WAN.
    
    <div>
    

    > [!NOTE]  
    > Los límites de ancho de banda hacen referencia a la cantidad de ancho de banda de un vínculo WAN que se asigna a la telefonía IP empresarial y al tráfico de audio y vídeo. Cuando un vínculo WAN se describe como “con ancho de banda restringido”, tiene un límite de ancho de banda inferior al tráfico máximo esperado a través del vínculo.

    
    </div>

5.  Identifique las subredes IP asignadas a cada sitio de red.

Para explicar estos conceptos, usaremos la topología de red de ejemplo que se muestra en la figura siguiente.

**Topología de ejemplo para el servicio de control de admisión de llamadas**

![Ejemplo de topología de red de Litware Inc.](images/Gg398334.477f3b52-2973-4026-9bc0-b1c6bf9f4803(OCS.15).jpg "Ejemplo de topología de red de Litware Inc.")

<div>


> [!NOTE]  
> Todos los sitios de red están asociados a una región de red. Por ejemplo, Portland, Reno y Albuquerque están incluidos en la región Norteamérica. En esta figura, solo se muestran los vínculos WAN que tienen aplicadas directivas de CAC con límites de ancho de banda. Los sitios de red Chicago, Nueva York y Detroit aparecen dentro del óvalo regional Norteamérica debido a que no tienen ancho de banda restringido y, por lo tanto, no precisan directivas de CAC.



</div>

Los componentes de esta topología de ejemplo se explican en las siguientes secciones. Para obtener más información sobre cómo se planificó esta topología, incluidos los límites de ancho de banda, consulte [example: Gathering Your Requirements for Call Admission Control in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md).

<div>

## <a name="identify-network-regions"></a>Identificar regiones de red

Una región de red representa una red troncal de red o un concentrador de red.

Un concentrador de red o una red troncal es parte de la infraestructura de una red informática que interconecta las diferentes partes de la red, lo que proporciona una ruta de acceso para el intercambio de información entre las diferentes LAN o subredes. Una red troncal puede enlazar diversas redes, ya sea de una pequeña ubicación a una extensa área geográfica. Con frecuencia, la capacidad de la red troncal es mayor que la de las redes que se conectan a ella.

Nuestra topología de ejemplo tiene tres regiones de red: Norteamérica, EMEA y APAC. Una región de red contiene un grupo de sitios de red (vea la definición de sitios de red que aparece más adelante en este tema). Trabaje con el equipo de operaciones de red para identificar sus regiones de red.

</div>

<div>

## <a name="associating-a-central-site-with-each-network-region"></a>Asociación de un sitio central con cada región de red

El CAC requiere que se defina un sitio central de Lync Server para cada región de red. El sitio central está seleccionado con la mejor conectividad de red y el mayor ancho de banda respecto al resto de sitios dentro de esa región de la red. El anterior ejemplo de topología de red muestra tres regiones de la red, cada uno con un sitio central que administra las decisiones de CAC. En el ejemplo anterior, la asociación correspondiente se muestra en la siguiente tabla.

<div>


> [!NOTE]  
> Los sitios centrales no corresponden necesariamente a sitios de red. En los ejemplos de esta documentación, algunos sitios centrales (Chicago, Londres y Beijing) comparten el mismo nombre que algunos sitios de red. Sin embargo, aunque un sitio central y un sitio de red compartan el mismo nombre, el sitio central es un elemento de la topología de Lync Server, mientras que el sitio de red forma parte de la red general en la que reside la topología de Lync Server.



</div>

### <a name="network-regions-central-sites-and-network-sites"></a>Regiones de red, sitios centrales y sitios de red

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Región de red</th>
<th>Sitio central</th>
<th>Sitios de red</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Norteamérica</p></td>
<td><p>Guadalajara</p></td>
<td><p>Guadalajara</p>
<p>Nueva York</p>
<p>Detroit</p>
<p>Portland</p>
<p>Reno</p>
<p>Albuquerque</p></td>
</tr>
<tr class="even">
<td><p>EMEA</p></td>
<td><p>México</p></td>
<td><p>México</p>
<p>Colonia</p></td>
</tr>
<tr class="odd">
<td><p>Pacífico</p></td>
<td><p>Beijing</p></td>
<td><p>Beijing</p>
<p>Papel</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="identify-network-sites"></a>Identificar sitios de red

Un sitio de red representa una ubicación en la que la organización tiene un local físico, por ejemplo, oficinas, un conjunto de edificios o un campus. Un local físico con una LAN y que tiene conectividad WAN con otros sitios se considera un sitio de red. Comience por realizar un inventario de las oficinas de la organización. En nuestra topología de ejemplo, la región de red Norteamérica está formada por los siguientes sitios de red: Nueva York, Chicago, Detroit, Portland, Reno y Albuquerque.

Debe asociar todos los sitios de red con una región de red. En función de si el sitio de red tiene un vínculo WAN restringido, se asocia una directiva de ancho de banda con el sitio de red. Para más información sobre las directivas de CAC y el ancho de banda que asigna mediante ellas, vea "Definir directivas de ancho de banda" posteriormente en este tema. Para configurar el CAC, asocie sitios de red con regiones de red y, a continuación, cree directivas de asignación de ancho de banda para aplicarlas a las conexiones con ancho de banda restringido entre un sitio o región determinada y las conexiones WAN entre los sitios y regiones.

</div>

<div>

## <a name="identify-network-links"></a>Identificar vínculos de red

Los vínculos de red representan conexiones a la WAN física que vincula diferentes regiones y sitios. En nuestra topología de ejemplo, hay dos vínculos de red regional, cinco vínculos de red entre regiones y sitios y un vínculo de red entre dos sitios.

Los dos vínculos de red regional están entre Norteamérica y EMEA, representado como NA-EMEA-LINK y entre APAC y EMEA, representado como EMEA-APAC-LINK.

Los vínculos de sitios se indican mediante las líneas que conectan Portland, Reno y Albuquerque con la región Norteamérica, Manila con la región APAC y Colonia con la región EMEA. La línea entre Reno y Albuquerque muestra un vínculo de red directo entre estos dos sitios.

</div>

<div>

## <a name="define-bandwidth-policies"></a>Definir directivas de ancho de banda

Colabore con el equipo de operaciones de red para determinar la cantidad de ancho de banda WAN disponible para tráfico de audio y vídeo en tiempo real a través de los vínculos WAN de la organización. Normalmente, las directivas de ancho de banda se aplican a vínculos WAN si el uso del ancho de banda está restringido; es decir, si se espera que sea mayor que el ancho de banda que se puede asignar para modalidades de audio y vídeo.

Las *directivas de ancho de banda* de CAC definen el ancho de banda máximo que se puede reservar para las modalidades de audio y vídeo en tiempo real. Ya que CAC no limita el ancho de banda de otro tráfico, no puede evitar que el tráfico de otros datos como una transferencia de archivos grande o transmisión de música, use todo el ancho de banda.

Las directivas de ancho de banda del CAC pueden definir cualquiera de las siguientes opciones o todas ellas:

  - Ancho de banda total máximo asignado para audio.

  - Ancho de banda total máximo asignado para vídeo.

  - Ancho de banda máximo asignado para una única llamada de audio (sesión).

  - Ancho de banda máximo asignado para una única videollamada (sesión).

<div>


> [!NOTE]  
> Todos los valores de ancho de banda de CAC representan los límites de ancho de banda <EM>unidireccional</EM> máximo.



</div>

<div>


> [!NOTE]  
> Las características de la Directiva de voz de Lync Server 2013 proporcionan la capacidad de invalidar las comprobaciones de la Directiva de ancho de banda para las llamadas entrantes al usuario (no para las llamadas salientes que realiza el usuario). Una vez establecida la sesión, se justificará detalladamente el consumo de ancho de banda. Esta configuración se debe usar con moderación. Para obtener más información, consulte <A href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">crear una directiva de voz y configurar registros de uso de RTC en Lync server 2013</A> o <A href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">modificar una directiva de voz y configurar registros de uso de RTC en Lync Server 2013</A> en la documentación sobre implementación.



</div>

Para optimizar la utilización del ancho de banda por sesión, tenga en cuenta el tipo de códecs de audio y vídeo que se van a usar. En concreto, evite una asignación insuficiente de ancho de banda a un códec que prevea que se va a usar con frecuencia. Por el contrario, si desea evitar que los medios usen un códec que precisa mayor ancho de banda, deberá establecer un ancho de banda máximo por sesión lo suficientemente bajo para disuadir de su uso. En lo que respecta al audio, no todos los códecs están disponibles para todos los escenarios. Por ejemplo:

  - Las llamadas de audio de punto a punto entre los puntos de conexión de Lync usarán RTAudio (8 kHz) o RTAudio (16 kHz) cuando se influye en el ancho de banda y la priorización de los códecs.

  - Las llamadas de conferencia entre los puntos de conexión de Lync y el servicio de conferencia A/V usarán G. 722 o Siren.

  - Las llamadas a la red telefónica conmutada (RTC) a los puntos de conexión de Lync o hacia ellos usarán G. 711 o RTAudio (8 kHz).

Use la tabla que aparece a continuación para optimizar la configuración de ancho de banda máximo por sesión.

### <a name="bandwidth-utilization-by-codecs"></a>Utilización de ancho de banda por códecs

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Códec</th>
<th>Requisito de ancho de banda sin corrección de errores de reenvío (FEC)</th>
<th>Requisito de ancho de banda con corrección de errores de reenvío (FEC)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTAudio (8 kHz)</p></td>
<td><p>49,8 kbps</p></td>
<td><p>61,6 kbps</p></td>
</tr>
<tr class="even">
<td><p>RTAudio (16 kHz)</p></td>
<td><p>67 kbps</p></td>
<td><p>96 kbps</p></td>
</tr>
<tr class="odd">
<td><p>Siren</p></td>
<td><p>57,6 kbps</p></td>
<td><p>73,6 kbps</p></td>
</tr>
<tr class="even">
<td><p>G. 711</p></td>
<td><p>102 kbps</p></td>
<td><p>166 kbps</p></td>
</tr>
<tr class="odd">
<td><p>G. 722</p></td>
<td><p>105,6 kbps</p></td>
<td><p>169,6 kbps</p></td>
</tr>
<tr class="even">
<td><p>RTVideo (CIF 15 fps)</p></td>
<td><p>260 kbps</p></td>
<td><p>No aplicable</p></td>
</tr>
<tr class="odd">
<td><p>RTVideo (VGA 30 fps)</p></td>
<td><p>610 kbps</p></td>
<td><p>No aplicable</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Los requisitos de ancho de banda tienen en cuenta la sobrecarga para: Ethernet II, IP, Protocolo de datagramas de usuario (UDP), Protocolo de transporte en tiempo real (RTP) y Protocolo de transporte en tiempo real seguro (SRTP). También incluyen 10 kbps para sobrecarga de RTCP.



</div>

Los códecs G.722.1 y Siren son similares, pero ofrecen diferentes velocidades de bits.

G. 722, el códec predeterminado para Conferencia de Lync Server, es completamente diferente de los códecs G. 722.1 y SIREN.

El códec Siren se usa en Lync Server en las siguientes situaciones:

  - Si la directiva de ancho de banda tiene un valor demasiado bajo para el uso de G.722

  - Si un cliente de Communications Server 2007 o Communications Server 2007 R2 se conecta a un servicio de conferencia de Lync Server (porque esos clientes no admiten el códec G. 722).

### <a name="bandwidth-utilization-by-scenario"></a>Utilización de ancho de banda por escenario

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Escenario</th>
<th>Requisito de ancho de banda optimizado para cantidad (kbps)</th>
<th>Requisito de ancho de banda para modo de equilibrado (kbps)</th>
<th>Requisito de ancho de banda optimizado para calidad (kbps)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Llamadas de audio de punto a punto</p></td>
<td><p>45 kbps</p></td>
<td><p>62 kbps</p></td>
<td><p>91 kbps</p></td>
</tr>
<tr class="even">
<td><p>Llamadas de conferencia</p></td>
<td><p>53 kbps</p></td>
<td><p>101 kbps</p></td>
<td><p>165 kbps</p></td>
</tr>
<tr class="odd">
<td><p>Llamadas RTC (entre Lync 2013 y la puerta de enlace RTC, con desvío de medios)</p></td>
<td><p>97 kbps</p></td>
<td><p>97 kbps</p></td>
<td><p>161 kbps</p></td>
</tr>
<tr class="even">
<td><p>Llamadas RTC (entre Lync 2013 y servidor de mediación, sin omisión de medios)</p></td>
<td><p>45 kbps</p></td>
<td><p>97 kbps</p></td>
<td><p>161 kbps</p></td>
</tr>
<tr class="odd">
<td><p>Llamadas RTC (entre el servidor de mediación y la puerta de enlace RTC, sin desvío de medios)</p></td>
<td><p>97 kbps</p></td>
<td><p>97 kbps</p></td>
<td><p>161 kbps</p></td>
</tr>
<tr class="even">
<td><p>Lync: llamadas a Polycom</p></td>
<td><p>101 Kbps</p></td>
<td><p>101 Kbps</p></td>
<td><p>101 Kbps</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="identify-ip-subnets"></a>Identificar subredes IP

Para cada sitio de red, tendrá que trabajar con el administrador de la red para determinar qué subredes IP están asignadas a cada sitio de red. Si el administrador de la red ya ha organizado las subredes IP en regiones de red y sitios de red, su trabajo se habrá simplificado en gran medida.

En nuestro ejemplo, el sitio Nueva York de la región Norteamérica tiene asignadas las siguientes subredes IP: 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24. Demos por supuesto que Bob, que normalmente trabaja en Detroit, viaja a la oficina de Nueva York para recibir formación. Cuando encienda su equipo y se conecte a la red, su equipo obtendrá una dirección IP de uno de los cuatro rangos reservados a Nueva York, por ejemplo, 172.29.80.103.

<div>


> [!WARNING]  
> Las subredes IP especificadas durante la configuración de red del servidor deben coincidir con el formato que proporcionan los equipos cliente para que se puedan usar adecuadamente para el desvío de medios. Un cliente de Lync toma su dirección IP local y enmascara la dirección IP con la máscara de subred asociada. Al determinar el identificador de omisión asociado a cada cliente, el registrador comparará la lista de subredes IP asociadas con cada sitio de red con la subred indicada por el cliente para comprobar que coincidan exactamente. Por este motivo, es importante que las subredes introducidas durante la configuración de la red del servidor sean subredes reales y no virtuales. (Si implementa el sistema de control de admisión de llamadas, pero no la omisión de medios, el control de admisión de llamadas funcionará correctamente incluso aunque configure subredes virtuales).<BR>Por ejemplo, si un cliente inicia sesión en un equipo con una dirección IP de 172.29.81.57 con una máscara de subred IP 255.255.255.0, Lync 2013 le solicitará el identificador de omisión asociado con la subred 172.29.81.0. Si la red se define como 172.29.0.0/16, aunque el cliente pertenezca a una subred virtual, el registrador no lo considerará una coincidencia debido a que el registrador está buscando específicamente la subred 172.29.81.0. Por lo tanto, es importante que el administrador escriba las subredes exactamente como lo proporcionan los clientes de Lync (que se aprovisionan con subredes durante la configuración de red, ya sea de forma estática o mediante DHCP).



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

