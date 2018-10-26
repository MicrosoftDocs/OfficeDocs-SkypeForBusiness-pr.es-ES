---
title: 'Lync Server 2013: Elección de una topología'
TOCTitle: Elección de una topología
ms:assetid: 23f2aeb6-fed9-4349-8fba-dcbf18ee4b04
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg425716(v=OCS.15)
ms:contentKeyID: 48274689
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Elección de una topología en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

Al elegir una topología, puede usar una de las siguientes opciones compatibles:


> [!NOTE]  
> A menos que se indique otra cosa, si tiene experiencia con Microsoft Lync Server 2010, encontrará que las instrucciones aquí no han cambiado en gran parte.



  - [Servidor perimetral consolidado simple con direcciones IP privadas y NAT en Lync Server 2013](lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md)

  - [Topología perimetral consolidada de un solo equipo con direcciones IP públicas en Lync Server 2013](lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md)

  - [Servidor perimetral consolidado ampliado, equilibrio de carga DNS con direcciones IP privadas mediante NAT en Lync Server 2013](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - [Perímetro consolidado escalado, equilibrio de carga DNS con direcciones IP públicas en Lync Server 2013](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - [Servidor perimetral consolidado ampliado con equilibradores de carga de hardware en Lync Server 2013](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md)

> [!IMPORTANT]  
> La interfaz perimetral interna y la interfaz perimetral externa deben usar el mismo tipo de equilibrio de carga. No puede usar equilibrio de carga DNS en una interfaz perimetral y equilibrio de carga de hardware en la otra interfaz perimetral.


En la siguiente tabla se resume la funcionalidad que disponible con las topologías de Microsoft Lync Server 2013 admitidas. Los encabezados de columna indican la funcionalidad disponible con una opción de configuración perimetral determinada. Si tomamos la opción perimetral escalada (DNS con equilibro de carga) como ejemplo, veremos que admite una alta disponibilidad, puede usar direcciones IP privadas no enrutables (con NAT) o direcciones IP públicas enrutables asignadas a las interfaces perimetrales externas y reduce el costo dado que no necesita un equilibrador de carga de hardware.

Escenarios de conmutación por error de servidor perimetral compatibles con equilibrio de carga de DNS son sesiones punto a punto de Lync a Lync, sesiones de conferencia de Lync, sesiones de Lynca PSTN y Office 365. Escenarios de conmutación por error de servidor perimetral que no se benefician del equilibrio de carga de DNS son la conmutación por error para el usuario remoto de Mensajería unificada de Exchange (UM) (antes de Exchange 2010 SP1), la conectividad de mensajería instantánea pública (MI) y la federación con servidores que ejecutan Office Communications Server.

### Resumen de opciones de topología de servidores perimetrales

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
<th>Conmutación por error de servidores perimetrales para sesiones de Lync a Lync</th>
<th>Conmutación por error de servidores perimetrales para sesiones de Federación EUM/PIC/OCS de Lync a Lync</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Perimetral simple usando NAT</p></td>
<td><p>N.º</p></td>
<td><p>N.º</p></td>
<td><p>N.º</p></td>
<td><p>N.º</p></td>
</tr>
<tr class="even">
<td><p>Perimetral simple usando IP pública</p></td>
<td><p>N.º</p></td>
<td><p>N.º</p></td>
<td><p>N.º</p></td>
<td><p>N.º</p></td>
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


**\*** La conmutación por error para conectividad de mensajería instantánea pública (MI) y la federación con servidores que ejecutan Office Communications Server no están disponibles con el equilibrio de carga DNS. La conmutación por error Mensajería unificada de Exchange (usuario remoto) usando el equilibrio de carga DNS requiere Exchange Server 2010 SP1 o versiones más recientes.

> [!NOTE]  
> Las topologías de perimetral simple y perimetral escalada (con equilibrio de carga DNS) pueden usar:
> <ul>
> <li><p>Direcciones IP públicas enrutables</p></li>
> <li><p>Dirección IP privada no enrutable si se usa la traducción de direcciones de red (NAT) simétrica</p></li></ul>
> 
> Si usa la dirección IP pública o la dirección IP privada con NAT, seguirá usando el mismo número de direcciones IP establecido en la configuración de Generador de topologías. Puede configurar el Servidor perimetral para que use una sola dirección IP con diferentes puertos por servicio o para que use distintas direcciones IP por servicio, pero en el mismo puerto (de manera predeterminada, TCP 443).
> 
> Si decide usar direcciones IP privadas no enrutables con NAT:
> 
> <ul><li><p>Debe usar direcciones IP privadas enrutables en las tres interfaces externas</p></li>
> <li><p>Debe configurar NAT simétrica para tráfico entrante y saliente</p></li></ul>
>
> La topología perimetral escalada (equil. carga hardware) debe usar direcciones IP.


Lync Server 2013 es compatible con interfaces perimetrales externas de acceso, conferencia web y A/V detrás de un enrutador o servidor de firewall que realiza la traducción de direcciones de red (NAT) para topologías de servidor perimetral consolidadas escaladas y únicas.

El uso de NAT para todas las interfaces externas perimetrales requiere el uso del equilibrio de carga de DNS. En comparación con el uso de equilibradores de carga de hardware, el uso de equilibrio de carga de DNS sin NAT permite reducir el número de la dirección IP pública por servidor perimetral en un grupo de servidores perimetrales, como se describe en la lista siguiente:

  - Lync Server 2013 Perimetral consolidada escalada (con equilibrio de carga DNS) Requiere tres direcciones IP públicas para cada servidor perimetral en un grupo.

  - Lync Server 2013 Perimetral consolidada escalada (con equilibrio de carga de hardware) Requiere tres direcciones IP públicas para direcciones IP virtuales del equilibrador de carga (requisito de una vez que no incrementa a medida que se agregan servidores perimetrales al grupo) más tres direcciones IP por servidor perimetral en un grupo.

### Requisitos de dirección IP para servidor perimetral consolidado escalado (dirección IP por rol)

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
<th>Número de direcciones IP necesarias Lync Server 2013 (con equilibrio de carga de hardware)</th>
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
<td><p>9</p></td>
<td><p>3 (1 por VIP) + 9</p></td>
</tr>
<tr class="odd">
<td><p>4</p></td>
<td><p>12</p></td>
<td><p>3 (1 por VIP) + 12</p></td>
</tr>
<tr class="even">
<td><p>5</p></td>
<td><p>15</p></td>
<td><p>3 (1 por VIP) + 15</p></td>
</tr>
</tbody>
</table>


### Requisitos de dirección IP para servidor perimetral consolidado escalado (dirección IP única para todos los roles)

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
<th>Número de direcciones IP necesarias Lync Server 2013 (con equilibrio de carga de hardware)</th>
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


Los principales aspectos a la hora de decantarse por una topología son la alta disponibilidad y el equilibrio de carga. El requisito de alta disponibilidad influye en la decisión del equilibrio de carga.

  - **Alta disponibilidad**   Si necesita una gran disponibilidad, implemente dos servidores perimetrales en un grupo como mínimo. Un solo grupo de servidores perimetrales admitirá un máximo de doce servidores perimetrales. En caso de que se requiera más capacidad, se pueden implementar varios grupos perimetrales. Como regla general, un 10% de una base de usuarios determinada necesitará acceso externo.
    
  > [!IMPORTANT]  
  > La Generador de topologías le permitirá configurar hasta veinte Servidores perimetrales en un solo Grupo de servidores perimetrales. El número máximo de Servidores perimetrales probados y admitidos en un grupo es doce y el hecho de que la Generador de topologías permita una cantidad mayor no debe interpretarse como la compatibilidad implícita con más de doce Servidores perimetrales en un solo Grupo de servidores perimetrales.


  - **Equilibrio de carga de hardware**   Se admite el equilibrio de carga de hardware para el equilibrio de carga de Lync Server 2013  Servidores perimetrales cuando se usan direcciones IP enrutables públicamente para las interfaces externas perimetrales. Por ejemplo, este método podría usarse en situaciones en las que se necesita conmutación por error para cualquiera de las siguientes aplicaciones:
    
      - Conectividad de mensajería instantánea pública
    
      - Federación con compañías que ejecutan Microsoft Office Communications Server 2007 o Microsoft Office Communications Server 2007 R2
    
      - Acceso externo a la mensajería unificada de Exchange 2007 o de Exchange 2010
        
        > [!IMPORTANT]  
        > Se admite el equilibrio de carga DNS para Exchange 2010 SP1 y opciones más recientes para Mensajería unificada de Exchange.
    
    Estas tres aplicaciones pueden seguir funcionando, pero no reparan en el equilibrio de carga DNS y solo se conectarán al primer servidor perimetral del grupo, de modo que si este no se encuentra disponible, la conexión no se establecerá. Por ejemplo, si hay varios servidores perimetrales en un grupo con los que se controla la carga de tráfico federado, solo un proxy de acceso recibirá el tráfico realmente, mientras que el resto permanecerá inactivo.

> [!IMPORTANT]  
> Se aconseja usar el equilibrio de carga DNS si va a federar con compañías por medio de Lync Server 2010 y Microsoft Office 365. Tenga presente que esto tendrá un enorme impacto en el rendimiento si la mayoría de los socios federados usa Office Communications Server 2007 o Office Communications Server 2007 R2.

