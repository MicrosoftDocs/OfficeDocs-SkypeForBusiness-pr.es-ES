---
title: 'Lync Server 2013: soluciones de resistencia de sitios de sucursal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Branch-site resiliency solutions
ms:assetid: 1700f99b-709c-4e47-88eb-c0a5490e26e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398234(v=OCS.15)
ms:contentKeyID: 48183517
ms.date: 12/11/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 42ede6730357f50967f13089e02e32ad1a21d8ce
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196583"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="branch-site-resiliency-solutions-in-lync-server-2013"></a>Soluciones de resistencia de sitios de sucursal en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-12-10_

Las ventajas que una organización obtiene al disponer de resistencia en las sucursales son más que evidentes. En concreto, si pierde la conexión con el sitio central, los usuarios del sitio de sucursal seguirán teniendo el servicio de telefonía IP y el correo de voz (si configura la configuración de reenrutamiento del correo de voz; para obtener más información, consulte [Branch-site Resiliency Requirements for Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md)). Sin embargo, una solución de resistencia probablemente no compense lo suficiente en sitios con menos de 25 usuarios.

Si decide proporcionar resistencia en las sucursales, tiene tres maneras de hacerlo. La siguiente tabla puede ayudarle a saber cuál es la mejor opción para su organización.

<div>



<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Si...</th>
<th>Se recomienda...</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Hospeda entre 25 y 1000 usuarios en la sucursal y no compensa una implementación completa o no se dispone de asistencia administrativa local</p></td>
<td><p>Aplicación de sucursal con funciones de supervivencia</p>
<p>La aplicación de sucursal con funciones de supervivencia es un servidor blade estándar de la industria con un registrador de Lync Server y un servidor de mediación que se ejecuta en Windows Server 2008 R2. La aplicación de sucursal con funciones de supervivencia también contiene una puerta de enlace de red telefónica conmutada (RTC). Los dispositivos de otros fabricantes calificados (desarrollados por socios de Microsoft en el programa de certificación/calificación de aplicación de sucursal con funciones de supervivencia [SBA]) ofrecen una conexión RTC ininterrumpida en caso de que se produzca un error de WAN, aunque este enfoque no proporciona presencia y conferencia resistentes, ya que ambas características dependen de los servidores front-end del sitio central.</p>
<p>Para obtener más información sobre las aplicaciones de sucursal &quot;con funciones de supervivencia, consulte&quot; detalles de aplicación de sucursal con funciones de supervivencia, más adelante en este tema.</p>
<p><strong>Nota:</strong> Si decide usar también un tronco SIP con la aplicación de sucursal con funciones de supervivencia, póngase en contacto con el proveedor de la aplicación de sucursal con funciones de supervivencia para obtener información sobre qué proveedor de servicios es el mejor para su organización.</p></td>
</tr>
<tr class="even">
<td><p>Host entre los usuarios de 1000 y 2000 en su sitio de sucursal, carecen de una conexión WAN resistente y tienen los administradores de Lync Server capacitados disponibles</p></td>
<td><p>Servidor de sucursal con funciones de supervivencia o dos aplicaciones de sucursal con funciones de supervivencia.</p>
<p>El servidor de sucursal con funciones de supervivencia es un servidor de Windows Server que cumple los requisitos de hardware especificados que tiene instalado el software del servidor de mediación y el registrador de Lync Server. Debe conectarse a una puerta de enlace RTC o a un tronco SIP hacia un proveedor de servicios telefónicos.</p>
<p>Para obtener más información sobre los servidores de sucursal &quot;con funciones de supervivencia, vea&quot; detalles del servidor de sucursal con funciones de supervivencia, más adelante en este tema.</p></td>
</tr>
<tr class="odd">
<td><p>Si necesita características de presencia y Conferencia además de las características de voz para un máximo de 5000 usuarios y tiene los administradores de Lync Server capacitados disponibles</p></td>
<td><p>Realizar una implementación como un sitio central con un servidor Standard Edition en lugar de como una sucursal.</p>
<p>Una implementación de Lync Server a gran escala proporciona una conexión RTC continua y una presencia resistente y conferencias en caso de que se produzca un error de WAN.</p>
<p>Para obtener información detallada sobre la preparación para esta solución, consulte <a href="lync-server-2013-planning-for-your-organization.md">Organization Planning for Lync server 2013</a>, <a href="lync-server-2013-determining-your-system-requirements.md">determining Your System Requirements for Lync Server 2013</a>, <a href="lync-server-2013-determining-your-infrastructure-requirements.md">determining Your Infrastructure requirements for Lync Server 2013</a>y otras secciones relevantes de la documentación de planeación.</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="resiliency-topologies"></a>Topologías de resistencia

La siguiente figura refleja las topologías recomendadas de resistencia en las sucursales.

**Opciones de resistencia de las sucursales**

![Opciones de resistencia de bifurcación de voz](images/Gg398234.47eecd19-08ae-4d82-acbe-61f0de760306(OCS.15).jpg "Opciones de resistencia de bifurcación de voz")

</div>

<div>

## <a name="survivable-branch-appliance-details"></a>Detalles de la aplicación de sucursal con funciones de supervivencia

