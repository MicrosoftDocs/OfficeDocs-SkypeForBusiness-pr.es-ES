---
title: Proceso de implementación para la integración de la mensajería unificada local
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for integrating on-premises Unified Messaging and Lync Server
ms:assetid: 269a4436-f09f-415b-96ab-49a64370a385
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425737(v=OCS.15)
ms:contentKeyID: 48183664
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d6d60b120db57ad73c33e682fa8150e99f5606e3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137169"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-integrating-on-premises-unified-messaging-and-lync-server-2013"></a>Proceso de implementación para la integración de la mensajería unificada local y Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-12-17_

Si desea integrar la mensajería unificada (UM) de Exchange con Lync Server 2013, debe realizar las tareas descritas en este tema. Además, asegúrese de revisar los procedimientos recomendados de planeación e implementación que se describen en [directrices para integrar la mensajería unificada local y Lync Server 2013](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md). En este tema se supone que ha implementado Lync Server 2013 con un servidor de mediación combinado y que ha habilitado usuarios para Lync Server 2013, pero no necesariamente que haya realizado todos los pasos de implementación y configuración para habilitar Enterprise Voice, tal y como se describe en [Deploying Enterprise Voice in Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) en la documentación sobre implementación.

<div>

## <a name="unified-messaging-integration-process"></a>Proceso de integración de la mensajería unificada

<div>


> [!IMPORTANT]
> Es importante que se coordine con los administradores de Exchange de la organización para confirmar las tareas que realizará cada uno para ayudar a garantizar una integración correcta y sin problemas.



