---
title: 'Lync Server 2013: Requisitos de certificado para Servidores internos'
TOCTitle: Requisitos de certificado para Servidores internos
ms:assetid: 0444cdbd-538c-43b1-b9a1-9d7d6cf818d6
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398094(v=OCS.15)
ms:contentKeyID: 48274282
ms.date: 02/18/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Requisitos de certificado para Servidores internos en Lync Server 2013

 

_**Última modificación del tema:** 2017-02-17_

Los servidores internos que ejecutan Lync Server y que requieren certificados incluyen un servidor Standard Edition, un servidor front-end Enterprise Edition, un servidor de mediación y un director. En la siguiente tabla se muestran los requisitos de certificado para estos servidores. Puede usar el asistente para certificados de Lync Server para solicitar dichos certificados.

> [!TIP]  
> Se admiten los certificados de comodín para los nombres alternativos de sujeto asociados a las direcciones URL simples en Grupo de servidores front-end, Servidor front-end o director. Para obtener información sobre el soporte técnico de certificados de comodín, consulte <a href="lync-server-2013-wildcard-certificate-support.md">Compatibilidad de certificado de comodín en Lync Server 2013</a>.



Aunque para los servidores internos se recomienda una entidad de certificación (CA) empresarial interna, también puede usar una pública. Para obtener una lista de entidades de certificación públicas que proporcionan certificados que cumplen los requisitos específicos para los certificados de comunicaciones unificadas (UC) y que están asociadas con Microsoft para asegurar que funcionan con el Asistente para certificados de Lync Server, consulte el artículo 929395 de Microsoft Knowledge Base, "Socios de certificado de comunicaciones unificadas de Exchange Server y para Communications Server", en [http://go.microsoft.com/fwlink/?linkid=202834\&clcid=0xC0A](http://go.microsoft.com/fwlink/?linkid=202834%26clcid=0xc0a).

La comunicación con el resto de aplicaciones y servidores como, por ejemplo, Exchange 2013, requiere el uso de un certificado compatible con las otras aplicaciones y productos. Para la versión de 2013, Lync Server 2013 y el resto de productos de servidor de Microsoft, incluidos Exchange 2013 y SharePoint Server, admiten el protocolo Open Authorization (OAuth) para la autorización y la autenticación de servidor a servidor. Para obtener más detalles, vea [Administración de la autenticación servidor a servidor (Oauth) y las aplicaciones de socio en Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) en la documentación sobre implementación o sobre operaciones.

Para conexiones desde clientes que ejecuten Sistema operativo Windows 7, Sistema operativo Windows Server 2008, Sistema operativo Windows Server 2008 R2, Sistema operativo Windows Vista y Microsoft Lync Phone Edition, Lync Server 2013 incluye compatibilidad con certificados firmados (aunque no los requiere de forma obligatoria) mediante la función de hash de cifrado SHA-256. Para permitir el acceso externo mediante SHA-256, el certificado externo lo emite una entidad de certificación pública que usa SHA-256.

En las tablas siguientes, se muestran los requisitos de certificado por rol de servidor para los grupos de servidores front-end y los servidores Standard Edition. Todos ellos son certificados de servidor web estándar, con clave privada y no exportables.

Tenga en cuenta que el uso mejorado de clave (EKU) del servidor se configura automáticamente al usar el asistente para certificados para solicitar certificados.


> [!NOTE]
> El nombre descriptivo de cada certificado debe ser único en el almacén del equipo.




> [!NOTE]
> Si ha configurado sipinternal.contoso.com o sipexternal.contoso.com en su DNS, tendrá que agregarlos al Nombre alternativo de sujeto de los certificados.



### Certificados para el servidor Standard Edition

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>Certificado</th>
<th>Nombre de sujeto/ Nombre común</th>
<th>Nombre alternativo de sujeto</th>
<th>Ejemplo</th>
<th>Comentarios</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Valor predeterminado</p></td>
<td><p>Nombre de dominio completo (FQDN) del grupo de servidores</p></td>
<td><p>FQDN del grupo de servidores y FQDN del servidor</p>
<p>Si hay varios dominios SIP y está habilitada la configuración automática de los clientes, el Asistente para certificados detectará y agregará los FQDN de todos los dominios SIP admitidos.</p>
<p>Si este grupo de servidores es el servidor de inicio automático de sesión de los clientes y se requiere una correspondencia exacta del sistema de nombres de dominio (DNS) en la directiva del grupo, necesitará también entradas para sip.sipdomain (para cada uno de los dominios SIP que tenga).</p></td>
<td><p>SN=se01.contoso.com; SAN=se01.contoso.com</p>
<p>Si este grupo de servidores es el servidor de inicio automático de sesión de los clientes y se requiere una correspondencia exacta de DNS en la directiva del grupo, necesitará también SAN=sip.contoso.com; SAN=sip.fabrikam.com</p></td>
<td><p>En el servidor Standard Edition, el FQDN del servidor es igual que el FQDN del grupo de servidores.</p>
<p>El asistente detecta todos los dominios SIP especificados durante la instalación y los agrega automáticamente al nombre alternativo de sujeto.</p>
<p>También puede usar este certificado para la autenticación de servidor a servidor.</p></td>
</tr>
<tr class="even">
<td><p>Web interno</p></td>
<td><p>FQDN del servidor</p></td>
<td><p>Cada uno de los siguientes elementos:</p>
<ul>
<li><p>FQDN web interno (que es igual que el FQDN del servidor)</p></li>
<li><p>URL sencilla de reunión</p></li>
<li><p>URL sencilla de marcado</p></li>
<li><p>URL sencilla de administración</p>
<p></p></li>
<li><p>O una entrada de comodín para las direcciones URL sencillas</p></li>
</ul>
<p></p></td>
<td><p>SN=se01.contoso.com; SAN=se01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</p>
<p>Con un certificado de comodín:</p>
<p>SN=se01.contoso.com; SAN=se01.contoso.com; SAN=*.contoso.com</p></td>
<td><p>El FQDN web interno del Generador de topologías no puede invalidarse.</p>
<p>Si dispone de varias URL simples de reunión, deberá incluirlas todas como nombres alternativos de sujeto.</p>
<p>Las entradas de comodín se admiten para las entradas de direcciones URL sencillas.</p></td>
</tr>
<tr class="odd">
<td><p>Web externo</p></td>
<td><p>FQDN del servidor</p></td>
<td><p>Cada uno de los siguientes elementos:</p>
<ul>
<li><p>FQDN web externo</p></li>
<li><p>URL sencilla de marcado</p></li>
<li><p>Direcciones URL sencillas de reunión por dominio SIP</p></li>
<li><p>O una entrada de comodín para las direcciones URL sencillas</p></li>
</ul></td>
<td><p>SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</p>
<p>Con un certificado de comodín:</p>
<p>SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=*.contoso.com</p></td>
<td><p>Si dispone de varias URL simples de reunión, deberá incluirlas todas como nombres alternativos de sujeto.</p>
<p>Las entradas de comodín se admiten para las entradas de direcciones URL sencillas.</p></td>
</tr>
</tbody>
</table>


### Certificados para un servidor front-end en un grupo de servidores front-end

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>Certificado</th>
<th>Nombre de sujeto/ Nombre común</th>
<th>Nombre alternativo de sujeto</th>
<th>Ejemplo</th>
<th>Comentarios</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Valor predeterminado</p></td>
<td><p>FQDN del grupo de servidores</p></td>
<td><p>FQDN del grupo de servidores y FQDN del servidor.</p>
<p>Si hay varios dominios SIP y está habilitada la configuración automática de los clientes, el Asistente para certificados detectará y agregará los FQDN de todos los dominios SIP admitidos.</p>
<p>Si este grupo de servidores es el servidor de inicio automático de sesión de los clientes y se requiere una correspondencia exacta de DNS en la directiva del grupo, necesitará también entradas para sip.sipdomain (para cada uno de los dominios SIP que tenga).</p></td>
<td><p>SN=eepool.contoso.com; SAN=eepool.contoso.com; SAN=ee01.contoso.com</p>
<p>Si este grupo de servidores es el servidor de inicio automático de sesión de los clientes y se requiere una correspondencia exacta de DNS en la directiva del grupo, necesitará también SAN=sip.contoso.com; SAN=sip.fabrikam.com</p></td>
<td><p>El asistente detecta todos los dominios SIP especificados durante la instalación y los agrega automáticamente al nombre alternativo de sujeto.</p>
<p>También puede usar este certificado para la autenticación de servidor a servidor.</p></td>
</tr>
<tr class="even">
<td><p>Web interno</p></td>
<td><p>FQDN del grupo de servidores</p></td>
<td><p>Cada uno de los siguientes elementos:</p>
<ul>
<li><p>FQDN web interno (que NO es el mismo que el FQDN del servidor)</p></li>
<li><p>FQDN del servidor</p></li>
<li><p>FQDN del grupo de servidores de Lync</p></li>
<li><p>URL sencilla de reunión</p></li>
<li><p>URL sencilla de marcado</p></li>
<li><p>URL sencilla de administración</p></li>
<li><p>O una entrada de comodín para las direcciones URL sencillas</p></li>
</ul>
<p></p></td>
<td><p>SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</p>
<p>Con un certificado de comodín:</p>
<p>SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=*.contoso.com</p></td>
<td><p>Si dispone de varias URL simples de reunión, deberá incluirlas todas como nombres alternativos de sujeto.</p>
<p>Las entradas de comodín se admiten para las entradas de direcciones URL sencillas.</p></td>
</tr>
<tr class="odd">
<td><p>Web externo</p></td>
<td><p>FQDN del grupo de servidores</p></td>
<td><p>Cada uno de los siguientes elementos:</p>
<ul>
<li><p>FQDN web externo</p></li>
<li><p>URL sencilla de marcado</p></li>
<li><p>URL sencilla de administración</p></li>
<li><p>O una entrada de comodín para las direcciones URL sencillas</p></li>
</ul></td>
<td><p>SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</p>
<p>Con un certificado de comodín:</p>
<p>SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=*.contoso.com</p></td>
<td><p>Si dispone de varias URL simples de reunión, deberá incluirlas todas como nombres alternativos de sujeto.</p>
<p>Las entradas de comodín se admiten para las entradas de direcciones URL sencillas.</p></td>
</tr>
</tbody>
</table>


### Certificados para el director

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Certificado</th>
<th>Nombre de sujeto/ Nombre común</th>
<th>Nombre alternativo de sujeto</th>
<th>Ejemplo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Valor predeterminado</p></td>
<td><p>FQDN del grupo de servidores del director</p></td>
<td><p>FQDN del director, FQDN del grupo de servidores del director</p>
<p>Si este grupo de servidores es el servidor de inicio automático de sesión de los clientes y se requiere una correspondencia exacta de DNS en la directiva del grupo, necesitará también entradas para sip.sipdomain (para cada uno de los dominios SIP que tenga).</p></td>
<td><p>SN=dir-pool.contoso.com; SAN=dir-pool.contoso.com; SAN=dir01.contoso.com</p>
<p>Si este grupo de servidores del director es el servidor de inicio automático de sesión de los clientes y se requiere una correspondencia exacta de DNS en la directiva del grupo, necesitará también SAN=sip.contoso.com; SAN=sip.fabrikam.com</p></td>
</tr>
<tr class="even">
<td><p>Web interno</p></td>
<td><p>FQDN del servidor</p></td>
<td><p>Cada uno de los siguientes elementos:</p>
<ul>
<li><p>FQDN web interno (que es igual que el FQDN del servidor)</p></li>
<li><p>URL sencilla de reunión</p></li>
<li><p>URL sencilla de marcado</p></li>
<li><p>URL sencilla de administración</p></li>
<li><p>O una entrada de comodín para las direcciones URL sencillas</p></li>
</ul>
<p></p></td>
<td><p>SN=dir01.contoso.com; SAN=dir01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</p>
<p>SN=dir01.contoso.com; SAN=dir01.contoso.com SAN=*.contoso.com</p></td>
</tr>
<tr class="odd">
<td><p>Web externo</p></td>
<td><p>FQDN del servidor</p></td>
<td><p>Cada uno de los siguientes elementos:</p>
<ul>
<li><p>FQDN web externo</p></li>
<li><p>URL sencilla de marcado</p></li>
<li><p>URL sencilla de administración</p></li>
<li><p>O una entrada de comodín para las direcciones URL sencillas</p></li>
</ul></td>
<td><p>El FQDN web externo de director debe ser diferente a Grupo de servidores front-end o Servidor front-end.</p>
<p>SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</p>
<p>SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=*.contoso.com</p></td>
</tr>
</tbody>
</table>


Si tiene un grupo de servidores de mediación independientes, cada uno de los servidores de mediación que incluya necesitará los certificados listados en la siguiente tabla. Si combina el servidor de mediación con los servidores front-end, bastará con los certificados enumerados anteriormente en la tabla "Certificados para un servidor front-end en un grupo de servidores front-end" de este tema.

### Certificados para un servidor de mediación independiente

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Certificado</th>
<th>Nombre de sujeto/ Nombre común</th>
<th>Nombre alternativo de sujeto</th>
<th>Ejemplo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Valor predeterminado</p></td>
<td><p>FQDN del grupo de servidores</p></td>
<td><p>FQDN del grupo de servidores</p>
<p>FQDN del servidor miembro del grupo</p></td>
<td><p>SN=medsvr-pool.contoso.net; SAN=medsvr-pool.contoso.net; SAN=medsvr01.contoso.net</p></td>
</tr>
</tbody>
</table>


### Certificados para una aplicación de sucursal con funciones de supervivencia

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Certificado</th>
<th>Nombre de sujeto/ Nombre común</th>
<th>Nombre alternativo de sujeto</th>
<th>Ejemplo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Valor predeterminado</p></td>
<td><p>FQDN de la aplicación</p></td>
<td><p>SIP.&lt;sipdomain&gt; (requiere una entrada por dominio SIP)</p></td>
<td><p>SN=sba01.contoso.net; SAN=sip.contoso.com; SAN=sip.fabrikam.com</p></td>
</tr>
</tbody>
</table>


## Vea también

#### Conceptos

[Compatibilidad de certificado de comodín en Lync Server 2013](lync-server-2013-wildcard-certificate-support.md)

