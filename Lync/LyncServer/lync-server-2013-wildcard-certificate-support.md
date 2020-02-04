---
title: 'Lync Server 2013: Compatibilidad de certificado de comodín'
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
ms.openlocfilehash: 8a3e64dcfd16212e618a8ebe152bd2516a25b26d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727500"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="wildcard-certificate-support-in-lync-server-2013"></a>Compatibilidad de certificado de comodín en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-03-21_

Lync Server 2013 usa certificados para proporcionar cifrado de comunicaciones y autenticación de identidades de servidor. En algunos casos, como la publicación web a través del proxy inverso, la coincidencia de entrada de nombre alternativo de asunto (SAN) con el nombre de dominio completo (FQDN) del servidor que presenta el servicio no es necesaria. En estos casos, puede usar certificados con entradas SAN con comodín (comúnmente conocidos como "certificados comodín") para reducir el costo de un certificado solicitado por una autoridad de certificación pública y para reducir la complejidad del proceso de planeación de certificados .

<div>


> [!WARNING]  
> Para conservar la funcionalidad de los dispositivos de comunicaciones unificadas (por ejemplo, los teléfonos de escritorio), debe probar el certificado implementado con cuidado para asegurarse de que los dispositivos funcionan correctamente después de implementar un certificado de comodín.



</div>

No se admite una entrada de comodín como nombre de asunto (también denominado nombre común o CN) para cualquier rol. Los siguientes roles de servidor se admiten al usar entradas con comodín en el SAN:

  - <span></span>  
    **Proxy inverso.**    La entrada San con comodín es compatible con el certificado de publicación de URL simple (reunirse y llamar).

  - <span></span>  
    **Proxy inverso.**    La entrada San con comodín es compatible con las entradas San para LyncDiscover en el certificado de publicación.

  - <span></span>  
    **Director.**    La entrada San con comodín es compatible con las direcciones URL simples (reunirse y llamar) y para las entradas de San para LyncDiscover y LyncDiscoverInternal en los componentes Web de director.

  - <span></span>  
    **Servidor front end (Standard Edition) y grupo de servidores front-end (Enterprise Edition).** La entrada SAN con comodín es compatible con las direcciones URL simples (reunirse y llamar) y para las entradas de SAN para LyncDiscover y LyncDiscoverInternal en los componentes Web front-end.

  - <span></span>  
    **Mensajería unificada de Exchange (UM).**    El servidor no usa entradas San cuando se implementa como un servidor independiente.

  - <span></span>  
    **Servidor de acceso de cliente de Microsoft Exchange Server.**    Las entradas con comodín en el San son compatibles con los clientes internos y externos.

  - <span></span>  
    **Mensajería unificada de Exchange y servidor de acceso de cliente de Microsoft Exchange Server en el mismo servidor.**    Se admiten entradas San con comodín.

Roles de servidor que no se tratan en este tema:

  - Roles de servidor interno (incluidos, entre otros, el servidor de mediación, el servidor de archivado y el servidor de supervisión, el dispositivo de sucursal con supervivencia o el servidor de sucursal superviviente)

  - Interfaces de servidor perimetral externo

  - Servidor perimetral interno
    
    <div>
    

    > [!NOTE]  
    > Para la interfaz de servidor perimetral interno, se puede asignar una entrada comodín a la SAN y es compatible. No se consulta la SAN en el servidor perimetral interno y una entrada SAN con comodín tiene un valor limitado.

    
    </div>

Para obtener más información sobre la configuración de certificados, incluido el uso de caracteres comodín en los certificados, consulte los siguientes temas:

  - [Requisitos de certificado para Servidores internos en Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md)

  - [Requisitos de certificado para el acceso de usuarios externos en Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md)

  - [Resumen de certificado - Carga equilibrada DNS y HLB en Lync Server 2013](lync-server-2013-certificate-summary-dns-and-hlb-load-balanced.md)

  - [Resumen de certificado - Director único en Lync Server 2013](lync-server-2013-certificate-summary-single-director.md)

  - [Resumen de certificado - Grupo de director escalado, equilibrador de carga de hardware en Lync Server 2013](lync-server-2013-certificate-summary-scaled-director-pool-hardware-load-balancer.md)

  - [Resumen de certificado - Proxy inverso en Lync Server 2013](lync-server-2013-certificate-summary-reverse-proxy.md)

  - [Instrucciones para integrar mensajería unificada local y Lync Server 2013](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md)

Para obtener detalles sobre la configuración de certificados para Exchange, incluido el uso de caracteres comodín, consulte la documentación del producto Exchange 2013.

</div>

<span> </span>

</div>

</div>

</div>

