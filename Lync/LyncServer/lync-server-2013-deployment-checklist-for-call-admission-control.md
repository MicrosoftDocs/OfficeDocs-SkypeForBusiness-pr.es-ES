---
title: 'Lync Server 2013: lista de comprobación para la implementación del control de admisión de llamadas'
description: 'Lync Server 2013: lista de comprobación para la implementación del control de admisión de llamadas.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for call admission control
ms:assetid: 7e56a169-3e63-44ab-bf28-1fdeb52381c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398631(v=OCS.15)
ms:contentKeyID: 48184621
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ea5b16d41228faf01637e7e0d78f5ce56f950a19
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557696"
---
# <a name="deployment-checklist-for-call-admission-control-in-lync-server-2013"></a>Lista de comprobación para la implementación del control de admisión de llamadas en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-08_

Para planear de forma eficaz el servicio de control de admisión de llamadas (CAC), debe tener en cuenta lo siguiente:

  - Requisitos previos para implementar el CAC.

  - Información necesaria para el CAC y las decisiones de configuración que debe tomar antes de la implementación.

<div>

## <a name="deployment-prerequisites-for-call-admission-control"></a>Requisitos previos del control de admisión de llamadas

Antes de implementar el control de admisión de llamadas, debe haber implementado ya los servidores internos de Lync Server 2013, incluido un grupo de servidores front-end o un servidor Standard Edition.

</div>

<div>

## <a name="information-requirements-for-call-admission-control"></a>Requisitos de información para el control de admisión de llamadas

La siguiente tabla resume la información requerida para implementar el control de admisión de llamadas.

### <a name="information-requirements-for-call-admission-control-deployment"></a>Requisitos de información para implementar el control de admisión de llamadas

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Información</th>
<th>Resumen de la información necesaria</th>
<th>Documentación</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Capacidades de Lync Server que necesita su organización</p></td>
<td><ul>
<li><p>Funcionalidades que admitirá su organización</p></li>
<li><p>Funcionalidades que se habilitarán para usuarios individuales</p></li>
</ul></td>
<td><p><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Definición de los requisitos para el control de admisión de llamadas en Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Topologías y componentes que se implementarán</p></td>
<td><ul>
<li><p>Los componentes relacionados con CAC se instalan automáticamente como parte de Lync Server 2013</p></li>
</ul></td>
<td><p><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Definición de los requisitos para el control de admisión de llamadas en Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Requisitos del sistema</p></td>
<td><ul>
<li><p>Requisitos de hardware</p></li>
<li><p>Requisitos de software</p></li>
<li><p>Requisitos de combinación</p></li>
</ul></td>
<td><p><a href="lync-server-2013-determining-your-system-requirements.md">Determinación de los requisitos del sistema para Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Requisitos de infraestructura</p></td>
<td><ul>
<li><p>No se necesitan requisitos específicos de infraestructura para el CAC</p></li>
</ul></td>
<td><p><a href="lync-server-2013-infrastructure-requirements-for-call-admission-control.md">Requisitos de infraestructura para el control de admisión de llamadas en Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Requisitos de la interfaz de red</p></td>
<td><ul>
<li><p>Información de la interfaz interna y externa</p></li>
<li><p>Información de enrutamiento (incluida información sobre el blog de NextHop, en el <a href="https://go.microsoft.com/fwlink/p/?linkid=203149">https://go.microsoft.com/fwlink/p/?LinkId=203149</a> canal de respuesta del cliente del equipo de Microsoft Lync Server)</p></li>
</ul></td>
<td><p><a href="lync-server-2013-deploying-external-user-access.md">Implementar el acceso de usuarios externos en Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Estrategia de implementación</p></td>
<td><ul>
<li><p>Secuencia de implementación</p></li>
<li><p>Grupo de trabajo o dominio</p></li>
<li><p>Seguridad</p></li>
<li><p>Supervisión y auditoría</p></li>
<li><p>Consideraciones de hardware</p></li>
</ul></td>
<td><p><a href="lync-server-2013-best-practices-for-call-admission-control.md">Procedimientos recomendados para el control de admisión de llamadas en Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Proceso de implementación</p></td>
<td><ul>
<li><p>Requisitos previos</p></li>
<li><p>Requisitos de información</p></li>
<li><p>Proceso y procedimientos</p></li>
</ul></td>
<td><p><a href="lync-server-2013-configure-call-admission-control.md">Configurar el control de admisión de llamadas en Lync Server 2013</a></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

