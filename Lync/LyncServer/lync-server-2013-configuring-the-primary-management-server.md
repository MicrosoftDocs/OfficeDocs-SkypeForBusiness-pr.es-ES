---
title: 'Lync Server 2013: configurar el servidor de administración principal'
description: 'Lync Server 2013: configurar el servidor de administración principal.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the primary management server
ms:assetid: 44e2e9a8-c130-4c66-9871-80b1ff11b27c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204844(v=OCS.15)
ms:contentKeyID: 48183986
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 43f986f4f03e96cafa27dfdd302bb98a00d8b2ae
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544166"
---
# <a name="configuring-the-primary-management-server-in-lync-server-2013"></a><span data-ttu-id="f55b3-103">Configurar el servidor de administración principal en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f55b3-103">Configuring the primary management server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f55b3-104">_**Última modificación del tema:** 2014-03-19_</span><span class="sxs-lookup"><span data-stu-id="f55b3-104">_**Topic Last Modified:** 2014-03-19_</span></span>

<span data-ttu-id="f55b3-105">Para sacar el máximo partido a las nuevas funciones de supervisión de estado incluidas en los administradores de Microsoft Lync Server 2013, primero debe designar un equipo para que actúe como servidor de administración principal; en ese equipo, debe instalar System Center Operations Manager 2007 R2 o System Center Operations Manager 2012.</span><span class="sxs-lookup"><span data-stu-id="f55b3-105">In order to take full advantage of the new health monitoring capabilities included in Microsoft Lync Server 2013 administrators must first designate a computer to act as your primary management server; on that computer you must then install System Center Operations Manager 2007 R2 or System Center Operations Manager 2012.</span></span> <span data-ttu-id="f55b3-106">Además, debe instalar una versión compatible de SQL Server para que funcione como su base de datos back-end de Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="f55b3-106">In addition, you must install a supported version of SQL Server to function as your Operations Manager back-end database.</span></span> <span data-ttu-id="f55b3-107">Si usa System Center Operations Manager 2012, puede usar cualquiera de las siguientes versiones de SQL Server como base de datos back-end:</span><span class="sxs-lookup"><span data-stu-id="f55b3-107">If you are using System Center Operations Manager 2012 you can use any of the following versions of SQL Server as your back-end database:</span></span>

  - <span data-ttu-id="f55b3-108">SQL Server 2008 R2 Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="f55b3-108">SQL Server 2008 R2 Service Pack 1</span></span>

  - <span data-ttu-id="f55b3-109">SQL Server 2008 R2 Service Pack 2</span><span class="sxs-lookup"><span data-stu-id="f55b3-109">SQL Server 2008 R2 Service Pack 2</span></span>

<span data-ttu-id="f55b3-110">Si usa System Center Operations Manager 2007 R2, se recomienda que instale SQL Server 2005 Service Pack 4 o SQL Server 2008 Service Pack 3.</span><span class="sxs-lookup"><span data-stu-id="f55b3-110">If you are using System Center Operations Manager 2007 R2 it is recommended that you install either SQL Server 2005 Service Pack 4 or SQL Server 2008 Service Pack 3.</span></span> <span data-ttu-id="f55b3-111">También puede usar SQL Server 2008 R2 como base de datos back-end para System Center Operations Manager 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="f55b3-111">You can also use SQL Server 2008 R2 as the backend database for System Center Operations Manager 2007 R2.</span></span> <span data-ttu-id="f55b3-112">Vea el apéndice 1 de esta documentación para obtener más información sobre cómo configurar SQL Server 2008 R2 para que funcione con System Center Operations Manager 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="f55b3-112">See Appendix 1 of this documentation for more information on configuring SQL Server 2008 R2 to work with System Center Operations Manager 2007 R2.</span></span>

