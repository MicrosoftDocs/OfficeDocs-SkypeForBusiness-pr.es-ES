---
title: 'Lync Server 2013: selección de una topología'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Choosing a topology
ms:assetid: 23f2aeb6-fed9-4349-8fba-dcbf18ee4b04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425716(v=OCS.15)
ms:contentKeyID: 48183634
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b91fc332c5eff86cd23393492bcd760bbda18db3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151400"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="choosing-a-topology-in-lync-server-2013"></a>Elección de una topología en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

_**Última modificación del tema:** 2013-02-21_

Al elegir una topología, puede usar una de las siguientes opciones compatibles:

<div>


> [!NOTE]
> A menos que se indique lo contrario, si tiene experiencia con Microsoft Lync Server 2010, encontrará que la guía no se modifica en gran medida.



</div>

  - [Servidor perimetral consolidado único con direcciones IP privadas y NAT en Lync Server 2013](lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md)

  - [Servidor perimetral consolidado único con direcciones IP públicas en Lync Server 2013](lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md)

  - [Servidor perimetral consolidado ampliado, equilibrio de carga DNS con direcciones IP privadas mediante NAT en Lync Server 2013](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - [Servidor perimetral consolidado escalado, equilibrio de carga DNS con direcciones IP públicas en Lync Server 2013](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - [Servidor perimetral consolidado ampliado con equilibradores de carga de hardware en Lync Server 2013](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md)

<div>


> [!IMPORTANT]
> La interfaz perimetral interna y la interfaz perimetral externa deben usar el mismo tipo de equilibrio de carga. No puede usar equilibrio de carga DNS en una interfaz perimetral y equilibrio de carga de hardware en la otra interfaz perimetral.



</div>

En la tabla siguiente se resumen las funciones disponibles en las topologías de Microsoft Lync Server 2013 compatibles. Los encabezados de columna indican la funcionalidad disponible con una opción de configuración perimetral determinada. Si tomamos la opción perimetral escalada (DNS con equilibro de carga) como ejemplo, veremos que admite una alta disponibilidad, puede usar direcciones IP privadas no enrutables (con NAT) o direcciones IP públicas enrutables asignadas a las interfaces perimetrales externas y reduce el costo dado que no necesita un equilibrador de carga de hardware.

Los escenarios de conmutación por error perimetral compatibles con el equilibrio de carga de DNS son sesiones de punto a punto de Lync a Lync, sesiones de conferencia de Lync, sesiones de Lync a RTC y Office 365. Los escenarios de conmutación por error perimetral que no se benefician del equilibrio de carga de DNS son la conmutación por error de la mensajería unificada de Exchange para usuarios remotos (UM) (antes de Exchange 2010 SP1), conectividad de mensajería instantánea pública (mi) y Federación con servidores que ejecutan Office Communications Server.

### <a name="summary-of-edge-server-topology-options"></a>Resumen de opciones de topología de servidores perimetrales

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
<th>Topología</th>
<th>Alta disponibilidad</th>
<th>Registros A DNS adicionales necesarios para el servidor perimetral externo del grupo</th>
<th>Conmutación por error perimetral para sesiones de Lync a Lync</th>
<th>Conmutación por error para sesiones de Federación de Lync a Lync EUM/PIC/OCS</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Perimetral simple usando NAT</p></td>
<td><p>No</p></td>
<td><p>No</p></td>
<td><p>No</p></td>
<td><p>No</p></td>
</tr>
<tr class="even">
<td><p>Perimetral simple usando IP pública</p></td>
<td><p>No</p></td>
<td><p>No</p></td>
<td><p>No</p></td>
<td><p>No</p></td>
</tr>
<tr class="odd">
<td><p>Perimetral escalada (con equilibrio de carga DNS) usando NAT</p></td>
<td><p>Sí</p></td>
<td><p>Sí</p></td>
<td><p>Sí</p></td>
<td><p>*</p></td>
</tr>
<tr class="even">
<td><p>Perimetral escalada (con equilibrio de carga DNS) usando IP pública</p></td>
<td><p>Sí</p></td>
<td><p>Sí</p></td>
<td><p>Sí</p></td>
<td><p>*</p></td>
</tr>
<tr class="odd">
<td><p>Perimetral escalada (equil. carga hardware)</p></td>
<td><p>Sí</p></td>
<td><p>No (un registro A DNS por VIP)</p></td>
<td><p>Sí</p></td>
<td><p>Sí</p></td>
</tr>
</tbody>
</table>


**\*** La conmutación por error para la conectividad de mensajería instantánea pública (mi) y la Federación con servidores que ejecutan Office Communications Server no están disponibles con el equilibrio de carga de DNS. La conmutación por error de mensajería unificada de Exchange (usuario remoto) mediante el equilibrio de carga de DNS requiere Exchange Server 2010 SP1 o una versión más reciente.



> [!NOTE]
> Las topologías de perimetral simple y perimetral escalada (con equilibrio de carga DNS) pueden usar:
> <ul><li><p>Direcciones IP públicas enrutables</p></li>
> <li><p>Dirección IP privada no enrutable si se usa la traducción de direcciones de red (NAT) simétrica</p></li>
>
> <ul><li> Si usa una dirección IP pública o una dirección IP privada con NAT, seguirá usando el mismo número de direcciones IP en función de la opción de configuración en el generador de topologías. Puede configurar el servidor perimetral para usar una dirección IP única con puertos distintos por servicio, o usar direcciones IP distintas por servicio, pero use el mismo puerto (de forma predeterminada, TCP 443).</li></ul>>
> Si decide usar direcciones IP privadas no enrutables con NAT:
> <ul><li><p>Debe usar direcciones IP privadas enrutables en las tres interfaces externas</p></li>
> <li><p>Debe configurar NAT simétrica para tráfico entrante y saliente</p></li></ul>>
> La topología perimetral escalada (equil. carga hardware) debe usar direcciones IP.



Lync Server 2013 admite la colocación de interfaces externas perimetrales de acceso, conferencia web y a/V detrás de un enrutador o firewall que realiza la traducción de direcciones de red (NAT) para topologías de servidor perimetral consolidado simples y escaladas.

El uso de NAT para todas las interfaces externas perimetrales requiere el uso del equilibrio de carga de DNS. En comparación con el uso de equilibradores de carga de hardware, el uso de equilibrio de carga de DNS sin NAT permite reducir el número de la dirección IP pública por servidor perimetral en un grupo de servidores perimetrales, como se describe en la lista siguiente:

  - Lync Server 2013 el perímetro consolidado escalado (con equilibrio de carga DNS) requiere tres direcciones IP públicas para cada servidor perimetral en un grupo de servidores perimetrales.

  - Lync Server 2013 servidor perimetral consolidado escalado (equilibrio de carga de hardware) requiere tres direcciones IP públicas para las direcciones IP virtuales del equilibrador de carga (un requisito de tiempo que no aumenta a medida que se agregan más servidores perimetrales al grupo) más tres direcciones IP públicas por Servidor perimetral en un grupo de servidores.

### <a name="ip-address-requirements-for-scaled-consolidated-edge-ip-address-per-role"></a>Requisitos de dirección IP para servidor perimetral consolidado escalado (dirección IP por rol)

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Número de servidores perimetrales por grupo</th>
<th>Número de direcciones IP necesarias Lync Server 2013 (con equilibrio de carga DNS)</th>
<th>Número de direcciones IP necesarias Lync Server 2013 (equilibrio de carga de hardware)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>segundo</p></td>
<td><p>6 </p></td>
<td><p>3 (1 por VIP) + 6</p></td>
</tr>
<tr class="even">
<td><p>3</p></td>
<td><p>9 </p></td>
<td><p>3 (1 por VIP) + 9</p></td>
</tr>
<tr class="odd">
<td><p>4</p></td>
<td><p>12</p></td>
<td><p>3 (1 por VIP) + 12</p></td>
</tr>
<tr class="even">
<td><p>2,5</p></td>
<td><p>15 </p></td>
<td><p>3 (1 por VIP) + 15</p></td>
</tr>
</tbody>
</table>


### <a name="ip-address-requirements-for-scaled-consolidated-edge-single-ip-address-for-all-roles"></a>Requisitos de dirección IP para servidor perimetral consolidado escalado (dirección IP única para todos los roles)

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Número de servidores perimetrales por grupo</th>
<th>Número de direcciones IP necesarias Lync Server 2013 (con equilibrio de carga DNS)</th>
<th>Número de direcciones IP necesarias Lync Server 2013 (equilibrio de carga de hardware)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>segundo</p></td>
<td><p>segundo</p></td>
<td><p>1 (1 por VIP) + 2</p></td>
</tr>
<tr class="even">
<td><p>3</p></td>
<td><p>3</p></td>
<td><p>1 (1 por VIP) + 3</p></td>
</tr>
<tr class="odd">
<td><p>4</p></td>
<td><p>4</p></td>
<td><p>1 (1 por VIP) + 4</p></td>
</tr>
<tr class="even">
<td><p>2,5</p></td>
<td><p>2,5</p></td>
<td><p>1 (1 por VIP) + 5</p></td>
</tr>
</tbody>
</table>


Los principales aspectos a la hora de decantarse por una topología son la alta disponibilidad y el equilibrio de carga. El requisito de alta disponibilidad influye en la decisión del equilibrio de carga.

  - **Alta disponibilidad**   Si necesita una alta disponibilidad, implemente al menos dos servidores perimetrales en un grupo. Un solo grupo de servidores perimetrales admitirá hasta doce servidores perimetrales. En caso de que se requiera más capacidad, se pueden implementar varios grupos perimetrales. Como norma general, un 10% de una base de usuarios determinada necesitará acceso externo.
    
    <div>
    

    > [!IMPORTANT]
    > El generador de topologías le permitirá configurar hasta veinte servidores perimetrales en un único grupo de servidores perimetrales. El número máximo de servidores perimetrales probados y admitidos en un grupo de servidores es de 12 y el generador de topologías que permite un número mayor que 12 no debe interpretarse como compatibilidad implícita para más de doce servidores perimetrales en un único grupo de servidores perimetrales.

    
    </div>

  - **Equilibrio de carga de hardware**   El equilibrio de carga de hardware se admite para equilibrar la carga de los servidores perimetrales de Lync Server 2013 al usar direcciones IP enrutables públicamente para las interfaces externas del servidor perimetral. Por ejemplo, este método podría usarse en situaciones en las que se necesita conmutación por error para cualquiera de las siguientes aplicaciones:
    
      - Conectividad de mensajería instantánea pública
    
      - Federación con compañías que ejecutan Microsoft Office Communications Server 2007 o Microsoft Office Communications Server 2007 R2
    
      - Acceso externo a la mensajería unificada de Exchange 2007 o de Exchange 2010
        
        <div>
        

        > [!IMPORTANT]
        > El equilibrio de carga de DNS para Exchange 2010 SP1 y las versiones más recientes son compatibles con la mensajería unificada de Exchange.

        
        </div>
    
    Estas tres aplicaciones pueden seguir funcionando, pero no reparan en el equilibrio de carga DNS y solo se conectarán al primer servidor perimetral del grupo, de modo que si este no se encuentra disponible, la conexión no se establecerá. Por ejemplo, si hay varios servidores perimetrales en un grupo con los que se controla la carga de tráfico federado, solo un proxy de acceso recibirá el tráfico realmente, mientras que el resto permanecerá inactivo.

<div>


> [!IMPORTANT]
> Se recomienda usar el equilibrio de carga de DNS si está federando con compañías mediante Lync Server 2010 y Microsoft Office 365. Tenga en cuenta que hay un impacto significativo en el rendimiento si la mayoría de los socios federados usan Office Communications Server 2007 o Office Communications Server 2007 R2.



</div>

</div>

<span> </span>

</div>

</div>

</div>

