---
title: "Proceso de implementación de la integración de la mensajería unificada local"
TOCTitle: Proceso de implementación de la integración de la mensajería unificada local y Lync Server
ms:assetid: 269a4436-f09f-415b-96ab-49a64370a385
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg425737(v=OCS.15)
ms:contentKeyID: 48274727
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Proceso de implementación de la integración de la mensajería unificada local y Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

Si desea integrar la Mensajería unificada de Exchange (UM) con Lync Server 2013, deberá llevar a cabo las tareas descritas en este tema. Asimismo, asegúrese de que repasa los procedimientos recomendados de planeación e implementación explicados en [Instrucciones para integrar mensajería unificada local y Lync Server 2013](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md). En este tema se da por hecho que se ha implementado Lync Server 2013 con un servidor de mediación y que, además, se han habilitado usuarios para Lync Server 2013, si bien no es obligatorio seguir todos los pasos de implementación y configuración para habilitar Telefonía IP empresarial descritos en [Implementar la telefonía IP empresarial en Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md), en la documentación de implementación.

## Proceso de integración de la mensajería unificada

> [!IMPORTANT]  
> Es importante estar coordinado con los administradores de Exchange de la organización para constatar qué tareas va a realizar cada uno a fin de que la integración se realice de forma correcta y sin fisuras.




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
<li><p>Microsoft Exchange Server 2007 Service Pack 1 (SP2) o el el último service pack</p></li>
<li><p>Microsoft Exchange Server 2010 o el último service pack</p></li>
<li><p>Microsoft Exchange Server 2013</p></li>
</ul></td>
<td><p>Si va a utilizar Microsoft Exchange Server 2013, instale los siguientes roles de Exchange Server en el mismo bosque que Lync Server 2013 o en otro distinto:</p>
<ul>
<li><p>Acceso de clientes</p></li>
<li><p>Buzón de correo</p></li>
</ul>
<p>En caso de que Microsoft Exchange Server 2013 y la Mensajería unificada de Exchange (UM) estén instalados en bosques distintos, configure cada bosque de Exchange para confíe en el bosque de Lync Server 2013.</p>
<p>Si va a utilizar Exchange 2010, instale los siguientes roles de Exchange Server en el mismo bosque que Lync Server 2013 o en otro distinto:</p>
<ul>
<li><p>Mensajería unificada</p></li>
<li><p>Transporte de concentradores</p></li>
<li><p>Acceso de clientes</p></li>
<li><p>Buzón de correo</p></li>
</ul>
<p>En caso de que Lync Server 2013 y la Mensajería unificada de Exchange (UM) estén instalados en bosques distintos, configure cada bosque de Exchange para confíe en el bosque de Lync Server 2013.</p></td>
<td><p>Administradores de organización (si es el primer servidor de Exchange Server en la organización)</p>
<p>O BIEN:</p>
<p>Administrador de organización de Exchange (si no es el primer servidor de Exchange Server en la organización)</p></td>
<td><p>Consulte la documentación correspondiente a la versión de Exchange Server:</p>
<dl>
<dt><span></span></dt>
<dd><p>Documentación de implementación de Exchange Server 2007 en <a href="http://go.microsoft.com/fwlink/?linkid=268694%26clcid=0xc0a">http://go.microsoft.com/fwlink/?linkid=268694&amp;clcid=0xC0A</a>.</p>
</dd>
<dt><span></span></dt>
<dd><p>Documentación de implementación de Exchange Server 2010 o el último service pack en <a href="http://go.microsoft.com/fwlink/?linkid=268695%26clcid=0xc0a">http://go.microsoft.com/fwlink/?linkid=268695&amp;clcid=0xC0A</a>.</p>
</dd>
<dt><span></span></dt>
<dd><p>Planificación e implementación de Microsoft Exchange Server 2013 en <a href="http://go.microsoft.com/fwlink/?linkid=266569%26clcid=0xc0a">http://go.microsoft.com/fwlink/?linkid=266569&amp;clcid=0xC0A</a>.</p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p>Instalar los certificados.</p></td>
<td><p>Descargue e instale los certificados correspondientes a cada servidor de Mensajería unificada de Exchange de una entidad de certificación raíz de confianza (CA). Estos certificados son necesarios para la seguridad de nivel de transporte (TLS) mutua (MTLS) entre servidores que ejecutan Mensajería unificada de Exchange y Lync Server 2013.</p></td>
<td><p>Administradores</p></td>
<td><p><a href="lync-server-2013-configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging.md">Configurar certificados en el servidor que ejecuta la mensajería unificada de Microsoft Exchange Server</a></p></td>
</tr>
<tr class="odd">
<td><p>Crear y configurar un nuevo plan de marcado SIP de Mensajería unificada de Exchange.</p></td>
<td><p>En el servidor de Mensajería unificada de Exchange, cree un plan de marcado SIP en función de los requisitos de implementación específicos de la organización.</p></td>
<td><p>Administrador de organización de Exchange</p></td>
<td><p>Para Exchange 2007 SP1 o el último service pack, consulte &quot;Cómo crear un plan de marcado de mensajería unificada URI con SIP&quot; en <a href="http://go.microsoft.com/fwlink/?linkid=268632%26clcid=0xc0a">http://go.microsoft.com/fwlink/?linkid=268632&amp;clcid=0xC0A</a>.</p>
<p>Para Exchange 2010 o el último service pack, consulte &quot;Crear un plan de marcado de mensajería unificada&quot; en <a href="http://go.microsoft.com/fwlink/?linkid=268674%26clcid=0xc0a">http://go.microsoft.com/fwlink/?linkid=268674&amp;clcid=0xC0A</a>.</p>
<p>Para Exchange 2013, vea &quot;Mensajería unificada&quot; en <a href="http://go.microsoft.com/fwlink/?linkid=266579%26clcid=0xc0a">http://go.microsoft.com/fwlink/?linkid=266579&amp;clcid=0xC0A</a>.</p></td>
</tr>
<tr class="even">
<td><p>Configurar la seguridad para el plan de marcado SIP de Mensajería unificada de Exchange.</p></td>
<td><p>Para cifrar el tráfico de Enterprise Voice, defina la configuración de seguridad en el plan de marcado SIP de Mensajería unificada de Exchange como <strong>SIP protegida</strong> o como <strong>Protegida</strong>. Se trata de un paso especialmente importante si se ha implementado o se tiene previsto implementar dispositivos de Lync Phone Edition en el entorno. Para que los dispositivos de Lync Phone Edition funcionen en un entorno con integración de Mensajería unificada de Exchange, la configuración de cifrado de Lync Server debe concordar con la configuración de seguridad del plan de marcado de Mensajería unificada de Exchange. Para obtener información detallada, consulte la documentación de implementación.</p></td>
<td><p>Administrador de organización de Exchange</p></td>
<td><p><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">Configuración de la mensajería unificada de Microsoft Exchange en Lync Server 2013</a></p>
<p>Para Exchange 2007 SP1 o el último service pack, consulte también:</p>
<p>&quot;Configurar los ajustes de seguridad en un plan de conmutación de mensajería unificada&quot; en <a href="http://go.microsoft.com/fwlink/?linkid=268696%26clcid=0xc0a">http://go.microsoft.com/fwlink/?linkid=268696&amp;clcid=0xC0A</a>.</p>
<p></p>
<p>En el caso de Exchange 2010 o el último service pack, véase también:</p>
<p>&quot;Configurar la seguridad de VoIP en un plan de marcado de MU&quot; <a href="http://go.microsoft.com/fwlink/?linkid=268697%26clcid=0xc0a">http://go.microsoft.com/fwlink/?linkid=268697&amp;clcid=0xC0A</a>.</p>
<p></p>
<p>Para Exchange 2013, vea &quot;Mensajería unificada&quot; en <a href="http://go.microsoft.com/fwlink/?linkid=266579%26clcid=0xc0a">http://go.microsoft.com/fwlink/?linkid=266579&amp;clcid=0xC0A</a>.</p></td>
</tr>
<tr class="odd">
<td><p>Agregar servidores de mensajería unificada al plan de marcado SIP de Mensajería unificada de Exchange.</p></td>
<td><p>Para que un servidor de mensajería unificada recién instalado pueda contestar y procesar llamadas entrantes, dicho servidor se debe agregar a un plan de marcado de MU. En tal caso, agregue el servidor al plan de marcado SIP de Mensajería unificada de Exchange.</p></td>
<td><p>Administradores</p>
<p>Administradores de Exchange Server</p></td>
<td><p>Para Exchange 2007 SP1 o el último service pack, consulte &quot;Cómo agregar un servidor de mensajería unificada a un plan de marcado&quot; en <a href="http://go.microsoft.com/fwlink/?linkid=268681%26clcid=0xc0a">http://go.microsoft.com/fwlink/?linkid=268681&amp;clcid=0xC0A</a>.</p>
<p>Para Exchange 2010 o el último service pack, consulte &quot;Ver o configurar las propiedades de un servidor de mensajería unificada&quot; en <a href="http://go.microsoft.com/fwlink/?linkid=268682%26clcid=0xc0a">http://go.microsoft.com/fwlink/?linkid=268682&amp;clcid=0xC0A</a>.</p>
<p></p>
<p>Para Exchange 2013, vea &quot;Mensajería unificada&quot; en <a href="http://go.microsoft.com/fwlink/?linkid=266579%26clcid=0xc0a">http://go.microsoft.com/fwlink/?linkid=266579&amp;clcid=0xC0A</a>.</p></td>
</tr>
<tr class="even">
<td><p>Configurar buzones de correo con direcciones SIP.</p></td>
<td><p>Asigne direcciones SIP a los buzones de correo de los usuarios de Enterprise Voice que vayan a usar características de Mensajería unificada de Exchange.</p></td>
<td><p>Lync Server 2013nm-ocs-14-3rd</p>
<p>Administrador de destinatarios de Exchange</p></td>
<td><p>Para Exchange 2007 SP1 o el último service pack, consulte &quot;Cómo agregar, quitar o modificar una dirección SIP para un usuario habilitado para mensajería unificada&quot; en <a href="http://go.microsoft.com/fwlink/?linkid=268698%26clcid=0xc0a">http://go.microsoft.com/fwlink/?linkid=268698&amp;clcid=0xC0A</a>.</p>
<p>Para Exchange 2010 o el último service pack, consulte &quot;Modificar una dirección SIP para un usuario habilitado para MU&quot; en <a href="http://go.microsoft.com/fwlink/?linkid=268699%26clcid=0xc0a">http://go.microsoft.com/fwlink/?linkid=268699&amp;clcid=0xC0A</a>.</p>
<p></p>
<p>Para Exchange 2013, vea &quot;Mensajería unificada&quot; en <a href="http://go.microsoft.com/fwlink/?linkid=266579%26clcid=0xc0a">http://go.microsoft.com/fwlink/?linkid=266579&amp;clcid=0xC0A</a>.</p></td>
</tr>
<tr class="odd">
<td><p>Ejecutar el script exchucutil.ps1.</p></td>
<td><p>En el servidor en el que se ejecuten los servicios de Mensajería unificada de Exchange, abra el Shell de administración de Exchange y ejecute el script exchucutil.ps1, que hace lo siguiente:</p>
<ul>
<li><p>Concede a Lync Server 2013 permiso para leer objetos de Servicios de dominio de Active Directory de Mensajería unificada de Exchange, concretamente, los planes de marcado SIP creados en la tarea anterior.</p></li>
<li><p>Crea un objeto de puerta de enlace IP de mensajería unificada en Active Directory para cada servidor Standard Edition o grupo de servidores Enterprise Edition de Lync Server 2013 que hospede usuarios habilitados para Enterprise Voice.</p></li>
<li><p>Crea un grupo de búsqueda de Mensajería unificada de Exchange para cada puerta de enlace. El identificador piloto del grupo de búsqueda será el nombre del plan de marcado asociado a la puerta de enlace correspondiente. Se deberá establecer una asignación 1:1 en caso de que exista más de un plan de marcado.</p></li>
</ul></td>
<td><p>Administrador de organización de Exchange</p>
<p>Administrador de destinatarios de Exchange</p></td>
<td><p><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">Configuración de la mensajería unificada de Microsoft Exchange en Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Configurar planes de marcado de Lync Server 2013.</p></td>
<td><p>Si está integrado en Exchange 2007 SP1 o el último service pack, o Exchange 2010, cree un nuevo plan de marcado de Telefonía IP empresarial con el mismo nombre que el nombre de dominio completo (FQDN) del plan de marcado de mensajería unificada de Exchange.</p>
<div>

