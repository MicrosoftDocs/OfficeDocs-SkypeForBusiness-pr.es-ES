---
title: Configuración de Lync Server para trabajar con System Center Operations Manager
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Lync Server to work with System Center Operations Manager
ms:assetid: b55a24ab-648b-4142-b3cd-3792860ba872
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205188(v=OCS.15)
ms:contentKeyID: 48185179
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ff72248e691d3e5358fda79a98d318cfc3a382eb
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008452"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-lync-server-2013-to-work-with-system-center-operations-manager"></a><span data-ttu-id="c5eff-102">Configuración de Lync Server 2013 para trabajar con System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="c5eff-102">Configuring Lync Server 2013 to work with System Center Operations Manager</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c5eff-103">_**Última modificación del tema:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="c5eff-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="c5eff-104">Para configurar la infraestructura de 2013 de Microsoft Lync Server para que funcione con System Center Operations Manager, debe hacer tres cosas:</span><span class="sxs-lookup"><span data-stu-id="c5eff-104">In order to configure your Microsoft Lync Server 2013 infrastructure to work with System Center Operations Manager you must do three things:</span></span>

  - <span data-ttu-id="c5eff-105">Identifique y configure el servidor de administración principal de System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="c5eff-105">Identify and configure your primary System Center Operations Manager management server.</span></span> <span data-ttu-id="c5eff-106">La configuración del servidor de administración incluye la instalación de System Center Operations Manager 2012 o System Center Operations Manager 2007 R2, así como la configuración de una base de datos back-end con SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c5eff-106">Configuring the management server includes installing System Center Operations Manager 2012 or System Center Operations Manager 2007 R2, as well as setting up a back-end database using SQL Server.</span></span> <span data-ttu-id="c5eff-107">La versión real de SQL Server que necesita usar depende de la versión de System Center Operations Manager que use.</span><span class="sxs-lookup"><span data-stu-id="c5eff-107">The actual version of SQL Server that you need to be use depends on the version of System Center Operations Manager you are using.</span></span> <span data-ttu-id="c5eff-108">Para obtener más información, consulte [configurar el servidor de administración principal en Lync server 2013](lync-server-2013-configuring-the-primary-management-server.md).</span><span class="sxs-lookup"><span data-stu-id="c5eff-108">For details, see [Configuring the primary management server in Lync Server 2013](lync-server-2013-configuring-the-primary-management-server.md).</span></span>

  - <span data-ttu-id="c5eff-109">Identifique y configure los equipos de Lync Server que desea supervisar.</span><span class="sxs-lookup"><span data-stu-id="c5eff-109">Identify and configure the Lync Server computers that you want to monitor.</span></span> <span data-ttu-id="c5eff-110">Para supervisar un equipo de Lync Server mediante System Center Operations Manager, debe instalar los archivos del agente de System Center Operations Manager y configurar cada servidor para que actúe como proxy.</span><span class="sxs-lookup"><span data-stu-id="c5eff-110">To monitor a Lync Server computer by using System Center Operations Manager you must install the System Center Operations Manager agent files, and configure each server to act as a proxy.</span></span>

  - <span data-ttu-id="c5eff-111">Identifique y configure los equipos que desea que actúen como *nodos de monitor*de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c5eff-111">Identify and configure the computers that you want to act as Lync Server *watcher nodes*.</span></span> <span data-ttu-id="c5eff-112">Los nodos de monitor son equipos que ejecutan periódicamente transacciones sintéticas de Lync Server, que son cmdlets de Windows PowerShell que comprueban que los componentes clave de Lync Server, como la capacidad de iniciar sesión en el sistema o la posibilidad de intercambiar mensajes instantáneos son funciona como se esperaba.</span><span class="sxs-lookup"><span data-stu-id="c5eff-112">Watcher nodes are computers that periodically run Lync Server synthetic transactions, which are Windows PowerShell cmdlets that verify that key Lync Server components, such as the ability to log on to the system or the ability to exchange instant messages are working as expected.</span></span>

<span data-ttu-id="c5eff-113">En los temas de esta sección se incluyen instrucciones para llevar a cabo cada una de estas tareas.</span><span class="sxs-lookup"><span data-stu-id="c5eff-113">The topics in this section contain instructions for carrying out each of these tasks.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="c5eff-114">En esta sección</span><span class="sxs-lookup"><span data-stu-id="c5eff-114">In This Section</span></span>

  - [<span data-ttu-id="c5eff-115">Configurar el servidor de administración principal en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c5eff-115">Configuring the primary management server in Lync Server 2013</span></span>](lync-server-2013-configuring-the-primary-management-server.md)

  - [<span data-ttu-id="c5eff-116">Instalación de los paquetes de administración de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c5eff-116">Installing the Lync Server 2013 management packs</span></span>](lync-server-2013-installing-the-lync-server-2013-management-packs.md)

  - [<span data-ttu-id="c5eff-117">Configurar los equipos de Lync Server que se supervisarán en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c5eff-117">Configuring the Lync Server computers that will be monitored in Lync Server 2013</span></span>](lync-server-2013-configuring-the-lync-server-computers-that-will-be-monitored.md)

  - [<span data-ttu-id="c5eff-118">Instalación y configuración de nodos de monitor en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c5eff-118">Installing and configuring watcher nodes in Lync Server 2013</span></span>](lync-server-2013-installing-and-configuring-watcher-nodes.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

