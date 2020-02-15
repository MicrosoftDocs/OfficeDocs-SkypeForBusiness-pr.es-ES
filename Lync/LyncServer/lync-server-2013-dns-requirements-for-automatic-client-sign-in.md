---
title: 'Lync Server 2013: requisitos de DNS para el inicio de sesión automático de los clientes'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for automatic client sign-in
ms:assetid: 3bcd4bb3-a022-4ffa-b005-1a95ad2b1796
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425884(v=OCS.15)
ms:contentKeyID: 48183873
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b022d9780d1498f70fd5918894a1412996731004
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42031244"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-automatic-client-sign-in-in-lync-server-2013"></a>Requisitos de DNS para el inicio de sesión automático de los clientes en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-06-19_

En esta sección se describen los registros del sistema de nombres de dominio (DNS) necesarios para el inicio de sesión automático de clientes. Cuando se implementan servidores Standard Edition o grupos de servidores front-end, se pueden configurar los clientes para que usen la detección automática para iniciar sesión en el servidor Standard Edition o el grupo de servidores front-end adecuado. Si va a requerir que los clientes se conecten de forma manual a Lync Server 2013, puede omitir este tema.

Para admitir el inicio de sesión automático de los clientes, debe:

  - Designar un único servidor o grupo de servidores para distribuir y autenticar las solicitudes de inicio de sesión de los clientes. Puede ser uno de los servidores o grupos de servidores existentes en la organización que hospede usuarios, o bien, puede designar un servidor o grupo de servidores dedicado para este fin que no hospede usuarios. Para lograr una alta disponibilidad, se recomienda designar un grupo de servidores front-end para esta función.

  - Crear un registro DNS SRV interno para admitir el inicio automático de sesión de clientes para este servidor o grupo de servidores.
    
    <div>
    

    > [!NOTE]  
    > En los siguientes requisitos de registro, el dominio SIP hace referencia a la parte correspondiente al host de los URI de SIP asignados a los usuarios. Por ejemplo, si los URI de SIP tienen el formato *@contoso.com, contoso.com es el dominio SIP. El dominio SIP suele ser distinto del dominio de Active Directory interno. Una organización también puede admitir varios dominios SIP.

    
    </div>

Para habilitar la configuración automática de los clientes, debe crear un registro SRV de DNS interno que asigne uno de los siguientes registros al nombre de dominio completo (FQDN) del grupo de servidores front-end o del servidor Standard Edition que distribuye las solicitudes de inicio de sesión de Lync. equipos

  - \_sipinternaltls. \_TCP. \<domain\> -para conexiones TLS internas

Solo tiene que crear un único registro SRV para el servidor Standard Edition o el grupo de servidores front-end que distribuirá las solicitudes de inicio de sesión.

En la tabla siguiente se muestran algunos registros de ejemplo que se requieren para la compañía ficticia Contoso, que admite los dominios SIP contoso.com y retail.contoso.com.

### <a name="example-of-dns-records-required-for-automatic-client-sign-in-with-multiple-sip-domains"></a>Ejemplo de registros DNS necesarios para el inicio de sesión automático de los clientes con varios dominios SIP

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>FQDN del grupo de servidores front-end utilizado para distribuir las solicitudes de inicio de sesión</th>
<th>Dominio SIP</th>
<th>Registro DNS SRV</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>pool01.contoso.com</p></td>
<td><p>contoso.com</p></td>
<td><p>Registro SRV para el dominio _sipinternaltls._tcp.contoso.com sobre el puerto 5061 que se asigna a pool01.contoso.com</p></td>
</tr>
<tr class="even">
<td><p>pool01.contoso.com</p></td>
<td><p>retail.contoso.com</p></td>
<td><p>Registro SRV para el dominio _sipinternaltls._tcp.retail.contoso.com sobre el puerto 5061 que se asigna a pool01.contoso.com</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> De forma predeterminada, las consultas de los registros DNS observan estrictamente la coincidencia de los nombres de dominio entre el dominio del nombre de usuario y el registro SRV. Si prefiere que las consultas DNS de los clientes usen la coincidencia de sufijos, puede configurar la directiva de grupo DisableStrictDNSNaming. Para obtener más información, consulte <A href="lync-server-2013-planning-for-clients-and-devices.md">Planning for clients and Devices in Lync Server 2013</A> en la documentación referente a la planeación.



</div>

<div>

## <a name="example-of-the-certificates-and-dns-records-required-for-automatic-client-sign-in"></a>Ejemplo de los certificados y registros DNS requeridos para el inicio de sesión automático de los clientes

En este ejemplo se utilizan los mismos nombres de ejemplo de la tabla anterior. La organización Contoso admite los dominios SIP de contoso.com y retail.contoso.com, y todos sus usuarios tienen un URI de SIP con uno de los formatos siguientes:

  - \<@retail\>de usuario. contoso.com

  - \<@contoso\>de usuario. com

</div>

</div>

<span> </span>

</div>

</div>

</div>

