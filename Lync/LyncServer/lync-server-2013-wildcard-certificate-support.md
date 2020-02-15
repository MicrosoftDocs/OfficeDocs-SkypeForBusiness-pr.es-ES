---
title: Compatibilidad con certificados comodín 2013 de Lync Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Wildcard certificate support
ms:assetid: 0bae2aa8-b6dc-46f5-a3be-3fe7581809d4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202161(v=OCS.15)
ms:contentKeyID: 48183382
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 18b1313432cac09f03cd414b90d9a068f271edef
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42041209"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="wildcard-certificate-support-in-lync-server-2013"></a>Compatibilidad con certificados comodín en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-03-21_

Lync Server 2013 usa certificados para proporcionar cifrado de comunicaciones y autenticación de identidad de servidor. En algunos casos, como la publicación web mediante proxy inverso, no es  necesaria la coincidencia sólida de entradas de nombre alternativo de sujeto (SAN) con el nombre de dominio completo (FQDN) del servidor que presenta el servicio. En estos casos, puede usar certificados con entradas de SAN de comodín (conocidas generalmente como “certificados de comodín”) para reducir el costo de un certificado solicitado de una entidad de certificación pública y para reducir la complejidad del proceso de planeamiento para certificados.

<div>


> [!WARNING]  
> Para retener la funcionalidad de los dispositivos de comunicaciones unificadas (UC) (por ejemplo, teléfonos de escritorio), debe probar el certificado implementado con cuidado para garantizar que los dispositivos funcionan correctamente después de implementar un certificado de comodín.



</div>

No hay compatibilidad para una entrada de comodín como nombre de sujeto (también denominado nombre común o CN) para ninguna función. Las siguientes funciones de servidor son compatibles al usar entradas de comodín en el SAN:

  - <span></span>  
    **Proxy inverso.**    La entrada San comodín se admite para el certificado de publicación de dirección URL sencilla (reunirse y llamar).

  - <span></span>  
    **Proxy inverso.**    La entrada San comodín es compatible con las entradas de San para LyncDiscover en el certificado de publicación.

  - <span></span>  
    **Director.**    La entrada de San comodín se admite para las direcciones URL sencillas (reunirse y llamar) y para las entradas de San para LyncDiscover y LyncDiscoverInternal en componentes Web de director.

  - <span></span>  
    **Servidor front-end (Standard Edition) y grupo de servidores front-end (Enterprise Edition).** La entrada SAN comodín se admite para las direcciones URL sencillas (reunirse y llamar) y para las entradas de SAN para LyncDiscover y LyncDiscoverInternal en los componentes Web front-end.

  - <span></span>  
    **Mensajería unificada (MU) de Exchange.**    El servidor no usa entradas de San cuando se implementa como un servidor independiente.

  - <span></span>  
    **Servidor de acceso de cliente de Microsoft Exchange Server.**    Las entradas de comodín en el San son compatibles con los clientes internos y externos.

  - <span></span>  
    **Mensajería unificada (MU) de Exchange y servidor de acceso de cliente de Microsoft Exchange Server en el mismo servidor.**    Se admiten las entradas San de comodín.

Funciones de servidor que no se abordan en este tema:

  - Roles de servidor interno (incluidos, entre otros, el servidor de mediación, el servidor de archivado y de supervisión, una aplicación de sucursal con funciones de supervivencia o un servidor de sucursal con funciones de supervivencia)

  - Interfaces del servidor perimetral externo

  - Servidor perimetral interno
    
    <div>
    

    > [!NOTE]  
    > Para la interfaz del servidor perimetral interno, se puede asignar una entrada de comodín al SAN y es compatible. No se consulta la SAN del servidor perimetral interno y una entrada de SAN comodín es de valor limitado.

    
    </div>

Para obtener más información acerca de la configuración de certificados, incluido el uso de caracteres comodín en los certificados, consulte los siguientes temas:

  - [Requisitos de certificado para servidores internos en Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md)

  - [Requisitos de certificado para el acceso de usuarios externos en Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md)

  - [Resumen de certificado-carga equilibrada DNS y HLB en Lync Server 2013](lync-server-2013-certificate-summary-dns-and-hlb-load-balanced.md)

  - [Resumen del certificado-Director único en Lync Server 2013](lync-server-2013-certificate-summary-single-director.md)

  - [Resumen de certificado-grupo de Director escalado, equilibrador de carga de hardware en Lync Server 2013](lync-server-2013-certificate-summary-scaled-director-pool-hardware-load-balancer.md)

  - [Resumen de certificado-proxy inverso en Lync Server 2013](lync-server-2013-certificate-summary-reverse-proxy.md)

  - [Directrices para la integración de la mensajería unificada local y Lync Server 2013](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md)

Para obtener más información acerca de la configuración de certificados para Exchange, incluido el uso de caracteres comodín, consulte la documentación del producto de Exchange 2013.

</div>

<span> </span>

</div>

</div>

</div>

