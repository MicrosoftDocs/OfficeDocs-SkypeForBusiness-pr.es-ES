---
title: Proceso de implementación para integrar la mensajería unificada local
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
ms.openlocfilehash: 76a45210fa90e5d2493885e54f07bb922f6d0495
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762618"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-integrating-on-premises-unified-messaging-and-lync-server-2013"></a>Proceso de implementación de la integración de la mensajería unificada local y Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-12-17_

Si desea integrar la mensajería unificada de Exchange (UM) con Lync Server 2013, debe realizar las tareas descritas en este tema. Además, asegúrese de revisar las prácticas recomendadas de planeamiento e implementación descritas en [directrices para integrar la mensajería unificada local y Lync Server 2013](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md). En este tema se supone que ha implementado Lync Server 2013 con un servidor de mediación en el que ha habilitado usuarios para Lync Server 2013, pero no necesariamente que haya realizado todos los pasos de implementación y configuración para habilitar la telefonía IP empresarial, como se describe en [implementar la telefonía IP empresarial en Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) , en la documentación de implementación.

<div>

## <a name="unified-messaging-integration-process"></a>Proceso de integración de la mensajería unificada

<div>


> [!IMPORTANT]
> Es importante estar coordinado con los administradores de Exchange de la organización para constatar qué tareas va a realizar cada uno a fin de que la integración se realice de forma correcta y sin fisuras.



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
<li><p>Microsoft Exchange Server 2007 Service Pack 1 (SP2) o el Service Pack más reciente</p></li>
<li><p>Microsoft Exchange Server 2010 o Service Pack más reciente</p></li>
<li><p>Microsoft Exchange Server 2013</p></li>
</ul></td>
<td><p>Si usa Microsoft Exchange Server 2013, instale los siguientes roles de servidor de Exchange en el mismo bosque o en un bosque diferente que Lync Server 2013:</p>
<ul>
<li><p>Acceso de clientes</p></li>
<li><p>Buzón de correo</p></li>
</ul>
<p>Si Microsoft Exchange Server 2013 y mensajería unificada de Exchange se instalan en bosques diferentes, configure cada bosque de Exchange para que confíe en el bosque de Lync Server 2013.</p>
<p>Si usa Exchange 2010, instale los siguientes roles de servidor de Exchange en el mismo bosque o en un bosque diferente que Lync Server 2013:</p>
<ul>
<li><p>Mensajería unificada</p></li>
<li><p>Transporte de concentradores</p></li>
<li><p>Acceso de clientes</p></li>
<li><p>Buzón de correo</p></li>
</ul>
<p>Si Lync Server 2013 y mensajería unificada de Exchange se instalan en bosques diferentes, configure cada bosque de Exchange para que confíe en el bosque de Lync Server 2013.</p></td>
<td><p>Administradores de organización (si es el primer servidor de Exchange Server en la organización)</p>
<p>O BIEN:</p>
<p>Administrador de organización de Exchange (si no es el primer servidor de Exchange Server en la organización)</p></td>
<td><p>Consulte la documentación correspondiente a la versión de Exchange Server:</p>
<dl>
<dt><span></span></dt>
<dd><p>Documentación de implementación de Exchange Server <a href="http://go.microsoft.com/fwlink/p/?linkid=268694">http://go.microsoft.com/fwlink/p/?LinkId=268694</a>2007 en.</p>
</dd>
<dt><span></span></dt>
<dd><p>Exchange Server 2010 o la documentación de implementación del Service <a href="http://go.microsoft.com/fwlink/p/?linkid=268695">http://go.microsoft.com/fwlink/p/?LinkId=268695</a>Pack más reciente en.</p>
</dd>
<dt><span></span></dt>
<dd><p>Microsoft Exchange Server 2013 Planning and Deployment en <a href="http://go.microsoft.com/fwlink/p/?linkid=266569">http://go.microsoft.com/fwlink/p/?LinkId=266569</a>.</p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p>Instalar los certificados.</p></td>
<td><p>Descargue e instale certificados para cada servidor de mensajería unificada de Exchange de una entidad de certificación (CA) raíz de confianza. Los certificados son necesarios para la seguridad del nivel de transporte mutuo (MTLS) entre los servidores que ejecutan la mensajería unificada de Exchange y Lync Server 2013.</p></td>
<td><p>Administradores</p></td>
<td><p><a href="lync-server-2013-configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging.md">Configurar certificados en el servidor que ejecuta la mensajería unificada de Microsoft Exchange Server</a></p></td>
</tr>
<tr class="odd">
<td><p>Cree y configure un nuevo plan de marcado SIP de Exchange UM.</p></td>
<td><p>En el servidor de mensajería unificada de Exchange, cree un plan de marcado SIP basado en los requisitos de implementación específicos de su organización.</p></td>
<td><p>Administrador de organización de Exchange</p></td>
<td><p>Para Exchange 2007 SP1 o el Service Pack más reciente &quot;, vea cómo crear un plan&quot; de marcado URI del SIP <a href="http://go.microsoft.com/fwlink/p/?linkid=268632">http://go.microsoft.com/fwlink/p/?linkId=268632</a>de mensajería unificada en.</p>
<p>Para Exchange 2010 o el Service Pack más reciente &quot;, consulte crear un plan&quot; de <a href="http://go.microsoft.com/fwlink/p/?linkid=268674">http://go.microsoft.com/fwlink/p/?linkId=268674</a>marcado de MU en.</p>
<p>Para Exchange 2013, consulte mensajería unificada <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>en.</p></td>
</tr>
<tr class="even">
<td><p>Configure las opciones de seguridad para el plan de marcado SIP de mensajería unificada de Exchange.</p></td>
<td><p>Para cifrar el tráfico de voz empresarial, establezca la configuración de seguridad en el plan de marcado SIP de mensajería unificada de Exchange como <strong>SIP protegido</strong> o <strong>seguro</strong>. Este es un paso especialmente importante si ha implementado o tiene previsto implementar dispositivos de Lync Phone Edition en su entorno. Para que los dispositivos de Lync Phone Edition funcionen en un entorno con integración de MU de Exchange, la configuración de cifrado de Lync Server debe alinearse con la configuración de seguridad del plan de marcado de MU de Exchange. Para obtener información detallada, consulte la documentación de implementación.</p></td>
<td><p>Administrador de organización de Exchange</p></td>
<td><p><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">Configurar la mensajería unificada en Microsoft Exchange para Lync Server 2013</a></p>
<p>Para Exchange 2007 SP1 o el Service Pack más reciente, vea también:</p>
<p>&quot;Cómo configurar la seguridad en un plan&quot; de marcado de mensajería <a href="http://go.microsoft.com/fwlink/p/?linkid=268696">http://go.microsoft.com/fwlink/p/?LinkId=268696</a>unificada en.</p>
<p>En el caso de Exchange 2010 o el último service pack, véase también:</p>
<p>&quot;Configurar la seguridad de VoIP en un plan&quot; <a href="http://go.microsoft.com/fwlink/p/?linkid=268697">http://go.microsoft.com/fwlink/p/?LinkId=268697</a>de marcado de MU</p>
<p>Para Exchange 2013, consulte mensajería unificada <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>en.</p></td>
</tr>
<tr class="odd">
<td><p>Agregue servidores de mensajería unificada al plan de marcado SIP de mensajería unificada de Exchange.</p></td>
<td><p>Para que un servidor de mensajería unificada recién instalado pueda responder y procesar llamadas entrantes, es necesario agregarlo a un plan de marcado de mensajería unificada. En este caso, agregue el servidor al plan de marcado SIP de mensajería unificada de Exchange.</p></td>
<td><p>Administradores</p>
<p>Administradores de Exchange Server</p></td>
<td><p>Para Exchange 2007 SP1 o el Service Pack más reciente &quot;, vea cómo agregar un servidor de mensajería unificada&quot; a <a href="http://go.microsoft.com/fwlink/p/?linkid=268681">http://go.microsoft.com/fwlink/p/?linkId=268681</a>un plan de marcado en.</p>
<p>Para Exchange 2010 o el Service Pack más reciente &quot;, consulte ver o configurar las propiedades de un&quot; servidor <a href="http://go.microsoft.com/fwlink/p/?linkid=268682">http://go.microsoft.com/fwlink/p/?linkId=268682</a>de mensajería unificada en.</p>
<p>Para Exchange 2013, consulte mensajería unificada <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>en.</p></td>
</tr>
<tr class="even">
<td><p>Configurar buzones de correo con direcciones SIP.</p></td>
<td><p>Asigne direcciones SIP a los buzones de usuarios de telefonía IP que usarán las características de mensajería unificada de Exchange.</p></td>
<td><p>Administrador de 2013 de Lync Server</p>
<p>Administrador de destinatarios de Exchange</p></td>
<td><p>Para Exchange 2007 SP1 o el Service Pack más reciente &quot;, vea cómo agregar, quitar o modificar una dirección SIP para un usuario&quot; habilitado para um <a href="http://go.microsoft.com/fwlink/p/?linkid=268698">http://go.microsoft.com/fwlink/p/?LinkId=268698</a>en.</p>
<p>Para Exchange 2010 o el Service Pack más reciente &quot;, consulte modificar una dirección SIP para un usuario&quot; habilitado <a href="http://go.microsoft.com/fwlink/p/?linkid=268699">http://go.microsoft.com/fwlink/p/?LinkId=268699</a>para um en.</p>
<p>Para Exchange 2013, consulte mensajería unificada <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>en.</p></td>
</tr>
<tr class="odd">
<td><p>Ejecutar el script exchucutil.ps1.</p></td>
<td><p>En el servidor que ejecuta los servicios de mensajería unificada de Exchange, abra el shell de administración de Exchange y ejecute el script ExchUCUtil. ps1, que hace lo siguiente:</p>
<ul>
<li><p>Concede el permiso de Lync Server 2013 para leer objetos de servicios de dominio de Active Directory UM de Exchange, específicamente, los planes de marcado SIP creados en la tarea anterior.</p></li>
<li><p>Crea un objeto de puerta de enlace IP de mensajería unificada en Active Directory para cada grupo de servidores de Lync Server 2013 Enterprise Edition o servidor Standard Edition que hospeda usuarios que están habilitados para telefonía IP empresarial.</p></li>
<li><p>Crea un grupo de captura de mensajería unificada de Exchange para cada puerta de enlace. El identificador piloto del grupo de extensiones será el nombre del plan de marcado asociado a la puerta de enlace correspondiente. Es necesario establecer una asignación 1:1 si existe más de un plan de marcado.</p></li>
</ul></td>
<td><p>Administrador de organización de Exchange</p>
<p>Administrador de destinatarios de Exchange</p></td>
<td><p><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">Configurar la mensajería unificada en Microsoft Exchange para Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Configure los planes de marcado de Lync Server 2013.</p></td>
<td><p>Si está integrando con Exchange 2007 SP1 o el Service Pack más reciente o Exchange 2010, cree un nuevo plan de marcado de voz empresarial con un nombre que coincida con el nombre de dominio completo del plan de marcado de Exchange UM (FQDN).</p>



