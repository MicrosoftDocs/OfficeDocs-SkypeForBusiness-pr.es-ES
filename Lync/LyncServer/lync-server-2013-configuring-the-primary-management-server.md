---
title: 'Lync Server 2013: configurar el servidor de administración principal'
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
ms.openlocfilehash: a4fee1fa728c3c418c1f837a83248d95df7e7544
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532317"
---
# <a name="configuring-the-primary-management-server-in-lync-server-2013"></a><span data-ttu-id="13d13-102">Configurar el servidor de administración principal en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="13d13-102">Configuring the primary management server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="13d13-103">_**Última modificación del tema:** 2014-03-19_</span><span class="sxs-lookup"><span data-stu-id="13d13-103">_**Topic Last Modified:** 2014-03-19_</span></span>

<span data-ttu-id="13d13-104">Para sacar el máximo partido a las nuevas funciones de supervisión de estado incluidas en los administradores de Microsoft Lync Server 2013, primero debe designar un equipo para que actúe como servidor de administración principal; en ese equipo, debe instalar System Center Operations Manager 2007 R2 o System Center Operations Manager 2012.</span><span class="sxs-lookup"><span data-stu-id="13d13-104">In order to take full advantage of the new health monitoring capabilities included in Microsoft Lync Server 2013 administrators must first designate a computer to act as your primary management server; on that computer you must then install System Center Operations Manager 2007 R2 or System Center Operations Manager 2012.</span></span> <span data-ttu-id="13d13-105">Además, debe instalar una versión compatible de SQL Server para que funcione como su base de datos back-end de Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="13d13-105">In addition, you must install a supported version of SQL Server to function as your Operations Manager back-end database.</span></span> <span data-ttu-id="13d13-106">Si usa System Center Operations Manager 2012, puede usar cualquiera de las siguientes versiones de SQL Server como base de datos back-end:</span><span class="sxs-lookup"><span data-stu-id="13d13-106">If you are using System Center Operations Manager 2012 you can use any of the following versions of SQL Server as your back-end database:</span></span>

  - <span data-ttu-id="13d13-107">SQL Server 2008 R2 Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="13d13-107">SQL Server 2008 R2 Service Pack 1</span></span>

  - <span data-ttu-id="13d13-108">SQL Server 2008 R2 Service Pack 2</span><span class="sxs-lookup"><span data-stu-id="13d13-108">SQL Server 2008 R2 Service Pack 2</span></span>

<span data-ttu-id="13d13-109">Si usa System Center Operations Manager 2007 R2, se recomienda que instale SQL Server 2005 Service Pack 4 o SQL Server 2008 Service Pack 3.</span><span class="sxs-lookup"><span data-stu-id="13d13-109">If you are using System Center Operations Manager 2007 R2 it is recommended that you install either SQL Server 2005 Service Pack 4 or SQL Server 2008 Service Pack 3.</span></span> <span data-ttu-id="13d13-110">También puede usar SQL Server 2008 R2 como base de datos back-end para System Center Operations Manager 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="13d13-110">You can also use SQL Server 2008 R2 as the backend database for System Center Operations Manager 2007 R2.</span></span> <span data-ttu-id="13d13-111">Vea el apéndice 1 de esta documentación para obtener más información sobre cómo configurar SQL Server 2008 R2 para que funcione con System Center Operations Manager 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="13d13-111">See Appendix 1 of this documentation for more information on configuring SQL Server 2008 R2 to work with System Center Operations Manager 2007 R2.</span></span>

<span data-ttu-id="13d13-112">Al instalar System Center Operations Manager 2012 o System Center Operations Manager 2007 R2, debe instalar todos los componentes de ese producto, incluidos:</span><span class="sxs-lookup"><span data-stu-id="13d13-112">When you install System Center Operations Manager 2012 or System Center Operations Manager 2007 R2 you need to install all the components of that product, including:</span></span>

  - <span data-ttu-id="13d13-113">Base de datos operativa</span><span class="sxs-lookup"><span data-stu-id="13d13-113">Operational database</span></span>

  - <span data-ttu-id="13d13-114">Servidor</span><span class="sxs-lookup"><span data-stu-id="13d13-114">Server</span></span>

  - <span data-ttu-id="13d13-115">Consola</span><span class="sxs-lookup"><span data-stu-id="13d13-115">Console</span></span>

  - <span data-ttu-id="13d13-116">Cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="13d13-116">Windows PowerShell cmdlets</span></span>

  - <span data-ttu-id="13d13-117">Consola web</span><span class="sxs-lookup"><span data-stu-id="13d13-117">Web console</span></span>

  - <span data-ttu-id="13d13-118">Reporting</span><span class="sxs-lookup"><span data-stu-id="13d13-118">Reporting</span></span>

  - <span data-ttu-id="13d13-119">Almacén de datos</span><span class="sxs-lookup"><span data-stu-id="13d13-119">Data warehouse</span></span>

