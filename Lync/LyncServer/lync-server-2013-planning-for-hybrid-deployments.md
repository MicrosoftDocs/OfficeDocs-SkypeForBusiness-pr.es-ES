---
title: 'Lync Server 2013: Planeación de implementaciones híbridas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for hybrid deployments
ms:assetid: f8b3d240-bc2e-42c9-acf8-d532d641a14c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205403(v=OCS.15)
ms:contentKeyID: 48185910
ms.date: 05/25/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4b0efc4a6a9e9f195705801969b8459c17855388
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036690"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-lync-server-2013-hybrid-deployments"></a>Planeación de implementaciones híbridas de Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2016-05-25_

Al planear una implementación híbrida, debe tener en cuenta los siguientes requisitos para los usuarios y la infraestructura de red.

<div>

## <a name="infrastructure-requirements"></a>Requisitos de infraestructura

Debe tener la siguiente configuración en su entorno para implementar e implementar una implementación híbrida.

  - Un inquilino de Microsoft Office 365 con Skype empresarial online habilitado. Tenga en cuenta que solo puede usar un único inquilino para una configuración híbrida con su implementación local.

  - Una única implementación local (infraestructura) de Skype empresarial Server o Lync Server que se implementa en una topología admitida. Consulte topología requirements.
    
    Para obtener información sobre cómo configurar la implementación de Lync Server 2013 o Lync Server 2010 para entornos híbridos, consulte [Configuring Lync server 2013 Hybrid Deployments](lync-server-2013-configuring-hybrid-deployments.md).

  - Herramientas administrativas de Skype empresarial Server 2015. Si usa Lync Server 2013 o Lync Server 2010, puede usar las herramientas administrativas de Lync Server 2013.

  - Para admitir el inicio de sesión único con Office 365 para que los usuarios puedan usar las mismas credenciales de inicio de sesión para iniciar sesión en Office de forma local, puede usar las características de sincronización de contraseñas de Azure Active Directory (AAD) Connect. También puede usar los servicios de Federación de Active Directory (AD FS) para el inicio de sesión único con Office 365.
    
    Para obtener más información, consulte [Integración de las identidades locales con Azure Active Directory](http://go.microsoft.com/fwlink/p/?linkid=619754).

  - Una solución de sincronización de directorios única para mantener sincronizados los objetos de Active Directory locales y en línea. Para obtener más información acerca de la sincronización de directorios, consulte [herramientas de integración de directorios](http://go.microsoft.com/fwlink/p/?linkid=530320).

</div>

<div>

## <a name="lync-client-support"></a>Compatibilidad con clientes de Lync

Existen algunas diferencias en las características admitidas en los clientes de Lync, así como las características disponibles en entornos locales y en línea. Antes de decidir dónde desea hospedar a los usuarios de su organización, puede ver la compatibilidad de clientes para las distintas configuraciones de Lync Server. Los siguientes clientes son compatibles con Skype empresarial online en una implementación híbrida de Lync:

  - Lync 2010

  - Lync 2013

  - Aplicación Lync de la tienda Windows

  - Lync Web App

  - Lync Mobile

  - Lync para Mac 2011

  - Sistema Lync Room

  - Lync Basic 2013

Para obtener más información acerca de la compatibilidad de clientes, vea los siguientes temas:

  - [Clientes para Lync Online](http://go.microsoft.com/fwlink/?linkid=281902)

  - [Tablas de comparación de clientes para Lync Server 2013](lync-server-2013-desktop-client-comparison-tables.md)

  - [Tablas de comparación de clientes móviles para Lync Server 2013](lync-server-2013-mobile-client-comparison-tables.md)

</div>

<span id="BKMK_Topology"></span>

<div>

## <a name="topology-requirements"></a>Requisitos de topología

Para configurar la implementación de en entornos híbridos con Skype empresarial online, debe disponer de una de las siguientes topologías admitidas:

  - Una implementación de Skype empresarial Server 2015 con todos los servidores que ejecutan Skype empresarial Server 2015.

  - Una implementación de Lync Server 2013 con todos los servidores que ejecutan Lync Server 2013.

  - Una implementación de Lync Server 2010 con todos los servidores que ejecutan Lync Server 2010 con las actualizaciones acumulativas más recientes.
    
      - El servidor perimetral de Federación y el servidor de próximo salto del servidor perimetral de Federación deben ejecutar Lync Server 2010 con las actualizaciones acumulativas más recientes.
    
      - Las herramientas administrativas de Skype empresarial Server 2015 o Lync Server 2013 deben instalarse en al menos un servidor o una estación de trabajo de administración.

  - Una implementación mixta de Lync Server 2013 y Skype empresarial Server 2015 con los siguientes roles de servidor en al menos un sitio que ejecute Skype empresarial Server 2015:
    
      - Al menos un grupo de servidores Enterprise o un servidor Standard Edition
    
      - El grupo de directores asociado con la Federación SIP, si existe
    
      - El grupo de servidores perimetrales asociado con la Federación SIP

  - Una implementación mixta de Lync Server 2010 y Skype empresarial Server 2015 con los siguientes roles de servidores en al menos un sitio que ejecute Skype empresarial Server 2015:
    
      - Al menos un grupo de servidores Enterprise o un servidor Standard Edition
    
      - El grupo de directores asociado con la Federación SIP, si existe
    
      - El grupo de servidores perimetrales asociado con la Federación SIP para el sitio

  - Una implementación mixta de Lync Server 2010 y Lync Server 2013 con los siguientes roles de servidor en al menos un sitio que ejecute Lync Server 2013:
    
      - Al menos un grupo de servidores Enterprise o un servidor Standard Edition en el sitio
    
      - El grupo de directores asociado con la Federación SIP, si existe en el sitio
    
      - El grupo de servidores perimetrales asociado con la Federación SIP para el sitio

<div>


> [!IMPORTANT]  
> Toda la administración de usuarios, incluidos los movimientos de usuario entre locales y UNRESOLVED_TOKEN_VAL (skypeforbusiness) en línea, debe realizarse con la última versión instalada de las herramientas administrativas. Las herramientas administrativas deben instalarse en un servidor independiente que tenga acceso de conexión a la implementación local existente y a Internet. El cmdlet <A href="https://docs.microsoft.com/powershell/module/skype/Move-CsUser">Move-CsUser</A> para mover usuarios desde la implementación local a UNRESOLVED_TOKEN_VAL (skype16_online) debe ejecutarse desde las herramientas administrativas conectadas a la implementación local.



</div>

Para obtener más información acerca de las topologías admitidas, consulte topologías [admitidas en Lync server 2013](lync-server-2013-supported-topologies.md)y las [topologías de referencia de Lync Server 2013 para implementaciones híbridas empresariales](http://go.microsoft.com/fwlink/p/?linkid=398709).

Para solucionar problemas de la información sobre implementaciones híbridas y conectar PowerShell a Lync Online, consulte [Lync Online: Lync PowerShell y Hybrid Troubleshooting](http://go.microsoft.com/fwlink/p/?linkid=306718).

</div>

<div>

## <a name="requirements-for-federation-allowedblocked-lists"></a>Requisitos para las listas de Federación permitidas/bloqueadas

La lista de dominios permitidos incluye los dominios que tienen configurado un nombre de dominio completo (FQDN) de un servidor perimetral. A veces se denominan *servidores asociados permitidos* o *socios de Federación directa*. Debe estar familiarizado con la diferencia entre la Federación abierta y la Federación cerrada, a las que se hace referencia como *detección de asociados* y lista de *dominios de asociados permitidos*, respectivamente, en implementaciones locales.

Se deben cumplir los siguientes requisitos para configurar correctamente una implementación híbrida:

  - La coincidencia de dominios debe configurarse de la misma manera para la implementación local y el inquilino de Office 365. Si la detección de asociados está habilitada en la implementación local, se debe configurar la Federación abierta para el inquilino en línea. Si la detección de asociados no está habilitada, la Federación cerrada debe configurarse para el inquilino en línea.

  - La lista de dominios bloqueados en la implementación local debe coincidir exactamente con la lista de dominios bloqueados del inquilino en línea.

  - La lista de dominios permitidos de la implementación local debe coincidir exactamente con la lista de dominios permitidos del inquilino en línea.

  - La Federación debe estar habilitada para las comunicaciones externas del inquilino en línea, que se configura mediante el panel de control de Lync Online.

</div>

<div>

## <a name="dns-settings"></a>Configuración de DNS

Al crear registros DNS para implementaciones híbridas, todos los registros DNS externos de Lync deben apuntar a la infraestructura local. Para obtener más información sobre los registros DNS necesarios, consulte [requisitos del sistema de nombres de dominio (DNS) para Lync Server 2013](lync-server-2013-domain-name-system-dns-requirements.md).

Además, debe asegurarse de que la resolución DNS que se describe en la tabla siguiente funciona en su implementación local:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Registro DNS</p></td>
<td><p>Resuelto por</p></td>
<td><p>Requisito de DNS</p></td>
</tr>
<tr class="even">
<td><p>Registro SRV de DNS para _sipfederationtls. _tcp. &lt;sipdomain.com&gt; para todos los dominios SIP compatibles que se resuelven para obtener acceso a las IP externas perimetrales</p></td>
<td><p>Servidor (es) perimetral</p></td>
<td><p>Habilitar la comunicación federada en una configuración híbrida. El servidor perimetral tiene que saber dónde enrutar el tráfico federado para el dominio SIP que se divide entre las instalaciones locales y en línea.</p></td>
</tr>
<tr class="odd">
<td><p>Registros A de DNS para el FQDN del servicio de conferencia web perimetral, por ejemplo, webcon.contoso.com para la resolución de direcciones IP externas del servidor perimetral de conferencia Web</p></td>
<td><p>Equipos de usuarios conectados a la red corporativa interna</p></td>
<td><p>Permitir que los usuarios en línea presenten o vean contenido en las reuniones hospedadas locales. El contenido incluye archivos de PowerPoint, pizarras, sondeos y notas compartidas.</p></td>
</tr>
</tbody>
</table>


En función de la configuración de DNS en la organización, es posible que deba agregar estos registros a la zona DNS hospedada interna para los dominios SIP correspondientes para proporcionar resolución DNS interna a estos registros.

</div>

<div>

## <a name="firewall-considerations"></a>Consideraciones de firewall

Los equipos de la red deben ser capaces de realizar búsquedas de DNS de Internet estándar. Si estos equipos pueden tener acceso a sitios de Internet estándar, la red cumple este requisito.

En función de la ubicación del centro de datos de Microsoft Online Services, también debe configurar los dispositivos de Firewall de red para que acepten conexiones basadas en nombres de dominio comodín (por \*ejemplo, todo el tráfico de. Outlook.com). Si los firewalls de su organización no admiten configuraciones de nombre comodín, tendrá que determinar manualmente los intervalos de direcciones IP que desea permitir y los puertos especificados.

Consulte el tema de ayuda [Office 365 URL e intervalos de direcciones IP](http://go.microsoft.com/fwlink/p/?linkid=252942).

</div>

<span id="b"></span>

<div>

## <a name="port-and-protocol-requirements"></a>Requisitos de protocolo y puerto

Además de los requisitos de puertos para la comunicación interna de Lync Server 2013, también debe configurar los siguientes puertos.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Protocolo/puerto</th>
<th>Aplicaciones</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>TCP 443</p></td>
<td><p>Abrir entrante</p>
<ul>
<li><p>Servicios de federación de Active Directory (rol de servidor de federación)</p>
<p>Para obtener más información, consulte <a href="http://go.microsoft.com/fwlink/p/?linkid=281899">Understanding AD FS role Services</a>.</p></li>
<li><p>Servicios de federación de Active Directory (rol de servidor proxy)</p></li>
<li><p>Portal de Microsoft Online Services</p></li>
<li><p>El portal de mi empresa</p></li>
<li><p>Outlook Web App</p></li>
<li><p>Cliente de Lync (comunicación a Lync Online desde Lync Server local)</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>TCP 80 y 443</p></td>
<td><p>Abrir entrante</p>
<ul>
<li><p>Herramienta de sincronización de directorios de Microsoft Online Services</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>TCP 5061</p></td>
<td><p>Abrir entrada/salida en el servidor perimetral</p></td>
</tr>
<tr class="even">
<td><p>PSOM/TLS 443</p></td>
<td><p>Abrir entrada/salida para sesiones de uso compartido de datos</p></td>
</tr>
<tr class="odd">
<td><p>STUN/TCP 443</p></td>
<td><p>Abrir entrada/salida para sesiones de audio, vídeo y uso compartido de aplicaciones</p></td>
</tr>
<tr class="even">
<td><p>STUN/UDP 3478</p></td>
<td><p>Abrir entrada/salida para sesiones de audio y vídeo</p></td>
</tr>
<tr class="odd">
<td><p>RTP/TCP 50000-59999</p></td>
<td><p>Abrir salida para sesiones de audio y vídeo</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-accounts-and-data"></a>Cuentas de usuarios y datos

En una implementación híbrida de Lync Server 2013, todos los usuarios que deseen hospedar en Lync Online deben crearse primero en la implementación local, de modo que la cuenta de usuario se cree en los servicios de dominio de Active Directory. A continuación, puede mover el usuario a Skype empresarial online, que moverá la lista de contactos del usuario.

Al sincronizar cuentas de usuario entre su Lync local y las implementaciones de Lync Online con AD FS y DirSync, debe sincronizar las cuentas de AD de todos los usuarios de Lync de la organización entre las implementaciones locales y en línea de Lync, incluso si los usuarios no se mueven a Lync Online. Si no sincroniza todos los usuarios, es posible que la comunicación entre los usuarios locales y en línea de su organización no funcione según lo esperado.

<div>


> [!IMPORTANT]  
> Si el usuario se crea mediante el portal en línea para Office 365, la cuenta de usuario no se sincronizará con Active Directory local y el usuario no existirá en Active Directory local. Si ya ha creado usuarios en Lync Online y desea configurar un entorno híbrido con un servidor de Lync local, consulte <A href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">Moving users from Lync Online to Lync on-premises in Lync Server 2013</A>.



</div>

También debe tener en cuenta los siguientes problemas relacionados con los usuarios al planear una implementación híbrida.

  - **Contactos de usuario**   el límite para los contactos de Lync Online es de 250. Los contactos que superen este número se quitarán de la lista de contactos del usuario cuando la cuenta se mueva a Lync Online.

  - **Mensajería instantánea y presencia**   las listas de contactos de usuarios, grupos y listas de control de acceso (ACL) se migran con la cuenta de usuario.

  - **Datos de conferencia, contenido de reuniones y reuniones**   programadas este contenido no se migra con la cuenta de usuario. Los usuarios deben reprogramar reuniones una vez que estas cuentas migran a Lync Online.

</div>

<div>

## <a name="user-policies-and-features"></a>Directivas de usuario y características

  - En un entorno híbrido de Lync Server 2013, los usuarios pueden estar habilitados para mensajería instantánea, voz y reuniones de forma local o en línea, pero no para ambas cosas a la vez.

  - **Cliente de Lync**     es posible que algunos usuarios necesiten una nueva versión de cliente cuando se muevan a Lync Online. Para Office Communications Server 2007 R2, los usuarios deben moverse a un grupo de servidores de Lync Server 2013 antes de la migración a Lync Online.
    
    Para obtener más información acerca de la compatibilidad con clientes, consulte [clientes para Lync Online](http://go.microsoft.com/fwlink/p/?linkid=281902) y [clientes y configuraciones de puertos de red compatibles con Lync](http://go.microsoft.com/fwlink/p/?linkid=281901).

  - **Las directivas locales y de configuración (no del usuario)**   en línea y en las directivas locales requieren una configuración independiente. No se pueden configurar directivas globales que se apliquen a ambas.

</div>

</div>

<span> </span>

</div>

</div>

</div>

