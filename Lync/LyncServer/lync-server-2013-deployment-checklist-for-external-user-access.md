---
title: 'Lync Server 2013: lista de comprobación para la implementación del acceso de usuarios externos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for external user access
ms:assetid: 3f55f502-88a0-4315-8783-45a32a0b78ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425910(v=OCS.15)
ms:contentKeyID: 48183947
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5010608f05f99d1d1830874a80b6f9f44fd25b38
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135897"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-external-user-access-in-lync-server-2013"></a>Lista de comprobación para la implementación para el acceso de usuarios externos en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-02-04_

Antes de implementar la red perimetral y de implementar la compatibilidad con usuarios externos, debe haber implementado ya los servidores internos de Microsoft Lync Server 2013, incluido un grupo de servidores front-end o un servidor Standard Edition. Si tiene previsto implementar los directores opcionales en la red interna, también debe implementarlos antes de implementar los servidores perimetrales. Para obtener más información sobre el proceso de implementación de Director, consulte [escenarios del Director en Lync Server 2013](lync-server-2013-scenarios-for-the-director.md) en la documentación referente a la planeación.

Microsoft Lync Server 2013 incluye herramientas que facilitan la planeación y la implementación de servidores internos y servidores perimetrales. Después que se haya completado la topología, publique la definición de la topología resultante a su entorno de producción. Para ello, deberá ser miembro de los grupos  **Administradores de dominio ** y  **RTCUniversalServerAdmins**.

  - **Herramienta de planeación**   Office Communications Server 2007 R2 incluye una herramienta de planeación y una herramienta de planeación de la periferia que puede usar para guiar el diseño de la topología. En Lync Server 2010, estas dos herramientas se combinaron en una sola herramienta de planeación con características y funciones adicionales, como la recopilación de recuentos de usuarios planeados, los requisitos de voz, los tipos de acceso de usuarios externos y las opciones de Federación. Además, puede planificar los parámetros de la red de la infraestructura, como las direcciones IP, los tipos de equilibradores de carga y otras consideraciones de red perimetrales.

  - ****   El generador de topologías el generador de topologías de Lync Server 2013 ayuda a definir la topología y los componentes. El generador de topologías es esencial para implementar servidores que ejecutan Lync Server 2013. El generador de topologías publica los resultados en un almacén de administración central que se usa para configurar todos los servidores que ejecutan Lync Server 2013 en su organización. No puede instalar Lync Server 2013 en servidores sin usar el generador de topologías.

Si ha diseñado la topología perimetral durante el proceso de planeación, incluida la ejecución del generador de topologías para definir la topología perimetral, puede usar estos resultados para iniciar la implementación del servidor perimetral. Si no ha terminado de crear la topología perimetral anteriormente o desea cambiar la información que especificó anteriormente, debe terminar de ejecutar Topology Builder antes de continuar con otros pasos de implementación. Para obtener más información sobre cómo crear su topología, consulte [escenarios para el acceso de usuarios externos en Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).

Para obtener más información sobre la herramienta de planeación y el generador de topologías, consulte [comienzos del proceso de planeación de Lync Server 2013](lync-server-2013-beginning-the-planning-process.md) en la documentación referente a la planeación.

En la siguiente tabla se proporciona información general sobre el proceso de implementación de servidores perimetrales. Para revisar las decisiones de planeación que deben realizarse antes de implementar el acceso de usuarios externos, consulte [escenarios para el acceso de usuarios externos en Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).

<div>


> [!WARNING]  
> La información de la siguiente tabla se centra en una nueva implementación. Si ha implementado servidores perimetrales en un entorno de Lync Server 2010, Office Communications Server 2007 R2 o Office Communications Server 2007, consulte la <A href="migration.md">migración</A> para obtener detalles sobre cómo migrar a Lync Server 2013. La migración no se admite desde ninguna versión anterior a Office Communications Server 2007 R2, incluidos Office Communications Server 2007, Live Communications Server 2005 y Live Communications Server 2003.



</div>

Para mejorar el rendimiento y la seguridad de los servidores perimetrales, además de facilitar la implementación de los mismos, aplique las mejores prácticas que se indican a continuación al implementar la red perimetral y los servidores perimetrales:

  - Implemente los servidores perimetrales solo después de haber probado y verificado el funcionamiento de Lync Server 2013 dentro de su organización.

  - Se recomienda implementar servidores perimetrales en un grupo de trabajo, en lugar de un dominio. De este modo, simplificará la instalación y mantendrá los Servicios de dominio de Active Directory (AD DS) fuera de la red perimetral. Ubicar los AD DS en la red perimetral puede suponer un grave riesgo de seguridad.

  - Se puede unir el servidor perimetral a un dominio ubicado por completo en la red perimetral, pero no es recomendable. Un servidor perimetral como parte del dominio interno supera los límites de la red de confianza, en la que Internet tiene menos confianza, la red perimetral tiene más confianza que Internet y la red interna es la que tiene más confianza. Un servidor perimetral como miembro del dominio forma parte automáticamente de la red de más confianza, pero reside en una red de confianza menor (el perímetro).

