---
title: Configurar la Federación SIP, la Federación XMPP y la mensajería instantánea pública
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
ms.openlocfilehash: d21f2c094eb7b5c342c31387b6732a2565f01197
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154412"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-sip-federation-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a>Configurar la Federación SIP, la Federación XMPP y la mensajería instantánea pública en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-10-07_

La federación, la conectividad de mensajería instantánea pública y el protocolo extensible de mensajería y presencia (XMPP) definen una clase diferente de usuarios externos: los usuarios federados. Los usuarios de una implementación de Lync Server o una implementación de XMPP federadas tienen acceso a un conjunto limitado de servicios y se autentican mediante la implementación externa. Los usuarios remotos son miembros de su implementación de Lync Server y tienen acceso a todos los servicios ofrecidos por su implementación de.

<div>


> [!NOTE]
> Una fecha de finalización del ciclo de vida de junio de 2014 para AOL y Yahoo! se ha anunciado. Para obtener más información, consulte <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">compatibilidad con la conectividad de mensajería instantánea pública en Lync Server 2013</A>.



</div>

La conectividad de mensajería instantánea pública es un tipo especial de Federación que permite a un cliente de Lync Server tener acceso a asociados de mensajería instantánea pública configurado con Lync 2013. Actualmente, los socios de conectividad de mensajería instantánea pública son:

  - <span></span>  
    America Online

  - <span></span>  
    Windows Live

  - <span></span>  
    Toolbar\!

Una configuración de conectividad de mensajería instantánea pública permite a los usuarios de Lync obtener acceso a usuarios de conectividad de mensajería instantánea pública mediante:

  - Mensajería instantánea y presencia

  - Visibilidad de contactos de conectividad de mensajería instantánea pública en el cliente de Lync

  - Conversaciones de MI de persona a persona con contactos

  - Llamadas de audio y vídeo con usuarios de Windows Live

La federación de Lync Server define un acuerdo entre su implementación de Lync Server y otras implementaciones de Office Communications Server 2007 R2 o Lync Server. Una configuración federada de Lync Server permite a los usuarios de Lync obtener acceso a usuarios federados mediante:

  - Mensajería instantánea y presencia

  - Creación de contactos federados en el cliente de Lync

La federación XMPP define una implementación externa basándose en el protocolo extensible de mensajería y presencia (XMPP). Una configuración XMPP permite a los usuarios de Lync obtener acceso a usuarios de dominios XMPP mediante:

  - Mensajería instantánea y presencia (solo de persona a persona)

  - Creación de contactos federados XMPP en el cliente Lync

<div>


> [!IMPORTANT]
> La capacidad XMPP de Lync Server 2013 se ha probado y es compatible con Microsoft para la Federación de mensajería instantánea con Google Talk. Para cualquier otro sistema XMPP, póngase en contacto con el proveedor de terceros para comprobar que admiten la Federación con Lync Server 2013 y para cualquier recomendación sobre implementación o solución de problemas.



</div>

<div>

## <a name="edge-server-external-federation-public-instant-messaging-connectivity-and-xmpp-users-deployment-process"></a>Federación externa de servidor perimetral, conectividad de mensajería instantánea pública y proceso de implementación de usuarios de XMPP


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
<td><p>Determine las opciones para agregar la implementación de servidor perimetral existente</p></td>
<td><p>Ejecute el generador de topologías para editar la configuración del servidor perimetral y cree y publique la topología. La topología perimetral existente replicará los cambios del almacén de administración central en el servidor perimetral.</p></td>
<td><p>Grupo Administradores de dominio y grupo RTCUniversalServerAdmins</p>



> [!NOTE]
> Puede editar una topología mediante una cuenta que es miembro del grupo de usuarios locales pero publicar una topología requiere una cuenta que es miembro del grupo Administradores de dominio y del grupo RTCUniversalServerAdmins.

