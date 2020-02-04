---
title: 'Lync Server 2013: Requisitos de certificado para Servidores internos'
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
ms.openlocfilehash: 0351ab4f54273e1eccc09992ab933525cc2527ae
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736795"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-requirements-for-internal-servers-in-lync-server-2013"></a>Requisitos de certificado para Servidores internos en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2017-02-17_

Los servidores internos que ejecutan Lync Server y que requieren certificados incluyen el servidor Standard Edition, el servidor front-end Enterprise Edition, el servidor de mediación y el director. En la tabla siguiente se muestran los requisitos de certificados para estos servidores. Puede usar el Asistente para certificados de Lync Server para solicitar estos certificados.

<div>


> [!TIP]  
> Los certificados comodín son compatibles con los nombres alternativos de asunto asociados con las direcciones URL simples del grupo de servidores front-end, del servidor front-end o del director. Para obtener más información acerca de la compatibilidad con certificados comodín, consulte <A href="lync-server-2013-wildcard-certificate-support.md">compatibilidad de certificados comodín en Lync Server 2013</A>.



</div>

Aunque se recomienda una entidad de certificación (CA) interna de empresa para los servidores internos, también puede usar una CA pública. Para obtener una lista de las entidades emisoras de certificados públicas que proporcionan certificados que cumplen con los requisitos específicos para certificados de comunicaciones unificadas (UC) y que se han asociado con Microsoft para garantizar que funcionan con el Asistente para certificados de Lync Server, consulte el artículo 929395 de Microsoft Knowledge base, " [https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834)asociados de certificados de comunicaciones unificadas para Exchange Server y Communications Server" en.

La comunicación con otras aplicaciones y servidores, como Exchange 2013, requiere un certificado que sea compatible con otras aplicaciones y productos. Para la versión 2013, Lync Server 2013 y otros productos de Microsoft Server, incluidos Exchange 2013 y SharePoint Server, admiten el protocolo de autorización abierta (OAuth) para la autenticación y la autorización de servidor a servidor. Para obtener más información, vea [administrar la autenticación de servidor a servidor (OAuth) y las aplicaciones de socios en Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) en la documentación de implementación o en la documentación de operaciones.

Para las conexiones de clientes que ejecutan el sistema operativo Windows 7, el sistema operativo Windows Server 2008, el sistema operativo Windows Server 2008 R2, el sistema operativo Windows Vista y Microsoft Lync Phone Edition, Lync Server 2013 incluye compatibilidad con (pero no requerir) certificados firmados con la función de hash criptográfica SHA-256. Para admitir el acceso externo mediante SHA-256, un certificado externo es emitido por una entidad de certificación pública con SHA-256.

En las tablas siguientes se muestran los requisitos de los certificados por función del servidor para los servidores front-end y los servidores Standard Edition. Todos son certificados de servidor web estándar, clave privada, no exportable.

Tenga en cuenta que el uso mejorado de clave (EKU) del servidor se configura automáticamente cuando usa el Asistente para certificados para solicitar certificados.

<div>


> [!NOTE]  
> Cada nombre descriptivo de certificado debe ser único en el almacén de equipos.



</div>

<div>


> [!NOTE]  
> Si ha configurado sipinternal.contoso.com o sipexternal.contoso.com en su DNS, tendrá que agregarlos en el nombre alternativo de asunto del certificado.



</div>

