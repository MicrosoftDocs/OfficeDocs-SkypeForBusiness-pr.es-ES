---
title: 'Lync Server 2013: requisitos de certificado para servidores internos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate requirements for internal servers
ms:assetid: 0444cdbd-538c-43b1-b9a1-9d7d6cf818d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398094(v=OCS.15)
ms:contentKeyID: 48183270
ms.date: 02/17/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 38bd350a4b552d63b635f8ec5a25ed7803de4b55
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187573"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="certificate-requirements-for-internal-servers-in-lync-server-2013"></a>Requisitos de certificado para servidores internos en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2017-02-17_

Los servidores internos que ejecutan Lync Server y que requieren certificados incluyen el servidor Standard Edition, el servidor front-end Enterprise Edition, el servidor de mediación y el director. En la siguiente tabla se muestran los requisitos de certificado para estos servidores. Puede usar el Asistente para certificados de Lync Server para solicitar estos certificados.

<div>


> [!TIP]  
> Los certificados comodín son compatibles con los nombres alternativos de sujeto asociados con las direcciones URL simples en el grupo de servidores front-end, el servidor front-end o el director. Para obtener más información sobre la compatibilidad con certificados comodín, consulte <A href="lync-server-2013-wildcard-certificate-support.md">compatibilidad con certificados comodín en Lync Server 2013</A>.



</div>

Aunque para los servidores internos se recomienda una entidad de certificación (CA) empresarial interna, también puede usar una pública. Para obtener una lista de las entidades de certificación públicas que proporcionan certificados que cumplen los requisitos específicos para los certificados de comunicaciones unificadas (UC) y que se han asociado con Microsoft para garantizar que funcionan con el Asistente para certificados de Lync Server, vea el artículo 929395 de Microsoft Knowledge base, "asociados de [https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834)certificados de comunicaciones unificadas para Exchange Server y para Communications Server" en.

La comunicación con otras aplicaciones y servidores, como Exchange 2013, requiere un certificado que sea compatible con las demás aplicaciones y productos. Para la versión 2013, Lync Server 2013 y otros productos de servidor de Microsoft, incluidos Exchange 2013 y SharePoint Server, admiten el protocolo Open Authorization (OAuth) para la autenticación y autorización de servidor a servidor. Para obtener más información, consulte [Managing Server-to-Server Authentication (OAuth) and Partner Applications in Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) en la documentación sobre implementación o sobre operaciones.

Para las conexiones de clientes que ejecutan el sistema operativo Windows 7, el sistema operativo Windows Server 2008, el sistema operativo Windows Server 2008 R2, el sistema operativo Windows Vista y Microsoft Lync Phone Edition, Lync Server 2013 incluye soporte para (pero no require) certificados firmados con la función de hash criptográfica SHA-256. Para permitir el acceso externo mediante SHA-256, el certificado externo lo emite una CA pública que usa SHA-256.

En las tablas siguientes, se muestran los requisitos de certificado por rol de servidor para los grupos de servidores front-end y los servidores Standard Edition. Todos ellos son certificados de servidor web estándar, con clave privada y no exportables.

Tenga en cuenta que el uso mejorado de clave (EKU) del servidor se configura automáticamente al usar el asistente para certificados para solicitar certificados.

<div>


> [!NOTE]  
> Cada nombre descriptivo del certificado debe ser único en el almacén del equipo.



</div>

<div>


> [!NOTE]  
> Si ha configurado sipinternal.contoso.com o sipexternal.contoso.com en su DNS, tendrá que agregarlos en el nombre alternativo de sujeto del certificado.



</div>