La aplicación de sucursal con funciones de supervivencia de Lync Server incluye los siguientes componentes:

  - Un registrador para la autenticación y registro de usuarios y el enrutado de llamadas

  - Un servidor de mediación para controlar la señalización entre el registrador y una puerta de enlace RTC

  - Una puerta de enlace RTC para enrutar llamadas a la RTC a modo de transporte de reserva en caso de que se produzca una interrupción en la red WAN

  - SQL Server Express para el almacenamiento local de los datos de usuario

La aplicación de sucursal con funciones de supervivencia también incluye troncos RTC, puertos analógicos y un adaptador Ethernet.

Si la conexión WAN del sitio de sucursal a un sitio central deja de estar disponible, los usuarios de la sucursal interna siguen registrándose con el registrador de la aplicación de sucursal con funciones de supervivencia y obtienen un servicio de voz sin interrupciones mediante la conexión de aplicación de sucursal con funciones de supervivencia a la RTC. En caso de que el vínculo WAN a una sucursal no esté disponible, los usuarios de sucursal que se conecten desde casa o desde otras ubicaciones remotas tendrán la posibilidad de registrarse con un servidor registrador ubicado en el sitio central. Estos usuarios disfrutarán de la funcionalidad de comunicaciones unificadas completa, con la única salvedad de que las llamadas entrantes a la sucursal se trasladarán al correo de voz. Cuando la conexión WAN vuelva, deberá restaurarse la funcionalidad completa para los usuarios de las sucursales. Ni la conmutación por error a la aplicación de sucursal con funciones de supervivencia ni la restauración del servicio requiere la presencia de un administrador de ti.

Lync Server admite hasta dos dispositivos de sucursal con funciones de supervivencia en un sitio de sucursal.

<div>


> [!NOTE]  
> Los usuarios hospedados en una aplicación de sucursal con funciones de supervivencia de Lync Server no pueden crear salones de chat nuevos ni ver la tarjeta de la sala para las salas existentes.



</div>

<div>

## <a name="survivable-branch-appliance-deployment-overview"></a>Descripción general de la implementación de la aplicación de sucursal con funciones de supervivencia

La aplicación de sucursal con funciones de supervivencia la fabrican los fabricantes de equipos originales en asociación con Microsoft y se implementan en su nombre por parte de distribuidores de valor agregado. Esta implementación solo debe realizarse después de que Lync Server se haya implementado en el sitio central, una conexión WAN con el sitio de sucursal esté en su lugar y los usuarios de sitios de sucursal estén habilitados para telefonía IP empresarial.

Para obtener más información sobre estas fases, consulte [Deploying a supervivenciaable Branch Appliance or Server with Lync Server 2013](lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md) en la documentación sobre implementación.


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
<td><p>Configurar los servicios de dominio de Active Directory para la aplicación de sucursal con funciones de supervivencia</p></td>
<td><p><strong>En el sitio central:</strong></p>
<ol>
<li><p>Cree una cuenta de usuario de dominio (o identidad empresarial) para el técnico que vaya a instalar y activar la aplicación de sucursal con funciones de supervivencia en el sitio de sucursal.</p></li>
<li><p>Cree una cuenta de equipo (con el nombre de dominio completo (FQDN) aplicable) para la aplicación de sucursal con funciones de supervivencia en los servicios de dominio de Active Directory.</p></li>
<li><p>En el generador de topologías, cree y publique la aplicación de sucursal con funciones de supervivencia.</p></li>
</ol></td>
<td><p>La cuenta de usuario del técnico debe ser miembro de RTCUniversalSBATechnicians. La aplicación de sucursal con funciones de supervivencia debe pertenecer al grupo RTCSBAUniversalServices, que se produce automáticamente al usar el generador de topologías.</p></td>
</tr>
<tr class="even">
<td><p>Instale y active la aplicación de sucursal con funciones de supervivencia.</p></td>
<td><p><strong>En la sucursal:</strong></p>
<ol>
<li><p>Conecte la aplicación de sucursal con funciones de supervivencia a un puerto Ethernet y a un puerto RTC.</p></li>
<li><p>Inicie la aplicación de sucursal con funciones de supervivencia.</p></li>
<li><p>Únase a la aplicación de sucursal con funciones de supervivencia en el dominio con la cuenta de usuario de dominio creada para la aplicación de sucursal con funciones de supervivencia en el sitio central. Establezca el FQDN y la dirección IP de forma que coincidan con el FQDN creado en la cuenta del equipo.</p></li>
<li><p>Configure la aplicación de sucursal con funciones de supervivencia mediante la interfaz de usuario OEM.</p></li>
<li><p>Compruebe la conectividad RTC.</p></li>
</ol></td>
<td><p>La cuenta de usuario del técnico debe ser miembro de RTCUniversalSBATechnicians.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="survivable-branch-server-details"></a>Detalles del servidor de sucursal con funciones de supervivencia

En el generador de topologías, cree el sitio de sucursal, agregue el servidor de sucursal con funciones de supervivencia al sitio y, a continuación, ejecute el Asistente para la implementación de Lync Server en el equipo en el que desea instalar el rol.

</div>

</div>

<div>

## <a name="see-also"></a>Consulta también


[Implementar Lync Server 2013](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

