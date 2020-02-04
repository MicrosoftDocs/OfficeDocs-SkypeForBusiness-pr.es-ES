---
title: 'Lync Server 2013: Lista de comprobación para la implementación del control de admisión de llamadas'
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
ms.openlocfilehash: 0bf88529734530e70c4d0536d5337395ff0742d2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740750"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-call-admission-control-in-lync-server-2013"></a>Lista de comprobación para la implementación del control de admisión de llamadas en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-08_

Para planear de forma eficaz el control de admisión de llamadas (CAC), debe tener en cuenta lo siguiente:

  - Requisitos previos para implementar CAC.

  - Información necesaria para el CAC y las decisiones de configuración que debe realizar antes de la implementación.

<div>

## <a name="deployment-prerequisites-for-call-admission-control"></a>Requisitos previos de implementación para el control de admisión de llamadas

Antes de implementar el control de admisión de llamadas, debe haber implementado los servidores internos de Lync Server 2013, incluido un grupo de servidores front-end o un servidor Standard Edition.

</div>

<div>

## <a name="information-requirements-for-call-admission-control"></a>Requisitos de información para el control de admisión de llamadas

En la tabla siguiente se resume la información necesaria para implementar el control de admisión de llamadas.

### <a name="information-requirements-for-call-admission-control-deployment"></a>Requisitos de información para la implementación de control de admisión de llamadas

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
<td><p>Capacidades de Lync Server requeridas por su organización</p></td>
<td><ul>
<li><p>Capacidades que la organización debe admitir</p></li>
<li><p>Capacidades que se deben habilitar para usuarios individuales</p></li>
</ul></td>
<td><p><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Definición de los requisitos de la organización para el servicio de control de admisión de llamadas en Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Topologías y componentes que se van a implementar</p></td>
<td><ul>
<li><p>Los componentes relacionados con CAC se instalan automáticamente como parte de Lync Server 2013</p></li>
</ul></td>
<td><p><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Definición de los requisitos de la organización para el servicio de control de admisión de llamadas en Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Requisitos del sistema</p></td>
<td><ul>
<li><p>Requisitos de hardware</p></li>
<li><p>Requisitos de software</p></li>
<li><p>Requisitos de collocation</p></li>
</ul></td>
<td><p><a href="lync-server-2013-determining-your-system-requirements.md">Determinar los requisitos del sistema para Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Requisitos de infraestructura</p></td>
<td><ul>
<li><p>No se necesitan requisitos de infraestructura específicos para CAC</p></li>
</ul></td>
<td><p><a href="lync-server-2013-infrastructure-requirements-for-call-admission-control.md">Requisitos de infraestructura para el control de admisión de llamadas en Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Requisitos de interfaz de red</p></td>
<td><ul>
<li><p>Información de la interfaz interna y externa</p></li>
<li><p>Información de enrutamiento (incluida información sobre el blog de <a href="http://go.microsoft.com/fwlink/p/?linkid=203149">http://go.microsoft.com/fwlink/p/?LinkId=203149</a>NextHop en, canal de respuesta para clientes del equipo de Microsoft Lync Server)</p></li>
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
<td><p><a href="lync-server-2013-best-practices-for-call-admission-control.md">Procedimientos recomendados para el servicio de control de admisión de llamadas en Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Proceso de implementación</p></td>
<td><ul>
<li><p>Requisitos previos</p></li>
<li><p>Requisitos de información</p></li>
<li><p>Procesos y procedimientos</p></li>
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

