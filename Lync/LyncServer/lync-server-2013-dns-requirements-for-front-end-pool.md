---
title: 'Lync Server 2013: Requisitos de DNS para el grupo de servidores front-end'
TOCTitle: Requisitos de DNS para el grupo de servidores front-end
ms:assetid: 02d2aa6b-9e01-437b-a2df-00590280150d
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398082(v=OCS.15)
ms:contentKeyID: 48274255
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Requisitos de DNS para el grupo de servidores front-end en Lync Server 2013

 

_**Última modificación del tema:** 2016-12-15_

Para completar con éxito este procedimiento, debe iniciar sesión en el servidor o dominio, al menos, como miembro del grupo administradores del dominio o como miembro del grupo DnsAdmins.

Tiene que configurar los registros del sistema de nombres de dominio (DNS) antes de publicar su topología en Generador de topologías. Además, algunos de los nombres de dominio completos (FQDN) usados en la configuración de una implementación de Lync Server 2013 son FQDN de un servidor lógico y no físico, por lo que es necesario realizar una configuración adicional antes de la publicación.

> [!WARNING]  
> Lync Server 2013 no admite dominios de etiqueta única. Por ejemplo, se admitiría un bosque con un dominio raíz denominado <strong>contoso.local</strong>, pero no un dominio raíz denominado <strong>local</strong>. Para obtener más información, vea el artículo 300684 de Microsoft Knowledge Base, “Información acerca de la configuración de Windows para dominios con nombres DNS de etiqueta única” en <a href="http://support.microsoft.com/kb/300684/es-es" class="uri">http://support.microsoft.com/kb/300684/es-es</a>.



> [!IMPORTANT]  
> El nombre que especifique debe ser idéntico al nombre del equipo configurado en el servidor. De manera predeterminada, el nombre de un equipo que no está unido a un dominio es un nombre corto, en lugar de un nombre de dominio completo (FQDN). Generador de topologías utiliza nombres de dominio completos, en vez de los cortos. <strong>Utilice únicamente caracteres estándar</strong> (A–Z, a–z, 0–9 y guiones) cuando asigne los nombres de dominio completo a los servidores que ejecutan Lync Server, Servidores perimetrales y grupos de servidores. No utilice caracteres Unicode ni de subrayado. Los DNS externos y las entidades de certificación (CA) públicas no admiten caracteres que no sean estándar en un nombre de dominio completo (cuando dicho nombre debe asignarse al nombre del sujeto en el certificado).



Antes de usar la topología ya implementada, asegúrese de que se han creado los siguientes registros DNS y Active Directory (según las características específicas que necesite):

  - Todas las funciones de servidor que existan en la topología se publicarán como objetos de Active Directory (esto se llevará a cabo al incorporar el equipo al dominio).

  - Existe un registro DNS A para cada uno de los servidores.

  - Existe un registro SRV de DNS para cada uno de los dominios SIP si tiene planeado usar el inicio de sesión automático para los clientes con el formato \_sipinternaltls\_tcp. *\<dominio SIP\>* . Si va a usar la configuración manual para los clientes, este registro no es necesario.

  - Un registro DNS A para cada URL sencilla configurada, de las que suelen haber cuatro: reunión, marcado, lwa y programador. Además, existe la dirección URL sencilla de administración, que es una URL especial para obtener acceso al Panel de control de Lync Server 2013.

  - El servidor que ejecute SQL Server debe estar incorporado a un dominio y ser accesible por el equipo desde el que Generador de topologías está publicando.

La tabla sigue las arquitecturas de referencia presentadas en la sección Planeación. Para obtener más información, vea el tema de [Escenarios para el acceso de usuarios externos en Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) en la documentación de planificación.

