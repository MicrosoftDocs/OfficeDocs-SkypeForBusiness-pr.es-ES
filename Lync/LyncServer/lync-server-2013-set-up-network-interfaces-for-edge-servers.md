---
title: 'Lync Server 2013: configurar interfaces de red para servidores perimetrales'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set up network interfaces for Edge Servers
ms:assetid: b0aecdf6-4ae2-46f6-b9b6-948bfc3df11e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412847(v=OCS.15)
ms:contentKeyID: 48185152
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 267db7062c19a0b1344d11f27205a51bf1e750ae
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42182153"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="set-up-network-interfaces-for-edge-servers-in-lync-server-2013"></a>Configurar interfaces de red para servidores perimetrales en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-08_

Cada servidor perimetral es un equipo de host múltiple con interfaces orientadas interna y externamente. La configuración del adaptador de sistema de nombres de dominio (DNS) depende de si hay servidores DNS en la red perimetral. Si existen servidores DNS en el perímetro, deben tener una zona que contenga uno o más registros A de DNS para el servidor o el grupo de servidores del próximo salto (es decir, un director o un grupo de servidores front-end designado) y para consultas externas deben hacer referencia a búsquedas de nombres a otros servidores DNS públicos. Si no existen servidores DNS en el perímetro, los servidores perimetrales usan servidores DNS externos para resolver las búsquedas de nombres en Internet y cada servidor perimetral usa un HOST para resolver los nombres de servidor del próximo salto en las direcciones IP.

<div>

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="seguridad" alt="security" />Nota de seguridad:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Por razones de seguridad, es recomendable que los servidores perimetrales no tengan acceso a un servidor DNS ubicado en la red interna.</td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="to-configure-interfaces-with-dns-servers-in-the-perimeter-network"></a>Para configurar interfaces con servidores DNS en la red perimetral

1.  Instale dos adaptadores de red para cada servidor perimetral, uno para la interfaz orientada internamente y otro para la interfaz orientada externamente.
    
    <div>
    

    > [!IMPORTANT]  
    > Las subredes internas y externas no deben ser enrutables entre sí.

    
    </div>

2.  En la interfaz externa, configure tres direcciones IP estáticas en la subred de la red perimetral externa (denominada red perimetral o subred filtrada) y apunte la puerta de enlace predeterminada a la interfaz interna del firewall externo. Configure el adaptador DNS para apuntar a un par de servidores DNS perimetrales.
    
    <div>
    

    > [!NOTE]  
    > Se puede usar solamente una dirección IP para esta interfaz, pero para hacerlo debe cambiar las asignaciones de puerto a valores no estándar. Debe determinar esto cuando cree la topología en el generador de topologías.

    
    </div>

3.  En la interfaz interna, configure una dirección IP estática en la subred de red perimetral interna y no establezca una puerta de enlace predeterminada. Configure el adaptador DNS para apuntar al menos a un servidor DNS, preferiblemente a un par de servidores DNS perimetrales.

4.  Cree rutas estáticas persistentes en la interfaz interna para todas las redes internas en las que residen los clientes, Lync Server 2013 y los servidores de mensajería unificada (MU) de Exchange.

</div>

<div>

## <a name="to-configure-interfaces-without-dns-servers-in-the-perimeter-network"></a>Para configurar interfaces sin servidores DNS en la red perimetral

1.  Instale dos adaptadores de red para cada servidor perimetral, uno para la interfaz orientada internamente y otro para la interfaz orientada externamente.
    
    <div>
    

    > [!IMPORTANT]  
    > Las subredes internas y externas no deben ser enrutables entre sí.

    
    </div>

2.  En la interfaz externa, configure tres direcciones IP estáticas en la subred de red perimetral externa y apunte la puerta de enlace predeterminada a la interfaz interna del firewall externo. Configure el adaptador DNS para apuntar al menos a un servidor DNS, preferiblemente a un par de servidores DNS externos.
    
    <div>
    

    > [!NOTE]  
    > Es posible, pero no se recomienda, usar tan solo una dirección IP para la interfaz externa. Para permitir que esto funcione, debe cambiar las asignaciones de puerto a valores no estándar y fuera del puerto predeterminado 443 que suele ser "compatible con firewall" para la comunicación con el cliente. La configuración de la dirección IP y la configuración del puerto se determinan al crear la topología en el generador de topologías.

    
    </div>

3.  En la interfaz interna, configure una dirección IP estática en la subred de red perimetral interna y no establezca una puerta de enlace predeterminada. Deje la configuración del adaptador DNS vacía.

4.  Cree rutas estáticas persistentes en la interfaz interna para todas las redes internas donde residen los clientes o servidores de Lync que ejecutan Lync Server 2013.

5.  Edite el archivo HOST en cada servidor perimetral para que contenga un registro para el servidor del próximo salto o IP virtual (VIP) (el registro será el director, el servidor Standard Edition o un grupo de servidores front-end que se haya configurado como la dirección del próximo salto del servidor perimetral en el generador de topologías). Si usa el equilibrio de carga de DNS, incluya una línea para cada miembro del grupo de servidores del próximo salto.

</div>

</div>

<span> </span>

</div>

</div>

</div>

