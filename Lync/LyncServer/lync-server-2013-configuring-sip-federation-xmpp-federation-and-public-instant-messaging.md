---
title: "Configurar la federación SIP, la federación XMPP y la mensajería instantánea pública"
TOCTitle: Configurar la federación SIP, la federación XMPP y la mensajería instantánea pública
ms:assetid: a6d04f0b-5cb8-4084-a3a2-d501938971f9
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205134(v=OCS.15)
ms:contentKeyID: 48276277
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurar la federación SIP, la federación XMPP y la mensajería instantánea pública en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

La federación, la conectividad de mensajería instantánea pública y el protocolo extensible de mensajería y presencia (XMPP) definen una clase diferente de usuarios externos: los usuarios federados. Los usuarios de una implementación federada de Lync Server o XMPP tienen acceso a un conjunto limitado de servicios y se autentican por medio de la implementación externa. Los usuarios remotos son miembros de su implementación de Lync Server y tienen acceso a todos los servicios que ofrece su implementación.


> [!NOTE]
> Se anunció que la fecha de finalización de AOL y Yahoo! será en junio de 2014. Para obtener detalles, consulte <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Soporte para la conectividad de mensajería instantánea pública en Lync Server 2013</A>.



La conectividad de mensajería instantánea pública es un tipo especial de federación que permite a un cliente de Lync Server obtener acceso a socios configurados de mensajería instantánea pública utilizando el Lync 2013. Actualmente, los socios de conectividad de mensajería instantánea pública son:

  America Online  

  Windows Live  

  Yahoo\!  

Una configuración de conectividad de mensajería instantánea pública permite a los usuarios de Lync obtener acceso a usuarios de conectividad de mensajería instantánea pública mediante:

  - Mensajería instantánea (IM) y presencia

  - Visibilidad de contactos de conectividad de mensajería instantánea pública en el cliente de Lync

  - Conversaciones de MI de persona a persona con contactos

  - Llamadas de audio y vídeo con usuarios de Windows Live

La federación de Lync Server define un acuerdo entre su implementación de Lync Server y otras implementaciones de Office Communications Server 2007 R2 o Lync Server. Una configuración federada de Lync Server permite a los usuarios de Lync obtener acceso a usuarios federados mediante:

  - Mensajería instantánea (IM) y presencia

  - Creación de contactos federados en el cliente de Lync

La federación XMPP define una implementación externa basándose en el protocolo extensible de mensajería y presencia (XMPP). Una configuración XMPP permite a los usuarios de Lync obtener acceso a usuarios de dominios XMPP mediante:

  - Mensajería instantánea y presencia: solo persona a persona

  - Creación de contactos federados de XMPP en el cliente Lync

> [!IMPORTANT]  
> La capacidad XMPP de Lync Server 2013 está probada y es compatible con Microsoft para la federación de mensajería instantánea con Google Talk. Para otros sistemas XMPP, póngase en contacto con el proveedor para comprobar que son compatibles con la federación con Lync Server 2013 y para cualquier recomendación sobre implementación o solución de problemas.



## Federación externa de servidor perimetral, conectividad de mensajería instantánea pública y proceso de implementación de usuarios de XMPP


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
<td><p>Ejecute Generador de topologías para editar la configuración de servidor perimetral y crear y publicar la topología. La topología perimetral existente replicará los cambios de Almacén de administración central en el servidor perimetral.</p></td>
<td><p>Grupo Administradores de dominio y grupo RTCUniversalServerAdmins</p>

> [!NOTE]
> Puede editar una topología mediante una cuenta que es miembro del grupo de usuarios locales pero publicar una topología requiere una cuenta que es miembro del grupo Administradores de dominio y del grupo RTCUniversalServerAdmins.

</td>
<td><p><a href="lync-server-2013-building-an-edge-and-director-topology.md">Creación de una topología perimetral y de director Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Prepararse para el programa de instalación</p></td>
<td><ol>
<li><p>Compruebe que se cumplen los requisitos previos del sistema.</p></li>
<li><p>Configure registros DNS internos y externos para admitir la conectividad de mensajería instantánea pública, la federación de Lync y la federación de XMPP</p></li>
<li><p>Configure puertos y protocolos en el firewall para admitir los tipos de federación que va a implementar</p></li>
<li><p>Obtenga e instale certificados públicos. El tiempo necesario para obtener certificados depende de qué entidad de certificación (CA) emite el certificado. Este paso es opcional en este punto de la implementación. Si no lleva a cabo este paso en este momento, debe hacerlo durante la configuración del servidor perimetral. No se puede iniciar el servicio de servidor perimetral hasta que se obtengan certificados.</p></li>
</ol>
<p></p></td>
<td><p>Según corresponda a su organización, ya que estas funciones se suelen dividir entre numerosos grupos de trabajo</p></td>
<td><p><a href="lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md">Planeación de la federación SIP, la federación XMPP y la mensajería instantánea pública en Lync Server 2013</a></p></td>
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
<td><p>Grupo Administradores</p></td>
<td><p><a href="lync-server-2013-setting-up-lync-federation.md">Configuración de federación de Lync en Lync Server 2013</a></p>
<p><a href="lync-server-2013-setting-up-public-instant-messaging-connectivity.md">Establecer conectividad de mensajería instantánea pública en Lync Server 2013</a></p>
<p><a href="lync-server-2013-setting-up-xmpp-federation.md">Configurar la federación XMPP en Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Configure la compatibilidad para el acceso de usuarios externos.</p></td>
<td><ol>
<li><p>Use el acceso de usuarios externos mediante el Panel de control de Lync Server</p></li>
<li><p>Configure la directiva de acceso externo para habilitar las comunicaciones con usuarios federados o usuarios públicos</p></li>
<li><p>Configure los dominios federados SIP para permitir o bloquear dominios</p></li>
<li><p>Habilite proveedores federados SIP para proveedores de conectividad de mensajería instantánea pública</p></li>
<li><p>Configure socios federados de XMPP para el dominio XMPP</p></li>
</ol></td>
<td><p>Grupo RTCUniversalServerAdmins o una cuenta de usuario que esté asignada al rol CSAdministrator</p></td>
<td><p><a href="lync-server-2013-configuring-support-for-external-user-access.md">Configurar la compatibilidad para el acceso de usuarios externos en Lync Server 2013</a></p>
<p><a href="lync-server-2013-configure-media-encryption-for-public-providers.md">Configurar el cifrado de medios para proveedores públicos en Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Compruebe la configuración del servidor perimetral</p></td>
<td><p>Compruebe la conectividad de servidor y la replicación de datos de configuración de servidores internos</p></td>
<td><p>Para la comprobación de la replicación, el grupo RTCUniversalServerAdmins o la cuenta de usuario que se asigna al rol CSAdministrator. Para la comprobación de la conectividad de usuario, un usuario para cada tipo de usuario federado</p></td>
<td><p><a href="lync-server-2013-verifying-your-edge-deployment.md">Comprobación de la implementación perimetral en Lync Server 2013</a></p>
<p><a href="lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md">Configuración XMPP de ejemplo en Lync Server 2013 - Federación XMPP con Google Talk</a></p></td>
</tr>
</tbody>
</table>