<span data-ttu-id="f55b3-113">Al instalar System Center Operations Manager 2012 o System Center Operations Manager 2007 R2, debe instalar todos los componentes de ese producto, incluidos:</span><span class="sxs-lookup"><span data-stu-id="f55b3-113">When you install System Center Operations Manager 2012 or System Center Operations Manager 2007 R2 you need to install all the components of that product, including:</span></span>

  - <span data-ttu-id="f55b3-114">Base de datos operativa</span><span class="sxs-lookup"><span data-stu-id="f55b3-114">Operational database</span></span>

  - <span data-ttu-id="f55b3-115">Servidor</span><span class="sxs-lookup"><span data-stu-id="f55b3-115">Server</span></span>

  - <span data-ttu-id="f55b3-116">Consola</span><span class="sxs-lookup"><span data-stu-id="f55b3-116">Console</span></span>

  - <span data-ttu-id="f55b3-117">Cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f55b3-117">Windows PowerShell cmdlets</span></span>

  - <span data-ttu-id="f55b3-118">Consola web</span><span class="sxs-lookup"><span data-stu-id="f55b3-118">Web console</span></span>

  - <span data-ttu-id="f55b3-119">Reporting</span><span class="sxs-lookup"><span data-stu-id="f55b3-119">Reporting</span></span>

  - <span data-ttu-id="f55b3-120">Almacén de datos</span><span class="sxs-lookup"><span data-stu-id="f55b3-120">Data warehouse</span></span>

<span data-ttu-id="f55b3-121">Estos componentes y su instalación no se explicarán en detalle en este documento.</span><span class="sxs-lookup"><span data-stu-id="f55b3-121">These components and their installation will not be discussed in detail in this document.</span></span> <span data-ttu-id="f55b3-122">Para obtener más información sobre System Center Operations Manager 2007 R2, consulte la documentación de Operations Manager 2007 R2 en <https://go.microsoft.com/fwlink/p/?linkid=257526> y la documentación de System Center Operations manager 2012 en <https://go.microsoft.com/fwlink/p/?linkid=257527> .</span><span class="sxs-lookup"><span data-stu-id="f55b3-122">For details about System Center Operations Manager 2007 R2, see the Operations Manager 2007 R2 documentation at <https://go.microsoft.com/fwlink/p/?linkid=257526> and the System Center Operations Manager 2012 documentation at <https://go.microsoft.com/fwlink/p/?linkid=257527>.</span></span> <span data-ttu-id="f55b3-123">Debe seguir estas instrucciones si va a usar SQL Server 2005 o SQL Server 2008 Service Pack 1 como base de datos back-end.</span><span class="sxs-lookup"><span data-stu-id="f55b3-123">You should follow those instructions if you are going to use SQL Server 2005 or SQL Server 2008 Service Pack 1 as your back-end database.</span></span>

<span data-ttu-id="f55b3-124">Si usa System Center Operations Manager 2012, puede usar SQL Server 2012 como base de datos back-end.</span><span class="sxs-lookup"><span data-stu-id="f55b3-124">If you are using System Center Operations Manager 2012 then you can use SQL Server 2012 as your back-end database.</span></span> <span data-ttu-id="f55b3-125">Para obtener más información sobre SQL Server 2012, vea los libros en pantalla de SQL Server 2012 en [https://go.microsoft.com/fwlink/p/?LinkId=257528](https://go.microsoft.com/fwlink/p/?linkid=257528) .</span><span class="sxs-lookup"><span data-stu-id="f55b3-125">For details about SQL Server 2012, see Books Online for SQL Server 2012 at [https://go.microsoft.com/fwlink/p/?LinkId=257528](https://go.microsoft.com/fwlink/p/?linkid=257528).</span></span>

<span data-ttu-id="f55b3-126">Tenga en cuenta que solo puede tener un único servidor de administración principal por cada implementación de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f55b3-126">Keep in mind that you can only have a single Primary Management Server per Lync Server deployment.</span></span> <span data-ttu-id="f55b3-127">Además, aunque puede usar System Center Operations Manager 2012 o System Center Operations Manager 2007 R2, no puede ejecutar las dos aplicaciones simultáneamente; debe elegir una o la otra.</span><span class="sxs-lookup"><span data-stu-id="f55b3-127">Also, while you can use either System Center Operations Manager 2012 or System Center Operations Manager 2007 R2, you cannot run the two applications simultaneously—you must choose one or the other.</span></span> <span data-ttu-id="f55b3-128">Por ejemplo, si ejecuta System Center Operations Manager 2012, todos los agentes de System Center también deben ejecutar System Center Operations Manager 2012.</span><span class="sxs-lookup"><span data-stu-id="f55b3-128">For example, if you are running System Center Operations Manager 2012 then all your System Center agents must also be running System Center Operations Manager 2012.</span></span> <span data-ttu-id="f55b3-129">No puede haber algunos agentes ejecutando System Center Operations Manager 2012 y otros agentes que ejecutan System Center Operations Manager 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="f55b3-129">You cannot have some agents running System Center Operations Manager 2012 and other agents running System Center Operations Manager 2007 R2.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

