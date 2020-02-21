---
title: 'Lync Server 2013: implementación del archivado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Archiving
ms:assetid: a89edd16-12d5-4602-ad2f-194b47d1188e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205147(v=OCS.15)
ms:contentKeyID: 48185031
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1d31a4bdf75b649dec1d18a834335b0d47a69a3e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42206765"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-archiving-in-lync-server-2013"></a><span data-ttu-id="62a41-102">Implementación del archivado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="62a41-102">Deploying Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="62a41-103">_**Última modificación del tema:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="62a41-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="62a41-104">Lync Server 2013 proporciona una solución para archivar contenido de mensajería instantánea (mi) y comunicaciones de conferencia en Lync Server.</span><span class="sxs-lookup"><span data-stu-id="62a41-104">Lync Server 2013 provides a solution for archiving instant messaging (IM) content and conferencing communications in Lync Server.</span></span> <span data-ttu-id="62a41-105">Puede implementar la compatibilidad con el archivado mediante la integración del almacenamiento de archivado con el almacenamiento de Exchange 2013, mediante el uso de bases de datos de SQL Server para el almacenamiento de datos de archivado de Lync Server 2013 o mediante el almacenamiento de Lync Server 2013 y Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="62a41-105">You can implement archiving support by integrating archiving storage with Exchange 2013 storage, by using SQL Server databases for storage of Lync Server 2013 archiving data, or by using both Lync Server 2013 and Exchange 2013 storage.</span></span> <span data-ttu-id="62a41-106">Controle de qué manera se archivan los datos a través de la configuración de directivas y archivado.</span><span class="sxs-lookup"><span data-stu-id="62a41-106">You control how data is archived using policies and archiving configurations.</span></span> <span data-ttu-id="62a41-107">Para obtener más información, consulte [planeación del archivado en Lync server 2013](lync-server-2013-planning-for-archiving.md) en la documentación de planeación y [Cómo funciona el archivado en Lync Server 2013](lync-server-2013-how-archiving-works.md) en la documentación sobre Planeación, la documentación sobre la implementación o las operaciones.</span><span class="sxs-lookup"><span data-stu-id="62a41-107">For details, see [Planning for Archiving in Lync Server 2013](lync-server-2013-planning-for-archiving.md) in the Planning documentation and [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<span data-ttu-id="62a41-108">Puede usar la información en esta sección para instalar y configurar el archivado inicialmente.</span><span class="sxs-lookup"><span data-stu-id="62a41-108">You can use the information in this section to set up and configure Archiving initially.</span></span> <span data-ttu-id="62a41-109">Después de la implementación, puede cambiar la configuración de archivado.</span><span class="sxs-lookup"><span data-stu-id="62a41-109">After deployment, you can change Archiving settings.</span></span> <span data-ttu-id="62a41-110">Para obtener más información sobre cómo implementar la compatibilidad de archivado para la administración cotidiana o para cumplir nuevos requisitos en su organización, consulte [Managing Lync Server 2013 archiving](lync-server-2013-managing-archiving.md) en la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="62a41-110">For details about how you implement archiving support for day-to-day management or to meet new requirements in your organization, see [Managing Lync Server 2013 Archiving](lync-server-2013-managing-archiving.md) in the Operations documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="62a41-111">En esta sección</span><span class="sxs-lookup"><span data-stu-id="62a41-111">In This Section</span></span>

  - [<span data-ttu-id="62a41-112">Cómo funciona el archivado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="62a41-112">How Archiving works in Lync Server 2013</span></span>](lync-server-2013-how-archiving-works.md)

  - [<span data-ttu-id="62a41-113">Lista de comprobación para la implementación del archivado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="62a41-113">Deployment checklist for Archiving in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-archiving.md)

  - [<span data-ttu-id="62a41-114">Configurar los sistemas y la infraestructura para el archivado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="62a41-114">Setting up systems and infrastructure for Archiving in Lync Server 2013</span></span>](lync-server-2013-setting-up-systems-and-infrastructure-for-archiving.md)

  - [<span data-ttu-id="62a41-115">Adición de bases de datos de archivado a una implementación existente de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="62a41-115">Adding Archiving databases to an existing Lync Server 2013 Deployment</span></span>](lync-server-2013-adding-archiving-databases-to-an-existing-lync-server-2013-deployment.md)

  - [<span data-ttu-id="62a41-116">Configuración de la compatibilidad con el archivado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="62a41-116">Configuring support for Archiving in Lync Server 2013</span></span>](lync-server-2013-configuring-support-for-archiving.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

