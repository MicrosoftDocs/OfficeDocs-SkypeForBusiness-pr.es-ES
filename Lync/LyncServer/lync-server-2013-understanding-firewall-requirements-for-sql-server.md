---
title: 'Lync Server 2013: Descripción de los requisitos de Firewall para SQL Server'
description: 'Lync Server 2013: Descripción de los requisitos de Firewall para SQL Server.'
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
ms.openlocfilehash: c434474b36ced0fe64b9398f7d0e6136ff523a93
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542386"
---
# <a name="understanding-firewall-requirements-for-sql-server-with-lync-server-2013"></a><span data-ttu-id="00244-103">Descripción de los requisitos de Firewall para SQL Server con Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="00244-103">Understanding firewall requirements for SQL Server with Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="00244-104">_**Última modificación del tema:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="00244-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="00244-105">Para una implementación de Standard Edition, las excepciones de Firewall se crean automáticamente durante la instalación de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="00244-105">For a Standard Edition deployment, firewall exceptions are created automatically during Lync Server 2013 Setup.</span></span> <span data-ttu-id="00244-106">Sin embargo, para las implementaciones de Enterprise Edition, debe configurar las excepciones de Firewall manualmente en el servidor back-end de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="00244-106">However, for Enterprise Edition deployments, you must configure the firewall exceptions manually on the SQL Server Back End Server.</span></span> <span data-ttu-id="00244-107">El protocolo TCP/IP permite que un puerto determinado se use una vez para una dirección IP determinada.</span><span class="sxs-lookup"><span data-stu-id="00244-107">The TCP/IP protocol allows for a given port to be used once for a given IP address.</span></span> <span data-ttu-id="00244-108">Esto significa que, para el servidor basado en SQL Server, puede asignar la instancia de base de datos predeterminada al puerto TCP 1433 predeterminado.</span><span class="sxs-lookup"><span data-stu-id="00244-108">This means that for the SQL Server-based server you can assign the default database instance the default TCP port 1433.</span></span> <span data-ttu-id="00244-109">Para las demás instancias deberá usar el Administrador de configuración de SQL Server para asignar puertos únicos y sin uso.</span><span class="sxs-lookup"><span data-stu-id="00244-109">For any other instances you will need to use the SQL Server Configuration Manager to assign unique and unused ports.</span></span> <span data-ttu-id="00244-110">En este tema se describen:</span><span class="sxs-lookup"><span data-stu-id="00244-110">This topic covers:</span></span>

  - <span data-ttu-id="00244-111">Requisitos de una excepción de firewall al usar la instancia predeterminada</span><span class="sxs-lookup"><span data-stu-id="00244-111">Requirements for a firewall exception when using the default instance</span></span>

  - <span data-ttu-id="00244-112">Requisitos de una excepción de firewall para el servicio SQL Server Browser</span><span class="sxs-lookup"><span data-stu-id="00244-112">Requirements for a firewall exception for the SQL Server Browser service</span></span>

  - <span data-ttu-id="00244-113">Requisitos de puertos de escucha estáticos al usar instancias especificadas por el usuario</span><span class="sxs-lookup"><span data-stu-id="00244-113">Requirements for static listening ports when using named instances</span></span>

<div>

## <a name="requirements-for-a-firewall-exception-when-using-the-default-instance"></a><span data-ttu-id="00244-114">Requisitos de una excepción de firewall al usar la instancia predeterminada</span><span class="sxs-lookup"><span data-stu-id="00244-114">Requirements for a Firewall Exception When Using the Default Instance</span></span>

<span data-ttu-id="00244-115">Si usa la instancia predeterminada de SQL Server para cualquier base de datos al implementar Lync Server 2013, se usan los siguientes requisitos de reglas de Firewall para ayudar a garantizar que el grupo de servidores front-end se comunica con la instancia predeterminada de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="00244-115">If you are using the SQL Server default instance for any database when deploying Lync Server 2013, the following firewall rule requirements are used to help ensure communication from the Front End pool to the SQL Server default instance.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="00244-116">Protocolo</span><span class="sxs-lookup"><span data-stu-id="00244-116">Protocol</span></span></th>
<th><span data-ttu-id="00244-117">Puerto</span><span class="sxs-lookup"><span data-stu-id="00244-117">Port</span></span></th>
<th><span data-ttu-id="00244-118">Dirección</span><span class="sxs-lookup"><span data-stu-id="00244-118">Direction</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="00244-119">TCP</span><span class="sxs-lookup"><span data-stu-id="00244-119">TCP</span></span></p></td>
<td><p><span data-ttu-id="00244-120">1433</span><span class="sxs-lookup"><span data-stu-id="00244-120">1433</span></span></p></td>
<td><p><span data-ttu-id="00244-121">Entrante para SQL Server</span><span class="sxs-lookup"><span data-stu-id="00244-121">Inbound to SQL Server</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="requirements-for-a-firewall-exception-for-the-sql-server-browser-service"></a><span data-ttu-id="00244-122">Requisitos de una excepción de firewall para el servicio SQL Server Browser</span><span class="sxs-lookup"><span data-stu-id="00244-122">Requirements for a Firewall Exception for the SQL Server Browser Service</span></span>