> [!NOTE]
> Deberá hacer esto para cada plan de marcado de mensajería unificada.


</div>
<p>Si está integrado en Exchange 2010 SP1, asegúrese de que se han configurado los planes de marcado de Telefonía IP empresarial de nivel de grupo o nivel de sitio/global pertinentes.</p>
<div>

> [!NOTE]
> Si está integrado en Exchange 2010 SP1, los nombres del plan de marcado de Lync Server y del plan de marcado SIP de mensajería unificada de Exchange no tienen por qué coincidir.


</div></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-configuring-dial-plans.md">Configurar planes de marcado en Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Ejecutar la herramienta de integración de Mensajería unificada de Exchange.</p></td>
<td><p>En Lync Server 2013, ejecute <strong>ocsumutil.exe</strong>, que efectúa lo siguiente:</p>
<ul>
<li><p>Crea los objetos de contacto de acceso de suscriptor y operador automático.</p></li>
<li><p>Valida que existe un plan de marcado de Telefonía IP empresarial con un nombre que coincida con el nombre de dominio completo (FQDN) del plan de marcado de mensajería unificada de Exchange. Si se está ejecutando Exchange 2010 SP1 o posterior, no es necesario que estos nombres coincidan y se puede pasar por alto la advertencia de la herramienta.</p></li>
</ul>
<p>Esta herramienta busca en Active Directory opciones de configuración de mensajería unificada de Exchange y permite al administrador de Lync Server 2013 ver, crear y editar objetos de contacto.</p></td>
<td><p>RTCUniversalServerAdmins <em>y</em> RTCUniversalUserAdmins</p>
<div>