</div>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Fase</th>
<th>Pasos</th>
<th>Grupos y roles necesarios</th>
<th>Documentación de implementación</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Implementar una de las siguientes aplicaciones:</p>
<ul>
<li><p>Microsoft Exchange Server 2007 Service Pack 1 (SP2) o el último Service Pack</p></li>
<li><p>Microsoft Exchange Server 2010 o Service Pack más reciente</p></li>
<li><p>Microsoft Exchange Server 2013</p></li>
</ul></td>
<td><p>Si usa Microsoft Exchange Server 2013, instale los siguientes roles de Exchange Server en el mismo bosque o en un bosque diferente que Lync Server 2013:</p>
<ul>
<li><p>Acceso de clientes</p></li>
<li><p>Buzón de correo</p></li>
</ul>
<p>Si Microsoft Exchange Server 2013 y mensajería unificada de Exchange están instalados en bosques distintos, configure cada bosque de Exchange para que confíe en el bosque de Lync Server 2013.</p>
<p>Si usa Exchange 2010, instale los siguientes roles de servidor de Exchange en el mismo bosque o en un bosque diferente que Lync Server 2013:</p>
<ul>
<li><p>Mensajería unificada</p></li>
<li><p>Transporte de concentradores</p></li>
<li><p>Acceso de clientes</p></li>
<li><p>Buzón de correo</p></li>
</ul>
<p>Si Lync Server 2013 y mensajería unificada de Exchange están instalados en bosques distintos, configure cada bosque de Exchange para que confíe en el bosque de Lync Server 2013.</p></td>
<td><p>Administradores de organización (si es el primer servidor de Exchange Server en la organización)</p>
<p>O BIEN</p>
<p>Administrador de organización de Exchange (si no es el primer servidor de Exchange Server en la organización)</p></td>
<td><p>Consulte la documentación correspondiente a la versión de Exchange Server:</p>
<dl>
<dt><span></span></dt>
<dd><p>Documentación de implementación de Exchange Server <a href="https://go.microsoft.com/fwlink/p/?linkid=268694">https://go.microsoft.com/fwlink/p/?LinkId=268694</a>2007 en.</p>
</dd>
<dt><span></span></dt>
<dd><p>Exchange Server 2010 o la documentación de implementación de Service <a href="https://go.microsoft.com/fwlink/p/?linkid=268695">https://go.microsoft.com/fwlink/p/?LinkId=268695</a>Pack más reciente en.</p>
</dd>
<dt><span></span></dt>
<dd><p>Planeación e implementación de Microsoft Exchange Server <a href="https://go.microsoft.com/fwlink/p/?linkid=266569">https://go.microsoft.com/fwlink/p/?LinkId=266569</a>2013 en.</p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p>Instalar los certificados.</p></td>
<td><p>Descargue e instale certificados para cada servidor de mensajería unificada de Exchange de una entidad de certificación (CA) raíz de confianza. Los certificados son necesarios para la seguridad de nivel de transporte mutuo (MTLS) entre los servidores que ejecutan la mensajería unificada de Exchange y Lync Server 2013.</p></td>
<td><p>Administradores</p></td>
<td><p><a href="lync-server-2013-configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging.md">Configurar certificados en el servidor que ejecuta la mensajería unificada de Microsoft Exchange Server</a></p></td>
</tr>
<tr class="odd">
<td><p>Cree y configure un nuevo plan de marcado SIP de mensajería unificada de Exchange.</p></td>
<td><p>En el servidor de mensajería unificada de Exchange, cree un plan de marcado SIP en función de los requisitos de implementación específicos de la organización.</p></td>
<td><p>Administrador de organización de Exchange</p></td>
<td><p>Para Exchange 2007 SP1 o el último Service Pack, &quot;vea cómo crear un plan&quot; de marcado URI de SIP de <a href="https://go.microsoft.com/fwlink/p/?linkid=268632">https://go.microsoft.com/fwlink/p/?linkId=268632</a>mensajería unificada en.</p>
<p>Para Exchange 2010 o el Service Pack más reciente &quot;, vea crear un plan&quot; de <a href="https://go.microsoft.com/fwlink/p/?linkid=268674">https://go.microsoft.com/fwlink/p/?linkId=268674</a>marcado de mensajería unificada en.</p>
<p>Para Exchange 2013, vea Mensajería unificada <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a>en.</p></td>
</tr>
<tr class="even">
<td><p>Configure las opciones de seguridad para el plan de marcado SIP de mensajería unificada de Exchange.</p></td>
<td><p>Para cifrar el tráfico de telefonía IP empresarial, configure la configuración de seguridad en el plan de marcado SIP de mensajería unificada de Exchange como <strong>SIP protegida</strong> o <strong>protegida</strong>. Este es un paso especialmente importante si ha implementado o tiene previsto implementar dispositivos Lync Phone Edition en su entorno. Para que los dispositivos de Lync Phone Edition funcionen en un entorno con integración de mensajería unificada de Exchange, la configuración de cifrado de Lync Server debe alinearse con la configuración de seguridad del plan de marcado de MU de Exchange. Para obtener información detallada, consulte la documentación de implementación.</p></td>
<td><p>Administrador de organización de Exchange</p></td>
<td><p><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">Configurar la mensajería unificada en Microsoft Exchange para Lync Server 2013</a></p>
<p>Para Exchange 2007 SP1 o el último Service Pack, vea también:</p>
<p>&quot;Cómo configurar la seguridad en un plan&quot; de marcado de mensajería <a href="https://go.microsoft.com/fwlink/p/?linkid=268696">https://go.microsoft.com/fwlink/p/?LinkId=268696</a>unificada en.</p>
<p>En el caso de Exchange 2010 o el último service pack, véase también:</p>
<p>&quot;Configurar la seguridad de VoIP en un plan&quot; <a href="https://go.microsoft.com/fwlink/p/?linkid=268697">https://go.microsoft.com/fwlink/p/?LinkId=268697</a>de marcado de mensajería unificada.</p>
<p>Para Exchange 2013, vea Mensajería unificada <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a>en.</p></td>
</tr>
<tr class="odd">
<td><p>Agregar servidores de mensajería unificada al plan de marcado SIP de mensajería unificada de Exchange.</p></td>
<td><p>Para que un servidor de mensajería unificada recién instalado pueda contestar y procesar llamadas entrantes, dicho servidor se debe agregar a un plan de marcado de MU. En este caso, agregue el servidor al plan de marcado SIP de mensajería unificada de Exchange.</p></td>
<td><p>Administradores</p>
<p>Administradores de Exchange Server</p></td>
<td><p>Para Exchange 2007 SP1 o el último Service Pack, &quot;vea cómo agregar un servidor de mensajería unificada a&quot; un <a href="https://go.microsoft.com/fwlink/p/?linkid=268681">https://go.microsoft.com/fwlink/p/?linkId=268681</a>plan de marcado en.</p>
<p>Para Exchange 2010 o el Service Pack más reciente &quot;, consulte ver o configurar las propiedades de un&quot; servidor <a href="https://go.microsoft.com/fwlink/p/?linkid=268682">https://go.microsoft.com/fwlink/p/?linkId=268682</a>de mensajería unificada en.</p>
<p>Para Exchange 2013, vea Mensajería unificada <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a>en.</p></td>
</tr>
<tr class="even">
<td><p>Configurar buzones de correo con direcciones SIP.</p></td>
<td><p>Asigne direcciones SIP a los buzones de correo de los usuarios de Enterprise Voice que van a usar las características de mensajería unificada de Exchange.</p></td>
<td><p>Administrador de Lync Server 2013</p>
<p>Administrador de destinatarios de Exchange</p></td>
<td><p>Para Exchange 2007 SP1 o el último Service Pack, &quot;vea cómo agregar, quitar o modificar una dirección SIP para un usuario&quot; habilitado para mensajería unificada en. <a href="https://go.microsoft.com/fwlink/p/?linkid=268698">https://go.microsoft.com/fwlink/p/?LinkId=268698</a></p>
<p>Para Exchange 2010 o el Service Pack más reciente &quot;, vea modificar una dirección SIP para un usuario&quot; habilitado <a href="https://go.microsoft.com/fwlink/p/?linkid=268699">https://go.microsoft.com/fwlink/p/?LinkId=268699</a>para mensajería unificada en.</p>
<p>Para Exchange 2013, vea Mensajería unificada <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a>en.</p></td>
</tr>
<tr class="odd">
<td><p>Ejecutar el script exchucutil.ps1.</p></td>
<td><p>En el servidor que ejecuta los servicios de mensajería unificada de Exchange, abra el shell de administración de Exchange y ejecute el script script ExchUCUtil. ps1, que hace lo siguiente:</p>
<ul>
<li><p>Concede el permiso Lync Server 2013 para leer los objetos de servicios de dominio de Active Directory de mensajería unificada de Exchange, en concreto, los planes de marcado SIP creados en la tarea anterior.</p></li>
<li><p>Crea un objeto de puerta de enlace IP de mensajería unificada en Active Directory para cada grupo de servidores de Lync Server 2013 Enterprise Edition o servidor Standard Edition que hospeda usuarios habilitados para telefonía IP empresarial.</p></li>
<li><p>Crea un grupo de extensiones de mensajería unificada de Exchange para cada puerta de enlace. El identificador piloto del grupo de búsqueda será el nombre del plan de marcado asociado a la puerta de enlace correspondiente. Se deberá establecer una asignación 1:1 en caso de que exista más de un plan de marcado.</p></li>
</ul></td>
<td><p>Administrador de organización de Exchange</p>
<p>Administrador de destinatarios de Exchange</p></td>
<td><p><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">Configurar la mensajería unificada en Microsoft Exchange para Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Configure los planes de marcado de Lync Server 2013.</p></td>
<td><p>Si está integrando con Exchange 2007 SP1 o el Service Pack más reciente o Exchange 2010, cree un nuevo plan de marcado de telefonía IP empresarial con un nombre que coincida con el nombre de dominio completo (FQDN) del plan de marcado de mensajería unificada de Exchange.</p>



