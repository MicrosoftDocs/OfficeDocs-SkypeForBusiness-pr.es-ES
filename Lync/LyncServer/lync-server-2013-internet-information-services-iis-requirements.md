---
title: 'Lync Server 2013: requisitos de Internet Information Services (IIS)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Internet Information Services (IIS) requirements
ms:assetid: 4f57a605-a8a9-4c5a-9a18-05ecb3d9ab6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398321(v=OCS.15)
ms:contentKeyID: 48184128
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9a086713c4c4c1ea5752c7e1b46ce46e48a0ea42
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42040949"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="internet-information-services-iis-requirements-in-lync-server-2013"></a><span data-ttu-id="d8685-102">Requisitos de Internet Information Services (IIS) en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d8685-102">Internet Information Services (IIS) requirements in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d8685-103">_**Última modificación del tema:** 2012-06-19_</span><span class="sxs-lookup"><span data-stu-id="d8685-103">_**Topic Last Modified:** 2012-06-19_</span></span>

<span data-ttu-id="d8685-104">Varios componentes de Lync Server 2013 necesitan Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="d8685-104">Several Lync Server 2013 components require Internet Information Services (IIS).</span></span> <span data-ttu-id="d8685-105">En este tema se describen las características específicas de IIS necesarias para admitir Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d8685-105">This topic describes the specific IIS features required to support Lync Server.</span></span> <span data-ttu-id="d8685-106">En los temas de esta sección se describen los requisitos de componentes específicos para IIS.</span><span class="sxs-lookup"><span data-stu-id="d8685-106">The topics in this section describe the requirements of specific components for IIS.</span></span>

<span data-ttu-id="d8685-p102">Al habilitar el rol servidor web (IIS) en Windows Server 2008, se instalan de forma predeterminada varios servicios de rol. En la siguiente tabla se describen los servicios adicionales de rol que se deben instalar al habilitar el rol servidor Web (IIS) en Windows Server 2008.</span><span class="sxs-lookup"><span data-stu-id="d8685-p102">When the Web Server (IIS) role is enabled on Windows Server 2008, various role services are installed by default. The following table describes the additional role services that must be installed when the Web Server (IIS) role is enabled on Windows Server 2008.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d8685-109">Servicio de rol</span><span class="sxs-lookup"><span data-stu-id="d8685-109">Role service</span></span></th>
<th><span data-ttu-id="d8685-110">Característica</span><span class="sxs-lookup"><span data-stu-id="d8685-110">Feature</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d8685-111">Características HTTP comunes</span><span class="sxs-lookup"><span data-stu-id="d8685-111">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="d8685-112">Redirección HTTP</span><span class="sxs-lookup"><span data-stu-id="d8685-112">HTTP Redirection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8685-113">Desarrollo de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="d8685-113">Application Development</span></span></p></td>
<td><p><span data-ttu-id="d8685-114">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="d8685-114">ASP.NET</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8685-115">Desarrollo de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="d8685-115">Application Development</span></span></p></td>
<td><p><span data-ttu-id="d8685-116">Extensibilidad de .NET</span><span class="sxs-lookup"><span data-stu-id="d8685-116">.NET Extensibility</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8685-117">Desarrollo de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="d8685-117">Application Development</span></span></p></td>
<td><p><span data-ttu-id="d8685-118">Extensiones ISAPI</span><span class="sxs-lookup"><span data-stu-id="d8685-118">ISAPI Extensions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8685-119">Desarrollo de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="d8685-119">Application Development</span></span></p></td>
<td><p><span data-ttu-id="d8685-120">Filtros ISAPI</span><span class="sxs-lookup"><span data-stu-id="d8685-120">ISAPI Filters</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8685-121">Estado y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="d8685-121">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="d8685-122">Herramientas de registro</span><span class="sxs-lookup"><span data-stu-id="d8685-122">Logging Tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8685-123">Estado y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="d8685-123">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="d8685-124">Seguimiento</span><span class="sxs-lookup"><span data-stu-id="d8685-124">Tracing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8685-125">Seguridad</span><span class="sxs-lookup"><span data-stu-id="d8685-125">Security</span></span></p></td>
<td><p><span data-ttu-id="d8685-126">Autenticación básica</span><span class="sxs-lookup"><span data-stu-id="d8685-126">Basic Authentication</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8685-127">Seguridad</span><span class="sxs-lookup"><span data-stu-id="d8685-127">Security</span></span></p></td>
<td><p><span data-ttu-id="d8685-128">Autenticación de Windows</span><span class="sxs-lookup"><span data-stu-id="d8685-128">Windows Authentication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8685-129">Herramientas de administración</span><span class="sxs-lookup"><span data-stu-id="d8685-129">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="d8685-130">Scripts y herramientas de administración de IIS</span><span class="sxs-lookup"><span data-stu-id="d8685-130">IIS Management Scripts and Tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8685-131">Herramientas de administración</span><span class="sxs-lookup"><span data-stu-id="d8685-131">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="d8685-132">Compatibilidad con la administración de IIS 6</span><span class="sxs-lookup"><span data-stu-id="d8685-132">IIS 6 Management Compatibility</span></span></p></td>
</tr>
</tbody>
</table>


<div>

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="seguridad" alt="security" /><span data-ttu-id="d8685-134">Nota de seguridad:</span><span class="sxs-lookup"><span data-stu-id="d8685-134">Security Note:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="d8685-135">Si usa IIS 7,0 en un sistema operativo Windows Server 2008, el programa de instalación de Lync Server deshabilita la autenticación de modo kernel en IIS.</span><span class="sxs-lookup"><span data-stu-id="d8685-135">If you are using IIS 7.0 on a Windows Server 2008 operating system, Lync Server Setup disables kernel mode authentication in IIS.</span></span></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d8685-136">En esta sección</span><span class="sxs-lookup"><span data-stu-id="d8685-136">In This Section</span></span>

  - [<span data-ttu-id="d8685-137">Requisitos de IIS para grupos de servidores front-end y servidores Standard Edition en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d8685-137">IIS requirements for Front End pools and Standard Edition servers in Lync Server 2013</span></span>](lync-server-2013-iis-requirements-for-front-end-pools-and-standard-edition-servers.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

