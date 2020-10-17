---
title: 'Lync Server 2013: requisitos técnicos para la aplicación de anuncio'
description: 'Lync Server 2013: requisitos técnicos para la aplicación de anuncio.'
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
ms.openlocfilehash: adc5019408b79301bbcda3993ceb7d96ee4d9b7d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550316"
---
# <a name="technical-requirements-for-the-announcement-application-in-lync-server-2013"></a><span data-ttu-id="8b636-103">Requisitos técnicos para la aplicación de anuncio en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8b636-103">Technical requirements for the Announcement application in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8b636-104">_**Última modificación del tema:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="8b636-104">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="8b636-105">En esta sección se describen los siguientes requisitos técnicos para la aplicación de anuncio:</span><span class="sxs-lookup"><span data-stu-id="8b636-105">This section describes the following technical requirements for the Announcement application:</span></span>

  - <span data-ttu-id="8b636-106">Requisitos de hardware</span><span class="sxs-lookup"><span data-stu-id="8b636-106">Hardware requirements</span></span>

  - <span data-ttu-id="8b636-107">Requisitos de software</span><span class="sxs-lookup"><span data-stu-id="8b636-107">Software requirements</span></span>

  - <span data-ttu-id="8b636-108">Requisitos de puerto</span><span class="sxs-lookup"><span data-stu-id="8b636-108">Port requirements</span></span>

  - <span data-ttu-id="8b636-109">Requisitos de archivos de audio</span><span class="sxs-lookup"><span data-stu-id="8b636-109">Audio file requirements</span></span>

<div>

## <a name="hardware-requirements"></a><span data-ttu-id="8b636-110">Requisitos de hardware</span><span class="sxs-lookup"><span data-stu-id="8b636-110">Hardware Requirements</span></span>

<span data-ttu-id="8b636-111">La aplicación de anuncio tiene los mismos requisitos de hardware que los servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="8b636-111">The Announcement application has the same hardware requirements as Front End Servers.</span></span> <span data-ttu-id="8b636-112">Para obtener más información sobre los requisitos de hardware, vea [plataformas de hardware de servidor para Lync Server 2013](lync-server-2013-server-hardware-platforms.md) en la documentación sobre compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="8b636-112">For details about hardware requirements, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Supportability documentation.</span></span>

</div>

<div>

## <a name="software-requirements"></a><span data-ttu-id="8b636-113">Requisitos de software</span><span class="sxs-lookup"><span data-stu-id="8b636-113">Software Requirements</span></span>

<span data-ttu-id="8b636-114">La aplicación de anuncio tiene los mismos requisitos de sistema operativo y requisitos previos de software que los servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="8b636-114">The Announcement application has the same operating system requirements and software prerequisites as Front End Servers.</span></span> <span data-ttu-id="8b636-115">Para obtener más información sobre los requisitos de software, consulte [Server and Tools Operating System support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) en la documentación sobre compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="8b636-115">For details about software requirements, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

<span data-ttu-id="8b636-116">Todos los servidores front-end o servidores Standard Edition que ejecutan la aplicación de anuncio deben tener instalado el tiempo de ejecución de Windows Media Format para los servidores que ejecutan Windows Server 2008 R2 o Microsoft Media Foundation para los servidores que ejecutan Windows Server 2012 o Windows Server 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="8b636-116">All Front End Servers or Standard Edition servers that run the Announcement application must have the Windows Media Format Runtime installed for servers running Windows Server 2008 R2, or Microsoft Media Foundation for servers running Windows Server 2012 or Windows Server 2012 R2.</span></span> <span data-ttu-id="8b636-117">Para Windows Server 2008 R2, el tiempo de ejecución de Windows Media Format se instala como parte de la experiencia de escritorio de Windows.</span><span class="sxs-lookup"><span data-stu-id="8b636-117">For Windows Server 2008 R2, the Windows Media Format Runtime is installed as part of Windows Desktop Experience.</span></span> <span data-ttu-id="8b636-118">Se requiere el tiempo de ejecución de Windows Media Format o Microsoft Media Foundation para los archivos de audio de Windows Media (. WMA) que la aplicación de anuncio reproduce para los anuncios y la música.</span><span class="sxs-lookup"><span data-stu-id="8b636-118">Windows Media Format Runtime or Microsoft Media Foundation is required for Windows Media Audio (.wma) files that the Announcement application plays for announcements and music.</span></span>

</div>

<div>

## <a name="port-requirements"></a><span data-ttu-id="8b636-119">Requisitos de los puertos</span><span class="sxs-lookup"><span data-stu-id="8b636-119">Port Requirements</span></span>

<span data-ttu-id="8b636-120">La aplicación de anuncio usa el siguiente puerto:</span><span class="sxs-lookup"><span data-stu-id="8b636-120">The Announcement application uses the following port:</span></span>

  - <span data-ttu-id="8b636-121">**Puerto 5071**     Se usa para solicitudes de escucha SIP</span><span class="sxs-lookup"><span data-stu-id="8b636-121">**Port 5071**   Used for SIP listening requests</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8b636-122">Este puertos es el predeterminado, pero puede cambiarlo utilizando el cmdlet <STRONG>Set-CsApplicationServer</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="8b636-122">This port is the default setting, which you can change by using the <STRONG>Set-CsApplicationServer</STRONG> cmdlet.</span></span> <span data-ttu-id="8b636-123">Para obtener más información sobre este cmdlet, consulte la documentación del shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8b636-123">For details about this cmdlet, see the Lync Server Management Shell documentation.</span></span>



</div>

</div>

<div>

## <a name="audio-file-requirements"></a><span data-ttu-id="8b636-124">Requisitos de archivos de audio</span><span class="sxs-lookup"><span data-stu-id="8b636-124">Audio File Requirements</span></span>

<span data-ttu-id="8b636-125">La aplicación de anuncio admite el formato de archivo de onda (. wav) y el formato de archivo de audio de Windows Media (. WMA) para música y anuncios.</span><span class="sxs-lookup"><span data-stu-id="8b636-125">The Announcement application supports Wave (.wav) file format and Windows Media audio (.wma) file format for music and announcements.</span></span> <span data-ttu-id="8b636-126">Los requisitos de archivos de audio para la aplicación de anuncio son los mismos que para la aplicación de grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="8b636-126">Audio file requirements for the Announcement application are the same as for the Response Group application.</span></span> <span data-ttu-id="8b636-127">Para obtener más información, consulte [Technical Requirements for Response Group in Lync Server 2013](lync-server-2013-technical-requirements-for-response-group.md).</span><span class="sxs-lookup"><span data-stu-id="8b636-127">For details, see [Technical requirements for Response Group in Lync Server 2013](lync-server-2013-technical-requirements-for-response-group.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

