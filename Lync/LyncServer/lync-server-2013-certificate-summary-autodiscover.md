---
title: 'Lync Server 2013: Resumen del certificado-detección automática'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Certificate summary - Autodiscover
ms:assetid: 16ac96bb-882a-4141-b75c-9530637548d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945616(v=OCS.15)
ms:contentKeyID: 51541451
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 59c3777f9b13dc18e3e52e80120009f93c20db3d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842656"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---autodiscover-in-lync-server-2013"></a>Resumen del certificado: detección automática en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-14_

El servicio de detección automática de Lync Server 2013 se ejecuta en los servidores de director y de grupo de servidores front-end, y cuando se publican en DNS, pueden ser usados por los clientes de Lync para ubicar los servicios de servidor y de usuario. Si está actualizando desde Lync Server 2010 y no ha implementado la movilidad, antes de que los clientes puedan usar el descubrimiento automático, debe modificar las listas de nombres alternativos del sujeto de certificado en cualquier Director y servidor front-end que ejecute el servicio de detección automática. Además, puede que sea necesario modificar las listas de nombres alternativos del asunto en los certificados que se usan para las reglas de publicación de servicios web externos en los proxies inversos.

La decisión sobre si usar o no las listas de nombres alternativos del sujeto en proxies inversos se basa en si publica el servicio de detección automática en el puerto 80 o en el puerto 443:

  - **Publicado en el puerto 80**   no es necesario realizar cambios en los certificados si la consulta inicial para el servicio de detección automática se realiza a través del puerto 80. Esto se debe a que los dispositivos móviles que ejecutan Lync tendrán acceso al proxy inverso en el puerto 80 externamente y, a continuación, se enlazarán a un director o servidor front-end en el puerto 8080 de forma interna. Para obtener más información, vea el apartado "proceso de detección automática inicial con el puerto 80" sección [requisitos técnicos de movilidad en Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).

  - **Publicado en el puerto 443**   la lista de nombres alternativos de asunto en certificados usados por la regla de publicación de servicios web externos debe contener un *lyncdiscover.\< sipdomain\> * entrada para cada dominio SIP de su organización.
    
    <div>
    

    > [!IMPORTANT]  
    > Recomendamos encarecidamente usar HTTPS a través de HTTP. HTTPS usa certificados para cifrar el tráfico. HTTP no proporciona el cifrado, y cualquier dato enviado será texto sin formato.

    
    </div>

La reemisión de certificados mediante una entidad emisora de certificados interna suele ser un proceso simple. Sin embargo, en el caso de certificados públicos que se usan en la regla de publicación de servicios Web, agregar varias entradas de nombre alternativo de asunto puede resultar costoso. Para evitar este problema, admitimos la conexión de detección automática inicial en el puerto 80, que luego se le redirige al puerto 8080 en el servidor de director o de front-end.

<div>


> [!NOTE]  
> Si su infraestructura de Lync Server 2013 usa certificados internos emitidos por una entidad de certificación (CA) interna y tiene previsto admitir dispositivos móviles que se conectan de forma inalámbrica, la cadena de certificados raíz de la entidad de certificación interna debe estar instalada en los dispositivos móviles o debe cambiar a un certificado público en su infraestructura de Lync Server 2013.



</div>

En este tema se describen los nombres alternativos de asunto agregados para el director, el servidor front-end y el proxy inverso. Solo se hace referencia a los nombres alternativos de asunto (SAN) agregados. Consulte las secciones de planificación para obtener instrucciones sobre otras entradas de los certificados. Para obtener más información, consulte [escenarios del Director de Lync server 2013](lync-server-2013-scenarios-for-the-director.md), [escenarios para el acceso de usuarios externos en Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md)y [escenarios de inverso de proxy en Lync Server 2013](lync-server-2013-scenarios-for-reverse-proxy.md).

En las siguientes tablas se definen las entradas SAN Discover para el grupo de directores, el grupo front-end y el proxy inverso:

### <a name="director-pool-certificate-requirements"></a>Requisitos de certificados del grupo de directores

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Descripción</th>
<th>Entrada de nombre alternativo de asunto</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Dirección URL del servicio de detección automática interna</p></td>
<td><p>SAN = lyncdiscoverinternal. &lt;nombre de dominio interno&gt;</p></td>
</tr>
<tr class="even">
<td><p>Dirección URL del servicio de detección automática externa</p></td>
<td><p>SAN = lyncdiscover. &lt;sipdomain&gt;</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Asigne el certificado recién actualizado con la nueva entrada SAN al certificado predeterminado. También puede usar SAN = *. &lt;sipdomain&gt;.



</div>

### <a name="front-end-pool-certificate-requirements"></a>Requisitos del certificado del grupo de servidores front-end

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Descripción</th>
<th>Entrada de nombre alternativo de asunto</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Dirección URL del servicio de detección automática interna</p></td>
<td><p>SAN = lyncdiscoverinternal. &lt;nombre de dominio interno&gt;</p></td>
</tr>
<tr class="even">
<td><p>Dirección URL del servicio de detección automática externa</p></td>
<td><p>SAN = lyncdiscover. &lt;sipdomain&gt;</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Asigne el certificado recién actualizado con la nueva entrada SAN al certificado predeterminado. También puede usar SAN = *. &lt;sipdomain&gt;



</div>

### <a name="reverse-proxy-public-ca-certificate-requirements"></a>Requisitos de los certificados de proxy inverso (CA pública)

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Descripción</th>
<th>Entrada de nombre alternativo de asunto</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Dirección URL del servicio de detección automática externa</p></td>
<td><p>SAN = lyncdiscover. &lt;sipdomain&gt;</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Asigne el certificado que acaba de actualizar con la nueva entrada de SAN a la escucha SSL en el proxy inverso.



</div>

</div>

<span> </span>

</div>

</div>

</div>

