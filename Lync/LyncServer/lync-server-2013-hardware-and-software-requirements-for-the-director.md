---
title: "Lync Server 2013 : Conf. mat. et logicielle requise pour le directeur"
TOCTitle: Requisitos de hardware y software para el director
ms:assetid: 747b701e-7f97-46fe-91c5-1e8d9addf9f7
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398560(v=OCS.15)
ms:contentKeyID: 48275664
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Requisitos de hardware y software para el director en Lync Server 2013

 

_**Última modificación del tema:** 2016-05-19_

En esta sección se especifican los requisitos de hardware y software del Director, y los escenarios de combinación admitidos por el Director.

## Requisitos de hardware del Director

En la tabla siguiente se enumeran los requisitos de hardware para el Director:

### Requisitos de hardware del director

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Componente de hardware</th>
<th>Requisito mínimo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CPU</p></td>
<td><ul>
<li><p>Procesador de 64 bits, cuatro núcleos, 2,0 GHz o superior</p></li>
<li><p>Procesador de 64 bits, dos núcleos, 2,0 GHz o superior</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Memoria</p></td>
<td><p>4 gigabytes (GB).</p></td>
</tr>
<tr class="odd">
<td><p>Disco</p></td>
<td><ul>
<li><p>Unidad de disco duro a 10.000 rpm</p></li>
<li><p>Unidad de estado sólido (SSD) de alto rendimiento con un rendimiento igual o superior al de las unidades HDD a 10.000 rpm</p></li>
<li><p>Dos unidades RAID 10 (seccionado y reflejado) a 15.000 RPM para los archivos de datos de las bases de datos</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Red</p></td>
<td><ul>
<li><p>Adaptadores de red duales a 1 gigabit por segundo (Gbps) (recomendado)</p></li>
<li><p>Un solo adaptador de red de 1 Gbps (compatible)</p></li>
</ul></td>
</tr>
</tbody>
</table>


## Requisitos de software para el Director

El rol de Director solo puede implementarse en servidores que ejecutan Lync Server 2013 Enterprise Edition.

Se requiere uno de los siguientes operativos de 64 bits para todos los roles de Directores:

  - El sistema operativo Windows Server 2008 R2 Standard

  - El sistema operativo Windows Server 2008 R2 Enterprise

  - El sistema operativo Windows Server 2008 R2 Datacenter

  - El sistema operativo Windows Server 2012 Standard

  - El sistema operativo Windows Server 2012 Datacenter

Lync Server 2013 también requiere la instalación de los programas y las actualizaciones siguientes que se explican en el tema [Compatibilidad y requisitos para un servidor adicional en Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md).

## Combinación admitida

El rol de servidor de Director no puede instalarse con ningún otro rol de servidor de Lync Server 2013. Sin embargo, si no implementa un Director, los Servidores front-end asumirán el rol.