### <a name="certificates-for-standard-edition-server"></a>Certificados para el servidor Standard Edition

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
<th>Nombre de sujeto/nombre común</th>
<th>Nombre alternativo de sujeto</th>
<th>Ejemplo</th>
<th>Comentarios</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Valor predeterminado</p></td>
<td><p>Nombre de dominio completo (FQDN) del grupo de servidores</p></td>
<td><p>FQDN del grupo de servidores y el FQDN del servidor</p>
<p>Si hay varios dominios SIP y está habilitada la configuración automática de los clientes, el Asistente para certificados detectará y agregará los FQDN de todos los dominios SIP admitidos.</p>
<p>Si este grupo de servidores es el servidor de inicio automático de sesión de los clientes y se requiere una correspondencia exacta del sistema de nombres de dominio (DNS) en la directiva del grupo, necesitará también entradas para sip.sipdomain (para cada uno de los dominios SIP que tenga).</p></td>
<td><p>SN = SE01. contoso. com; SAN = SE01. contoso. com</p>
<p>Si este grupo de servidores es el servidor de inicio automático de sesión de los clientes y se necesita una correspondencia exacta de DNS en la directiva del grupo, necesitará también SAN=sip.contoso.com; SAN=sip.fabrikam.com</p></td>
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
<li><p>URL sencillas de reunión</p></li>
<li><p>URL sencilla de marcado</p></li>
<li><p>URL sencilla de administración</p></li>
<li><p>O una entrada de comodín para las direcciones URL sencillas</p></li>
</ul></td>
<td><p>SN = SE01. contoso. com; SAN = SE01. contoso. com; SAN = cumplir. contoso. com; SAN = cumplir. fabrikam. com; SAN = marcado. contoso. com; SAN = admin. contoso. com</p>
<p>Con un certificado de comodín:</p>
<p>SN = SE01. contoso. com; SAN = SE01. contoso. com; SAN = *. contoso. com</p></td>
<td><p>No puede invalidar el FQDN de la web interna en el generador de topologías.</p>
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
<li><p>Cumplir direcciones URL sencillas por dominio SIP</p></li>
<li><p>O una entrada con comodín para las direcciones URL simples</p></li>
</ul></td>
<td><p>SN = SE01. contoso. com; SAN = webcon01. contoso. com; SAN = cumplir. contoso. com; SAN = cumplir. fabrikam. com; SAN = marcado. contoso. com</p>
<p>Con un certificado de comodín:</p>
<p>SN = SE01. contoso. com; SAN = webcon01. contoso. com; SAN = *. contoso. com</p></td>
<td><p>Si dispone de varias URL simples de reunión, deberá incluirlas todas como nombres alternativos de sujeto.</p>
<p>Las entradas de comodín se admiten para las entradas de direcciones URL sencillas.</p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-front-end-server-in-a-front-end-pool"></a>Certificados para un servidor front-end en un grupo de servidores front-end

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
<th>Nombre de sujeto/nombre común</th>
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
<p>Si este grupo de servidores es el servidor de inicio automático de sesión de los clientes y se necesita una correspondencia exacta de DNS en la directiva del grupo, necesitará también entradas para sip.sipdomain (para cada uno de los dominios SIP que tenga).</p></td>
<td><p>SN = eepool. contoso. com; SAN = eepool. contoso. com; SAN = ee01. contoso. com</p>
<p>Si este grupo de servidores es el servidor de inicio automático de sesión de los clientes y se necesita una correspondencia exacta de DNS en la directiva del grupo, necesitará también SAN=sip.contoso.com; SAN=sip.fabrikam.com</p></td>
<td><p>El asistente detecta todos los dominios SIP especificados durante la instalación y los agrega automáticamente al nombre alternativo de sujeto.</p>
<p>También puede usar este certificado para la autenticación de servidor a servidor.</p></td>
</tr>
<tr class="even">
<td><p>Web interno</p></td>
<td><p>FQDN del grupo de servidores</p></td>
<td><p>Cada uno de los siguientes elementos:</p>
<ul>
<li><p>FQDN Web interno (que no es el mismo que el FQDN del servidor)</p></li>
<li><p>FQDN del servidor</p></li>
<li><p>FQDN del grupo de Lync</p></li>
<li><p>URL sencillas de reunión</p></li>
<li><p>URL sencilla de marcado</p></li>
<li><p>URL sencilla de administración</p></li>
<li><p>O una entrada de comodín para las direcciones URL sencillas</p></li>
</ul></td>
<td><p>SN = ee01. contoso. com; SAN = ee01. contoso. com; SAN = cumplir. contoso. com; SAN = cumplir. fabrikam. com; SAN = marcado. contoso. com; SAN = admin. contoso. com</p>
<p>Con un certificado de comodín:</p>
<p>SN = ee01. contoso. com; SAN = ee01. contoso. com; SAN = *. contoso. com</p></td>
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
<td><p>SN = ee01. contoso. com; SAN = webcon01. contoso. com; SAN = cumplir. contoso. com; SAN = cumplir. fabrikam. com; SAN = marcado. contoso. com</p>
<p>Con un certificado de comodín:</p>
<p>SN = ee01. contoso. com; SAN = webcon01. contoso. com; SAN = *. contoso. com</p></td>
<td><p>Si dispone de varias URL simples de reunión, deberá incluirlas todas como nombres alternativos de sujeto.</p>
<p>Las entradas de comodín se admiten para las entradas de direcciones URL sencillas.</p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-director"></a>Certificados para el director

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
<th>Nombre de sujeto/nombre común</th>
<th>Nombre alternativo de sujeto</th>
<th>Ejemplo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Valor predeterminado</p></td>
<td><p>FQDN del grupo de servidores del director</p></td>
<td><p>FQDN del director, FQDN del grupo de servidores del director</p>
<p>Si este grupo de servidores es el servidor de inicio automático de sesión de los clientes y se necesita una correspondencia exacta de DNS en la directiva del grupo, necesitará también entradas para sip.sipdomain (para cada uno de los dominios SIP que tenga).</p></td>
<td><p>SN = dir-pool.contoso.com; SAN = dir-pool.contoso.com; SAN = dir01. contoso. com</p>
<p>Si este grupo de servidores del director es el servidor de inicio automático de sesión de los clientes y se necesita una correspondencia exacta de DNS en la directiva del grupo, necesitará también SAN=sip.contoso.com; SAN=sip.fabrikam.com</p></td>
</tr>
<tr class="even">
<td><p>Web interno</p></td>
<td><p>FQDN del servidor</p></td>
<td><p>Cada uno de los siguientes elementos:</p>
<ul>
<li><p>FQDN web interno (que es igual que el FQDN del servidor)</p></li>
<li><p>FQDN del servidor</p></li>
<li><p>FQDN del grupo de Lync</p></li>
<li><p>URL sencillas de reunión</p></li>
<li><p>URL sencilla de marcado</p></li>
<li><p>URL sencilla de administración</p></li>
<li><p>O una entrada de comodín para las direcciones URL sencillas</p></li>
</ul></td>
<td><p>SN = dir01. contoso. com; SAN = dir01. contoso. com; SAN = cumplir. contoso. com; SAN = cumplir. fabrikam. com; SAN = marcado. contoso. com; SAN = admin. contoso. com</p>
<p>SN = dir01. contoso. com; SAN = dir01. contoso. com SAN = *. contoso. com</p></td>
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
<td><p>El FQDN Web externo del Director debe ser diferente del grupo de servidores front-end o del servidor front-end.</p>
<p>SN = dir01. contoso. com; SAN = directorwebcon01. contoso. com SAN = meet. contoso. com; SAN = cumplir. fabrikam. com; SAN = marcado. contoso. com</p>
<p>SN = dir01. contoso. com; SAN = directorwebcon01. contoso. com SAN = *. contoso. com</p></td>
</tr>
</tbody>
</table>