<div>

## <a name="deployment-process-for-edge-servers"></a>Proceso de implementación de servidores perimetrales


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
<li><p>Ejecute el generador de topologías para establecer la configuración del servidor perimetral, crear y publicar la topología y, a continuación, use el shell de administración de Lync Server para exportar el archivo de configuración de la topología.</p></li>
</ul></td>
<td><p>Grupo <strong>administradores de dominio</strong> y grupo <strong>RTCUniversalServerAdmins</strong> o <strong>CsAdmins</strong></p>
<div>

> [!NOTE]  
> Se puede definir una topología mediante una cuenta que sea miembro del grupo de usuarios local, pero para publicar una topología se necesita una cuenta que sea miembro del grupo <STRONG>Administradores de dominio</STRONG> y del grupo <STRONG>RTCUniversalServerAdmins</STRONG>.


</div></td>
<td><p><a href="lync-server-2013-building-an-edge-and-director-topology.md">Creación de una topología de servidores perimetrales y de directores en Lync Server 2013</a> en la documentación sobre implementación</p></td>
</tr>
<tr class="even">
<td><p>Prepare la configuración.</p></td>
<td><ol>
<li><p>Compruebe que se cumplen los requisitos previos del sistema.</p></li>
<li><p>Configure las direcciones IP (IPv4 e IPv6, si se usan) para las interfaces de red interna y pública en cada servidor perimetral.</p></li>
<li><p>Configure los registros DNS internos y externos (A de host y AAAA para IPv4 e IPv6), incluida la configuración del sufijo DNS en el equipo que se va a implementar como servidor perimetral.</p></li>
<li><p>(Opcional) Cree e instale los certificados públicos. El tiempo necesario para obtener los certificados depende de la entidad de certificación (CA) que emite el certificado. Si no se realiza este paso en este momento, debe hacerse durante la instalación del servidor perimetral. El servicio de servidor perimetral no puede iniciarse hasta que se obtengan los certificados.</p></li>
<li><p>Proporcione soporte para la conectividad de mensajería instantánea pública si la implementación va a admitir comunicaciones con usuarios de Windows Live, AOL o Yahoo!.</p>
<div>

> [!IMPORTANT]  
> <UL>
> <LI>
> <P>A partir del 1 de septiembre de 2012, la licencia de suscripción de usuario de conectividad de mensajería instantánea pública de Microsoft Lync ("PIC USL") ya no está disponible para la compra de contratos nuevos o de renovación. Los clientes con licencias activas podrán seguir federando a Yahoo! Messenger hasta que se cierre la fecha del servicio. Una fecha de finalización del ciclo de vida de junio de 2014 para AOL y Yahoo! se ha anunciado. Para obtener más información, consulte <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">compatibilidad con la conectividad de mensajería instantánea pública en Lync Server 2013</A>.</P>
> <LI>
> <P>La capa de PIC es una licencia por usuario por mes que es necesaria para que Lync Server u Office Communications Server se federe con Yahoo! Service. La capacidad de Microsoft para proporcionar este servicio ha estado supeditada al soporte de Yahoo!, el acuerdo subyacente para el que se liquida.</P>
> <LI>
> <P>Más que nunca, Lync es una herramienta eficaz para la conexión entre organizaciones y con personas de todo el mundo. La Federación con Windows Live Messenger no requiere licencias de usuario o de dispositivo adicionales aparte de la CAL de Lync Standard. La Federación de Skype se agregará a esta lista, lo que permite a los usuarios de Lync llegar a cientos de millones de personas con mi y voz.</P></LI></UL>