> [!NOTE]
> Tendrá que hacerlo para cada plan de marcado de mensajería unificada.


<p>Si está integrando con Exchange 2010 SP1, asegúrese de que se hayan configurado los planes de marcado de Enterprise Voice de nivel global/sitio o grupo de servidores.</p>



> [!NOTE]
> Si está integrando con Exchange 2010 SP1, no es necesario que coinciden los nombres del plan de marcado de Lync Server y el plan de marcado SIP de mensajería unificada de Exchange.

</td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-configuring-dial-plans.md">Configurar planes de marcado en Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Ejecute la herramienta de integración de mensajería unificada de Exchange.</p></td>
<td><p>En Lync Server 2013, ejecute <strong>OCSUMUtil. exe</strong>, que:</p>
<ul>
<li><p>Crea los objetos de contacto de acceso de suscriptor y operador automático.</p></li>
<li><p>Valida que hay un plan de marcado de telefonía IP empresarial con un nombre que coincide con el FQDN del plan de marcado de mensajería unificada de Exchange. Si ejecuta Exchange 2010 SP1 o posterior, no es necesario que los nombres del plan de marcado sean coincidentes y puede omitir la advertencia de la herramienta sobre esto.</p></li>
</ul>
<p>Esta herramienta busca en Active Directory la configuración de mensajería unificada de Exchange y permite al administrador de 2013 de Lync Server ver, crear y editar objetos de contacto.</p></td>
<td><p>RTCUniversalServerAdmins <em>y</em> RTCUniversalUserAdmins</p>



