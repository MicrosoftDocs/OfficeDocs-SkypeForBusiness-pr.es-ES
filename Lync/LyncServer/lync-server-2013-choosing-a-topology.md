---
title: 'Lync Server 2013: Elección de una topología'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Choosing a topology
ms:assetid: 23f2aeb6-fed9-4349-8fba-dcbf18ee4b04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425716(v=OCS.15)
ms:contentKeyID: 48183634
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3aa98d479ca2bfeaf6214bbd1e66bb3f41b09782
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842579"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="choosing-a-topology-in-lync-server-2013"></a>Elección de una topología en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

_**Última modificación del tema:** 2013-02-21_

Al elegir una topología, puede usar una de las siguientes opciones de topología compatibles:

<div>


> [!NOTE]
> A menos que se indique lo contrario, si tiene experiencia con Microsoft Lync Server 2010, verá que la guía se encuentra en gran medida.



</div>

  - [Servidor perimetral consolidado simple con direcciones IP privadas y NAT en Lync Server 2013](lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md)

  - [Topología perimetral consolidada de un solo equipo con direcciones IP públicas en Lync Server 2013](lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md)

  - [Servidor perimetral consolidado ampliado, equilibrio de carga DNS con direcciones IP privadas mediante NAT en Lync Server 2013](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - [Perímetro consolidado escalado, equilibrio de carga DNS con direcciones IP públicas en Lync Server 2013](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - [Servidor perimetral consolidado ampliado con equilibradores de carga de hardware en Lync Server 2013](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md)

<div>


> [!IMPORTANT]
> La interfaz perimetral interna y la interfaz perimetral externa necesitan usar el mismo tipo de equilibrio de carga. No puede usar equilibrio de carga de DNS en una interfaz perimetral y equilibrio de carga de hardware en la otra interfaz perimetral.



</div>

En la siguiente tabla se resumen las funciones disponibles en las topologías de Microsoft Lync Server 2013. Los encabezados de columna indican la funcionalidad disponible para una opción de configuración de borde determinada. Con la opción de borde escalado (con carga de DNS equilibrada) como ejemplo, puede ver que admite alta disponibilidad, puede usar direcciones IP privadas no enrutables (con NAT) o direcciones IP públicas enrutables asignadas a las interfaces externas de borde y reduce el costo porque un el equilibrador de carga de hardware no es necesario.

Escenarios de conmutación por error perimetral compatibles con el equilibrio de carga de DNS, son sesiones de punto a punto entre Lync, sesiones de conferencia de Lync, sesiones entre usuarios de Skype empresarial y Office 365. Los escenarios de conmutación por error perimetral que no se benefician del equilibrio de carga de DNS son la conmutación por error de mensajería unificada de Exchange de usuario remoto (anterior a Exchange 2010 SP1), la conectividad de mensajería instantánea pública (mi) y la Federación con servidores que ejecutan comunicaciones de Office. Servidores.

### <a name="summary-of-edge-server-topology-options"></a>Resumen de las opciones de topología de servidores perimetrales

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
<th>Se requieren registros DNS adicionales adicionales para el servidor perimetral externo en el grupo Edge</th>
<th>Conmutación por error de borde para sesiones de Lync a Lync</th>
<th>Conmutación por error de Edge para sesiones de Federación de Lync EUM/PIC/OCS</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Un solo lado con NAT</p></td>
<td><p>No</p></td>
<td><p>No</p></td>
<td><p>No</p></td>
<td><p>No</p></td>
</tr>
<tr class="even">
<td><p>Un solo lado con IP pública</p></td>
<td><p>No</p></td>
<td><p>No</p></td>
<td><p>No</p></td>
<td><p>No</p></td>
</tr>
<tr class="odd">
<td><p>Borde escalado (equilibrio de carga de DNS) con NAT</p></td>
<td><p>Sí</p></td>
<td><p>Sí</p></td>
<td><p>Sí</p></td>
<td><p>*</p></td>
</tr>
<tr class="even">
<td><p>Borde escalado (DNS carga equilibrada) mediante IP pública</p></td>
<td><p>Sí</p></td>
<td><p>Sí</p></td>
<td><p>Sí</p></td>
<td><p>*</p></td>
</tr>
<tr class="odd">
<td><p>Carga de hardware perimetral con escala equilibrada)</p></td>
<td><p>Sí</p></td>
<td><p>No (un registro A DNS por VIP)</p></td>
<td><p>Sí</p></td>
<td><p>Sí</p></td>
</tr>
</tbody>
</table>


**\*** La conmutación por error de la conectividad de mensajería instantánea pública (mi) y la Federación con servidores que ejecutan Office Communications Server no están disponibles con el equilibrio de carga de DNS. Mensajería unificada de Exchange (usuario remoto) la conmutación por error con el equilibrio de carga de DNS requiere Exchange Server 2010 SP1 o posterior.



> [!NOTE]
> Las topologías de borde y borde simple (equilibrio de carga de DNS) pueden usar:
> <ul><li><p>Direcciones IP públicas enrutables</p></li>
> <li><p>Dirección IP privada no enrutable si se usa la traducción de direcciones de red (NAT) simétrica</p></li>
>
> <ul><li> Si usa una dirección IP pública o una dirección IP privada con NAT, seguirá usando el mismo número de direcciones IP basadas en la elección de configuración en el generador de topología. Puede configurar el servidor perimetral para usar una única dirección IP con puertos distintos por servicio o usar direcciones IP distintas por cada servicio, pero use el mismo puerto (de forma predeterminada, TCP 443).</li></ul>>
> Si decide usar direcciones IP privadas no enrutables con NAT:
> <ul><li><p>Debe usar direcciones IP privadas enrutables en las tres interfaces externas</p></li>
> <li><p>Debe configurar NAT simétrico para el tráfico entrante y saliente</p></li></ul>>
> La topología de borde con escala (equilibrio de carga de hardware) debe usar direcciones IP públicas.



Lync Server 2013 admite la colocación de interfaces externas de acceso, conferencia web y borde A/V detrás de un enrutador o firewall que realice la traducción de direcciones de red (NAT) para topologías de servidores perimetrales únicos y escalables.

El uso de NAT para todas las interfaces externas de borde requiere el uso del equilibrio de carga de DNS. En comparación con el uso de equilibradores de carga de hardware, el uso del equilibrio de carga de DNS sin NAT le permite reducir el número de direcciones IP públicas por servidor perimetral en un grupo de límites, tal y como se describe en la siguiente lista:

  - Lync Server 2013 el límite consolidado escalado (DNS Load balanceed) requiere tres direcciones IP públicas para cada servidor perimetral de un grupo perimetral.

  - Lync Server 2013 el límite consolidado escalado (equilibrio de carga de hardware) requiere tres direcciones IP públicas para las direcciones IP virtuales del equilibrador de carga (un requisito de tiempo que no aumenta a medida que se agregan más servidores perimetrales al grupo) y tres direcciones IP públicas por Servidor perimetral en un grupo.

### <a name="ip-address-requirements-for-scaled-consolidated-edge-ip-address-per-role"></a>Requisitos de dirección IP para el límite consolidado escalado (dirección IP por función)

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Número de servidores perimetrales por grupo</th>
<th>Número de direcciones IP requeridas Lync Server 2013 (equilibrio de carga DNS)</th>
<th>Número de direcciones IP requeridas Lync Server 2013 (equilibrio de carga de hardware)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>2</p></td>
<td><p>6</p></td>
<td><p>3 (1 por VIP) + 6</p></td>
</tr>
<tr class="even">
<td><p>3</p></td>
<td><p>99,999</p></td>
<td><p>3 (1 por VIP) + 9</p></td>
</tr>
<tr class="odd">
<td><p>4</p></td>
<td><p>2007</p></td>
<td><p>3 (1 por VIP) + 12</p></td>
</tr>
<tr class="even">
<td><p>5</p></td>
<td><p>4,5</p></td>
<td><p>3 (1 por VIP) + 15</p></td>
</tr>
</tbody>
</table>


### <a name="ip-address-requirements-for-scaled-consolidated-edge-single-ip-address-for-all-roles"></a>Requisitos de dirección IP para arista consolidada escalada (dirección IP única para todas las funciones)

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Número de servidores perimetrales por grupo</th>
<th>Número de direcciones IP requeridas Lync Server 2013 (equilibrio de carga DNS)</th>
<th>Número de direcciones IP requeridas Lync Server 2013 (equilibrio de carga de hardware)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>2</p></td>
<td><p>2</p></td>
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
<td><p>5</p></td>
<td><p>5</p></td>
<td><p>1 (1 por VIP) + 5</p></td>
</tr>
</tbody>
</table>


Los principales puntos de decisiones para la selección de topología son la alta disponibilidad y el equilibrio de carga. El requisito de alta disponibilidad puede influir en la decisión de equilibrio de carga.

  - **Alta disponibilidad**   Si necesita una mayor disponibilidad, implemente un mínimo de dos servidores perimetrales en un grupo. Un único grupo de borde soportará hasta doce servidores perimetrales. Si se requiere más capacidad, puede implementar varias agrupaciones perimetrales. Como regla general, el 10% de una base de usuarios determinada necesitará acceso externo.
    
    <div>
    

    > [!IMPORTANT]
    > El generador de topología le permitirá configurar hasta veinte servidores perimetrales en un único Pool perimetral. La cantidad máxima admitida y probada de servidores perimetrales en un grupo es de doce y el creador de topologías que permite un número mayor de doce no se debe interpretar como compatibilidad implícita para más de doce servidores perimetrales en un solo grupo de borde.

    
    </div>

  - **Equilibrio de carga de hardware**   El equilibrio de carga de hardware es compatible con el equilibrio de carga de servidores perimetrales de Lync Server 2013 al usar direcciones IP enrutables públicas para las interfaces externas de Edge. Por ejemplo, usaría este enfoque en situaciones en las que se necesita la conmutación por error para cualquiera de las siguientes aplicaciones:
    
      - Conectividad de mensajería instantánea pública
    
      - Federación con empresas que ejecutan Microsoft Office Communications Server 2007 o Microsoft Office Communications Server 2007 R2
    
      - Acceso externo a la mensajería unificada de Exchange 2007 o UM de Exchange 2010
        
        <div>
        

        > [!IMPORTANT]
        > El equilibrio de carga de DNS para Exchange 2010 SP1 y versiones posteriores es compatible con la mensajería unificada de Exchange.

        
        </div>
    
    Estas tres aplicaciones seguirán funcionando, pero no son conscientes del equilibrio de carga de DNS y solo se conectarán al primer servidor perimetral del grupo. Si el servidor no está disponible, se producirá un error en la conexión. Por ejemplo, si se implementan varios servidores perimetrales en un grupo para controlar la carga de tráfico federada, solo un proxy de acceso realmente recibe tráfico mientras otros están inactivos.

<div>


> [!IMPORTANT]
> Se recomienda usar el equilibrio de carga de DNS si está en la Federación con empresas que usan Lync Server 2010 y Microsoft Office 365. Tenga en cuenta que se produce un importante impacto en el rendimiento si la mayoría de los socios federados usan Office Communications Server 2007 u Office Communications Server 2007 R2.



</div>

</div>

<span> </span>

</div>

</div>

</div>

