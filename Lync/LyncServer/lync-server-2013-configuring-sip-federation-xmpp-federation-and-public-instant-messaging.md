---
title: Configurar la federación SIP, la federación XMPP y la mensajería instantánea pública
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring SIP federation, XMPP federation and public instant messaging
ms:assetid: a6d04f0b-5cb8-4084-a3a2-d501938971f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205134(v=OCS.15)
ms:contentKeyID: 48184998
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 45abe0b4c32cf236912ad1a0e39f842653817e59
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739210"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-sip-federation-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a>Configurar la federación SIP, la federación XMPP y la mensajería instantánea pública en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-10-07_

La Federación, la conectividad de mensajería instantánea pública y el protocolo de presencia y mensajería extensible (XMPP) definen una clase diferente de usuarios externos: usuarios federados. Los usuarios de una implementación federada de Lync Server o una implementación XMPP tienen acceso a un conjunto limitado de servicios y se autentican mediante la implementación externa. Los usuarios remotos son miembros de su implementación de Lync Server y tienen acceso a todos los servicios ofrecidos por su implementación.

<div>


> [!NOTE]
> Una fecha de fin de vida de junio de 2014 para AOL y Yahoo! ha sido anunciado. Para obtener más información, consulte <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">compatibilidad de la conectividad de mensajería instantánea pública en Lync Server 2013</A>.



</div>

La conectividad de mensajería instantánea pública es un tipo especial de Federación que permite que un cliente de Lync Server acceda a socios de mensajería instantánea pública configurados mediante la 2013 de Lync. Los actuales Partners públicos de conectividad de mensajería instantánea son:

  - <span></span>  
    America Online

  - <span></span>  
    Windows Live

  - <span></span>  
    Yahoo\!

Una configuración de conectividad de mensajería instantánea pública permite a los usuarios de Lync acceder a los usuarios de conectividad de mensajería instantánea pública de la siguiente manera:

  - Mensajería instantánea (MI) y presencia

  - Visibilidad de los contactos de conectividad de mensajería instantánea pública en el cliente de Lync

  - Conversaciones de mensajería instantánea de persona a persona con contactos

  - Llamadas de audio y vídeo con usuarios de Windows Live

La Federación de Lync Server define un contrato entre la implementación de Lync Server y otras implementaciones de Office Communications Server 2007 R2 o Lync Server. Una configuración federada de Lync Server permite a los usuarios de Lync acceder a usuarios federados mediante las siguientes acciones:

  - Mensajería instantánea (MI) y presencia

  - Creación de contactos federados en el cliente de Lync

La Federación XMPP define una implementación externa basada en el protocolo de presencia y mensajería extensible. Una configuración XMPP permite a los usuarios de Lync acceder a usuarios del dominio XMPP permitidos mediante:

  - Mensajería instantánea y presencia: solo para personas

  - Creación de los contactos de XMPP federados en el cliente de Lync

<div>


> [!IMPORTANT]
> La capacidad XMPP de Lync Server 2013 está probada y es compatible con Microsoft para la federación de mensajería instantánea con Google Talk. Para otros sistemas XMPP, póngase en contacto con el proveedor para comprobar que son compatibles con la federación con Lync Server 2013 y para cualquier recomendación sobre implementación o solución de problemas.



</div>

<div>

## <a name="edge-server-external-federation-public-instant-messaging-connectivity-and-xmpp-users-deployment-process"></a>Federación externa de servidores perimetrales, conectividad pública de mensajería instantánea y proceso de implementación de usuarios XMPP


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
<td><p>Determinar las opciones para agregar a la implementación perimetral existente</p></td>
<td><p>Ejecute el generador de topología para editar la configuración del servidor perimetral y crear y publicar la topología. La topología de borde existente replicará los cambios del almacén de administración central en el servidor perimetral.</p></td>
<td><p>Grupo administradores de dominio y grupo RTCUniversalServerAdmins</p>



> [!NOTE]
> Puede editar una topología con una cuenta que sea miembro del grupo usuarios locales, pero la publicación de una topología requiere una cuenta que sea miembro del grupo administradores de dominio y del grupo RTCUniversalServerAdmins