> [!IMPORTANT]
> Para ejecutar ocsumutil.exe correctamente, el usuario debe pertenecer a ambos grupos.





> [!NOTE]
> Para crear objetos de contacto, el usuario que ejecute ocsumutil.exe debe poseer el permiso adecuado en la unidad organizativa de Active Directory en la que los nuevos objetos de contacto están almacenados. Este permiso se puede conceder mediante la ejecución del cmdlet <STRONG>Grant-CsOUPermission</STRONG> . Para obtener más información, vea la documentación referente a Lync Server Management Shell.

</td>
<td><p><a href="lync-server-2013-configure-lync-server-2013-to-work-with-unified-messaging-on-microsoft-exchange-server.md">Configurar Lync Server 2013 para trabajar con la mensajería unificada en Microsoft Exchange Server</a></p></td>
</tr>
<tr class="even">
<td><p>Si procede, realizar otros pasos de configuración de Enterprise Voice.</p></td>
<td><p>En caso de que Enterprise Voice todavía no se haya configurado en los servidores o usuarios, lleve a cabo una de las siguientes acciones:</p>
<ul>
<li><p>Implementar y configurar</p>
<p>Puertas de enlace y servidores de mediación de la red telefónica conmutada (RTC)</p></li>
<li><p>Definir directivas de voz, registros de uso de RTC y rutas de llamadas realizadas.</p></li>
<li><p>Habilitar a los usuarios para Enterprise Voice.</p></li>
<li><p>De forma alternativa, configurar usuarios específicos con planes de marcado.</p></li>
</ul>
<p>Según cuáles sean las características de Enterprise Voice que se habiliten, es posible que sea necesario realizar más pasos de configuración.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>RTCUniversalUserAdmins</p></td>
<td><p>Consulte los temas de las siguientes secciones:</p>
<ul>
<li><p><a href="lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md">Configurar directivas de voz, registros de uso de RTC y rutas de voz en Lync Server 2013</a></p></li>
<li><p><a href="lync-server-2013-deploying-enterprise-voice.md">Implementar la telefonía IP empresarial en Lync Server 2013</a></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Habilite a los usuarios de Enterprise Voice para la mensajería unificada de Exchange.</p></td>
<td><p>En el servidor de mensajería unificada de Exchange, asegúrese de que se ha creado una directiva de buzón de mensajería unificada y que cada usuario tiene una asignación de número de extensión única y, a continuación, habilite al usuario para la mensajería unificada.</p></td>
<td><p>Administrador de destinatarios de Exchange</p></td>
<td><p>Para Exchange 2007 SP1 o el último Service Pack, &quot;vea cómo habilitar a un usuario para la&quot; mensajería <a href="https://go.microsoft.com/fwlink/p/?linkid=268700">https://go.microsoft.com/fwlink/p/?LinkId=268700</a>unificada en.</p>
<p>Para Exchange 2010 o el Service Pack más reciente &quot;, consulte habilitar a un usuario&quot; para <a href="https://go.microsoft.com/fwlink/p/?linkid=268701">https://go.microsoft.com/fwlink/p/?LinkId=268701</a>mensajería unificada en.</p>
<p>Para Exchange 2013, vea Mensajería unificada <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a>en.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

