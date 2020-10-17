---
title: 'Lync Server 2013: Guía de operaciones'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Operations Guide
ms:assetid: dcb9ddff-6fe3-4077-a2e3-0ba64f65e264
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720467(v=OCS.15)
ms:contentKeyID: 63969658
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 212a640577d55e80225a597c9263b7a2573d257f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48524537"
---
# <a name="operations-guide-for-lync-server-2013"></a><span data-ttu-id="8bd94-102">Guía de operaciones para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8bd94-102">Operations Guide for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8bd94-103">_**Última modificación del tema:** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="8bd94-103">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="8bd94-104">En este documento se describen los procesos operativos, las tareas y las herramientas necesarias para mantener un entorno de software de comunicaciones de Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8bd94-104">This document describes the operational processes, tasks, and tools that are required for you to maintain a Microsoft Lync Server 2013 communications software environment.</span></span> <span data-ttu-id="8bd94-105">Explica cómo administrar Lync Server 2013 de acuerdo con el modelo de Microsoft Operations Framework (MOF) y le ayuda a diseñar un entorno de administración operativa eficaz, que incluye la implementación de programaciones, procesos y procedimientos para mantener un entorno de trabajo eficaz.</span><span class="sxs-lookup"><span data-stu-id="8bd94-105">It explains how to manage Lync Server 2013 according to the Microsoft Operations Framework (MOF) model and it will help you design an efficient operational management environment, which includes implementing schedules, processes and procedures to maintain an efficient working environment.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="8bd94-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="8bd94-106">In This Section</span></span>

<span data-ttu-id="8bd94-107">Se incluyen las siguientes secciones:</span><span class="sxs-lookup"><span data-stu-id="8bd94-107">The following sections are included:</span></span>

  - [<span data-ttu-id="8bd94-108">Procedimientos recomendados para entornos de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8bd94-108">Best practices for Lync Server 2013 environments</span></span>](lync-server-2013-best-practices-for-lync-server-environments.md)

  - [<span data-ttu-id="8bd94-109">Tareas diarias en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8bd94-109">Daily tasks in Lync Server 2013</span></span>](lync-server-2013-daily-tasks.md)

  - [<span data-ttu-id="8bd94-110">Tareas semanales en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8bd94-110">Weekly tasks in Lync Server 2013</span></span>](lync-server-2013-weekly-tasks.md)

  - [<span data-ttu-id="8bd94-111">Tareas mensuales en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8bd94-111">Monthly tasks in Lync Server 2013</span></span>](lync-server-2013-monthly-tasks.md)

  - [<span data-ttu-id="8bd94-112">Tareas necesarias en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8bd94-112">As-needed tasks in Lync Server 2013</span></span>](lync-server-2013-as-needed-tasks.md)

  - [<span data-ttu-id="8bd94-113">Listas de comprobación de operaciones para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8bd94-113">Operations checklists for Lync Server 2013</span></span>](lync-server-2013-operations-checklists.md)

  - [<span data-ttu-id="8bd94-114">Supervisión de Lync Server 2013 con System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="8bd94-114">Monitoring Lync Server 2013 with System Center Operations Manager</span></span>](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md)

  - [<span data-ttu-id="8bd94-115">Dependencias operativas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8bd94-115">Operational dependencies in Lync Server 2013</span></span>](lync-server-2013-operational-dependencies.md)

  - [<span data-ttu-id="8bd94-116">Solución de problemas y indicadores de estado clave en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8bd94-116">Troubleshooting and Key Health Indicators in Lync Server 2013</span></span>](lync-server-2013-troubleshooting-and-key-health-indicators.md)

<span data-ttu-id="8bd94-117">Se supone que se ha completado la implementación de Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8bd94-117">It is assumed that your Microsoft Lync Server 2013 deployment is completed.</span></span> <span data-ttu-id="8bd94-118">Si no es así, consulte el contenido de planeación e implementación de Microsoft Lync Server 2013 antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="8bd94-118">If this is not the case, refer to the planning and deployment content for Microsoft Lync Server 2013 before you continue.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8bd94-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8bd94-119">See Also</span></span>


[<span data-ttu-id="8bd94-120">Introducción a Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8bd94-120">Getting started with Lync Server 2013</span></span>](lync-server-2013-getting-started.md)  
[<span data-ttu-id="8bd94-121">Planeación para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8bd94-121">Planning for Lync Server 2013</span></span>](lync-server-2013-planning.md)  
[<span data-ttu-id="8bd94-122">Implementación de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8bd94-122">Deployment of Lync Server 2013</span></span>](lync-server-2013-deployment.md)  
[<span data-ttu-id="8bd94-123">Shell de administración de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8bd94-123">Lync Server 2013 Management Shell</span></span>](lync-server-2013-lync-server-management-shell.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

