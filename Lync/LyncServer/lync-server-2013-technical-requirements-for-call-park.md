---
title: 'Lync Server 2013: Requisitos técnicos para el estacionamiento de llamadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for Call Park
ms:assetid: 38bcf302-2b72-4492-9266-f6dc31b566e1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204818(v=OCS.15)
ms:contentKeyID: 48183897
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 742d6ef62068e3e6e3bbd953e078b186e86bb497
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746610"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-call-park-in-lync-server-2013"></a><span data-ttu-id="ae0da-102">Requisitos técnicos para el estacionamiento de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ae0da-102">Technical requirements for Call Park in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ae0da-103">_**Última modificación del tema:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="ae0da-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="ae0da-104">En esta sección se describen los siguientes requisitos técnicos de Call Park:</span><span class="sxs-lookup"><span data-stu-id="ae0da-104">This section describes the following technical requirements for Call Park:</span></span>

  - <span data-ttu-id="ae0da-105">Requisitos de hardware</span><span class="sxs-lookup"><span data-stu-id="ae0da-105">Hardware requirements</span></span>

  - <span data-ttu-id="ae0da-106">Requisitos de software</span><span class="sxs-lookup"><span data-stu-id="ae0da-106">Software requirements</span></span>

  - <span data-ttu-id="ae0da-107">Requisitos de los puertos</span><span class="sxs-lookup"><span data-stu-id="ae0da-107">Port requirements</span></span>

  - <span data-ttu-id="ae0da-108">Requisitos de los archivos de audio</span><span class="sxs-lookup"><span data-stu-id="ae0da-108">Audio file requirements</span></span>

<div>

## <a name="hardware-requirements"></a><span data-ttu-id="ae0da-109">Requisitos de hardware</span><span class="sxs-lookup"><span data-stu-id="ae0da-109">Hardware Requirements</span></span>

<span data-ttu-id="ae0da-110">La aplicación de estacionamiento de llamadas tiene los mismos requisitos de hardware que los servidores de aplicaciones para el usuario.</span><span class="sxs-lookup"><span data-stu-id="ae0da-110">The Call Park application has the same hardware requirements as Front End Servers.</span></span> <span data-ttu-id="ae0da-111">Para obtener más información sobre los requisitos de hardware, vea [plataformas de hardware de servidor para Lync Server 2013](lync-server-2013-server-hardware-platforms.md) en la documentación de soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="ae0da-111">For details about hardware requirements, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Supportability documentation.</span></span>

</div>

<div>

## <a name="software-requirements"></a><span data-ttu-id="ae0da-112">Requisitos de software</span><span class="sxs-lookup"><span data-stu-id="ae0da-112">Software Requirements</span></span>

<span data-ttu-id="ae0da-113">La aplicación de estacionamiento de llamadas tiene los mismos requisitos de sistema operativo y requisitos previos de software que los servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="ae0da-113">The Call Park application has the same operating system requirements and software prerequisites as Front End Servers.</span></span> <span data-ttu-id="ae0da-114">Para obtener más información sobre los requisitos de software, vea [compatibilidad del sistema operativo servidor y herramientas en Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) en la documentación de soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="ae0da-114">For details about software requirements, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

<span data-ttu-id="ae0da-115">Todos los servidores front-end y los servidores Standard Edition en los que se implemente la aplicación de estacionamiento de llamadas deben tener instalado Windows Media Format Runtime para servidores que ejecuten Windows Server 2008 R2 o Microsoft Media Foundation para servidores que ejecuten Windows Server 2012 o Windows Server 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="ae0da-115">All Front End Servers and Standard Edition servers where the Call Park application is deployed must have the Windows Media Format Runtime installed for servers running Windows Server 2008 R2, or Microsoft Media Foundation for servers running Windows Server 2012 or Windows Server 2012 R2.</span></span> <span data-ttu-id="ae0da-116">Para Windows Server 2008 R2, Windows Media Format Runtime se instala como parte de la experiencia de escritorio de Windows.</span><span class="sxs-lookup"><span data-stu-id="ae0da-116">For Windows Server 2008 R2, Windows Media Format Runtime is installed as part of Windows Desktop Experience.</span></span> <span data-ttu-id="ae0da-117">Se necesita Windows Media Format Runtime o Microsoft Media Foundation para los archivos de audio de Windows Media (. WMA) que llaman a reproducciones de estacionamiento para música en espera.</span><span class="sxs-lookup"><span data-stu-id="ae0da-117">Windows Media Format Runtime or Microsoft Media Foundation is required for Windows Media Audio (.wma) files that Call Park plays for music on hold.</span></span>