### <a name="certificates-for-standard-edition-server"></a>Certificados para un servidor Standard Edition

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
<th>Nombre del asunto/nombre común</th>
<th>Nombre alternativo de sujeto</th>
<th>Ejemplo</th>
<th>Comentarios</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Predeterminado</p></td>
<td><p>Nombre de dominio completo (FQDN) del grupo</p></td>
<td><p>FQDN del grupo y el FQDN del servidor</p>
<p>Si hay varios dominios SIP y está habilitada la configuración automática de los clientes, el Asistente para certificados detectará y agregará los FQDN de todos los dominios SIP admitidos.</p>
<p>Si este grupo de servidores es el servidor de inicio automático de sesión de los clientes y se requiere una correspondencia exacta del sistema de nombres de dominio (DNS) en la directiva del grupo, necesitará también entradas para sip.sipdomain (para cada uno de los dominios SIP que tenga).</p></td>
<td><p>SN=se01.contoso.com; SAN=se01.contoso.com</p>
<p>Si este grupo de servidores es el servidor de inicio automático de sesión de los clientes y se requiere una correspondencia exacta de DNS en la directiva del grupo, necesitará también SAN=sip.contoso.com; SAN=sip.fabrikam.com</p></td>
<td><p>En el servidor Standard Edition, el FQDN del servidor es el mismo que el FQDN del grupo.</p>
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
<li><p>URL sencilla de administración</p></li>
<li><p>O bien, una entrada comodín para las direcciones URL simples</p></li>
</ul></td>
<td><p>SN=se01.contoso.com; SAN=se01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</p>
<p>Con un certificado de comodín:</p>
<p>SN=se01.contoso.com; SAN=se01.contoso.com; SAN=*.contoso.com</p></td>
<td><p>No puede invalidar el FQDN de la web interna en el generador de topología.</p>
<p>Si tiene varias direcciones URL simples, debe incluirlas como nombres alternativos de asunto.</p>
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
<li><p>O bien, una entrada comodín para las direcciones URL simples</p></li>
</ul></td>
<td><p>SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</p>
<p>Con un certificado de comodín:</p>
<p>SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=*.contoso.com</p></td>
<td><p>Si tiene varias direcciones URL simples, debe incluirlas como nombres alternativos de asunto.</p>
<p>Las entradas de comodín se admiten para las entradas de direcciones URL sencillas.</p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-front-end-server-in-a-front-end-pool"></a>Certificados para el servidor front-end en un grupo de servidores front-end

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
<th>Nombre del asunto/nombre común</th>
<th>Nombre alternativo de sujeto</th>
<th>Ejemplo</th>
<th>Comentarios</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Predeterminado</p></td>
<td><p>FQDN del grupo de servidores</p></td>
<td><p>FQDN del grupo y FQDN del servidor.</p>
<p>Si hay varios dominios SIP y está habilitada la configuración automática de los clientes, el Asistente para certificados detectará y agregará los FQDN de todos los dominios SIP admitidos.</p>
<p>Si este grupo es el servidor de inicio de sesión automático para clientes y se requiere coincidencia de DNS estricta en la Directiva de grupo, también necesitarás entradas para SIP. sipdomain (para cada dominio SIP que tengas).</p></td>
<td><p>SN=eepool.contoso.com; SAN=eepool.contoso.com; SAN=ee01.contoso.com </p>
<p>Si este grupo de servidores es el servidor de inicio automático de sesión de los clientes y se requiere una correspondencia exacta de DNS en la directiva del grupo, necesitará también SAN=sip.contoso.com; SAN=sip.fabrikam.com</p></td>
<td><p>El asistente detecta todos los dominios SIP especificados durante la instalación y los agrega automáticamente al nombre alternativo de sujeto.</p>
<p>También puede usar este certificado para la autenticación de servidor a servidor.</p></td>
</tr>
<tr class="even">
<td><p>Interno de la web</p></td>
<td><p>FQDN del grupo de servidores</p></td>
<td><p>Cada uno de los siguientes elementos:</p>
<ul>
<li><p>FQDN web interno (que NO es el mismo que el FQDN del servidor)</p></li>
<li><p>FQDN del servidor</p></li>
<li><p>FQDN del grupo de Lync</p></li>
<li><p>URL sencilla de reunión</p></li>
<li><p>URL sencilla de marcado</p></li>
<li><p>URL sencilla de administración</p></li>
<li><p>O bien, una entrada comodín para las direcciones URL simples</p></li>
</ul></td>
<td><p>SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</p>
<p>Con un certificado de comodín:</p>
<p>SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=*.contoso.com</p></td>
<td><p>Si tiene varias direcciones URL simples, debe incluirlas como nombres alternativos de asunto.</p>
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
<li><p>O bien, una entrada comodín para las direcciones URL simples</p></li>
</ul></td>
<td><p>SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</p>
<p>Con un certificado de comodín:</p>
<p>SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=*.contoso.com</p></td>
<td><p>Si tiene varias direcciones URL simples, debe incluirlas como nombres alternativos de asunto.</p>
<p>Las entradas de comodín se admiten para las entradas de direcciones URL sencillas.</p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-director"></a>Certificados para Director

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
<th>Nombre del asunto/nombre común</th>
<th>Nombre alternativo de sujeto</th>
<th>Ejemplo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Predeterminado</p></td>
<td><p>FQDN del grupo de directores</p></td>
<td><p>FQDN del Director, FQDN del grupo de directores</p>
<p>Si este grupo es el servidor de inicio de sesión automático para clientes y se requiere coincidencia de DNS estricta en la Directiva de grupo, también necesitarás entradas para SIP. sipdomain (para cada dominio SIP que tengas).</p></td>
<td><p>SN = dir-pool.contoso.com; SAN = dir-pool.contoso.com; SAN = dir01. contoso. com</p>
<p>Si este grupo de directores es el servidor de inicio de sesión automático para clientes y se requiere una coincidencia de DNS estricta en la Directiva de grupo, también necesita SAN = SIP. contoso. com; SAN = SIP. fabrikam. com</p></td>
</tr>
<tr class="even">
<td><p>Interno de la web</p></td>
<td><p>FQDN del servidor</p></td>
<td><p>Cada uno de los siguientes elementos:</p>
<ul>
<li><p>FQDN web interno (que es igual que el FQDN del servidor)</p></li>
<li><p>FQDN del servidor</p></li>
<li><p>FQDN del grupo de Lync</p></li>
<li><p>URL sencilla de reunión</p></li>
<li><p>URL sencilla de marcado</p></li>
<li><p>URL sencilla de administración</p></li>
<li><p>O bien, una entrada comodín para las direcciones URL simples</p></li>
</ul></td>
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
<li><p>O bien, una entrada comodín para las direcciones URL simples</p></li>
</ul></td>
<td><p>El FQDN de la web externa del Director debe ser diferente del de la aplicación front end o del servidor front-end.</p>
<p>SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</p>
<p>SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=*.contoso.com</p></td>
</tr>
</tbody>
</table>


