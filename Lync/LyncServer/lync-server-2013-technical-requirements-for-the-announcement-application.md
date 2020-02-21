---
title: 'Lync Server 2013: requisitos técnicos para la aplicación de anuncio'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for the Announcement application
ms:assetid: fbd8c204-3765-4b22-a0c9-a781b5126366
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205413(v=OCS.15)
ms:contentKeyID: 48185944
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8687c5b9c5f422994817910eec640cc795798d18
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194753"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-the-announcement-application-in-lync-server-2013"></a><span data-ttu-id="144b9-102">Requisitos técnicos para la aplicación de anuncio en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="144b9-102">Technical requirements for the Announcement application in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="144b9-103">_**Última modificación del tema:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="144b9-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="144b9-104">En esta sección se describen los siguientes requisitos técnicos para la aplicación de anuncio:</span><span class="sxs-lookup"><span data-stu-id="144b9-104">This section describes the following technical requirements for the Announcement application:</span></span>

  - <span data-ttu-id="144b9-105">Requisitos de hardware</span><span class="sxs-lookup"><span data-stu-id="144b9-105">Hardware requirements</span></span>

  - <span data-ttu-id="144b9-106">Requisitos de software</span><span class="sxs-lookup"><span data-stu-id="144b9-106">Software requirements</span></span>

  - <span data-ttu-id="144b9-107">Requisitos de puerto</span><span class="sxs-lookup"><span data-stu-id="144b9-107">Port requirements</span></span>

  - <span data-ttu-id="144b9-108">Requisitos de archivos de audio</span><span class="sxs-lookup"><span data-stu-id="144b9-108">Audio file requirements</span></span>

<div>

## <a name="hardware-requirements"></a><span data-ttu-id="144b9-109">Requisitos de hardware</span><span class="sxs-lookup"><span data-stu-id="144b9-109">Hardware Requirements</span></span>

<span data-ttu-id="144b9-110">La aplicación de anuncio tiene los mismos requisitos de hardware que los servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="144b9-110">The Announcement application has the same hardware requirements as Front End Servers.</span></span> <span data-ttu-id="144b9-111">Para obtener más información sobre los requisitos de hardware, vea [plataformas de hardware de servidor para Lync Server 2013](lync-server-2013-server-hardware-platforms.md) en la documentación sobre compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="144b9-111">For details about hardware requirements, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Supportability documentation.</span></span>

</div>

<div>

## <a name="software-requirements"></a><span data-ttu-id="144b9-112">Requisitos de software</span><span class="sxs-lookup"><span data-stu-id="144b9-112">Software Requirements</span></span>

<span data-ttu-id="144b9-113">La aplicación de anuncio tiene los mismos requisitos de sistema operativo y requisitos previos de software que los servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="144b9-113">The Announcement application has the same operating system requirements and software prerequisites as Front End Servers.</span></span> <span data-ttu-id="144b9-114">Para obtener más información sobre los requisitos de software, consulte [Server and Tools Operating System support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) en la documentación sobre compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="144b9-114">For details about software requirements, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

<span data-ttu-id="144b9-115">Todos los servidores front-end o servidores Standard Edition que ejecutan la aplicación de anuncio deben tener instalado el tiempo de ejecución de Windows Media Format para los servidores que ejecutan Windows Server 2008 R2 o Microsoft Media Foundation para los servidores que ejecutan Windows Server 2012 o Windows Server 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="144b9-115">All Front End Servers or Standard Edition servers that run the Announcement application must have the Windows Media Format Runtime installed for servers running Windows Server 2008 R2, or Microsoft Media Foundation for servers running Windows Server 2012 or Windows Server 2012 R2.</span></span> <span data-ttu-id="144b9-116">Para Windows Server 2008 R2, el tiempo de ejecución de Windows Media Format se instala como parte de la experiencia de escritorio de Windows.</span><span class="sxs-lookup"><span data-stu-id="144b9-116">For Windows Server 2008 R2, the Windows Media Format Runtime is installed as part of Windows Desktop Experience.</span></span> <span data-ttu-id="144b9-117">Se requiere el tiempo de ejecución de Windows Media Format o Microsoft Media Foundation para los archivos de audio de Windows Media (. WMA) que la aplicación de anuncio reproduce para los anuncios y la música.</span><span class="sxs-lookup"><span data-stu-id="144b9-117">Windows Media Format Runtime or Microsoft Media Foundation is required for Windows Media Audio (.wma) files that the Announcement application plays for announcements and music.</span></span>

</div>

<div>

## <a name="port-requirements"></a><span data-ttu-id="144b9-118">Requisitos de los puertos</span><span class="sxs-lookup"><span data-stu-id="144b9-118">Port Requirements</span></span>

<span data-ttu-id="144b9-119">La aplicación de anuncio usa el siguiente puerto:</span><span class="sxs-lookup"><span data-stu-id="144b9-119">The Announcement application uses the following port:</span></span>

  - <span data-ttu-id="144b9-120">**Puerto 5071**   usado para solicitudes de escucha SIP</span><span class="sxs-lookup"><span data-stu-id="144b9-120">**Port 5071**   Used for SIP listening requests</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="144b9-121">Este puertos es el predeterminado, pero puede cambiarlo utilizando el cmdlet <STRONG>Set-CsApplicationServer</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="144b9-121">This port is the default setting, which you can change by using the <STRONG>Set-CsApplicationServer</STRONG> cmdlet.</span></span> <span data-ttu-id="144b9-122">Para obtener más información sobre este cmdlet, consulte la documentación del shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="144b9-122">For details about this cmdlet, see the Lync Server Management Shell documentation.</span></span>



</div>

</div>

<div>

## <a name="audio-file-requirements"></a><span data-ttu-id="144b9-123">Requisitos de archivos de audio</span><span class="sxs-lookup"><span data-stu-id="144b9-123">Audio File Requirements</span></span>

<span data-ttu-id="144b9-124">La aplicación de anuncio admite el formato de archivo de onda (. wav) y el formato de archivo de audio de Windows Media (. WMA) para música y anuncios.</span><span class="sxs-lookup"><span data-stu-id="144b9-124">The Announcement application supports Wave (.wav) file format and Windows Media audio (.wma) file format for music and announcements.</span></span> <span data-ttu-id="144b9-125">Los requisitos de archivos de audio para la aplicación de anuncio son los mismos que para la aplicación de grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="144b9-125">Audio file requirements for the Announcement application are the same as for the Response Group application.</span></span> <span data-ttu-id="144b9-126">Para obtener más información, consulte [Technical Requirements for Response Group in Lync Server 2013](lync-server-2013-technical-requirements-for-response-group.md).</span><span class="sxs-lookup"><span data-stu-id="144b9-126">For details, see [Technical requirements for Response Group in Lync Server 2013](lync-server-2013-technical-requirements-for-response-group.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

