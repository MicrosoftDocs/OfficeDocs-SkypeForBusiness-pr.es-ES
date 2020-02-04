---
title: 'Lync Server 2013: requisitos de DNS para el inicio de sesión automático de cliente'
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
ms.openlocfilehash: 6d033621382587367630d9119c2176e976cb2c2d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739160"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-automatic-client-sign-in-in-lync-server-2013"></a>Requisitos de DNS para el inicio de sesión automático de cliente en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-06-19_

En esta sección se describen los registros del sistema de nombres de dominio (DNS) necesarios para el inicio de sesión automático de los clientes. Cuando se implementan servidores Standard Edition o grupos de servidores front-end, se pueden configurar los clientes para que usen la detección automática para iniciar sesión en el servidor Standard Edition o en el grupo de servidores front-end adecuado. Si tiene previsto exigir que sus clientes se conecten manualmente a Lync Server 2013, puede omitir este tema.

Para admitir el inicio de sesión automático de los clientes, necesita:

  - Designar un único servidor o grupo de servidores para distribuir y autenticar las solicitudes de inicio de sesión de los clientes. Puede ser uno de los servidores o grupos de servidores existentes en la organización que hospede usuarios, o bien, puede designar un servidor o grupo de servidores dedicado para este fin que no hospede usuarios. Para lograr una alta disponibilidad, recomendamos designar un grupo de servidores front-end para esta función.

  - Crear un registro SRV de DNS interno para admitir el inicio de sesión automático de los clientes para este servidor o grupo de servidores.
    
    <div>
    

    > [!NOTE]  
    > En los siguientes requisitos de registro, el dominio SIP hace referencia a la parte correspondiente al host de los URI de SIP asignados a los usuarios. Por ejemplo, si los URI de SIP tienen el formato *@contoso.com, contoso.com es el dominio SIP. El dominio SIP suele ser distinto del dominio de Active Directory interno. Una organización también puede admitir varios dominios SIP.

    
    </div>

Para habilitar la configuración automática para sus clientes, debe crear un registro SRV de DNS interno que asigne uno de los siguientes registros al nombre de dominio completo (FQDN) del grupo de servidores front-end o el servidor Standard Edition que distribuye las solicitudes de inicio de sesión de Lync. cliente

  - \_sipinternaltls. \_TCP. \<dominio\> : para conexiones TLS internas

Solo tiene que crear un único registro SRV para el grupo de servidores front-end o el servidor Standard Edition o que distribuirá solicitudes de inicio de sesión.

En la tabla siguiente se muestran algunos registros de ejemplo necesarios para la compañía ficticia Contoso, que admite los dominios SIP de contoso.com y retail.contoso.com.

### <a name="example-of-dns-records-required-for-automatic-client-sign-in-with-multiple-sip-domains"></a>Ejemplo de registros de DNS necesarios para el inicio de sesión automático de los clientes con varios dominios SIP

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
<th>Registro SRV de DNS</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>pool01.contoso.com</p></td>
<td><p>contoso.com</p></td>
<td><p>Registro SRV para el dominio _sipinternaltls._tcp.contoso.com por el puerto 5061 que se asigna a pool01.contoso.com</p></td>
</tr>
<tr class="even">
<td><p>pool01.contoso.com</p></td>
<td><p>retail.contoso.com</p></td>
<td><p>Registro SRV para el dominio _sipinternaltls._tcp.retail.contoso.com por el puerto 5061 que se asigna a pool01.contoso.com</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> De forma predeterminada, las consultas de los registros de DNS observan estrictamente los resultados de los nombres de dominio entre el dominio del nombre de usuario y el registro SRV. Si prefiere que las consultas de DNS de los clientes usen los resultados de sufijos, puede configurar la directiva de grupo DisableStrictDNSNaming. Para obtener más información, vea <A href="lync-server-2013-planning-for-clients-and-devices.md">planificación de clientes y dispositivos en Lync Server 2013</A> en la documentación de planeación.



</div>

<div>

## <a name="example-of-the-certificates-and-dns-records-required-for-automatic-client-sign-in"></a>Ejemplo de los certificados y registros de DNS necesarios para el inicio de sesión automático de los clientes

En este ejemplo se utilizan los mismos nombres de ejemplo de la tabla anterior. La organización Contoso admite los dominios SIP de contoso.com y retail.contoso.com, y todos sus usuarios tienen un URI de SIP con uno de los formatos siguientes:

  - \<usuario\>@retail. contoso.com

  - \<@contoso\>de usuario. com

</div>

</div>

<span> </span>

</div>

</div>

</div>

