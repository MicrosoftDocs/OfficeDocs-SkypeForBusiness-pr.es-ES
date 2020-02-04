---
title: 'Lync Server 2013: Lista de comprobación de la implementación del acceso de usuarios externos'
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
ms.openlocfilehash: 6ad2ad90ab43402babdd10478e1d86cac2a38ddf
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762728"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-external-user-access-in-lync-server-2013"></a>Lista de comprobación de la implementación del acceso de usuarios externos en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-02-04_

Antes de implementar la red perimetral e implementar compatibilidad para usuarios externos, ya debe haber implementado sus servidores internos de Microsoft Lync Server 2013, incluido un grupo de servidores front-end o un servidor Standard Edition. Si planea implementar los directores opcionales en su red interna, también debe implementarlos antes de implementar servidores perimetrales. Para obtener más información sobre el proceso de implementación de Director, consulte [escenarios del Director de Lync Server 2013](lync-server-2013-scenarios-for-the-director.md) en la documentación de planeación.

Microsoft Lync Server 2013 incluye herramientas para facilitar la planificación y la implementación de servidores internos y servidores perimetrales. Una vez completada la topología, publique la definición de topología resultante en su entorno de producción. Para ello, debe ser miembro del grupo **administradores de dominio** y del grupo **RTCUniversalServerAdmins** .

  - **Herramienta de planeación**   Office Communications Server 2007 R2 incluye una herramienta de planificación y una herramienta de planeación de bordes que puede usar para guiar el diseño de la topología. En Lync Server 2010, estas dos herramientas se combinaron en una sola herramienta de planeación con características y funciones adicionales, como la recopilación de recuento de usuarios planificados, los requisitos de voz, los tipos de acceso de usuarios externos y las opciones de Federación. Además, puede planear los parámetros de red de la infraestructura, como direcciones IP, tipos de equilibradores de carga y otras consideraciones de la red perimetral.

  - ****   El generador de topologías Lync Server 2013 Builder le ayuda a definir su topología y sus componentes. El generador de topología es esencial para implementar servidores que ejecuten Lync Server 2013. El generador de topología publica los resultados en un almacén de administración central que se usa para configurar todos los servidores que ejecutan Lync Server 2013 de su organización. No puede instalar Lync Server 2013 en servidores sin usar el generador de topologías.

Si ha diseñado su topología perimetral durante el proceso de planeación, incluida la ejecución del generador de topología para definir la topología perimetral, puede usar esos resultados para iniciar la implementación del servidor perimetral. Si no ha terminado de crear la topología de borde antes o quiere cambiar la información que especificó anteriormente, debe terminar de ejecutar el generador de topología antes de seguir con otros pasos de implementación. Para obtener más información sobre cómo crear su topología, consulte [escenarios para el acceso de usuarios externos en Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).

Para obtener más información sobre la herramienta de planificación y el generador de topología, consulte [comenzar el proceso de planeación de Lync Server 2013](lync-server-2013-beginning-the-planning-process.md) en la documentación de planeación.

En la tabla siguiente se proporciona una descripción general del proceso de implementación del servidor perimetral. Para revisar las decisiones de planeación que se deben realizar antes de implementar el acceso de usuarios externos, consulte [escenarios para el acceso de usuarios externos en Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).

<div>


> [!WARNING]  
> La información de la tabla siguiente se centra en una nueva implementación. Si ha implementado servidores perimetrales en un entorno de Lync Server 2010, Office Communications Server 2007 R2 u Office Communications Server 2007, consulte la <A href="migration.md">migración</A> para obtener más detalles sobre cómo migrar a Lync Server 2013. La migración no es compatible desde ninguna versión anterior a Office Communications Server 2007 R2, incluidos Office Communications Server 2007, Live Communications Server 2005 y Live Communications Server 2003.



</div>

Para mejorar la seguridad y el rendimiento del servidor perimetral, y para facilitar la implementación, aplique los siguientes procedimientos recomendados al implementar la red perimetral y los servidores perimetrales:

  - Implemente servidores perimetrales solo después de probar y comprobar el funcionamiento de Lync Server 2013 dentro de su organización.

  - Le recomendamos que implemente servidores perimetrales en un grupo de trabajo en lugar de un dominio. Esto simplifica la instalación y mantiene fuera de la red perimetral los servicios de dominio de Active Directory (AD DS). Localizar AD DS en la red perimetral puede representar un importante riesgo para la seguridad.

  - Unirse a un servidor perimetral a un dominio ubicado por completo en la red perimetral es compatible, pero no recomendado. Un servidor perimetral como parte del dominio interno infringe los límites de la red de confianza, donde Internet es de menor confianza, la red perimetral es más confiable que Internet y la red interna es de mayor confianza. Un servidor perimetral como miembro del dominio es automáticamente una parte de la red de mayor confianza, pero reside en una red de menos confianza (el perímetro).

