---
title: 'Lync Server 2013: planeamiento de implementaciones híbridas'
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
ms.openlocfilehash: e0902150170d51aa590afc8b3d02c887968a2031
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41751980"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-lync-server-2013-hybrid-deployments"></a>Planeación de implementaciones híbridas de Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2016-05-25_

Al planear una implementación híbrida, debe tener en cuenta los siguientes requisitos para los usuarios y su infraestructura de red.

<div>

## <a name="infrastructure-requirements"></a>Requisitos de infraestructura

Debe tener el siguiente configurado en su entorno para implementar e implementar una implementación híbrida.

  - Un inquilino de Microsoft Office 365 con Skype empresarial online habilitado. Tenga en cuenta que solo puede usar un único inquilino para una configuración híbrida con su implementación local.

  - Una sola implementación local (infraestructura) de Skype empresarial Server o Lync Server implementada en una topología compatible. Consulte requisitos de topología.
    
    Para obtener información sobre cómo configurar su implementación de Lync Server 2013 o Lync Server 2010 para entornos híbridos, consulte [configuración de implementaciones híbridas de Lync server 2013](lync-server-2013-configuring-hybrid-deployments.md).

  - Herramientas administrativas de Skype empresarial Server 2015. Si está usando Lync Server 2013 o Lync Server 2010, puede usar las herramientas administrativas de Lync Server 2013.

  - Para admitir el inicio de sesión único con Office 365 de modo que los usuarios puedan usar las mismas credenciales de inicio de sesión para iniciar sesión en Office como locales, puede usar las características de sincronización de contraseñas de Azure Active Directory (AAD) Connect. También puede usar los Servicios de federación de Active Directory (AD FS) para el inicio de sesión único con Office 365.
    
    Para obtener más información, consulte [integrar las identidades locales con Azure Active Directory](http://go.microsoft.com/fwlink/p/?linkid=619754).

  - Una única solución de sincronización de directorios para mantener sincronizados los objetos de Active Directory locales y en línea. Para obtener más información sobre la sincronización de directorios, consulte [herramientas de integración de directorios](http://go.microsoft.com/fwlink/p/?linkid=530320).

</div>

<div>

## <a name="lync-client-support"></a>Compatibilidad con clientes de Lync

Existen algunas diferencias en las características compatibles con los clientes de Lync, así como las características disponibles en entornos locales y en línea. Antes de decidir dónde desea alojar a los usuarios de su organización, puede ver la compatibilidad de cliente para las distintas configuraciones de Lync Server. Los siguientes clientes son compatibles con Skype empresarial online en una implementación híbrida de Lync:

  - Lync 2010

  - Lync 2013

  - Aplicación de la Tienda Windows de Lync

  - Lync Web App

  - Lync Mobile

  - Lync para Mac 2011

  - Sistema Lync Room

  - Lync Basic 2013

Para obtener más información sobre la compatibilidad del cliente, vea los siguientes temas:

  - [Clientes de Lync Online](http://go.microsoft.com/fwlink/?linkid=281902)

  - [Tablas de comparación de clientes para Lync Server 2013](lync-server-2013-desktop-client-comparison-tables.md)

  - [Tablas de comparación de clientes móviles para Lync Server 2013](lync-server-2013-mobile-client-comparison-tables.md)

</div>

<span id="BKMK_Topology"></span>

<div>

## <a name="topology-requirements"></a>Requisitos de topología

Para configurar la implementación de un entorno híbrido con Skype empresarial online, debe tener una de las siguientes topologías compatibles:

  - Una implementación de Skype empresarial Server 2015 con todos los servidores que ejecutan Skype empresarial Server 2015.

  - Una implementación de Lync Server 2013 con todos los servidores que ejecutan Lync Server 2013.

  - Una implementación de Lync Server 2010 con todos los servidores que ejecutan Lync Server 2010 y las últimas actualizaciones acumulativas.
    
      - El servidor perimetral de Federación y el servidor de próximo salto del servidor perimetral de Federación deben ejecutar Lync Server 2010 con las últimas actualizaciones acumulativas.
    
      - Las herramientas administrativas de Skype empresarial Server 2015 o Lync Server 2013 deben instalarse en al menos un servidor o en una estación de trabajo de administración.

  - Una implementación mixta de Lync Server 2013 y Skype empresarial Server 2015 con los siguientes roles de servidor en al menos un sitio que ejecute Skype empresarial Server 2015:
    
      - Al menos un grupo de servidores Enterprise o un servidor Standard Edition
    
      - El grupo de directores asociado con la federación SIP, si existe
    
      - El grupo de servidores perimetrales asociado con la federación SIP

  - Una implementación mixta de Lync Server 2010 y Skype empresarial Server 2015 con los siguientes servidores en al menos un sitio que ejecute Skype empresarial Server 2015:
    
      - Al menos un grupo de servidores Enterprise o un servidor Standard Edition
    
      - El grupo de directores asociado con la federación SIP, si existe
    
      - El grupo de servidores perimetrales asociado con la federación SIP para el sitio

  - Una implementación mixta de Lync Server 2010 y Lync Server 2013 con los siguientes roles de servidor en al menos un sitio que ejecute Lync Server 2013:
    
      - Al menos un grupo de servidores Enterprise o un servidor Standard Edition en el sitio
    
      - El grupo de directores asociado con la federación SIP, si existe en el sitio
    
      - El grupo de servidores perimetrales asociado con la federación SIP para el sitio

<div>


> [!IMPORTANT]  
> Toda la administración de usuarios, incluidos los movimientos de usuario locales y UNRESOLVED_TOKEN_VAL (skypeforbusiness) en línea, debe realizarse con la última versión instalada de las herramientas administrativas. Las herramientas administrativas deben instalarse en un servidor independiente que tenga acceso de conexión a la implementación local existente y a Internet. El cmdlet <A href="https://docs.microsoft.com/powershell/module/skype/Move-CsUser">Move-CsUser</A> para mover usuarios de la implementación local a UNRESOLVED_TOKEN_VAL (skype16_online) debe ejecutarse desde las herramientas administrativas conectadas a la implementación local.



</div>

Para obtener más información sobre las topologías admitidas, consulte topologías [admitidas en Lync server 2013](lync-server-2013-supported-topologies.md)y [topologías de referencia de Lync Server 2013 para implementaciones híbridas empresariales](http://go.microsoft.com/fwlink/p/?linkid=398709).

Para obtener información sobre la solución de problemas de implementaciones híbridas y sobre cómo conectar PowerShell a Lync Online, vea [Lync Online: Lync PowerShell y solución de problemas híbrida](http://go.microsoft.com/fwlink/p/?linkid=306718).

</div>

<div>

## <a name="requirements-for-federation-allowedblocked-lists"></a>Requisitos para las listas de Federación permitida/bloqueada

La lista de dominios permitidos incluye los dominios que tienen configurado un nombre de dominio completo (FQDN) del perímetro de asociado. En ocasiones, se conocen como *servidores de asociado permitidos* o *asociados directos de federación*. Familiarícese con la diferencia entre las federaciones abiertas y cerradas, conocidas respectivamente como *detección de asociado* o *lista de dominios de asociado permitidos* en las implementaciones locales.

Los requisitos siguientes necesitan cumplirse para configurar correctamente una implementación híbrida:

  - La coincidencia de dominios necesita configurarse de la misma manera para la implementación local y para el inquilino de Office 365. Si la detección de asociado está habilitada en la implementación local, configure una federación abierta para el inquilino en línea. Si, por el contrario, la detección de asociado no está habilitada, configure una federación cerrada para el inquilino en línea.

  - La lista de dominios bloqueados de la implementación local necesita coincidir exactamente con la lista de dominios bloqueados del inquilino en línea.

  - La lista de dominios permitidos de la implementación local necesita coincidir exactamente con la lista de dominios permitidos del inquilino en línea.

  - La Federación debe habilitarse para las comunicaciones externas del inquilino en línea, que se configura con el panel de control de Lync Online.

</div>

<div>

## <a name="dns-settings"></a>Configuración DNS

Al crear registros DNS para implementaciones híbridas, todos los registros DNS externos de Lync deberían apuntar a la infraestructura local. Para obtener más información sobre los registros DNS necesarios, consulte [los requisitos del sistema de nombres de dominio (DNS) de Lync Server 2013](lync-server-2013-domain-name-system-dns-requirements.md).

Además, debe asegurarse de que la resolución DNS que se describe en la siguiente tabla funciona en su implementación local:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Registro DNS</p></td>
<td><p>Lo puede resolver</p></td>
<td><p>Requisito de DNS</p></td>
</tr>
<tr class="even">
<td><p>Registro SRV de DNS para _sipfederationtls. _tcp. &lt;sipdomain.com&gt; para todos los dominios SIP compatibles que se resuelven para acceder a las IP externas perimetrales</p></td>
<td><p>Servidores perimetrales</p></td>
<td><p>Habilite la comunicación federada en una configuración híbrida. El servidor perimetral tiene que saber hacia dónde redirigir el tráfico federado para el dominio SIP que se divide entre las formas local y en línea.</p></td>
</tr>
<tr class="odd">
<td><p>DNS un registro (s) para el servicio de conferencias web perimetrales FQDN, por ejemplo, webcon.contoso.com la resolución de las IP externas perimetrales de la conferencia Web</p></td>
<td><p>Equipos de usuarios conectados a la red corporativa interna</p></td>
<td><p>Permitir que los usuarios en línea presenten o vean contenido en reuniones hospedadas en el entorno. El contenido incluye archivos de PowerPoint, pizarras, sondeos y notas compartidas.</p></td>
</tr>
</tbody>
</table>


Según el modo en que se configure DNS en su organización, es posible que tenga que agregar estos registros a la zona DNS hospedada interna de los dominios SIP correspondientes para proporcionar resolución DNS interna a estos registros.

</div>

<div>

## <a name="firewall-considerations"></a>Consideraciones sobre el Firewall

Los equipos de la red deben poder realizar búsquedas DNS estándar de Internet. Si estos equipos pueden comunicarse con sitios de Internet estándar, su red cumple con este requisito.

En función de la ubicación del centro de datos de Microsoft Online Services, también debe configurar los dispositivos de Firewall de red para que acepten conexiones basadas en nombres de dominio con comodín ( \*por ejemplo, todo el tráfico de. Outlook.com). Si los firewalls de su organización no admiten configuraciones de nombre comodín, tendrá que determinar manualmente los intervalos de direcciones IP que desea permitir y los puertos especificados.

Consulte el tema de ayuda [Office 365 URL e intervalos de direcciones IP](http://go.microsoft.com/fwlink/p/?linkid=252942).

</div>

<span id="b"></span>

<div>

## <a name="port-and-protocol-requirements"></a>Requisitos de puerto y protocolo

Además de los requisitos de puerto para la comunicación interna de Lync Server 2013, también debe configurar los siguientes puertos.


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
<td><p>Entrada abierta</p>
<ul>
<li><p>Servicios de Federación de Active Directory (rol de servidor de Federación)</p>
<p>Para obtener más información, consulte <a href="http://go.microsoft.com/fwlink/p/?linkid=281899">Understanding AD FS role Services</a>.</p></li>
<li><p>Servicios de Federación de Active Directory (rol de servidor proxy)</p></li>
<li><p>Portal de Microsoft Online Services</p></li>
<li><p>Portal de mi empresa</p></li>
<li><p>Outlook Web App</p></li>
<li><p>Cliente de Lync (comunicación a Lync Online desde Lync Server local)</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>TCP 80 y 443</p></td>
<td><p>Entrada abierta</p>
<ul>
<li><p>Herramienta de sincronización de directorios de Microsoft Online Services</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>TCP 5061</p></td>
<td><p>Entrada o salida abierta en el servidor perimetral</p></td>
</tr>
<tr class="even">
<td><p>PSOM/TLS 443</p></td>
<td><p>Entrada o salida abierta para sesiones de uso compartido de datos</p></td>
</tr>
<tr class="odd">
<td><p>STUN/TCP 443</p></td>
<td><p>Entrada o salida abierta para sesiones de uso compartido de aplicaciones, vídeo y audio</p></td>
</tr>
<tr class="even">
<td><p>STUN/UDP 3478</p></td>
<td><p>Entrada o salida abierta para sesiones de audio y vídeo</p></td>
</tr>
<tr class="odd">
<td><p>RTP/TCP 50000-59999</p></td>
<td><p>Salida abierta para sesiones de audio y vídeo</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-accounts-and-data"></a>Cuentas de usuario y datos

En una implementación híbrida de Lync Server 2013, todos los usuarios que desee que se encontrarán en Lync Online deben crearse en la implementación local, de modo que la cuenta de usuario se cree en servicios de dominio de Active Directory. Después, puede mover el usuario a Skype empresarial online, que moverá la lista de contactos del usuario.

Al sincronizar cuentas de usuario entre su Lync local y las implementaciones de Lync Online con AD FS y DirSync, debe sincronizar las cuentas de AD de todos los usuarios de Lync de su organización entre las implementaciones de Lync locales y en línea, incluso si los usuarios no se mueven a Lync Online. Si no sincroniza todos los usuarios, puede ser que la comunicación entre los usuarios locales y en línea de su organización no funcione como se podría esperar.

<div>


> [!IMPORTANT]  
> Si el usuario se crea mediante el portal en línea para Office 365, la cuenta de usuario no se sincronizará con Active Directory local y el usuario no existirá en Active Directory local. Si ya ha creado usuarios en Lync Online y desea configurar un entorno híbrido con un servidor de Lync local, consulte <A href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">mover usuarios de Lync Online a Lync local en Lync Server 2013</A>.



</div>

También debe tener en cuenta los siguientes problemas relacionados con el usuario al planear una implementación híbrida.

  - **Contactos de usuarios**   el límite de contactos para los usuarios de Lync Online es 250. Los contactos que se encuentren por encima de ese número se eliminarán de la lista de contactos del usuario cuando se mueva la cuenta a Lync Online.

  - **Mensajería instantánea y presencia**   las listas de contactos, los grupos y las listas de control de acceso (ACL) se migran con la cuenta de usuario.

  - **Datos de conferencia, contenido de la reunión y reuniones**   programadas este contenido no se migra con la cuenta de usuario. Los usuarios deben reprogramar las reuniones después de migrar sus cuentas a Lync Online.

</div>

<div>

## <a name="user-policies-and-features"></a>Directivas de usuario y características

  - En un entorno híbrido de Lync Server 2013, se puede habilitar a los usuarios para mensajería instantánea, voz y reuniones locales o en línea, pero no ambos simultáneamente.

  - **Cliente de Lync**     es posible que algunos usuarios necesiten una nueva versión de cliente cuando se muevan a Lync Online. Para Office Communications Server 2007 R2, los usuarios deben moverse a un grupo de servidores de Lync Server 2013 antes de la migración a Lync Online.
    
    Para obtener más información sobre la compatibilidad del cliente, consulte [clientes para Lync Online](http://go.microsoft.com/fwlink/p/?linkid=281902) y [configuración de puertos de red y clientes de Lync compatibles](http://go.microsoft.com/fwlink/p/?linkid=281901).

  - **Las directivas locales y de configuración (no de usuario)**   en línea y en las directivas locales requieren una configuración independiente. No puede establecer directivas globales que se apliquen a ambos.

</div>

</div>

<span> </span>

</div>

</div>

</div>