<span data-ttu-id="13d13-120">Estos componentes y su instalación no se explicarán en detalle en este documento.</span><span class="sxs-lookup"><span data-stu-id="13d13-120">These components and their installation will not be discussed in detail in this document.</span></span> <span data-ttu-id="13d13-121">Para obtener más información sobre System Center Operations Manager 2007 R2, consulte la documentación de Operations Manager 2007 R2 en <https://go.microsoft.com/fwlink/p/?linkid=257526> y la documentación de System Center Operations manager 2012 en <https://go.microsoft.com/fwlink/p/?linkid=257527> .</span><span class="sxs-lookup"><span data-stu-id="13d13-121">For details about System Center Operations Manager 2007 R2, see the Operations Manager 2007 R2 documentation at <https://go.microsoft.com/fwlink/p/?linkid=257526> and the System Center Operations Manager 2012 documentation at <https://go.microsoft.com/fwlink/p/?linkid=257527>.</span></span> <span data-ttu-id="13d13-122">Debe seguir estas instrucciones si va a usar SQL Server 2005 o SQL Server 2008 Service Pack 1 como base de datos back-end.</span><span class="sxs-lookup"><span data-stu-id="13d13-122">You should follow those instructions if you are going to use SQL Server 2005 or SQL Server 2008 Service Pack 1 as your back-end database.</span></span>

<span data-ttu-id="13d13-123">Si usa System Center Operations Manager 2012, puede usar SQL Server 2012 como base de datos back-end.</span><span class="sxs-lookup"><span data-stu-id="13d13-123">If you are using System Center Operations Manager 2012 then you can use SQL Server 2012 as your back-end database.</span></span> <span data-ttu-id="13d13-124">Para obtener más información sobre SQL Server 2012, vea los libros en pantalla de SQL Server 2012 en [https://go.microsoft.com/fwlink/p/?LinkId=257528](https://go.microsoft.com/fwlink/p/?linkid=257528) .</span><span class="sxs-lookup"><span data-stu-id="13d13-124">For details about SQL Server 2012, see Books Online for SQL Server 2012 at [https://go.microsoft.com/fwlink/p/?LinkId=257528](https://go.microsoft.com/fwlink/p/?linkid=257528).</span></span>

<span data-ttu-id="13d13-125">Tenga en cuenta que solo puede tener un único servidor de administración principal por cada implementación de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="13d13-125">Keep in mind that you can only have a single Primary Management Server per Lync Server deployment.</span></span> <span data-ttu-id="13d13-126">Además, aunque puede usar System Center Operations Manager 2012 o System Center Operations Manager 2007 R2, no puede ejecutar las dos aplicaciones simultáneamente; debe elegir una o la otra.</span><span class="sxs-lookup"><span data-stu-id="13d13-126">Also, while you can use either System Center Operations Manager 2012 or System Center Operations Manager 2007 R2, you cannot run the two applications simultaneously—you must choose one or the other.</span></span> <span data-ttu-id="13d13-127">Por ejemplo, si ejecuta System Center Operations Manager 2012, todos los agentes de System Center también deben ejecutar System Center Operations Manager 2012.</span><span class="sxs-lookup"><span data-stu-id="13d13-127">For example, if you are running System Center Operations Manager 2012 then all your System Center agents must also be running System Center Operations Manager 2012.</span></span> <span data-ttu-id="13d13-128">No puede haber algunos agentes ejecutando System Center Operations Manager 2012 y otros agentes que ejecutan System Center Operations Manager 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="13d13-128">You cannot have some agents running System Center Operations Manager 2012 and other agents running System Center Operations Manager 2007 R2.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