</td>
<td><p><a href="lync-server-2013-building-an-edge-and-director-topology.md">Creación de una topología perimetral y de director Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Prepararse para la configuración</p></td>
<td><ol>
<li><p>Asegúrese de que se cumplan los requisitos previos del sistema.</p></li>
<li><p>Configurar registros DNS internos y externos para admitir la conectividad de mensajería instantánea pública, la Federación de Lync y la Federación de XMPP</p></li>
<li><p>Configurar puertos y protocolos en el firewall para admitir los tipos de Federación que se están implementando</p></li>
<li><p>Obtenga e instale certificados públicos. El tiempo necesario para obtener certificados depende de la entidad emisora de certificados (CA) que emite el certificado. Este paso es opcional en este punto de la implementación. Si no realiza este paso en este punto, debe hacerlo durante la configuración del servidor perimetral. El servicio de servidor perimetral no se puede iniciar hasta que se obtengan los certificados</p></li>
</ol></td>
<td><p>Según corresponda a su organización, puesto que estos roles suelen dividirse entre numerosos grupos de trabajo</p></td>
<td><p><a href="lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md">Planificación de SIP, Federación XMPP y mensajería instantánea pública en Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Configurar servidores perimetrales para escenarios de Federación</p></td>
<td><ol>
<li><p>Transporte el archivo de configuración de la topología exportada a cada servidor perimetral o permita que se complete la replicación</p></li>
<li><p>Volver a ejecutar el Asistente para la implementación para instalar componentes complementarios para la Federación</p></li>
<li><p>Configurar los servidores perimetrales</p></li>
<li><p>Solicitar e instalar certificados para cada servidor perimetral</p></li>
<li><p>Reiniciar los servicios del servidor perimetral</p></li>
</ol></td>
<td><p>Grupo administradores</p></td>
<td><p><a href="lync-server-2013-setting-up-lync-federation.md">Configuración de federación de Lync en Lync Server 2013</a></p>
<p><a href="lync-server-2013-setting-up-public-instant-messaging-connectivity.md">Establecer conectividad de mensajería instantánea pública en Lync Server 2013</a></p>
<p><a href="lync-server-2013-setting-up-xmpp-federation.md">Configurar la federación XMPP en Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Configurar la compatibilidad con el acceso de usuarios externos.</p></td>
<td><ol>
<li><p>Usar el acceso de usuarios externos del panel de control de Lync Server</p></li>
<li><p>Configurar la Directiva de acceso externo para habilitar las comunicaciones con usuarios federados o usuarios públicos</p></li>
<li><p>Configurar dominios federados SIP para permitir o bloquear dominios</p></li>
<li><p>Habilitar proveedores federados SIP para proveedores de conectividad de mensajería instantánea pública</p></li>
<li><p>Configurar socios de XMPP federados por dominio XMPP</p></li>
</ol></td>
<td><p>RTCUniversalServerAdmins una cuenta de usuario o grupo que está asignada al rol CSAdministrator</p></td>
<td><p><a href="lync-server-2013-configuring-support-for-external-user-access.md">Configurar la compatibilidad para el acceso de usuarios externos en Lync Server 2013</a></p>
<p><a href="lync-server-2013-configure-media-encryption-for-public-providers.md">Configurar el cifrado de medios para proveedores públicos en Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Comprobar la configuración del servidor perimetral</p></td>
<td><p>Comprobar la Conectividad del servidor y la replicación de datos de configuración desde servidores internos</p></td>
<td><p>Para la verificación de la replicación, RTCUniversalServerAdmins cuenta de usuario o grupo que se asigna al CSAdministrator roleFor la verificación de la conectividad de los usuarios, un usuario para cada tipo de usuario federado.</p></td>
<td><p><a href="lync-server-2013-verifying-your-edge-deployment.md">Comprobación de la implementación perimetral en Lync Server 2013</a></p>
<p><a href="lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md">Configuración XMPP de ejemplo en Lync Server 2013 - Federación XMPP con Google Talk</a></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