> [!NOTE]
> Deberá hacer esto para cada plan de marcado de mensajería unificada.


<p>Si está integrando con el SP1 de Exchange 2010, asegúrese de que los planes de marcado de voz empresariales de nivel global/sitio o de grupo se hayan configurado de forma adecuada.</p>



> [!NOTE]
> Si está integrando con Exchange 2010 SP1, no es necesario que coincidan los nombres del plan de marcado de Lync Server y del plan de marcado SIP de mensajería unificada de Exchange.

</td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-configuring-dial-plans.md">Configurar planes de marcado en Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Ejecute la herramienta de integración de mensajería unificada de Exchange.</p></td>
<td><p>En Lync Server 2013, ejecute <strong>OCSUMUtil. exe</strong>, que:</p>
<ul>
<li><p>Crea los objetos de contacto de acceso de suscriptor y operador automático.</p></li>
<li><p>Valida que haya un plan de marcado de voz de empresa con un nombre que coincida con el FQDN del plan de marcado de mensajería unificada de Exchange. Si está ejecutando Exchange 2010 SP1 o posterior, no es necesario que los nombres del plan de marcado coincidan y puede ignorar la advertencia de la herramienta sobre este.</p></li>
</ul>
<p>Esta herramienta explora la configuración de mensajería unificada de Active Directory para Exchange y permite que el administrador de 2013 de Lync Server vea, cree y edite objetos de contacto.</p></td>
<td><p>RTCUniversalServerAdmins <em>y</em> RTCUniversalUserAdmins</p>



