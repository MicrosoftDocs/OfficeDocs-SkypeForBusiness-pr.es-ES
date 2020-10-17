---
title: 'Lync Server 2013: requisitos de hardware y software para el director'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hardware and software requirements for the Director
ms:assetid: 747b701e-7f97-46fe-91c5-1e8d9addf9f7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398560(v=OCS.15)
ms:contentKeyID: 48184517
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b00e294291bcafb859cc900ca71463f1315cdfe8
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536867"
---
# <a name="hardware-and-software-requirements-for-the-director-in-lync-server-2013"></a>Requisitos de hardware y software para el Director en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-20_

En esta sección se detallan los requisitos de hardware y software para el director y los escenarios de combinación compatibles con el director.

<div>

## <a name="hardware-requirements-for-the-director"></a>Requisitos de hardware para el director

En la siguiente tabla se enumeran los requisitos de hardware para el Director:

### <a name="hardware-requirements-for-the-director"></a>Requisitos de hardware para el director

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
<li><p>procesador de 64 bits, Quad-Core, 2,0 GHz o superior</p></li>
<li><p>procesador dual de 64 bits, doble núcleo, 2,0 GHz o superior</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Memoria</p></td>
<td><p>4 gigabytes (GB)</p></td>
</tr>
<tr class="odd">
<td><p>Disco</p></td>
<td><ul>
<li><p>unidad de disco duro (HDD) a 10.000 RPM</p></li>
<li><p>Unidad de estado sólido (SSD) de alto rendimiento con rendimiento igual o superior a un disco duro de 10K RPM</p></li>
<li><p>2x discos RAID 10 (seccionados y reflejados) a 15.000 RPM para archivos de datos de bases de datos</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Red</p></td>
<td><ul>
<li><p>Adaptadores de red duales de 1 Gigabit por segundo (Gbps) (recomendado)</p></li>
<li><p>Adaptador de red único de 1 Gbps (admitido)</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="software-requirements-for-the-director"></a>Requisitos de software para el director

El rol de Director solo se puede implementar en servidores que ejecuten Lync Server 2013 Enterprise Edition.

Se requiere uno de los siguientes sistemas operativos de 64 bits para los directores:

  - Sistema operativo Windows Server 2008 R2 Standard con Service Pack 1

  - El sistema operativo Windows Server 2008 R2 Enterprise con Service Pack 1

  - El sistema operativo Windows Server 2008 R2 Datacenter con Service Pack 1

  - Sistema operativo Windows Server 2012 Standard

  - El sistema operativo Windows Server 2012 Datacenter

Lync Server 2013 también requiere la instalación de los siguientes programas y actualizaciones que se detallan en el tema [compatibilidad y requisitos de servidor adicionales en Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md).

</div>

<div>

## <a name="supported-collocation"></a>Escenarios de instalación compatibles

El rol de servidor Director no se puede combinar con ningún otro rol de servidor en Lync Server 2013. Sin embargo, si no implementa un director, los servidores front-end asumirán el rol.

</div>

</div>

<span> </span>

</div>

</div>

</div>

