---
title: 'Lync Server 2013: Resumen del certificado-detección automática'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Autodiscover
ms:assetid: 16ac96bb-882a-4141-b75c-9530637548d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945616(v=OCS.15)
ms:contentKeyID: 51541451
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ae57440d4843151da61d24a9ff015778a5c65b07
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043992"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---autodiscover-in-lync-server-2013"></a>Resumen de certificado-detección automática en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-14_

El servicio Detección automática de Lync Server 2013 se ejecuta en los servidores de director y de grupo de servidores front-end y, cuando se publican en DNS, los clientes de Lync pueden usarlos para buscar servicios de usuario y servidor. Si va a actualizar desde Lync Server 2010 y no ha implementado la movilidad, antes de que los clientes puedan usar la detección automática, debe modificar las listas de nombres alternativos de sujeto de certificado en cualquier Director y servidor front-end que ejecute el servicio Detección automática. Además, es posible que haya que modificar las listas de nombres alternativos de sujeto en certificados usados para las reglas de publicación de servicios web en proxies inversos.

La decisión sobre si usar listas de nombres alternativos de sujetos en servidores proxy inversos se basa en si publica el servicio Detección automática en el puerto 80 o en el puerto 443:

  - **Publicado en el puerto 80**   no es necesario realizar cambios en los certificados si la consulta inicial al servicio Detección automática se produce a través del puerto 80. Esto se debe a que los dispositivos móviles que ejecutan Lync tendrán acceso al proxy inverso en el puerto 80 externamente y, a continuación, se enlazarán a un director o un servidor front-end en el puerto 8080 internamente. Para obtener más información, consulte la sección "proceso de detección automática inicial con el puerto 80" sección [Technical Requirements for Mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).

  - **Publicado en el puerto 443**   la lista de nombres alternativos de sujeto en los certificados usados por la regla de publicación de servicios web externos debe contener un *lyncdiscover.\< entrada\> sipdomain* para cada dominio SIP dentro de la organización.
    
    <div>
    

    > [!IMPORTANT]  
    > Se recomienda encarecidamente usar HTTPS sobre HTTP. HTTPS usa certificados para cifrar el tráfico. HTTP no proporciona el cifrado, y los datos enviados serán texto sin formato.

    
    </div>

La reemisión de certificados mediante una entidad de certificación interna suele ser un proceso sencillo. Pero en el caso de los certificados públicos que se usan en la regla de publicación de servicios Web, agregar varias entradas de nombre alternativo de sujeto puede resultar caro. Para solucionar este problema, admitimos la conexión de detección automática inicial a través del puerto 80, que luego se redirige al puerto 8080 en el director o el servidor front-end.

<div>


> [!NOTE]  
> Si su infraestructura de Lync Server 2013 usa certificados internos emitidos por una entidad de certificación (CA) interna y planea admitir dispositivos móviles que se conectan de forma inalámbrica, es necesario instalar la cadena de certificados raíz de la CA interna. en los dispositivos móviles o debe cambiar a un certificado público en su infraestructura de Lync Server 2013.



</div>

En este tema se describen los nombres alternativos de sujeto agregados necesarios para el director, el servidor front-end y el proxy inverso. Solo se hace referencia a los nombres alternativos de sujeto (SAN) agregados. Consulte las secciones de planeación para obtener información sobre otras entradas en los certificados. Para obtener más información, consulte [escenarios para el Director en Lync server 2013](lync-server-2013-scenarios-for-the-director.md), [escenarios para el acceso de usuarios externos en Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md)y [escenarios para el proxy inverso en Lync Server 2013](lync-server-2013-scenarios-for-reverse-proxy.md).

En las siguientes tablas se definen las entradas de SAN de detección automática para el grupo de directores, el grupo de servidores front-end y el proxy inverso:

### <a name="director-pool-certificate-requirements"></a>Requisitos de certificado de grupo de directores

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Descripción</th>
<th>Entrada de nombre alternativo del sujeto</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>URL de servicio Detección automática interna</p></td>
<td><p>SAN = lyncdiscoverinternal. &lt;nombre de dominio interno&gt;</p></td>
</tr>
<tr class="even">
<td><p>URL de servicio Detección automática externa</p></td>
<td><p>SAN = lyncdiscover. &lt;sipdomain&gt;</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Asigne el certificado recién actualizado a la nueva entrada de SAN al certificado predeterminado. Como alternativa, puede usar SAN = *. &lt;sipdomain&gt;.



</div>

### <a name="front-end-pool-certificate-requirements"></a>Requisitos de certificado de grupo de servidores front-end

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Descripción</th>
<th>Entrada de nombre alternativo del sujeto</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>URL de servicio Detección automática interna</p></td>
<td><p>SAN = lyncdiscoverinternal. &lt;nombre de dominio interno&gt;</p></td>
</tr>
<tr class="even">
<td><p>URL de servicio Detección automática externa</p></td>
<td><p>SAN = lyncdiscover. &lt;sipdomain&gt;</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Asigne el certificado recién actualizado a la nueva entrada de SAN al certificado predeterminado. Como alternativa, puede usar SAN = *. &lt;sipdomain&gt;



</div>

### <a name="reverse-proxy-public-ca-certificate-requirements"></a>Requisitos de certificado (CA pública) de proxy inverso

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Descripción</th>
<th>Entrada de nombre alternativo del sujeto</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>URL de servicio Detección automática externa</p></td>
<td><p>SAN = lyncdiscover. &lt;sipdomain&gt;</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Asigne el certificado recién actualizado a la nueva entrada de SAN a la escucha de SSL en el proxy inverso.



</div>

</div>

<span> </span>

</div>

</div>

</div>

