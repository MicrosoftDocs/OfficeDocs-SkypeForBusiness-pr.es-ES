---
title: 'Lync Server 2013: Soluciones de resistencia de sitios de sucursales'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Branch-site resiliency solutions
ms:assetid: 1700f99b-709c-4e47-88eb-c0a5490e26e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398234(v=OCS.15)
ms:contentKeyID: 48183517
ms.date: 12/11/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce14328aed7ae4769d2f2aff18edb9c6135fe025
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842745"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="branch-site-resiliency-solutions-in-lync-server-2013"></a>Soluciones de resistencia de sitios de sucursales en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-12-10_

Existen ventajas obvias para proporcionar resistencia a sitios de sucursales a su organización. En concreto, si pierde la conexión con el sitio central, los usuarios del sitio de la sucursal seguirán teniendo el servicio de voz empresarial y el correo de voz (si configura el redireccionamiento de correo de voz; para obtener más información, consulte [requisitos de resistencia de sitio de sucursal para Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md)). Sin embargo, en el caso de sitios con menos de 25 usuarios, una solución de resistencia puede no proporcionar un retorno de la inversión suficiente.

Si decide proporcionar resistencia a sitios de sucursales, tiene tres opciones. La siguiente tabla puede ayudarle a determinar la mejor opción para su organización.

<div>



