---
title: 'Lync Server 2013: Configurar interfaces de red para servidores perimetrales'
TOCTitle: Configurar interfaces de red para servidores perimetrales
ms:assetid: b0aecdf6-4ae2-46f6-b9b6-948bfc3df11e
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg412847(v=OCS.15)
ms:contentKeyID: 48276376
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurar interfaces de red para servidores perimetrales en Lync Server 2013

 

_**Última modificación del tema:** 2012-09-08_

Cada servidor perimetral es un equipo de host múltiple con interfaces orientadas interna y externamente. La configuración del adaptador de sistema de nombres de dominio (DNS) depende de si hay servidores DNS en la red perimetral. Si existen servidores DNS en el perímetro, deben tener una zona que contenga uno o más registros A de DNS para el servidor o el grupo de servidores del próximo salto (es decir, un director o un grupo de servidores front-end designado) y para consultas externas deben hacer referencia a búsquedas de nombres a otros servidores DNS públicos. Si no existen servidores DNS en el perímetro, los servidores perimetrales usan servidores DNS externos para resolver las búsquedas de nombres en Internet y cada servidor perimetral usa un HOST para resolver los nombres de servidor del próximo salto en las direcciones IP.

<table>
<thead>
<tr class="header">
<th><img src="images/Gg399038.security(OCS.15).gif" title="security" alt="security" />Seguridad Nota:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Por razones de seguridad, es recomendable que los servidores perimetrales no tengan acceso a un servidor DNS ubicado en la red interna.</td>
</tr>
</tbody>
</table>


## Para configurar interfaces con servidores DNS en la red perimetral

1.  Instale dos adaptadores de red para cada servidor perimetral, uno para la interfaz orientada internamente y otro para la interfaz orientada externamente.
    
    > [!IMPORTANT]  
    > Las subredes internas y externas no deben ser enrutables entre sí.
    


2.  En la interfaz externa, configure tres direcciones IP estáticas en la subred de la red perimetral externa (denominada red perimetral o subred filtrada) y apunte la puerta de enlace predeterminada a la interfaz interna del firewall externo. Configure el adaptador DNS para apuntar a un par de servidores DNS perimetrales.
    

    > [!NOTE]
    > Se puede usar solamente una dirección IP para esta interfaz, pero para hacerlo debe cambiar las asignaciones de puerto a valores no estándar. Puede determinarlo al crear la topología en Generador de topologías.



3.  En la interfaz interna, configure una dirección IP estática en la subred de red perimetral interna y no establezca una puerta de enlace predeterminada. Configure el adaptador DNS para apuntar al menos a un servidor DNS, preferiblemente a un par de servidores DNS perimetrales.

4.  Cree rutas estáticas persistentes en la interfaz interna para todas las redes internas donde residen los clientes, Lync Server 2013 y los servidores de mensajería unificada de Exchange.

## Para configurar interfaces sin servidores DNS en la red perimetral

1.  Instale dos adaptadores de red para cada servidor perimetral, uno para la interfaz orientada internamente y otro para la interfaz orientada externamente.
    
    > [!IMPORTANT]  
    > Las subredes internas y externas no deben ser enrutables entre sí.
    


2.  En la interfaz externa, configure tres direcciones IP estáticas en la subred de red perimetral externa y apunte la puerta de enlace predeterminada a la interfaz interna del firewall externo. Configure el adaptador DNS para apuntar al menos a un servidor DNS, preferiblemente a un par de servidores DNS externos.
    

    > [!NOTE]
    > Si bien es posible, no se recomienda usar una sola dirección IP para la interfaz externa. Para que funcione, debe cambiar las asignaciones de los puertos por valores no estándar y diferentes del valor predeterminado 443 para el puerto. En general, este valor es compatible con firewall y permite la comunicación cliente. La configuración de la dirección IP y del puerto se establece al crear la topología en Generador de topologías.



3.  En la interfaz interna, configure una dirección IP estática en la subred de red perimetral interna y no establezca una puerta de enlace predeterminada. Deje la configuración del adaptador DNS vacía.

4.  Cree rutas estáticas persistentes en la interfaz interna para todas las redes internas donde residen los servidores o clientes Lync que ejecutan Lync Server 2013.

5.  Edite el archivo del HOST en cada servidor perimetral para contener un registro para el servidor o el IP virtual (VIP) del próximo salto (el registro será el director, un servidor Standard Edition o un grupo de servidores front-end que se configuró como la dirección del próximo salto del servidor perimetral en Generador de topologías). Si usa el equilibrio de carga de DNS, incluya una línea para cada miembro del grupo de servidores del próximo salto.

