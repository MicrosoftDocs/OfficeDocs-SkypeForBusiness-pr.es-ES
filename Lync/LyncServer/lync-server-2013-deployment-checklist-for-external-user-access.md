---
title: "Lista de comprobación de la implementación del acceso de usuarios externos"
TOCTitle: Lista de comprobación de la implementación del acceso de usuarios externos
ms:assetid: 3f55f502-88a0-4315-8783-45a32a0b78ea
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg425910(v=OCS.15)
ms:contentKeyID: 48275026
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lista de comprobación de la implementación del acceso de usuarios externos en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

Para implementar la red perimetral y la compatibilidad con el acceso de usuarios externos, debe haber implementado ya los servidores internos de Microsoft Lync Server 2013, como Grupo de servidores front-end o Servidor Standard Edition. Si piensa implementar Directores en la red interna, también debe implementarlos antes de implementar los Servidores perimetrales. Para obtener más información sobre el proceso de implementación de Director, consulte [Escenarios para el director en Lync Server 2013](lync-server-2013-scenarios-for-the-director.md) en la documentación sobre planeación.

Microsoft Lync Server 2013 incluye herramientas para facilitar la planeación y la implementación de servidores internos y servidores perimetrales. Después que se haya completado la topología, publique la definición de la topología resultante a su entorno de producción. Para ello, deberá ser miembro de los grupos **Administradores de dominio** y **RTCUniversalServerAdmins**.

  - **Herramienta de planificación**    Office Communications Server 2007 R2 incluía una herramienta de planificación y una herramienta de planificación perimetral que podía utilizar para el diseño de la topología de la guía. En el Lync Server 2010, estas dos herramientas se combinaron en un único Herramienta de planeación que tiene características y funcionalidades adicionales, como la recopilación de recuentos de usuarios previstos, los requisitos de voz, los tipos de acceso de usuarios externos y las opciones de federación. Además, puede planificar los parámetros de la red de la infraestructura, como las direcciones IP, los tipos de equilibradores de carga y otras consideraciones de red perimetrales.

  - **Generador de topología**    Lync Server 2013  Generador de topologías le ayuda a definir su topología y sus componentes. Generador de topologías es esencial para implementar los servidores que se ejecutan en Lync Server 2013. Generador de topologías publica los resultados a un Almacén de administración central que se utiliza para configurar todos los servidores que se ejecutan en Lync Server 2013 de su organización. No puede instalar Lync Server 2013 en los servidores sin utilizar Generador de topologías.

Si ha diseñado su topología perimetral durante el proceso de planificación, incluida la ejecución de Generador de topologías para definir la topología perimetral, puede utilizar estos resultados para iniciar la implementación del servidor perimetral. Si no finalizó la creación de su topología perimetral antes o si desea cambiar la información que especificó previamente, tiene que finalizar la ejecución de Generador de topologías antes de seguir con los demás pasos de la implementación. Para obtener información detallada sobre la creación de la topología, consulte [Escenarios para el acceso de usuarios externos en Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).

Para obtener información detallada sobre la herramienta de planificación y el generador de topología, consulte [Iniciar el proceso de planeación para Lync Server 2013](lync-server-2013-beginning-the-planning-process.md) en la documentación de planeación.

En la siguiente tabla se proporciona información general sobre el proceso de implementación de servidores perimetrales. Para comprobar las decisiones de planificación que se deben llevar a cabo antes de la implementación del acceso de los usuarios externos, consulte [Escenarios para el acceso de usuarios externos en Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).

> [!WARNING]  
> La información de la siguiente tabla se centra en una nueva implementación. Si ha implementado servidores perimetrales en un entorno de Lync Server 2010, Office Communications Server 2007 R2 o Office Communications Server 2007, consulte <a href="migration.md">Migración</a> para obtener información sobre la migración a Lync Server 2013. La migración no se admite en ninguna versión anterior de Office Communications Server 2007 R2, incluidos Office Communications Server 2007, Live Communications Server 2005 y Live Communications Server 2003.



Para mejorar el rendimiento y la seguridad de los servidores perimetrales, además de facilitar la implementación de los mismos, aplique las mejores prácticas que se indican a continuación al implementar la red perimetral y los servidores perimetrales:

  - Implemente los servidores perimetrales solo después de haber probado y verificado el funcionamiento de Lync Server 2013 dentro de su organización.

  - Se recomienda implementar servidores perimetrales en un grupo de trabajo, en lugar de un dominio. De este modo, simplificará la instalación y mantendrá los Servicios de dominio de Active Directory (AD DS) fuera de la red perimetral. Ubicar los AD DS en la red perimetral puede suponer un grave riesgo de seguridad.

  - Se puede unir el servidor perimetral a un dominio ubicado por completo en la red perimetral, pero no es recomendable. Un servidor perimetral como parte del dominio interno supera los límites de la red de confianza, en la que Internet tiene menos confianza, la red perimetral tiene más confianza que Internet y la red interna es la que tiene más confianza. Un servidor perimetral como miembro del dominio forma parte automáticamente de la red de más confianza, pero reside en una red de confianza menor (el perímetro).