<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Si...</th>
<th>Le recomendamos que use un...</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Hospedar entre 25 y 1000 usuarios de su sitio de sucursal y si el retorno de la inversión no admite una implementación completa o si no está disponible el soporte administrativo local</p></td>
<td><p>Aplicación de sucursal con funciones de supervivencia</p>
<p>El equipo de rama con más supervivencia es un servidor blade estándar de la industria con un registrador de Lync Server y un servidor de mediación que se ejecuta en Windows Server 2008 R2. El dispositivo de sucursal con la supervivencia también contiene una puerta de enlace de red telefónica conmutada (RTC). Los dispositivos de terceros cualificados (desarrollados por los socios de Microsoft en el programa de certificación/titulación de la aplicación de rama superviviente (SBA) proporcionan una conexión RTC continua en el caso de una falla de WAN, pero este enfoque no proporciona resistencia presencia y Conferencia porque estas características dependen de servidores front-end en el sitio central.</p>
<p>Para obtener más información sobre los equipos de las &quot;sucursales que son supervivientes&quot; , vea detalles sobre el equipo de la aplicación que más se muestra en este tema.</p>
<p><strong>Nota:</strong> Si decide usar también un tronco de SIP con su equipo de sucursal con la supervivencia, póngase en contacto con el proveedor de su equipo de sucursales con la supervivencia para obtener información sobre el proveedor de servicios más adecuado para su organización.</p></td>
</tr>
<tr class="even">
<td><p>Hospedar entre usuarios de 1000 y 2000 en su sitio de sucursal, carecer de una conexión WAN resistente y tener disponibles los administradores de Lync Server capacitados</p></td>
<td><p>Servidor de sucursal superviviente o dos dispositivos de sucursal con la supervivencia.</p>
<p>El servidor de sucursal con la supervivencia es un servidor de Windows que cumple los requisitos de hardware especificados que tienen instalado Lync Server registrador y el software Media Server. Debe conectarse a una puerta de enlace PSTN o a un tronco SIP a un proveedor de servicios telefónicos.</p>
<p>Para obtener más información sobre los servidores de sucursal &quot;que se van a&quot; utilizar, consulte detalles de servidores de sucursal que se más adelante en este tema.</p></td>
</tr>
<tr class="odd">
<td><p>Si necesita características de presencia y de conferencia, además de características de voz para un máximo de 5000 usuarios, y tiene los administradores de Lync Server capacitados disponibles</p></td>
<td><p>Implementar como un sitio central con un servidor Standard Edition en lugar de como un sitio de sucursal.</p>
<p>Una implementación de Lync Server a escala completa proporciona una conexión RTC continua y una presencia resistente y conferencias en caso de que se produzca un error de WAN.</p>
<p>Para obtener detalles sobre la preparación para esta solución, consulte Planificación de la <a href="lync-server-2013-planning-for-your-organization.md">organización para Lync server 2013</a>, determinación de los <a href="lync-server-2013-determining-your-system-requirements.md">requisitos del sistema para Lync Server 2013</a>, determinación de los <a href="lync-server-2013-determining-your-infrastructure-requirements.md">requisitos de infraestructura para Lync Server 2013</a>y otras secciones relevantes de la documentación de planificación.</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="resiliency-topologies"></a>Topologías de resiliencia

En la siguiente ilustración se muestran las topologías recomendadas para la resistencia a sitios de sucursales.

**Opciones de resistencia de sitio de sucursal**

![Opciones de resistencia de rama de voz] (images/Gg398234.47eecd19-08ae-4d82-acbe-61f0de760306(OCS.15).jpg "Opciones de resistencia de rama de voz")

</div>

<div>

## <a name="survivable-branch-appliance-details"></a>Detalles de los dispositivos de rama supervivientes

El equipo de sucursal con supervivencia de Lync Server incluye los siguientes componentes:

  - Un registrador para la autenticación de usuarios, registro y enrutamiento de llamadas

  - Un servidor de mediación para controlar la señalización entre el registrador y una puerta de enlace RTC

  - Una puerta de enlace RTC para el enrutamiento de llamadas a la RTC como transporte de reserva en el caso de una interrupción de la WAN

  - SQL Server Express para almacenamiento de datos de usuario local

El dispositivo de sucursal con la supervivencia también incluye troncos de la RTC, puertos análogos y un adaptador Ethernet.

Si la conexión WAN del sitio de la sucursal a un sitio central no está disponible, los usuarios de la sucursal interna siguen registrándose con el registrador de la aplicación de rama superviviente y obtienen un servicio de voz ininterrumpido usando la conexión de la aplicación de la aplicación de supervivencia a la RTC. Los usuarios de un sitio de sucursal que se conecten desde casa u otras ubicaciones remotas podrán registrarse con un servidor de registro en un sitio central si el vínculo WAN al sitio de la sucursal no está disponible. Estos usuarios tendrán una funcionalidad de comunicaciones unificadas completa, con la única excepción de que las llamadas entrantes al sitio de la sucursal Irán a correo de voz. Cuando la conexión WAN esté disponible, la funcionalidad completa debe restaurarse a los usuarios del sitio de la sucursal. Ni la conmutación por error a la aplicación de rama superviviente ni la restauración de servicio requiere la presencia de un administrador de ti.

Lync Server admite hasta dos sucursales de superviviente en un sitio de sucursal.

<div>


> [!NOTE]  
> Los usuarios que estén alojados en un equipo con la aplicación de Lync Server superviviente no pueden crear nuevos salones de chat o ver la tarjeta de la sala de las habitaciones existentes.



</div>

<div>

## <a name="survivable-branch-appliance-deployment-overview"></a>Descripción general de la implementación de dispositivos de sucursales

El equipo de sucursales que es superviviente es fabricado por los fabricantes de equipos originales en colaboración con Microsoft y distribuido en su nombre por tiendas minoristas de valor añadido. Esta implementación solo debe realizarse después de que Lync Server se haya implementado en el sitio central, una conexión WAN al sitio de la sucursal esté en vigor y los usuarios del sitio de la sucursal estén habilitados para telefonía IP empresarial.

Para obtener más información sobre estas fases, consulte [implementación de un dispositivo de sucursal o servidor con Lync server 2013](lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md) en la documentación de implementación.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Fase</th>
<th>Pasos</th>
<th>Derechos de usuario</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Configurar los servicios de dominio de Active Directory para la aplicación de rama superviviente</p></td>
<td><p><strong>En el sitio central:</strong></p>
<ol>
<li><p>Cree una cuenta de usuario de dominio (o identidad empresarial) para el técnico que instalará y activará la aplicación de la rama que tiene el mismo nivel en el sitio de la sucursal.</p></li>
<li><p>Cree una cuenta de equipo (con el nombre de dominio completo aplicable (FQDN)) para el equipo de sucursales supervivientes en los servicios de dominio de Active Directory.</p></li>
<li><p>En el generador de topologías, cree y publique la aplicación de rama que sea superviviente.</p></li>
</ol></td>
<td><p>La cuenta de usuario del técnico debe ser miembro de RTCUniversalSBATechnicians. La aplicación de la rama superviviente debe pertenecer al grupo RTCSBAUniversalServices, que se produce automáticamente al utilizar Topology Builder.</p></td>
</tr>
<tr class="even">
<td><p>Instale y active la aplicación de rama que sea superviviente.</p></td>
<td><p><strong>En el sitio de la sucursal:</strong></p>
<ol>
<li><p>Conecte el equipo con la sucursal que sea superviviente a un puerto Ethernet y Puerto RTC.</p></li>
<li><p>Inicia la aplicación de la sucursal que sea superviviente.</p></li>
<li><p>Únase al dominio de la sucursal con la que se pueda hacer uso de la cuenta de usuario de dominio que se creó para la aplicación de la rama superviviente en el sitio central. Establezca el FQDN y la dirección IP para que coincidan con el FQDN creado en la cuenta del equipo.</p></li>
<li><p>Configure el equipo con la interfaz de usuario OEM.</p></li>
<li><p>Pruebe la conectividad RTC.</p></li>
</ol></td>
<td><p>La cuenta de usuario del técnico debe ser miembro de RTCUniversalSBATechnicians.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="survivable-branch-server-details"></a>Detalles del servidor de sucursal superviviente

En el generador de topología, cree el sitio de sucursal, agregue el servidor de sucursal con la supervivencia y, a continuación, ejecute el Asistente para la implementación de Lync Server en el equipo en el que desea instalar el rol.

</div>

</div>

<div>

## <a name="see-also"></a>Vea también


[Implementar Lync Server 2013](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

