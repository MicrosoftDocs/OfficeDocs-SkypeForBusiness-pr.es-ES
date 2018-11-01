---
title: Plataformas de hardware de servidor para Lync Server 2013
TOCTitle: Plataforma de hardware de servidor
ms:assetid: c964c1c0-0153-472b-88ad-a38866e0df0c
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398835(v=OCS.15)
ms:contentKeyID: 48276658
ms.date: 07/24/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Plataformas de hardware de servidor para Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

Los roles de servidor de Lync Server 2013 y los equipos que ejecutan herramientas administrativas de Lync Server requieren un hardware de 64 bits.

El hardware específico que se usa para la implementación de Lync Server 2013 puede variar según los requisitos de uso y tamaño. En esta sección se describe el hardware recomendado. Aunque se trata de recomendaciones y no de requisitos, el uso de hardware que no cumpla estas recomendaciones puede repercutir considerablemente en el rendimiento y ocasionar otros problemas.

## Plataforma de hardware recomendada

Para obtener un mejor rendimiento, se aconseja ejecutar Lync Server en servidores que cumplan los requisitos de la tabla siguiente. Si usa un hardware menos eficaz, puede tener problemas de funcionalidad o un rendimiento deficiente. Tenga en cuenta que estos requisitos de hardware son más exigentes que los de las versiones anteriores de Lync Server, principalmente porque en Lync Server 2013 todos los servidores front-end ejecutan SQL Server.


> [!NOTE]
> La formación de equipos de NIC es compatible y debe ser transparente para Lync Server. Para más información, consulte <A href="https://go.microsoft.com/fwlink/p/?linkid=389910">Communications Server or Lync Server and network adapter teaming (Communications Server o Lync Server y formación de equipos de adaptadores de red)</A>.



### Hardware recomendado para los servidores front-end, back-end, Standard Edition, de chat persistente y para el Almacén de chat persistente y el Almacén de cumplimiento de chat persistente (roles de servidor back-end del servidor de chat persistente)

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Componente de hardware</th>
<th>Recomendado</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CPU</p></td>
<td><p>Procesador dual de 64 bits, seis núcleos, 2,26 gigahercios (GHz) o superior.</p>
<p>Los roles de servidor de Lync Server no admiten los procesadores Intel Itanium.</p></td>
</tr>
<tr class="even">
<td><p>Memoria</p></td>
<td><p>32 gigabytes (GB).</p></td>
</tr>
<tr class="odd">
<td><p>Disco</p></td>
<td><ul>
<li><p>8 o más unidades de disco duro (HHD) de 10 000 rpm con al menos 72 GB de espacio libre en disco.</p>
<p>Dos de los discos deben tener RAID 1; seis de los discos deben tener RAID 10.</p>
<p>O BIEN</p></li>
<li><p>Unidades de estado sólido (SSD) con un rendimiento igual al de 8 unidades de disco duro mecánicas de 10 000 rpm.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Red</p></td>
<td><ul>
<li><p>1 adaptador de red de puerto doble, 1 Gbps o superior (recomendado: 2, lo que requiere la formación de equipos con una sola dirección MAC y una sola dirección IP).</p>
<div>

> [!NOTE]
> No se admiten configuraciones duales ni de múltiples ubicaciones para Servidores front-end, Servidores back-end, Servidores Standard Edition y Servidores de chat persistente.<BR>Las conexiones ILO, DRAC, etc. no expuestas al sistema operativo y utilizadas para monitorizar y administrar el hardware de servidor no constituyen un servidor de hosts múltiples y, por lo tanto, son compatibles.


</div></li>
</ul></td>
</tr>
</tbody>
</table>


### Hardware recomendado para los servidores perimetrales, los servidores de mediación autónomos y los Directores

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Componente de hardware</th>
<th>Recomendado</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CPU</p></td>
<td><ul>
<li><p>Procesador dual de 64 bits, cuatro núcleos, 2,0 gigahercios (GHz) o superior.</p>
<p>O BIEN</p></li>
<li><p>Procesador de cuatro vías de 64 bits, de doble núcleo, 2,0 GHz o superior.</p></li>
</ul>
<p>Los roles de servidor de Lync Server no admiten los procesadores Intel Itanium.</p></td>
</tr>
<tr class="even">
<td><p>Memoria</p></td>
<td><p>16 gigabytes (GB).</p></td>
</tr>
<tr class="odd">
<td><p>Disco</p></td>
<td><ul>
<li><p>4 o más unidades de disco duro (HHD) de 10 000 rpm con al menos 72 GB de espacio libre en disco.</p>
<p>Los discos deben presentar una configuración de 2 unidades RAID 1.</p>
<p>O BIEN</p></li>
<li><p>Unidades de estado sólido (SSD) con un rendimiento igual al de 4 unidades de disco duro mecánicas de 10 000 rpm.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Red</p></td>
<td><ul>
<li><p>1 adaptador de red de puerto doble, 1 Gbps o superior (recomendado: 2, lo que requiere la formación de equipos con una sola dirección MAC y una sola dirección IP). En los Servidores perimetrales, se requieren 2 interfaces de red, y son compatibles en Servidores de mediación independientes.</p></li>
</ul>
<div>

> [!NOTE]
> No se admiten configuraciones duales ni de múltiples ubicaciones para Directores.<BR>Las conexiones ILO, DRAC, etc. no expuestas al sistema operativo y utilizadas para monitorizar y administrar el hardware de servidor no constituyen un servidor de hosts múltiples y, por lo tanto, son compatibles.


</div>
<p>Servidores perimetrales requiere dos interfaces de red que sean adaptadores de servidor de puerto doble, 1 Gbps o superior (o dos parejas de adaptadores de red, sumando un total de cuatro adaptadores, con cada pareja unida a una dirección MAC única y a una dirección IP única).</p>
<p>La instalación de tarjetas de interfaz de red (NIC) adicionales para configurar direcciones IP de RTC específicas se puede llevar a cabo en Servidores de mediación independientes.</p></td>
</tr>
</tbody>
</table>

