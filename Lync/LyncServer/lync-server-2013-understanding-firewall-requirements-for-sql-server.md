---
title: 'Lync Server 2013: Descripción de los requisitos de firewall para SQL Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Understanding firewall requirements for SQL Server
ms:assetid: 31d7df2c-589f-465e-be74-cf6767db190d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425818(v=OCS.15)
ms:contentKeyID: 48183781
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 586985c3059e12d358249a71dc2435c3be9254f1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850282"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="understanding-firewall-requirements-for-sql-server-with-lync-server-2013"></a>Descripción de los requisitos de firewall para SQL Server con Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-21_

Para una implementación de Standard Edition, las excepciones de Firewall se crean automáticamente durante la instalación de Lync Server 2013. Sin embargo, para las implementaciones de Enterprise Edition, debe configurar las excepciones de Firewall manualmente en el servidor back-end de SQL Server. El protocolo TCP/IP permite que un puerto determinado se use una vez para una determinada dirección IP. Esto significa que para el servidor basado en SQL Server, puede asignar la instancia de base de datos predeterminada al puerto TCP predeterminado 1433. En el caso de otras instancias, tendrá que usar el administrador de configuración de SQL Server para asignar puertos únicos y sin usar. Este tema trata:

  - Requisitos para una excepción de Firewall al usar la instancia predeterminada

  - Requisitos de una excepción de Firewall para el servicio SQL Server Browser

  - Requisitos para puertos de escucha estáticos al utilizar instancias con nombre

<div>

## <a name="requirements-for-a-firewall-exception-when-using-the-default-instance"></a>Requisitos para una excepción de Firewall al usar la instancia predeterminada

Si está usando la instancia predeterminada de SQL Server para cualquier base de datos al implementar Lync Server 2013, se usan los siguientes requisitos de regla de Firewall para garantizar la comunicación desde el grupo de servidores front-end a la instancia predeterminada de SQL Server.


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
<td><p>Entrante a SQL Server</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="requirements-for-a-firewall-exception-for-the-sql-server-browser-service"></a>Requisitos de una excepción de Firewall para el servicio SQL Server Browser

El servicio SQL Server Browser buscará instancias de base de datos y comunicará el puerto que la instancia (con nombre o predeterminado) está configurada para usar.


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

## <a name="requirements-for-static-listening-ports-when-using-named-instances"></a>Requisitos para puertos de escucha estáticos al utilizar instancias con nombre

Al usar instancias con nombre en la configuración de SQL Server para bases de datos compatibles con Lync Server 2013, debe configurar los puertos estáticos mediante el administrador de configuración de SQL Server. Después de asignar los puertos estáticos a cada instancia con nombre, cree excepciones para cada puerto estático en el firewall.


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
<td><p>Definición estática</p></td>
<td><p>Entrada</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="sql-server-documentation"></a>Documentación de SQL Server

La documentación de 2012 de Microsoft SQL Server proporciona instrucciones detalladas sobre cómo configurar el acceso a Firewall para bases de datos. Para obtener más información sobre Microsoft SQL Server 2012, consulte "configurar el Firewall de Windows para permitir el acceso [http://go.microsoft.com/fwlink/p/?linkId=218031](http://go.microsoft.com/fwlink/p/?linkid=218031)a SQL Server" en.

</div>

</div>

<span> </span>

</div>

</div>

</div>