Si tiene un grupo de servidores de mediación independiente, cada uno de los servidores de mediación de cada uno necesita los certificados enumerados en la tabla siguiente. Si Collocate el servidor de mediación con los servidores front-end, los certificados que figuran en la tabla "certificados para el servidor front-end en la agrupación front end" anteriormente en este tema son suficientes.

### <a name="certificates-for-stand-alone-mediation-server"></a>Certificados para el servidor de mediación independiente

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
<th>Nombre del asunto/nombre común</th>
<th>Nombre alternativo de sujeto</th>
<th>Ejemplo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Predeterminado</p></td>
<td><p>FQDN del grupo de servidores</p></td>
<td><p>FQDN del grupo de servidores</p>
<p>FQDN del servidor miembro del grupo</p></td>
<td><p>SN=medsvr-pool.contoso.net; SAN=medsvr-pool.contoso.net; SAN=medsvr01.contoso.net</p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-survivable-branch-appliance"></a>Certificados para la aplicación de rama superviviente

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
<th>Nombre del asunto/nombre común</th>
<th>Nombre alternativo de sujeto</th>
<th>Ejemplo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Predeterminado</p></td>
<td><p>FQDN de la aplicación</p></td>
<td><p>SIP. &lt;sipdomain&gt; (necesita una entrada por cada dominio SIP)</p></td>
<td><p>SN=sba01.contoso.net; SAN=sip.contoso.com; SAN=sip.fabrikam.com</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a>Vea también


[Compatibilidad de certificado de comodín en Lync Server 2013](lync-server-2013-wildcard-certificate-support.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