</td>
<td><p><a href="lync-server-2013-building-an-edge-and-director-topology.md">Creación de una topología perimetral y de Director en Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Prepararse para el programa de instalación</p></td>
<td><ol>
<li><p>Asegúrese de que se cumplen los requisitos previos del sistema.</p></li>
<li><p>Configure registros DNS internos y externos para admitir la conectividad de mensajería instantánea pública, la federación de Lync y la federación de XMPP</p></li>
<li><p>Configure puertos y protocolos en el firewall para admitir los tipos de federación que va a implementar</p></li>
<li><p>Obtenga e instale certificados públicos. El tiempo necesario para obtener certificados depende de qué entidad de certificación (CA) emite el certificado. Este paso es opcional en este punto de la implementación. Si no lleva a cabo este paso en este momento, debe hacerlo durante la configuración del servidor perimetral. No se puede iniciar el servicio de servidor perimetral hasta que se obtengan certificados.</p></li>
</ol></td>
<td><p>Según corresponda a su organización, ya que estas funciones se suelen dividir entre numerosos grupos de trabajo</p></td>
<td><p><a href="lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md">Planeación de SIP, la Federación XMPP y la mensajería instantánea pública en Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Configure los servidores perimetrales para escenarios de federación</p></td>
<td><ol>
<li><p>Transporte el archivo de configuración de topología exportado a cada servidor perimetral o permita la replicación para completar</p></li>
<li><p>Vuelva a ejecutar el Asistente para implementación para instalar componentes auxiliares para la federación</p></li>
<li><p>Configure los servidores perimetrales</p></li>
<li><p>Solicite e instale certificados para cada servidor perimetral</p></li>
<li><p>Reinicie los servicios de servidor perimetral</p></li>
</ol></td>
<td><p>Grupo de administradores</p></td>
<td><p><a href="lync-server-2013-setting-up-lync-federation.md">Configuración de la Federación de Lync en Lync Server 2013</a></p>
<p><a href="lync-server-2013-setting-up-public-instant-messaging-connectivity.md">Configuración de la conectividad de mensajería instantánea pública en Lync Server 2013</a></p>
<p><a href="lync-server-2013-setting-up-xmpp-federation.md">Configuración de la Federación XMPP en Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Configure la compatibilidad para el acceso de usuarios externos.</p></td>
<td><ol>
<li><p>Usar el acceso de usuarios externos del panel de control de Lync Server</p></li>
<li><p>Configure la directiva de acceso externo para habilitar las comunicaciones con usuarios federados o usuarios públicos</p></li>
<li><p>Configure los dominios federados SIP para permitir o bloquear dominios</p></li>
<li><p>Habilite proveedores federados SIP para proveedores de conectividad de mensajería instantánea pública</p></li>
<li><p>Configure socios federados de XMPP para el dominio XMPP</p></li>
</ol></td>
<td><p>Grupo RTCUniversalServerAdmins o cuenta de usuario que se asigna al rol CSAdministrator</p></td>
<td><p><a href="lync-server-2013-configuring-support-for-external-user-access.md">Configuración de la compatibilidad para el acceso de usuarios externos en Lync Server 2013</a></p>
<p><a href="lync-server-2013-configure-media-encryption-for-public-providers.md">Configurar el cifrado de medios para proveedores públicos en Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Compruebe la configuración del servidor perimetral</p></td>
<td><p>Compruebe la conectividad de servidor y la replicación de datos de configuración de servidores internos</p></td>
<td><p>Para la comprobación de la replicación, el grupo RTCUniversalServerAdmins o la cuenta de usuario que se asigna al rol CSAdministrator. Para la comprobación de la conectividad de usuario, un usuario para cada tipo de usuario federado</p></td>
<td><p><a href="lync-server-2013-verifying-your-edge-deployment.md">Comprobar la implementación perimetral en Lync Server 2013</a></p>
<p><a href="lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md">Configuración XMPP de ejemplo en Lync Server 2013: Federación XMPP con Google Talk</a></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

