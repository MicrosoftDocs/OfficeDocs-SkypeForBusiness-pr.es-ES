---
title: 'Lync Server 2013: configuración de plataformas del sistema para el archivado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up system platforms for Archiving
ms:assetid: 2df40fdf-0e32-46d4-9fb2-1ce1d7bfa328
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204768(v=OCS.15)
ms:contentKeyID: 48183716
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0d8d9499d68bcca3848e1e069b4962bb7526091d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850662"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-system-platforms-for-archiving-in-lync-server-2013"></a><span data-ttu-id="e9bf2-102">Configurar plataformas del sistema para el archivado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9bf2-102">Setting up system platforms for Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e9bf2-103">_**Última modificación del tema:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="e9bf2-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="e9bf2-104">Antes de iniciar la implementación del archivado, debe instalar el sistema operativo y cualquier otro software necesario en el hardware que cumpla con los requisitos del sistema:</span><span class="sxs-lookup"><span data-stu-id="e9bf2-104">Before starting the deployment of Archiving, you must install the required operating system and any other prerequisite software on hardware that meets system requirements:</span></span>

  - <span data-ttu-id="e9bf2-105">**Plataformas 2013 de**   Lync Server las implementaciones de Lync Server 2013 no tienen servidores de archivado.</span><span class="sxs-lookup"><span data-stu-id="e9bf2-105">**Lync Server 2013 platform**   Lync Server 2013 deployments do not have Archiving Servers.</span></span> <span data-ttu-id="e9bf2-106">En su lugar, los agentes de recopilación de datos unificados se ejecutan en servidores front-end y servidores Standard Edition para capturar datos para su archivado, por lo que no se necesita ninguna plataforma de sistema independiente para hospedar el archivado.</span><span class="sxs-lookup"><span data-stu-id="e9bf2-106">Instead, Unified Data Collection Agents run on Front End Servers and Standard Edition servers to capture data for archiving, so no separate system platform is required to host Archiving.</span></span>

  - <span data-ttu-id="e9bf2-107">**Plataforma de almacenamiento de datos**   en Lync Server 2013, puede almacenar datos mediante uno de los siguientes procedimientos:</span><span class="sxs-lookup"><span data-stu-id="e9bf2-107">**Data storage platform**   In Lync Server 2013, you can store data by using either of the following:</span></span>
    
      - <span data-ttu-id="e9bf2-108">**Integración de Microsoft Exchange**   si quiere almacenar datos de archivado de Lync Server 2013 con la implementación de Exchange 2013, en lugar de configurar una base de datos independiente para el almacenamiento de datos de archivado, la implementación de Exchange debe ser ejecutando Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="e9bf2-108">**Microsoft Exchange integration**   If you want to store Lync Server 2013 Archiving data by using your Exchange 2013 deployment, instead of or in addition to setting up a separate database for storage of Archiving data, your Exchange deployment must be running Exchange 2013.</span></span> <span data-ttu-id="e9bf2-109">Para obtener detalles sobre la configuración de plataformas del sistema para Exchange 2013, consulte la documentación del producto de Exchange.</span><span class="sxs-lookup"><span data-stu-id="e9bf2-109">For details about setting up system platforms for Exchange 2013, see the Exchange product documentation.</span></span>
    
      - <span data-ttu-id="e9bf2-110">**SQL Server**   si desea usar una base de datos de SQL Server independiente para almacenar los datos de archivado, en lugar de o además de usar la integración de Microsoft Exchange, debe configurar la plataforma del sistema para la base de datos antes de implementar el archivado.</span><span class="sxs-lookup"><span data-stu-id="e9bf2-110">**SQL Server**   If you want to use a separate SQL Server database for storage of archiving data, instead of or in addition to using Microsoft Exchange integration, you must set up the system platform for the database prior to deployment of Archiving.</span></span> <span data-ttu-id="e9bf2-111">Los requisitos de la plataforma de sistema específica dependen de si usa Microsoft SQL Server 2008 R2 o Microsoft SQL Server 2012 para la base de datos de archivado.</span><span class="sxs-lookup"><span data-stu-id="e9bf2-111">The specific system platform requirements depend on whether you use Microsoft SQL Server 2008 R2 or Microsoft SQL Server 2012 for the Archiving database.</span></span> <span data-ttu-id="e9bf2-112">Para obtener detalles sobre la configuración de plataformas del sistema para estas bases de datos, consulte la documentación del producto Microsoft SQL Server 2008 R2 y Microsoft SQL Server 2012.</span><span class="sxs-lookup"><span data-stu-id="e9bf2-112">For details about setting up system platforms for these databases, see the Microsoft SQL Server 2008 R2 and Microsoft SQL Server 2012 product documentation.</span></span>

  - <span data-ttu-id="e9bf2-113">**Plataforma de servidor de archivos**   Lync Server 2013 almacena los archivos de archivado de Lync Server en la misma ubicación que especifique para el almacenamiento de archivos al configurar los servidores front-end o los servidores Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="e9bf2-113">**File server platform**   Lync Server 2013 stores Lync Server archiving files in the same location that you specify for file storage when you set up your Front End Servers or Standard Edition servers.</span></span> <span data-ttu-id="e9bf2-114">No puede especificar una ubicación independiente para archivar el almacenamiento de archivos, por lo que no se requiere ninguna plataforma de sistema independiente para archivar el almacenamiento de archivos.</span><span class="sxs-lookup"><span data-stu-id="e9bf2-114">You cannot specify a separate location for archiving file storage, so no separate system platform is required for Archiving file storage.</span></span> <span data-ttu-id="e9bf2-115">Si usa la integración de Microsoft Exchange, Exchange 2013 los archivos de comunicaciones de Lync archivadas se almacenan en servidores de Exchange 2013 para los usuarios alojados en esos servidores de Exchange.</span><span class="sxs-lookup"><span data-stu-id="e9bf2-115">If you use Microsoft Exchange integration, Exchange 2013 the files for archived Lync communications are stored on Exchange 2013 servers for users homed on those Exchange servers.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