</div></li>
<li><p>Provisioning Support for XMPP and Federation Support for Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 Partners, si la implementación va a usar estos</p></li>
<li><p>Configure los firewalls.</p></li>
</ol></td>
<td><p>Según sea necesario para la organización</p></td>
<td><p><a href="lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md">Preparación de la instalación de los servidores en la red perimetral para Lync Server 2013</a> en la documentación sobre implementación</p></td>
</tr>
<tr class="odd">
<td><p>Configure el proxy inverso.</p></td>
<td><ul>
<li><p>Configure el proxy inverso (por ejemplo, para Microsoft Forefront Threat Management Gateway 2010 o Microsoft Internet Security and Acceleration (ISA) Server con Service Pack 1) en la red perimetral, obtenga los certificados públicos necesarios y configure el reglas de publicación web en el servidor de proxy inverso.</p>
<p>Prepare el servidor proxy inverso para los servicios de movilidad si ha planificado la movilidad y está implementado los servicios de movilidad en el grupo de servidores front-end o el servidor Standard Edition.</p></li>
</ul></td>
<td><p>Grupo <strong>Administradores</strong> o administrador de proxy inverso</p></td>
<td><p><a href="lync-server-2013-setting-up-reverse-proxy-servers.md">Configuración de servidores proxy inversos para Lync Server 2013</a> en la documentación de implementación</p></td>
</tr>
<tr class="even">
<td><p>Configure un director (recomendado).</p></td>
<td><ul>
<li><p>(Opcional) Instale y configure uno o más directores en la red interna.</p></li>
</ul></td>
<td><p>Grupo <strong>Administradores</strong></p></td>
<td><p><a href="lync-server-2013-setting-up-the-director.md">Configuración del Director en Lync Server 2013</a> en la documentación de implementación</p></td>
</tr>
<tr class="odd">
<td><p>Configure los servidores perimetrales.</p></td>
<td><ol>
<li><p>Instale el software necesario como requisito previo.</p></li>
<li><p>Transporte el archivo de configuración de la topología exportado a cada servidor perimetral.</p></li>
<li><p>Instale el software Lync Server 2013 en cada servidor perimetral.</p></li>
<li><p>Configure los servidores perimetrales.</p></li>
<li><p>Solicite e instale los certificados de cada servidor perimetral.</p></li>
<li><p>Inicie los servicios de los servidores perimetrales.</p></li>
</ol></td>
<td><p>Grupo <strong>Administradores</strong></p></td>
<td><p><a href="lync-server-2013-setting-up-edge-servers.md">Configuración de servidores perimetrales en Lync Server 2013</a> en la documentación sobre implementación</p></td>
</tr>
<tr class="even">
<td><p>La planeación eficaz del acceso de usuarios externos requiere que se tenga en cuenta lo siguiente:</p></td>
<td><ol>
<li><p>Use el panel de control de Lync Server para configurar la compatibilidad para cada uno de los siguientes (según corresponda):</p>
<ul>
<li><p>Relé multimedia</p></li>
<li><p>Federación</p></li>
<li><p>Acceso de usuarios remotos</p></li>
<li><p>Federación con Lync Server, Office Communications Server y Live Communications Server</p></li>
<li><p>Conectividad de mensajería instantánea pública</p></li>
<li><p>Federación XMPP</p></li>
<li><p>Usuarios anónimos</p></li>
</ul></li>
<li><p>Configure cuentas de usuario para compatibilidad con acceso de usuarios remotos, federación, conectividad de mensajería instantánea pública y usuarios anónimos (según corresponda)</p></li>
</ol></td>
<td><p>Grupo <strong>RTCUniversalServerAdmins</strong> o una cuenta de usuario que esté asignada al rol <strong>CSAdministrator</strong></p></td>
<td><p><a href="lync-server-2013-configuring-support-for-external-user-access.md">Configuración de la compatibilidad para el acceso de usuarios externos en Lync Server 2013</a> en la documentación de implementación</p></td>
</tr>
<tr class="odd">
<td><p>Compruebe la configuración del servidor perimetral.</p></td>
<td><ol>
<li><p>Compruebe la conectividad del servidor y la replicación de datos de configuración de servidores internos.</p></li>
<li><p>Compruebe que se pueden conectar los usuarios externos, como usuarios remotos, usuarios de dominios federados, usuarios de mensajería instantánea pública y usuarios anónimos, según corresponda a la implementación.</p></li>
<li><p>Comprobación de la configuración y la comunicación con el analizador de conectividad remota de Lync Server<a href="https://www.testocsconnectivity.com" class="uri">https://www.testocsconnectivity.com</a></p></li>
<li><p>Solucione las dificultades de comunicación y configuración</p></li>
</ol></td>
<td><p>Para la comprobación de la replicación, el grupo <strong>RTCUniversalServerAdmins</strong> o una cuenta de usuario que esté asignada al rol <strong>CSAdministrator</strong></p>
<p>Para la comprobación de la conectividad de los usuarios, un usuario para cada tipo de acceso de usuarios externos que sea compatible</p>
<p>Usuarios remotos</p></td>
<td><p><a href="lync-server-2013-verifying-your-edge-deployment.md">Comprobar la implementación perimetral en Lync Server 2013</a> en la documentación de implementación</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