</div>

<div>

## <a name="port-requirements"></a><span data-ttu-id="ae0da-118">Requisitos de los puertos</span><span class="sxs-lookup"><span data-stu-id="ae0da-118">Port Requirements</span></span>

<span data-ttu-id="ae0da-119">La aplicación de estacionamiento de llamadas usa el siguiente puerto:</span><span class="sxs-lookup"><span data-stu-id="ae0da-119">The Call Park application uses the following port:</span></span>

  - <span data-ttu-id="ae0da-120">**Puerto 5075**   usado para solicitudes de escucha de SIP.</span><span class="sxs-lookup"><span data-stu-id="ae0da-120">**Port 5075**   Used for SIP listening requests.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ae0da-121">Este puerto es una configuración predeterminada que puedes cambiar con el cmdlet <STRONG>Set-CsApplicationServer</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="ae0da-121">This port is a default setting that you can change by using the <STRONG>Set-CsApplicationServer</STRONG> cmdlet.</span></span> <span data-ttu-id="ae0da-122">Para obtener más información sobre este cmdlet, consulte la documentación del shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ae0da-122">For details about this cmdlet, see the Lync Server Management Shell documentation.</span></span>



</div>

</div>

<div>

## <a name="audio-file-requirements"></a><span data-ttu-id="ae0da-123">Requisitos de archivos de audio</span><span class="sxs-lookup"><span data-stu-id="ae0da-123">Audio File Requirements</span></span>

<span data-ttu-id="ae0da-124">La aplicación de estacionamiento de llamadas solo admite archivos de audio de Windows Media (. WMA) para música en espera.</span><span class="sxs-lookup"><span data-stu-id="ae0da-124">The Call Park application supports only Windows Media Audio (.wma) files for music on hold.</span></span> <span data-ttu-id="ae0da-125">Puedes usar Microsoft Expression Encoder 4 para personalizar los archivos para la música en espera.</span><span class="sxs-lookup"><span data-stu-id="ae0da-125">You can use the Microsoft Expression Encoder 4 to customize files for music on hold.</span></span> <span data-ttu-id="ae0da-126">Para descargar Expression Encoder 4, consulta "Expression Encoder 4" en [http://go.microsoft.com/fwlink/p/?linkId=202843](http://go.microsoft.com/fwlink/p/?linkid=202843).</span><span class="sxs-lookup"><span data-stu-id="ae0da-126">To download Expression Encoder 4, see "Expression Encoder 4" at [http://go.microsoft.com/fwlink/p/?linkId=202843](http://go.microsoft.com/fwlink/p/?linkid=202843).</span></span> <span data-ttu-id="ae0da-127">Usa la herramienta para convertir el archivo en un formato .wma.</span><span class="sxs-lookup"><span data-stu-id="ae0da-127">Use the tool to convert the file to a .wma format.</span></span> <span data-ttu-id="ae0da-128">El formato recomendado para los archivos de reactivar música en espera de llamadas es media audio 9, 44 kHz, 16 bits, mono, CBR, 32 kbps.</span><span class="sxs-lookup"><span data-stu-id="ae0da-128">The recommended format for Call Park music-on-hold files is Media Audio 9, 44 kHz, 16 bits, Mono, CBR, 32 kbps.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ae0da-129">El archivo convertido se reproduce por el teléfono solo a 16 kHz, aunque se grabó a 44 kHz.</span><span class="sxs-lookup"><span data-stu-id="ae0da-129">The converted file plays over the phone only at 16 kHz, even if it was recorded at 44 kHz.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