> [!IMPORTANT]
> Para ejecutar ocsumutil.exe correctamente, el usuario debe pertenecer a ambos grupos.





> [!NOTE]
> Para crear objetos de contacto, el usuario que ejecute ocsumutil.exe necesita tener el permiso adecuado en la unidad organizativa de Active Directory donde están almacenados los nuevos objetos contacto. Este permiso se puede conceder si se ejecuta el cmdlet <STRONG>Grant-CsOUPermission</STRONG>. Para obtener más información, consulte la documentación del shell de administración de Lync Server.

</td>
<td><p><a href="lync-server-2013-configure-lync-server-2013-to-work-with-unified-messaging-on-microsoft-exchange-server.md">Configurar Lync Server 2013 para trabajar con la mensajería unificada en Microsoft Exchange Server</a></p></td>
</tr>
<tr class="even">
<td><p>Si es necesario, realice otros pasos de configuración de voz empresarial.</p></td>
<td><p>Si aún no ha configurado la configuración de voz de empresa en sus servidores o usuarios, siga uno o varios de estos procedimientos:</p>
<ul>
<li><p>Implementar y configurar</p>
<p>puertas de enlace de red telefónica conmutada (RTC) y servidores de mediación.</p></li>
<li><p>Definir directivas de voz, registros de uso de RTC y rutas de llamadas realizadas.</p></li>
<li><p>Habilitar a los usuarios para Enterprise Voice.</p></li>
<li><p>De forma alternativa, configurar usuarios específicos con planes de marcado.</p></li>
</ul>
<p>Puede que se requieran otros pasos de configuración según las características de Enterprise Voice que habilite.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>RTCUniversalUserAdmins</p></td>
<td><p>Consulte los temas de las siguientes secciones:</p>
<ul>
<li><p><a href="lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md">Configuración de directivas de voz, registros de uso de RTC y rutas de voz en Lync Server 2013</a></p></li>
<li><p><a href="lync-server-2013-deploying-enterprise-voice.md">Implementación de telefonía IP empresarial en Lync Server 2013</a></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Habilite los usuarios de telefonía IP empresarial para la mensajería unificada de Exchange.</p></td>
<td><p>En el servidor de mensajería unificada de Exchange, asegúrese de que se ha creado una directiva de buzón de mensajería unificada y de que cada usuario tiene una asignación de número de extensión única y, después, habilite al usuario para la mensajería unificada.</p></td>
<td><p>Administrador de destinatarios de Exchange</p></td>
<td><p>Para Exchange 2007 SP1 o el Service Pack más reciente &quot;, vea cómo habilitar un usuario para mensajería&quot; unificada en <a href="http://go.microsoft.com/fwlink/p/?linkid=268700">http://go.microsoft.com/fwlink/p/?LinkId=268700</a>.</p>
<p>Para Exchange 2010 o el Service Pack más reciente &quot;, vea Habilitar un usuario para&quot; mensajería <a href="http://go.microsoft.com/fwlink/p/?linkid=268701">http://go.microsoft.com/fwlink/p/?LinkId=268701</a>unificada en.</p>
<p>Para Exchange 2013, consulte mensajería unificada <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>en.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