<div>

## <a name="deployment-process-for-edge-servers"></a>Proceso de implementación para servidores perimetrales


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
<td><p>Cree la topología de arista adecuada y determine los componentes apropiados.</p></td>
<td><ul>
<li><p>Ejecute el generador de topología para establecer la configuración del servidor perimetral, crear y publicar la topología y, a continuación, usar el shell de administración de Lync Server para exportar el archivo de configuración de topología.</p></li>
</ul></td>
<td><p>Grupo <strong>administradores de dominio</strong> y grupo <strong>RTCUniversalServerAdmins</strong> o <strong>CsAdmins</strong></p>
<div>

> [!NOTE]  
> Puede definir una topología con una cuenta que sea miembro del grupo usuarios locales, pero la publicación de una topología requiere una cuenta que sea miembro del grupo <STRONG>administradores de dominio</STRONG> y del grupo <STRONG>RTCUniversalServerAdmins</STRONG> .


</div></td>
<td><p><a href="lync-server-2013-building-an-edge-and-director-topology.md">Creación de una topología de Edge y Director en Lync Server 2013</a> en la documentación de implementación</p></td>
</tr>
<tr class="even">
<td><p>Prepararse para la configuración.</p></td>
<td><ol>
<li><p>Asegúrese de que se cumplan los requisitos previos del sistema.</p></li>
<li><p>Configure las direcciones IP (IPv4 e IPv6, si las hay) para las interfaces de red orientadas interna y pública en cada servidor perimetral.</p></li>
<li><p>Configure los registros DNS internos y externos (host A y AAAA para IPv4 e IPv6), incluyendo la configuración del sufijo DNS en el equipo que se va a implementar como servidor perimetral.</p></li>
<li><p>Faculta Crear e instalar certificados públicos. El tiempo necesario para obtener certificados depende de la entidad emisora de certificados (CA) que emite el certificado. Si no realiza este paso en este punto, debe hacerlo durante la instalación del servidor perimetral. Los servicios del servidor perimetral no se pueden iniciar hasta que se obtengan e instalen certificados.</p></li>
<li><p>Proporcionar compatibilidad con la conectividad de mensajería instantánea pública, si su implementación es compatible con las comunicaciones con Windows Live, AOL o Yahoo! User.</p>
<div>

> [!IMPORTANT]  
> <UL>
> <LI>
> <P>A partir del 1 de septiembre de 2012, la licencia de suscripción de usuario de conectividad de mensajería instantánea pública de Microsoft Lync ("PIC USL") ya no está disponible para la compra de contratos nuevos o de renovación. Los clientes con licencias activas podrán seguir federando a Yahoo! Messenger hasta que se cierre la fecha del servicio. Una fecha de fin de vida de junio de 2014 para AOL y Yahoo! ha sido anunciado. Para obtener más información, consulte <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">compatibilidad de la conectividad de mensajería instantánea pública en Lync Server 2013</A>.</P>
> <LI>
> <P>El PIC USL es una licencia por usuario por mes de suscripción que es necesaria para que Lync Server o Office Communications Server se federe con Yahoo! Mensajería. La capacidad de Microsoft para proporcionar este servicio está supeditada al soporte de Yahoo!, el contrato subyacente para el que se está pospuesto.</P>
> <LI>
> <P>Más que nunca, Lync es una herramienta eficaz para la conexión entre organizaciones y con personas de todo el mundo. La Federación con Windows Live Messenger no requiere licencias adicionales para usuarios y dispositivos más allá de la CAL de Lync Standard. La Federación de Skype se agrega a esta lista, lo que permite a los usuarios de Lync llegar a cientos de millones de personas con la mensajería instantánea y la voz.</P></LI></UL>


