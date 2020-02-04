---
title: 'Lync Server 2013: Configurar interfaces de red para servidores perimetrales'
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
ms.openlocfilehash: dfbae47a5f5e99e603e3f095a2e07dbb9b49515f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764646"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-up-network-interfaces-for-edge-servers-in-lync-server-2013"></a>Configurar interfaces de red para servidores perimetrales en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-08_

Cada servidor perimetral es un equipo de host múltiple con interfaces externas e internas. La configuración del sistema de nombres de dominio (DNS) del adaptador depende de si hay servidores DNS en la red perimetral. Si los servidores DNS existen en el perímetro, deben tener una zona que contenga uno o más registros A de DNS para el siguiente servidor o grupo de servidores (es decir, un director o un grupo de servidores front-end designados) y para las consultas externas que hacen referencia a otros servidores DNS públicos. Si no hay servidores DNS en el perímetro, los servidores perimetrales usan servidores DNS externos para resolver búsquedas de nombres de Internet, y cada servidor perimetral usa un HOST para resolver los nombres de servidor del próximo salto en direcciones IP.

<div>

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="seguridad" alt="security" />Nota de seguridad:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Por razones de seguridad, le recomendamos que no tenga acceso a los servidores perimetrales a un servidor DNS ubicado en la red interna.</td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="to-configure-interfaces-with-dns-servers-in-the-perimeter-network"></a>Para configurar interfaces con servidores DNS en la red perimetral

1.  Instale dos adaptadores de red para cada servidor perimetral, uno para la interfaz interna y otro para la interfaz externa.
    
    <div>
    

    > [!IMPORTANT]  
    > Las subredes internas y externas no deben ser enrutables entre sí.

    
    </div>

2.  En la interfaz externa, configure tres direcciones IP estáticas en la red perimetral externa (también denominada subred DMZ, zona desmilitarizada y subred filtrada) y apunte la puerta de enlace predeterminada a la interfaz interna del firewall externo. Configure los parámetros DNS del adaptador para que apunten a un par de servidores DNS perimetrales.
    
    <div>
    

    > [!NOTE]  
    > Es posible usar como mínimo una dirección IP para esta interfaz, pero para ello tendrá que cambiar las asignaciones de puertos a valores no estándar. Esto se determina al crear la topología en el generador de topología.

    
    </div>

3.  En la interfaz interna, configure una dirección IP estática en la subred de la red perimetral interna y no establezca una puerta de enlace predeterminada. Configure los parámetros DNS del adaptador para que apunten a al menos un servidor DNS, preferiblemente un par de servidores DNS perimetrales.

4.  Cree rutas estáticas persistentes en la interfaz interna para todas las redes internas donde residen los clientes, Lync Server 2013 y los servidores de mensajería unificada de Exchange (UM).

</div>

<div>

## <a name="to-configure-interfaces-without-dns-servers-in-the-perimeter-network"></a>Para configurar interfaces sin servidores DNS en la red perimetral

1.  Instale dos adaptadores de red para cada servidor perimetral, uno para la interfaz interna y otro para la interfaz externa.
    
    <div>
    

    > [!IMPORTANT]  
    > Las subredes internas y externas no deben ser enrutables entre sí.

    
    </div>

2.  En la interfaz externa, configure tres direcciones IP estáticas en la subred de la red perimetral externa. También puede configurar la puerta de enlace predeterminada en la interfaz externa. Por ejemplo, defina el enrutador orientado a Internet o el firewall externo como puerta de enlace predeterminada. Configure los parámetros de DNS para que apunten a un servidor DNS, preferiblemente a un par de servidores DNS externos.
    
    <div>
    

    > [!NOTE]  
    > Es posible, pero no recomendable, usar como mínimo una dirección IP para la interfaz externa. Para que esto funcione, debe cambiar las asignaciones de puertos a valores no estándar y fuera del puerto predeterminado 443, que suele ser "compatible con el firewall" para la comunicación de clientes. La configuración de la dirección IP y la configuración del puerto se determinan al crear la topología en el generador de topología.

    
    </div>

3.  En la interfaz interna, configure una dirección IP estática en la subred de la red perimetral interna y no establezca una puerta de enlace predeterminada. Deje vacía la configuración del DNS del adaptador.

4.  Cree rutas estáticas persistentes en la interfaz interna para todas las redes internas donde residen los clientes o servidores de Lync que ejecutan Lync Server 2013.

5.  Edite el archivo HOST en cada servidor perimetral para que contenga un registro para el servidor del próximo salto o IP virtual (VIP) (el registro será el director, el servidor Standard Edition o un grupo de servidores front-end que se haya configurado como la dirección del próximo salto del servidor perimetral en el generador de topología). Si está usando el equilibrio de carga de DNS, incluya una línea para cada miembro del grupo de próximos saltos.

</div>

</div>

<span> </span>

</div>

</div>

</div>