## Proceso de implementación de servidores perimetrales


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
<th>Permisos</th>
<th>Documentación</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Cree la topología perimetral adecuada y determine los componentes adecuados.</p></td>
<td><ul>
<li><p>Ejecute Generador de topologías para configurar las opciones de servidor perimetral, así como para crear y publicar la topología y, a continuación, use el Shell de administración de Lync Server para exportar el archivo de configuración de la topología.</p></li>
</ul>
<p></p></td>
<td><p>Grupo <strong>Administradores de domino</strong> y <strong>RTCUniversalServerAdmins</strong> o grupo <strong>CsAdmins</strong></p>


> [!NOTE]
> Se puede definir una topología mediante una cuenta que sea miembro del grupo de usuarios local, pero para publicar una topología se necesita una cuenta que sea miembro del grupo <STRONG>Administradores de dominio</STRONG> y del grupo <STRONG>RTCUniversalServerAdmins</STRONG>.


</td>
<td><p><a href="lync-server-2013-building-an-edge-and-director-topology.md">Creación de una topología perimetral y de director Lync Server 2013</a> en la documentación de implementación</p></td>
</tr>
<tr class="even">
<td><p>Prepare la configuración.</p></td>
<td><ol>
<li><p>Compruebe que se cumplen los requisitos previos del sistema.</p></li>
<li><p>Configure las direcciones IP (IPv4 e IPv6, si se usan) para las interfaces de red interna y pública en cada servidor perimetral.</p></li>
<li><p>Configure los registros DNS internos y externos (A de host y AAAA para IPv4 e IPv6), incluida la configuración del sufijo DNS en el equipo que se va a implementar como servidor perimetral.</p></li>
<li><p>(Opcional) Cree e instale los certificados públicos. El tiempo necesario para obtener los certificados depende de la entidad de certificación (CA) que emite el certificado. Si no se realiza este paso en este momento, debe hacerse durante la instalación del servidor perimetral. El servicio de servidor perimetral no puede iniciarse hasta que se obtengan los certificados.</p></li>
<li><p>Proporcione soporte para la conectividad de mensajería instantánea pública si la implementación va a admitir comunicaciones con usuarios de Windows Live, AOL o Yahoo!.</p>

