---
title: 'Lync Server 2013: configurar SQL Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure SQL Server
ms:assetid: 84504918-cb4f-4b2f-be17-a70770b69025
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398669(v=OCS.15)
ms:contentKeyID: 48184699
ms.date: 01/22/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3d46a857f0f9ef55dc375b4d465205668fe5f79e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145719"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-sql-server-in-lync-server-2013"></a><span data-ttu-id="13b94-102">Configurar SQL Server en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="13b94-102">Configure SQL Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="13b94-103">_**Última modificación del tema:** 2015-01-22_</span><span class="sxs-lookup"><span data-stu-id="13b94-103">_**Topic Last Modified:** 2015-01-22_</span></span>

<span data-ttu-id="13b94-104">Para cada base de datos que implemente, puede usar una única instancia de SQL Server para todas las bases de datos de la implementación de Lync Server 2013 que se puede combinar en un servidor de bases de datos.</span><span class="sxs-lookup"><span data-stu-id="13b94-104">For each database that you deploy, you can use a single SQL Server instance for all databases for your Lync Server 2013 deployment that can be collocated on a database server.</span></span> <span data-ttu-id="13b94-105">Para obtener más información acerca de la base de datos combinación, consulte [Supported Server combinación en Lync server 2013](lync-server-2013-supported-server-collocation.md) en la documentación sobre compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="13b94-105">For details about database collocation, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md) in the Supportability documentation.</span></span>

<span data-ttu-id="13b94-106">Además, cada instancia de SQL Server debe estar instalada y disponible antes de completar los pasos del generador de topologías que configuran las bases de datos, o bien, crear manualmente las bases de datos con los cmdlets de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="13b94-106">Additionally, each SQL Server instance must be installed and available prior to completing the steps in Topology Builder that set up the databases, or manually creating the databases with Windows PowerShell cmdlets.</span></span> <span data-ttu-id="13b94-107">Para obtener más información acerca de la compatibilidad de SQL Server, consulte [configuración de hardware para Lync Server 2013](lync-server-2013-hardware-setup.md).</span><span class="sxs-lookup"><span data-stu-id="13b94-107">For details about SQL Server supportability, see [Hardware setup for Lync Server 2013](lync-server-2013-hardware-setup.md).</span></span>

<div>

## <a name="to-install-microsoft-sql-server-2012"></a><span data-ttu-id="13b94-108">Para instalar Microsoft SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="13b94-108">To install Microsoft SQL Server 2012</span></span>

  - <span data-ttu-id="13b94-109">Consulte la documentación de Microsoft SQL Server 2012 en <https://technet.microsoft.com/library/bb500395(v=sql.110).aspx>:.</span><span class="sxs-lookup"><span data-stu-id="13b94-109">See the Microsoft SQL Server 2012 documentation at: <https://technet.microsoft.com/library/bb500395(v=sql.110).aspx>.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

