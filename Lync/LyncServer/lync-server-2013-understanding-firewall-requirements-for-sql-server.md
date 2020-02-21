---
title: 'Lync Server 2013: Descripción de los requisitos de Firewall para SQL Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Understanding firewall requirements for SQL Server
ms:assetid: 31d7df2c-589f-465e-be74-cf6767db190d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425818(v=OCS.15)
ms:contentKeyID: 48183781
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 57f32d84e4cd08c40f95a47af7c988599678c972
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193173"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="understanding-firewall-requirements-for-sql-server-with-lync-server-2013"></a>Descripción de los requisitos de Firewall para SQL Server con Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-21_

Para una implementación de Standard Edition, las excepciones de Firewall se crean automáticamente durante la instalación de Lync Server 2013. Sin embargo, para las implementaciones de Enterprise Edition, debe configurar las excepciones de Firewall manualmente en el servidor back-end de SQL Server. El protocolo TCP/IP permite que un puerto determinado se use una vez para una dirección IP determinada. Esto significa que, para el servidor basado en SQL Server, puede asignar la instancia de base de datos predeterminada al puerto TCP 1433 predeterminado. Para las demás instancias deberá usar el Administrador de configuración de SQL Server para asignar puertos únicos y sin uso. En este tema se describen:

  - Requisitos de una excepción de firewall al usar la instancia predeterminada

  - Requisitos de una excepción de firewall para el servicio SQL Server Browser

  - Requisitos de puertos de escucha estáticos al usar instancias especificadas por el usuario

<div>

## <a name="requirements-for-a-firewall-exception-when-using-the-default-instance"></a>Requisitos de una excepción de firewall al usar la instancia predeterminada

Si usa la instancia predeterminada de SQL Server para cualquier base de datos al implementar Lync Server 2013, se usan los siguientes requisitos de reglas de Firewall para ayudar a garantizar que el grupo de servidores front-end se comunica con la instancia predeterminada de SQL Server.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Protocolo</th>
<th>Puerto</th>
<th>Dirección</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>TCP</p></td>
<td><p>1433</p></td>
<td><p>Entrante para SQL Server</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="requirements-for-a-firewall-exception-for-the-sql-server-browser-service"></a>Requisitos de una excepción de firewall para el servicio SQL Server Browser

El servicio SQL Server Browser buscará las instancias de base de datos y comunicará al puerto que la instancia (especificada por el usuario o predeterminada) está configurada para su uso.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Protocolo</th>
<th>Puerto</th>
<th>Dirección</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>UDP</p></td>
<td><p>1434</p></td>
<td><p>Entrada</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="requirements-for-static-listening-ports-when-using-named-instances"></a>Requisitos de puertos de escucha estáticos al usar instancias especificadas por el usuario

Cuando se usan instancias con nombre en la configuración de SQL Server para bases de datos compatibles con Lync Server 2013, se configuran los puertos estáticos mediante el administrador de configuración de SQL Server. Una vez asignados los puertos estáticos a cada instancia especificada por el usuario, puede crear excepciones para cada puerto estático del firewall.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Protocolo</th>
<th>Puerto</th>
<th>Dirección</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>TCP</p></td>
<td><p>Definido estáticamente</p></td>
<td><p>Entrada</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="sql-server-documentation"></a>Documentación de SQL Server

La documentación de Microsoft SQL Server 2012 proporciona instrucciones detalladas sobre cómo configurar el acceso a Firewall para bases de datos. Para obtener más información acerca de Microsoft SQL Server 2012, consulte "configuración del firewall de Windows para permitir el [https://go.microsoft.com/fwlink/p/?linkId=218031](https://go.microsoft.com/fwlink/p/?linkid=218031)acceso a SQL Server" en.

</div>

</div>

<span> </span>

</div>

</div>

</div>