> [!IMPORTANT]  
> <ul>
> <li><p>El 1 de septiembre de 2012, la licencia de suscripción del usuario de Public IM Connectivity de Microsoft Lync (&quot;PIC USL&quot;) dejó de estar disponible para su compra en los contratos nuevos y en las prórrogas de contratos. Los clientes que tengan licencias activas podrán seguir federándose con Yahoo! Messenger hasta la fecha de cierre del servicio. La fecha anunciada para el fin de vida de AOL y Yahoo! es junio de 2014. Para más detalles, vea <a href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Soporte para la conectividad de mensajería instantánea pública en Lync Server 2013</a>.</p></li>
> <li><p>PIC USL es una licencia de suscripción por usuario/por mes requerida por Lync Server u Office Communications Server para la federación con Yahoo! Messenger. La posibilidad de Microsoft de proporcionar este servicio depende de la compatibilidad con Yahoo!, cuyo contrato subyacente está llegando a su fin.</p></li>
> <li><p>Hoy más que nunca, Lync es una herramienta eficaz para conectarse dentro de una organización y con individuos de todo el mundo. La federación con Windows Live Messenger no requiere ninguna licencia de usuario o dispositivo adicional aparte de la CAL estándar de Lync. La federación con Skype se agregará a esta lista, lo que permitirá a los usuarios de Lync conectarse con cientos de millones de personas a través de mensajería instantánea y voz.</p></li>
> </ul>
> </li>
<li><p>Proporcione soporte para XMPP y compatibilidad con la federación para Office Communications Server 2007, Office Communications Server 2007 R2, los socios de Lync Server 2010, si la implementación los utiliza</p></li>
<li><p>Configure los firewalls.</p></li>
</ol></td>
<td><p>Según sea necesario para la organización</p></td>
<td><p><a href="lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md">Preparar la instalación de los servidores en la red del perímetro para Lync Server 2013</a> en la documentación de implementación</p></td>
</tr>
<tr class="odd">
<td><p>Configure el proxy inverso.</p></td>
<td><ul>
<li><p>Configure el proxy inverso (por ejemplo, para Microsoft Forefront Threat Management Gateway 2010 o Microsoft Internet Security and Acceleration (ISA) Server con Service Pack 1) en la red perimetral, obtenga los certificados públicos necesarios y configure las reglas de publicación web en el servidor proxy inverso.</p>
<p>Prepare el servidor proxy inverso para los servicios de movilidad si ha planificado la movilidad y está implementado los servicios de movilidad en el grupo de servidores front-end o el servidor Standard Edition.</p></li>
</ul></td>
<td><p>Grupo <strong>Administradores</strong> o administrador de proxy inverso</p></td>
<td><p></p>
<p><a href="lync-server-2013-setting-up-reverse-proxy-servers.md">Configuración de los servidores proxy inversos para Lync Server 2013</a> en la documentación de implementación</p></td>
</tr>
<tr class="even">
<td><p>Configure un director (recomendado).</p></td>
<td><ul>
<li><p>(Opcional) Instale y configure uno o más directores en la red interna.</p></li>
</ul></td>
<td><p>Grupo <strong>Administradores</strong></p></td>
<td><p><a href="lync-server-2013-setting-up-the-director.md">Configuración del director en Lync Server 2013</a> en la documentación de implementación</p></td>
</tr>
<tr class="odd">
<td><p>Configure los servidores perimetrales.</p></td>
<td><ol>
<li><p>Instale el software necesario como requisito previo.</p></li>
<li><p>Transporte el archivo de configuración de la topología exportado a cada servidor perimetral.</p></li>
<li><p>Instale el software de Lync Server 2013 en cada servidor perimetral.</p></li>
<li><p>Configure los servidores perimetrales.</p></li>
<li><p>Solicite e instale los certificados de cada servidor perimetral.</p></li>
<li><p>Inicie los servicios de los servidores perimetrales.</p></li>
</ol></td>
<td><p>Grupo <strong>Administradores</strong></p></td>
<td><p><a href="lync-server-2013-setting-up-edge-servers.md">Configuración de servidores perimetrales en Lync Server 2013</a> en la documentación de implementación</p></td>
</tr>
<tr class="even">
<td><p>La planeación eficaz del acceso de usuarios externos requiere que se tenga en cuenta lo siguiente:</p></td>
<td><ol>
<li><p>Use el Panel de control de Lync Server para configurar la compatibilidad con cada una de las opciones siguientes (según corresponda):</p>
<ul>
<li><p>Relé multimedia</p></li>
<li><p>Federación</p></li>
<li><p>Acceso de usuarios remotos</p></li>
<li><p>Federación con el Lync Server, Lync Server, Office Communications Server y Live Communications Server</p></li>
<li><p>Conectividad de mensajería instantánea pública</p></li>
<li><p>Federación XMPP</p></li>
<li><p>Usuarios anónimos</p></li>
</ul></li>
<li><p>Configure cuentas de usuario para compatibilidad con acceso de usuarios remotos, federación, conectividad de mensajería instantánea pública y usuarios anónimos (según corresponda)</p></li>
</ol></td>
<td><p>Grupo <strong>RTCUniversalServerAdmins</strong> o una cuenta de usuario que esté asignada al rol <strong>CSAdministrator</strong></p>
<p></p></td>
<td><p><a href="lync-server-2013-configuring-support-for-external-user-access.md">Configurar la compatibilidad para el acceso de usuarios externos en Lync Server 2013</a> en la documentación de implementación</p></td>
</tr>
<tr class="odd">
<td><p>Compruebe la configuración del servidor perimetral.</p></td>
<td><ol>
<li><p>Compruebe la conectividad del servidor y la replicación de datos de configuración de servidores internos.</p></li>
<li><p>Compruebe que se pueden conectar los usuarios externos, como usuarios remotos, usuarios de dominios federados, usuarios de mensajería instantánea pública y usuarios anónimos, según corresponda a la implementación.</p></li>
<li><p>Compruebe la configuración y la comunicación con el analizador de conectividad remota de Lync Server <a href="https://www.testocsconnectivity.com/" class="uri">https://www.testocsconnectivity.com/</a></p></li>
<li><p>Solucione las dificultades de comunicación y configuración</p></li>
</ol></td>
<td><p>Para la comprobación de la replicación, el grupo <strong>RTCUniversalServerAdmins</strong> o una cuenta de usuario que esté asignada al rol <strong>CSAdministrator</strong></p>
<p>Para la comprobación de la conectividad de los usuarios, un usuario para cada tipo de acceso de usuarios externos que sea compatible</p>
<p>Usuarios remotos</p></td>
<td><p><a href="lync-server-2013-verifying-your-edge-deployment.md">Comprobación de la implementación perimetral en Lync Server 2013</a> en la documentación de implementación</p></td>
</tr>
</tbody>
</table>

