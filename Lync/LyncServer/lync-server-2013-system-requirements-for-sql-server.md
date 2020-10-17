---
title: 'Lync Server 2013: requisitos del sistema para SQL Server'
description: 'Lync Server 2013: requisitos del sistema para SQL Server.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: System requirements for SQL Server
ms:assetid: 9c235085-cbfa-4e9e-9cec-3f5749039a6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205112(v=OCS.15)
ms:contentKeyID: 48184904
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 524136174be8798aed1dc7d5d236dbb45ab18330
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562636"
---
# <a name="system-requirements-for-sql-server-in-lync-server-2013"></a><span data-ttu-id="991a1-103">Requisitos del sistema para SQL Server en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="991a1-103">System requirements for SQL Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="991a1-104">_**Última modificación del tema:** 2013-10-25_</span><span class="sxs-lookup"><span data-stu-id="991a1-104">_**Topic Last Modified:** 2013-10-25_</span></span>

<span data-ttu-id="991a1-105">Antes de implementar el servidor Enterprise Edition, instale Microsoft SQL Server 2008 R2 o Microsoft SQL Server 2012 en un equipo dedicado que cumpla los requisitos de hardware.</span><span class="sxs-lookup"><span data-stu-id="991a1-105">Before you deploy Enterprise Edition server, install Microsoft SQL Server 2008 R2 or Microsoft SQL Server 2012 on a dedicated computer that meets the hardware requirements.</span></span> <span data-ttu-id="991a1-106">Para obtener más información sobre los requisitos de hardware, vea [plataformas de hardware de servidor para Lync Server 2013](lync-server-2013-server-hardware-platforms.md) en la documentación sobre compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="991a1-106">For details about hardware requirements, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Supportability documentation.</span></span> <span data-ttu-id="991a1-107">Para obtener más información sobre los requisitos de software, consulte [compatibilidad de software de base de datos en Lync Server 2013](lync-server-2013-database-software-support.md) en la documentación sobre compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="991a1-107">For details about software requirements, see [Database software support in Lync Server 2013](lync-server-2013-database-software-support.md) in the Supportability documentation.</span></span> <span data-ttu-id="991a1-108">Para obtener información acerca de los permisos necesarios para la implementación, consulte [permisos de implementación para SQL Server en Lync server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="991a1-108">For information about the permissions necessary for deployment, see [Deployment permissions for SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span></span>

<span data-ttu-id="991a1-109">Antes de crear el grupo de servidores front-end, también debe configurar Firewall de Windows para permitir el acceso de Lync Server 2013 a SQL Server a través de puertos específicos mediante la definición de puertos para el servidor mediante el administrador de configuración de SQL Server y la apertura de puertos en firewall de Windows con seguridad avanzada.</span><span class="sxs-lookup"><span data-stu-id="991a1-109">Before you create the Front End pool, you must also configure Windows Firewall to allow Lync Server 2013 access to SQL Server over specific ports by defining ports for the server using SQL Server Configuration Manager and opening ports in Windows Firewall with Advanced Security.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