Si tiene un grupo de servidores de mediación independientes, cada uno de los servidores de mediación que incluya necesitará los certificados listados en la siguiente tabla. Si combina el servidor de mediación con los servidores front-end, bastará con los certificados enumerados anteriormente en la tabla "Certificados para un servidor front-end en un grupo de servidores front-end" de este tema.

### <a name="certificates-for-stand-alone-mediation-server"></a>Certificados para un servidor de mediación independiente

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
<th>Nombre de sujeto/nombre común</th>
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
<td><p>SN = medsvr-pool.contoso.net; SAN = medsvr-pool.contoso.net; SAN = medsvr01. contoso. net</p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-survivable-branch-appliance"></a>Certificados para una aplicación de sucursal con funciones de supervivencia

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
<th>Nombre de sujeto/nombre común</th>
<th>Nombre alternativo de sujeto</th>
<th>Ejemplo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Valor predeterminado</p></td>
<td><p>FQDN de la aplicación</p></td>
<td><p>SIP. &lt;sipdomain&gt; (necesita una entrada por dominio SIP)</p></td>
<td><p>SN = sba01. contoso. net; SAN = SIP. contoso. com; SAN = SIP. fabrikam. com</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a>Consulta también


[Compatibilidad con certificados comodín en Lync Server 2013](lync-server-2013-wildcard-certificate-support.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

