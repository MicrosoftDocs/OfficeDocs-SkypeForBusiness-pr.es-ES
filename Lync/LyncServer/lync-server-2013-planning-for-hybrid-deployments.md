---
title: 'Lync Server 2013: Planear las implementaciones híbridas de Lync Server'
TOCTitle: Planear las implementaciones híbridas de Lync Server
ms:assetid: f8b3d240-bc2e-42c9-acf8-d532d641a14c
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205403(v=OCS.15)
ms:contentKeyID: 48277253
ms.date: 06/02/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Planear las implementaciones híbridas de Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

Cuando planee una implementación híbrida, tenga en cuenta los siguientes requisitos para los usuarios y la infraestructura de red.

## Requisitos de infraestructura

Debe disponer en su entorno de los siguientes elementos para implementar y configurar una implementación híbrida de Lync Server 2013:

  - Un inquilino de Office 365 con Lync Online habilitado.

  - Un servidor de Servicios de federación de Active Directory (AD FS) local o que use Microsoft Azure. Para obtener más información sobre AD FS, vea [Servicios de federación de Active Directory (AD FS) 2.0](http://go.microsoft.com/fwlink/p/?linkid=393795) o [Configurar Servicios de federación de Active Directory para Windows Azure Pack](http://go.microsoft.com/fwlink/p/?linkid=522475).

  - Una implementación local de Lync Server 2013 o Lync Server 2010 con las actualizaciones acumulativas para Lync Server 2010: marzo de 2013 (o posterior) aplicadas.

  - Herramientas administrativas de Lync Server 2013.

  - Sincronización de directorios. Para obtener más información sobre la sincronización de directorios, vea [Administración de identidad híbrida](http://go.microsoft.com/fwlink/p/?linkid=231010).

## Compatibilidad con clientes de Lync

Hay algunas diferencias en las características compatibles con los clientes de Lync y en las disponibles en entornos locales y en línea. Antes de decidir dónde hospedará a los usuarios de su organización, consulte la compatibilidad de clientes de las diversas configuraciones de Lync Server. Los siguientes clientes son compatibles con Skype Empresarial Online en una implementación híbrida de Lync:

  - Lync 2010

  - Lync 2013

  - Aplicación de la Tienda Windows de Lync

  - Lync Web App

  - Lync Mobile

  - Lync para Mac 2011

  - Sistema de salas de Lync

  - Lync Basic 2013

Para obtener información detallada sobre la compatibilidad de clientes, vea los siguientes temas:

  - [Clientes para Lync Online](http://go.microsoft.com/fwlink/?linkid=281902)

  - [Tablas de comparación de clientes para Lync Server 2013](lync-server-2013-desktop-client-comparison-tables.md)

  - [Tablas de comparación de clientes móviles para Lync Server 2013](lync-server-2013-mobile-client-comparison-tables.md)

## Requisitos de topología

Para configurar la implementación de Lync Server 2013 para implementaciones híbridas con Skype Empresarial Online, debe disponer de una de las siguientes topologías compatibles:

  - Microsoft Office Communications Server 2007 R2 con una implementación local de Lync Server 2013. El Servidor perimetral de federación de Lync Server 2013 y el servidor del próximo salto desde el Servidor perimetral de federación deben ejecutar Lync Server 2013. Debe contar con un Almacén de administración central implementado. El Servidor perimetral y el grupo deben estar implementados a escala local.
    
    > [!IMPORTANT]  
    > Esta topología se admite, pero parte de la funcionalidad puede estar limitada. Por ejemplo, es posible que la información de presencia no funcione como se espera entre los usuarios de Microsoft Lync Online y los usuarios locales de Office Communications Server 2007 R2.
    


  - Microsoft Lync Server 2010 con las actualizaciones acumulativas para Lync Server 2010: marzo de 2013 (o posterior) aplicadas y las herramientras administrativas de Lync Server 2013 instaladas localmente. El Servidor perimetral de federación y el servidor del próximo salto desde el Servidor perimetral de federación deben ejecutar Microsoft Lync Server 2010 con las actualizaciones acumulativas de marzo de 2013 (o posterior) aplicadas, o Lync Server 2013.
    
    > [!IMPORTANT]  
    > Las herramientas administrativas de Lync Server 2013 deben instalarse en un servidor aparte que tenga acceso para conectarse con la implementación existente de Lync Server 2010. El cmdlet Move-CsUser para mover usuarios desde la implementación local a Lync Online debe ejecutarse desde las herramientas administrativas de Lync Server 2013 conectadas a la implementación local.
    


  - Una implementación de Lync Server 2013 donde todos los servidores ejecuten Lync Server 2013.

Para obtener más información sobre las topologías compatibles, vea [Topologías compatibles en Lync Server 2013](lync-server-2013-supported-topologies.md) y [Topologías de referencia de Lync Server 2013 para implementaciones híbridas de Enterprise](http://go.microsoft.com/fwlink/p/?linkid=398709).

Para obtener información de solución de problemas sobre implementaciones híbridas y la conexión de PowerShell a Lync Online, vea [Lync Online: solución de problemas de Lync PowerShell e implementaciones híbridas](http://go.microsoft.com/fwlink/p/?linkid=306718).

## Requisitos para las listas de permitidos/bloqueados de la federación

La lista de dominios permitidos incluye los dominios que tienen configurado un nombre de dominio completo (FQDN) del perímetro de asociado. En ocasiones, se conocen como *servidores de asociado permitidos* o *asociados directos de federación*. Familiarícese con la diferencia entre las federaciones abiertas y cerradas, conocidas respectivamente como *detección de asociado* o *lista de dominios de asociado permitidos* en las implementaciones locales.

Los requisitos siguientes deben cumplirse para configurar correctamente una implementación híbrida:

  - La coincidencia de dominios debe configurarse de la misma manera para la implementación local y para el inquilino de Office 365. Si la detección de asociado está habilitada en la implementación local, configure una federación abierta para el inquilino en línea. Si, por el contrario, la detección de asociado no está habilitada, configure una federación cerrada para el inquilino en línea.

  - La lista de dominios bloqueados de la implementación local debe coincidir exactamente con la lista de dominios bloqueados del inquilino en línea.

  - La lista de dominios permitidos de la implementación local debe coincidir exactamente con la lista de dominios permitidos del inquilino en línea.

  - La federación debe habilitarse para las comunicaciones externas del inquilino en línea, que se configura con el Panel de control de Lync Online.

## Configuración de DNS

Cuando cree registros SRV de DNS para implementaciones híbridas, los registros \_sipfederationtls.\_tcp.\<dominio\> y \_sip.\_tls.\<dominio\>, deben apuntar al proxy de acceso local.

## Observaciones sobre el firewall

Los equipos de la red deben poder efectuar búsquedas estándar de DNS en Internet. Si estos equipos acceden a sitios de Internet estándar, la red cumplirá este requisito.

Según la ubicación del centro de datos de Microsoft Online Services, configure también los dispositivos de firewall de la red para que acepten conexiones basadas en nombres de dominio con comodín (por ejemplo, todo el tráfico desde \*.outlook.com). Si los firewall de la organización no admiten configuraciones de nombres con comodín, determine manualmente los intervalos de las direcciones IP que desea permitir y los puertos especificados.

Consulte el tema de ayuda [Intervalos de direcciones IP y URL de Office 365](http://go.microsoft.com/fwlink/p/?linkid=252942).

## Requisitos de puerto y protocolo

Además de los requisitos de puerto para la comunicación de Lync Server 2013 interna, configure también los puertos siguientes.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Protocolo o puerto</th>
<th>Aplicaciones</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>TCP 443</p></td>
<td><p>Entrada abierta</p>
<ul>
<li><p>Servicios de federación de Active Directory (rol de servidor de federación)</p>
<p>Para obtener más información, vea <a href="http://go.microsoft.com/fwlink/p/?linkid=281899">Descripción de los servicios del rol AD FS</a>.</p></li>
<li><p>Servicios de federación de Active Directory (rol de servidor proxy)</p></li>
<li><p>Portal de Microsoft Online Services</p></li>
<li><p>El portal de mi empresa</p></li>
<li><p>Outlook Web App</p></li>
<li><p>Cliente de Lync (comunicación a Lync Online desde implementación local de Lync Server)</p></li>
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
<td><p>Entrada o salida abierta en el Servidor perimetral</p></td>
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
<tr class="even">
<td><p>TCP 443</p></td>
<td><p>Entrada abierta</p>
<ul>
<li><p>Servicios de federación de Active Directory (rol de servidor de federación)</p>
<p>Para obtener más información, vea <a href="http://go.microsoft.com/fwlink/p/?linkid=281899">Descripción de los servicios del rol AD FS</a>.</p></li>
<li><p>Servicios de federación de Active Directory (rol de servidor proxy)</p></li>
<li><p>Portal de Microsoft Online Services</p></li>
<li><p>El portal de mi empresa</p></li>
<li><p>Outlook Web App</p></li>
<li><p>Cliente de Lync (comunicación a Lync Online desde implementación local de Lync Server)</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>TCP 80 y 443</p></td>
<td><p>Entrada abierta</p>
<ul>
<li><p>Herramienta de sincronización de directorios de Microsoft Online Services</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>TCP 5061</p></td>
<td><p>Entrada o salida abierta en el Servidor perimetral</p></td>
</tr>
<tr class="odd">
<td><p>PSOM/TLS 443</p></td>
<td><p>Entrada o salida abierta para sesiones de uso compartido de datos</p></td>
</tr>
<tr class="even">
<td><p>STUN/TCP 443</p></td>
<td><p>Entrada o salida abierta para sesiones de uso compartido de aplicaciones, vídeo y audio</p></td>
</tr>
<tr class="odd">
<td><p>STUN/UDP 3478</p></td>
<td><p>Entrada o salida abierta para sesiones de audio y vídeo</p></td>
</tr>
<tr class="even">
<td><p>RTP/TCP 50000-59999</p></td>
<td><p>Salida abierta para sesiones de audio y vídeo</p></td>
</tr>
</tbody>
</table>



> [!NOTE]
> Si necesita federarse con asociados que ejecuten Office Communications Server 2007, deberá abrir los puertos 50000-59999 RTP/UDP y RTP/TCP de entrada o salida. Para obtener más información sobre los requisitos de firewall de A/V, vea <A href="lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md">Determinar los requisitos de los puertos y el firewall de A/V externos en Lync Server 2013</A>. Para obtener más información sobre puertos y protocolos, vea <A href="lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md">Resumen de puerto - Servidor perimetral consolidado ampliado con equilibradores de carga de hardware en Lync Server 2013</A>.



## Cuentas de usuarios y datos

En una implementación híbrida de Lync Server 2013, primero deberá crear en la implementación local los usuarios que desee hospedar en Lync Online, de modo que la cuenta de usuario se cree en Servicios de dominio de Active Directory. Después, puede mover el usuario a Skype Empresarial Online que, a su vez, moverá la lista de contactos del usuario.

Al sincronizar cuentas de usuario entre sus implementaciones de Lync local y en línea con AD FS y Dirsync, tiene que sincronizar las cuentas de AD para todos los usuarios de Lync de su organización entre sus implementaciones de Lync local y en línea, incluso si los usuarios no se mueven a Lync Online. Si no sincroniza todos los usuarios, puede ser que la comunicación entre los usuarios locales y en línea de su organización no funcione como se podría esperar.

> [!IMPORTANT]  
> Si el usuario se crea con el portal en línea de Office 365, la cuenta de usuario no se sincronizará con la implementación local de Active Directory de modo que el usuario no existirá en ella. Si ya tiene usuarios creados en Lync Online y desea configurar una híbrida con Lync Server local, vea <a href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">Mover usuarios de Lync Online a Lync local en Lync Server 2013</a>.



También debe tener en cuenta los siguientes problemas relacionados con el usuario al planear una implementación híbrida.

  - **Contactos de usuario**   El límite de contactos para los usuarios de Lync Online es de 250. Los contactos que superen dicho número se quitarán de la lista de contactos del usuario cuando la cuenta se mueva a Lync Online.

  - **Mensajería instantánea y presencia**   Las listas de contactos de usuarios, grupos y listas de control de acceso (ACL) se migran con la cuenta de usuario.

  - **Datos de conferencia, contenido de reuniones y reuniones programadas**   Este contenido no se migra con la cuenta de usuario. Los usuarios deben reprogramar reuniones una vez que estas cuentas migran a Lync Online.

## Directivas de usuario y características

  - En un entorno híbrido de Lync Server 2013, se puede habilitar a los usuarios para mensajería instantánea, voz y reuniones en modo local o en línea, pero no en ambos a la vez.

  - **Cliente de Lync**    Algunos usuarios pueden necesitar una nueva versión de cliente cuando pasan a Lync Online. Para Office Communications Server 2007 R2, es necesario mover los usuarios a un grupo de Lync Server 2013 antes de migrar a Lync Online.
    
    Para obtener más información sobre la compatibilidad de clientes, vea [Clientes para Lync Online](http://go.microsoft.com/fwlink/p/?linkid=281902) y [Configuraciones de puerto de red y clientes Lync compatibles](http://go.microsoft.com/fwlink/p/?linkid=281901) .

  - **Configuración y directivas locales (no del usuario)**   Las directivas en línea y locales necesitan una configuración diferente. No se pueden establecer directivas globales para aplicarlas a ambas.