<span data-ttu-id="00244-123">El servicio SQL Server Browser buscará las instancias de base de datos y comunicará al puerto que la instancia (especificada por el usuario o predeterminada) está configurada para su uso.</span><span class="sxs-lookup"><span data-stu-id="00244-123">The SQL Server Browser service will locate database instances and communicate the port that the instance (named or default) is configured to use.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="00244-124">Protocolo</span><span class="sxs-lookup"><span data-stu-id="00244-124">Protocol</span></span></th>
<th><span data-ttu-id="00244-125">Puerto</span><span class="sxs-lookup"><span data-stu-id="00244-125">Port</span></span></th>
<th><span data-ttu-id="00244-126">Dirección</span><span class="sxs-lookup"><span data-stu-id="00244-126">Direction</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="00244-127">UDP</span><span class="sxs-lookup"><span data-stu-id="00244-127">UDP</span></span></p></td>
<td><p><span data-ttu-id="00244-128">1434</span><span class="sxs-lookup"><span data-stu-id="00244-128">1434</span></span></p></td>
<td><p><span data-ttu-id="00244-129">Entrada</span><span class="sxs-lookup"><span data-stu-id="00244-129">Inbound</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="requirements-for-static-listening-ports-when-using-named-instances"></a><span data-ttu-id="00244-130">Requisitos de puertos de escucha estáticos al usar instancias especificadas por el usuario</span><span class="sxs-lookup"><span data-stu-id="00244-130">Requirements for Static Listening Ports When Using Named Instances</span></span>

<span data-ttu-id="00244-131">Cuando se usan instancias con nombre en la configuración de SQL Server para bases de datos compatibles con Lync Server 2013, se configuran los puertos estáticos mediante el administrador de configuración de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="00244-131">When using named instances in the SQL Server configuration for databases supporting Lync Server 2013, you configure static ports by using SQL Server Configuration Manager.</span></span> <span data-ttu-id="00244-132">Una vez asignados los puertos estáticos a cada instancia especificada por el usuario, puede crear excepciones para cada puerto estático del firewall.</span><span class="sxs-lookup"><span data-stu-id="00244-132">After the static ports have been assigned to each named instance, you create exceptions for each static port in the firewall.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="00244-133">Protocolo</span><span class="sxs-lookup"><span data-stu-id="00244-133">Protocol</span></span></th>
<th><span data-ttu-id="00244-134">Puerto</span><span class="sxs-lookup"><span data-stu-id="00244-134">Port</span></span></th>
<th><span data-ttu-id="00244-135">Dirección</span><span class="sxs-lookup"><span data-stu-id="00244-135">Direction</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="00244-136">TCP</span><span class="sxs-lookup"><span data-stu-id="00244-136">TCP</span></span></p></td>
<td><p><span data-ttu-id="00244-137">Definido estáticamente</span><span class="sxs-lookup"><span data-stu-id="00244-137">Statically defined</span></span></p></td>
<td><p><span data-ttu-id="00244-138">Entrada</span><span class="sxs-lookup"><span data-stu-id="00244-138">Inbound</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="sql-server-documentation"></a><span data-ttu-id="00244-139">Documentación de SQL Server</span><span class="sxs-lookup"><span data-stu-id="00244-139">SQL Server Documentation</span></span>

<span data-ttu-id="00244-140">La documentación de Microsoft SQL Server 2012 proporciona instrucciones detalladas sobre cómo configurar el acceso a Firewall para bases de datos.</span><span class="sxs-lookup"><span data-stu-id="00244-140">Microsoft SQL Server 2012 documentation provides detailed guidance on how to configure firewall access for databases.</span></span> <span data-ttu-id="00244-141">Para obtener más información acerca de Microsoft SQL Server 2012, consulte "configuración del firewall de Windows para permitir el acceso a SQL Server" en [https://go.microsoft.com/fwlink/p/?linkId=218031](https://go.microsoft.com/fwlink/p/?linkid=218031) .</span><span class="sxs-lookup"><span data-stu-id="00244-141">For details about Microsoft SQL Server 2012, see “Configuring the Windows Firewall to Allow SQL Server Access” at [https://go.microsoft.com/fwlink/p/?linkId=218031](https://go.microsoft.com/fwlink/p/?linkid=218031).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

