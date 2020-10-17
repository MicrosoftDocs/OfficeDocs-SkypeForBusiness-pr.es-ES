---
title: 'Lync Server 2013: configurar plataformas del sistema para archivado'
description: 'Lync Server 2013: configurar plataformas del sistema para el archivado.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up system platforms for Archiving
ms:assetid: 2df40fdf-0e32-46d4-9fb2-1ce1d7bfa328
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204768(v=OCS.15)
ms:contentKeyID: 48183716
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2f210083451ae8fcb87c53e52b5512de6f1f18d0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554186"
---
# <a name="setting-up-system-platforms-for-archiving-in-lync-server-2013"></a><span data-ttu-id="712fd-103">Configurar plataformas del sistema para el archivado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="712fd-103">Setting up system platforms for Archiving in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="712fd-104">_**Última modificación del tema:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="712fd-104">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="712fd-105">Antes de iniciar la implementación de archivado, debe instalar el sistema operativo requerido y cualquier otro software necesario como requisito previo en el hardware que cumpla los requisitos del sistema:</span><span class="sxs-lookup"><span data-stu-id="712fd-105">Before starting the deployment of Archiving, you must install the required operating system and any other prerequisite software on hardware that meets system requirements:</span></span>

  - <span data-ttu-id="712fd-106">Plataforma Lync Server **2013**     Las implementaciones de Lync Server 2013 no tienen servidores de archivado.</span><span class="sxs-lookup"><span data-stu-id="712fd-106">**Lync Server 2013 platform**   Lync Server 2013 deployments do not have Archiving Servers.</span></span> <span data-ttu-id="712fd-107">En su lugar, agentes de colección de datos unificada se ejecutan en servidores front-end y servidores de Standard Edition para capturar datos de archivado, de modo que ninguna plataforma independiente del sistema sea necesaria para hospedar el archivado.</span><span class="sxs-lookup"><span data-stu-id="712fd-107">Instead, Unified Data Collection Agents run on Front End Servers and Standard Edition servers to capture data for archiving, so no separate system platform is required to host Archiving.</span></span>

  - <span data-ttu-id="712fd-108">Plataforma de almacenamiento de **datos**     En Lync Server 2013, puede almacenar datos mediante uno de los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="712fd-108">**Data storage platform**   In Lync Server 2013, you can store data by using either of the following:</span></span>
    
      - <span data-ttu-id="712fd-109">Integración de Microsoft **Exchange**     Si desea almacenar los datos de archivado de Lync Server 2013 mediante la implementación de Exchange 2013, en lugar de configurar una base de datos independiente para el almacenamiento de los datos de archivado o además de la configuración de una base de datos independiente, la implementación de Exchange debe ejecutar Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="712fd-109">**Microsoft Exchange integration**   If you want to store Lync Server 2013 Archiving data by using your Exchange 2013 deployment, instead of or in addition to setting up a separate database for storage of Archiving data, your Exchange deployment must be running Exchange 2013.</span></span> <span data-ttu-id="712fd-110">Para obtener información detallada sobre cómo configurar las plataformas del sistema para Exchange 2013, consulte la documentación del producto de Exchange.</span><span class="sxs-lookup"><span data-stu-id="712fd-110">For details about setting up system platforms for Exchange 2013, see the Exchange product documentation.</span></span>
    
      - <span data-ttu-id="712fd-111">**SQL Server**     Si desea usar una base de datos de SQL Server independiente para el almacenamiento de datos de archivado, en lugar de usar o además del uso de la integración de Microsoft Exchange, debe configurar la plataforma del sistema para la base de datos antes de la implementación del archivado.</span><span class="sxs-lookup"><span data-stu-id="712fd-111">**SQL Server**   If you want to use a separate SQL Server database for storage of archiving data, instead of or in addition to using Microsoft Exchange integration, you must set up the system platform for the database prior to deployment of Archiving.</span></span> <span data-ttu-id="712fd-112">Los requisitos específicos de la plataforma del sistema dependen de si usa Microsoft SQL Server 2008 R2 o Microsoft SQL Server 2012 para la base de datos de archivado.</span><span class="sxs-lookup"><span data-stu-id="712fd-112">The specific system platform requirements depend on whether you use Microsoft SQL Server 2008 R2 or Microsoft SQL Server 2012 for the Archiving database.</span></span> <span data-ttu-id="712fd-113">Para obtener información detallada sobre cómo configurar las plataformas del sistema para estas bases de datos, consulte la documentación del producto Microsoft SQL Server 2008 R2 y Microsoft SQL Server 2012.</span><span class="sxs-lookup"><span data-stu-id="712fd-113">For details about setting up system platforms for these databases, see the Microsoft SQL Server 2008 R2 and Microsoft SQL Server 2012 product documentation.</span></span>

  - <span data-ttu-id="712fd-114">Plataforma de servidor de **archivos**     Lync Server 2013 almacena los archivos de archivado de Lync Server en la misma ubicación que se especifica para el almacenamiento de archivos al configurar los servidores front-end o los servidores Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="712fd-114">**File server platform**   Lync Server 2013 stores Lync Server archiving files in the same location that you specify for file storage when you set up your Front End Servers or Standard Edition servers.</span></span> <span data-ttu-id="712fd-115">No puede especificar una ubicación independiente para el almacenamiento de archivos de archivado, por lo que no es necesaria ninguna plataforma del sistema independiente para el almacenamiento de archivos de archivado.</span><span class="sxs-lookup"><span data-stu-id="712fd-115">You cannot specify a separate location for archiving file storage, so no separate system platform is required for Archiving file storage.</span></span> <span data-ttu-id="712fd-116">Si usa la integración de Microsoft Exchange, Exchange 2013 los archivos de las comunicaciones de Lync archivadas se almacenan en los servidores de Exchange 2013 para los usuarios alojados en esos servidores de Exchange.</span><span class="sxs-lookup"><span data-stu-id="712fd-116">If you use Microsoft Exchange integration, Exchange 2013 the files for archived Lync communications are stored on Exchange 2013 servers for users homed on those Exchange servers.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