</div></li>
<li><p>Soporte técnico para la compatibilidad con la compatibilidad con la Federación de Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 Partners, si la implementación va a usar estos</p></li>
<li><p>Configurar firewalls.</p></li>
</ol></td>
<td><p>Según corresponda a su organización</p></td>
<td><p><a href="lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md">Prepararse para la instalación de servidores en la red perimetral para Lync Server 2013</a> en la documentación de implementación</p></td>
</tr>
<tr class="odd">
<td><p>Configurar proxy inverso.</p></td>
<td><ul>
<li><p>Configurar el proxy inverso (por ejemplo, para Microsoft Forefront Threat Management Gateway 2010 o Microsoft Internet Security and Acceleration (ISA) Server con Service Pack 1) en la red perimetral, obtener los certificados públicos necesarios y configurar los reglas de publicación web en el servidor proxy inverso.</p>
<p>Prepare el proxy inverso para los servicios de movilidad si ha planeado para la movilidad y va a implementar los servicios de movilidad en el grupo de servidores front-end o en el servidor Standard Edition.</p></li>
</ul></td>
<td><p>Grupo <strong>administradores</strong> o administrador de proxy inverso</p></td>
<td><p><a href="lync-server-2013-setting-up-reverse-proxy-servers.md">Configuración de servidores proxy inversos para Lync Server 2013</a> en la documentación de implementación</p></td>
</tr>
<tr class="even">
<td><p>Configurar un director (opcional).</p></td>
<td><ul>
<li><p>Faculta Instale y configure uno o más directores en la red interna.</p></li>
</ul></td>
<td><p>Grupo <strong>administradores</strong></p></td>
<td><p><a href="lync-server-2013-setting-up-the-director.md">Configuración del Director de Lync Server 2013</a> en la documentación de implementación</p></td>
</tr>
<tr class="odd">
<td><p>Configurar servidores perimetrales.</p></td>
<td><ol>
<li><p>Instale el software necesario.</p></li>
<li><p>Transporte el archivo de configuración de la topología exportada a cada servidor perimetral.</p></li>
<li><p>Instale el software Lync Server 2013 en cada servidor perimetral.</p></li>
<li><p>Configurar los servidores perimetrales.</p></li>
<li><p>Solicite e instale certificados para cada servidor perimetral.</p></li>
<li><p>Inicie los servicios del servidor perimetral.</p></li>
</ol></td>
<td><p>Grupo <strong>administradores</strong></p></td>
<td><p><a href="lync-server-2013-setting-up-edge-servers.md">Configuración de servidores perimetrales en Lync Server 2013</a> en la documentación de implementación</p></td>
</tr>
<tr class="even">
<td><p>Configurar la implementación para el acceso de usuarios externos.</p></td>
<td><ol>
<li><p>Use el panel de control de Lync Server para configurar la compatibilidad de cada uno de los siguientes (según corresponda):</p>
<ul>
<li><p>Relé multimedia</p></li>
<li><p>Ruta de Federación</p></li>
<li><p>Acceso de usuarios remotos</p></li>
<li><p>Federación con Lync Server, Office Communications Server y Live Communications Server</p></li>
<li><p>Conectividad de mensajería instantánea pública</p></li>
<li><p>Federación XMPP</p></li>
<li><p>Usuarios anónimos</p></li>
</ul></li>
<li><p>Configurar cuentas de usuario para el acceso de usuarios remotos, la Federación, la conectividad de mensajería instantánea pública, el XMPP y la compatibilidad con usuarios anónimos (según corresponda)</p></li>
</ol></td>
<td><p><strong>RTCUniversalServerAdmins</strong> una cuenta de usuario o grupo que está asignada al rol <strong>CSAdministrator</strong></p></td>
<td><p>Configuración de la compatibilidad con el <a href="lync-server-2013-configuring-support-for-external-user-access.md">acceso de usuarios externos en Lync Server 2013</a> en la documentación de implementación</p></td>
</tr>
<tr class="odd">
<td><p>Verifica la configuración del servidor perimetral.</p></td>
<td><ol>
<li><p>Comprobar la Conectividad del servidor y la replicación de datos de configuración desde servidores internos.</p></li>
<li><p>Compruebe que los usuarios externos pueden conectarse, incluidos los usuarios remotos, los usuarios de dominios federados, los usuarios de mensajería instantánea pública y los usuarios anónimos, según corresponda a su implementación.</p></li>
<li><p>Comprobar la configuración y la comunicación con el analizador de conectividad remota de Lync Server<a href="https://www.testocsconnectivity.com" class="uri">https://www.testocsconnectivity.com</a></p></li>
<li><p>Solucionar problemas de configuración y comunicación</p></li>
</ol></td>
<td><p>Para la verificación de la replicación, <strong>RTCUniversalServerAdmins</strong> cuenta de usuario o de grupo que está asignada al rol <strong>CSAdministrator</strong></p>
<p>Para comprobar la conectividad de los usuarios, un usuario para cada tipo de acceso de usuarios externos que admita</p>
<p>Usuarios remotos</p></td>
<td><p><a href="lync-server-2013-verifying-your-edge-deployment.md">Comprobar la implementación de extremos en Lync Server 2013</a> en la documentación de implementación</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