### Registros DNS requeridos para el Grupo de servidores front-end

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Ubicación</th>
<th>Tipo</th>
<th>FQDN</th>
<th>Asignado a/Comentarios</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DNS interno</p></td>
<td><p>A</p></td>
<td><p>pool01.contoso.net</p></td>
<td><p>Grupo01 (Equilibrio de carga de DNS). Requiere un registro DNS A para la dirección IP de cada Servidor front-end dentro del grupo de servidores, que se asigne al grupo de servidores FQDN.</p></td>
</tr>
<tr class="even">
<td><p>DNS interno</p></td>
<td><p>A</p></td>
<td><p>pool01.contoso.net</p></td>
<td><p>Grupo01 (IP virtual (VIP) del equilibrador de carga de hardware)</p></td>
</tr>
<tr class="odd">
<td><p>DNS interno</p></td>
<td><p>A</p></td>
<td><p>fe01.contoso.net</p>
<p>fe02.contoso.net</p>
<p>fe03.contoso.net</p>
<p>…</p></td>
<td><p>Servidor front-end Grupo01 (NODO 1)</p>
<p>Servidor front-end Grupo01 (NODO 2)</p>
<p>Servidor front-end Grupo01 (NODO 3)</p>
<p>…</p></td>
</tr>
<tr class="even">
<td><p>DNS interno</p></td>
<td><p>A</p></td>
<td><p>fe02.contoso.net</p></td>
<td><p>Servidor front-end Grupo01 (NODO 2)</p></td>
</tr>
<tr class="odd">
<td><p>DNS interno</p></td>
<td><p>A</p></td>
<td><p>lsweb.contoso.net</p></td>
<td><p>Grupo01 (VIP) para el tráfico web cliente-servidor</p></td>
</tr>
<tr class="even">
<td><p>DNS interno</p></td>
<td><p>A</p></td>
<td><p>sqlbe.contoso.net</p></td>
<td><p>Servidor back-end del Grupo01 que ejecuta SQL Server 2008 R2.</p></td>
</tr>
<tr class="odd">
<td><p>DNS interno</p></td>
<td><p>A</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Se requiere para Lync Phone Edition, o para el inicio automático de sesión de los clientes sin registros DNS SRV, y para la coincidencia exacta de dominios. No es necesario en todos los casos.</p></td>
</tr>
<tr class="even">
<td><p>DNS interno</p></td>
<td><p>A</p></td>
<td><p>sip.fabrikam.com</p></td>
<td><p>Asume un segundo dominio SIP. Se requiere para Lync Phone Edition, para el inicio automático de sesión de los clientes sin registros DNS SRV y para la coincidencia exacta de dominios. No es necesario en todos los casos.</p></td>
</tr>
<tr class="odd">
<td><p>DNS interno</p></td>
<td><p>A</p></td>
<td><p>dialin.contoso.com</p></td>
<td><p>URL sencilla para conferencias de acceso telefónico local publicadas internamente: el Servidor front-end (o Director, si está instalado) responde a consultas de URL sencilla</p></td>
</tr>
<tr class="even">
<td><p>DNS interno</p></td>
<td><p>A</p></td>
<td><p>meet.contoso.com</p></td>
<td><p>URL sencilla para conferencias publicadas internamente: el Servidor front-end (o Director, si está instalado) responde a consultas de URL sencilla</p></td>
</tr>
<tr class="odd">
<td><p>DNS interno</p></td>
<td><p>A</p></td>
<td><p>admin.contoso.com</p>
<p>Administrador</p></td>
<td><p>Registro opcional, URL sencilla para Panel de control de Lync Server 2013 que se publican internamente: el Servidor front-end (o Director, si está instalado) responde a consultas de URL sencilla Se recomienda usar solo el nombre de host (sin nombre de dominio).</p></td>
</tr>
</tbody>
</table>



> [!NOTE]
> VIP = dirección IP virtual para el equilibrador de carga de hardware



## Registros DNS SRV para el Grupo de servidores front-end


<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th>Ubicación</th>
<th>Tipo</th>
<th>FQDN</th>
<th>FQDN de destino</th>
<th>Puerto</th>
<th>Asignado a/Comentarios</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DNS interno</p></td>
<td><p>SRV</p></td>
<td><p>_sipinternaltls._tcp.contoso.com</p></td>
<td><p>pool01.contoso.com</p></td>
<td><p>5061</p></td>
<td><p>Requerido para que la configuración automática de clientes de Lync 2013 funcione internamente</p></td>
</tr>
<tr class="even">
<td><p>DNS interno</p></td>
<td><p>SRV</p></td>
<td><p>_sipinternaltls._tcp.fabrikam.com</p></td>
<td><p>pool01.fabrikam.com</p></td>
<td><p>5061</p></td>
<td><p>Requerido para que la configuración automática de clientes de Lync 2013 funcione internamente</p></td>
</tr>
<tr class="odd">
<td><p>DNS interno</p></td>
<td><p>SRV</p></td>
<td><p>_ntp._udp.contoso.com</p></td>
<td><p>dc01.contoso.com</p></td>
<td><p>123</p></td>
<td><p>Origen del NTP (Network Time Protocol) requerido para los dispositivos que ejecuten Lync Phone Edition. Internamente, esto deberá apuntar al controlador de dominio. Si el controlador de dominio no se ha definido, intentará usar el servidor NTP time.windows.com</p></td>
</tr>
</tbody>
</table>