> [!IMPORTANT]  
> Para ejecutar ocsumutil.exe correctamente, el usuario debe pertenecer a ambos grupos.

</div>
<div>

> [!NOTE]  
> Para crear objetos de contacto, el usuario que ejecute ocsumutil.exe debe poseer el permiso adecuado en la unidad organizativa de Active&nbsp;Directory en la que los nuevos objetos de contacto están almacenados. Este permiso se puede obtener si se ejecuta el cmdlet <STRONG>Grant-CsOUPermission</STRONG>. Para obtener información detallada, consulte la documentación del Shell de administración de Lync Server.


</div></td>
<td><p><a href="lync-server-2013-configure-lync-server-2013-to-work-with-unified-messaging-on-microsoft-exchange-server.md">Configurar Lync Server 2013 para trabajar con la mensajería unificada en Microsoft Exchange Server</a></p></td>
</tr>
<tr class="even">
<td><p>Si procede, realizar otros pasos de configuración de Telefonía IP empresarial.</p></td>
<td><p>En caso de que Telefonía IP empresarial todavía no se haya configurado en los servidores o usuarios, lleve a cabo una de las siguientes acciones:</p>
<ul>
<li><p>Implementar y configurar</p>
<p>puertas de enlace de red telefónica conmutada (RTC) y servidores de mediación.</p></li>
<li><p>Definir directivas de voz, registros de uso de RTC y rutas de llamadas realizadas.</p></li>
<li><p>Habilitar a los usuarios para Enterprise Voice.</p></li>
<li><p>De forma alternativa, configurar usuarios específicos con planes de marcado.</p></li>
</ul>
<p>Según cuáles sean las características de Telefonía IP empresarial que se habiliten, es posible que sea necesario realizar más pasos de configuración.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>RTCUniversalUserAdmins</p></td>
<td><p>Consulte los temas de las siguientes secciones:</p>
<ul>
<li><p><a href="lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md">Configuración de directivas de voz, registros de uso de RTC y rutas de voz en Lync Server 2013</a></p></li>
<li><p><a href="lync-server-2013-deploying-enterprise-voice.md">Implementar la telefonía IP empresarial en Lync Server 2013</a></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Habilitar a los usuarios para Enterprise Voice para la Mensajería unificada de Exchange.</p></td>
<td><p>En el servidor de Mensajería unificada de Exchange, asegúrese de que se ha creado una directiva de buzón de correo de mensajería unificada y que cada usuario tiene asignado un número de extensión único y, a continuación, habilite al usuario para la mensajería unificada.</p></td>
<td><p>Administrador de destinatarios de Exchange</p></td>
<td><p>Para Exchange 2007 SP1 o el último service pack, consulte &quot;Cómo habilitar a un usuario para que utilice mensajería unificada&quot; en <a href="http://go.microsoft.com/fwlink/?linkid=268700%26clcid=0xc0a">http://go.microsoft.com/fwlink/?linkid=268700&amp;clcid=0xC0A</a>.</p>
<p>En el caso de Exchange 2010 o el último service pack, consulte &quot;Habilitar un usuario para mensajería unificada&quot; en <a href="http://go.microsoft.com/fwlink/?linkid=268701%26clcid=0xc0a">http://go.microsoft.com/fwlink/?linkid=268701&amp;clcid=0xC0A</a>.</p>
<p></p>
<p>Para Exchange 2013, vea &quot;Mensajería unificada&quot; en <a href="http://go.microsoft.com/fwlink/?linkid=266579%26clcid=0xc0a">http://go.microsoft.com/fwlink/?linkid=266579&amp;clcid=0xC0A</a>.</p></td>
</tr>
</tbody>
</table>

