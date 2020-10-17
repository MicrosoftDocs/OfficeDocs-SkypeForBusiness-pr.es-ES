---
title: 'Lync Server 2013: requisitos técnicos para el grupo de respuesta'
description: 'Lync Server 2013: requisitos técnicos para el grupo de respuesta.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for Response Group
ms:assetid: 477488bd-124f-437b-9327-732a0d7271ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204863(v=OCS.15)
ms:contentKeyID: 48184044
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f3125ed8c732960e23970229e99bf5a8487eb96a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550326"
---
# <a name="technical-requirements-for-response-group-in-lync-server-2013"></a><span data-ttu-id="512ff-103">Requisitos técnicos para el grupo de respuesta en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="512ff-103">Technical requirements for Response Group in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="512ff-104">_**Última modificación del tema:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="512ff-104">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="512ff-105">En esta sección se describen los siguientes requisitos técnicos para la aplicación del grupo de respuesta:</span><span class="sxs-lookup"><span data-stu-id="512ff-105">This section describes the following technical requirements for the Response Group application:</span></span>

  - <span data-ttu-id="512ff-106">Requisitos de hardware</span><span class="sxs-lookup"><span data-stu-id="512ff-106">Hardware requirements</span></span>

  - <span data-ttu-id="512ff-107">Requisitos de software</span><span class="sxs-lookup"><span data-stu-id="512ff-107">Software requirements</span></span>

  - <span data-ttu-id="512ff-108">Requisitos de puerto</span><span class="sxs-lookup"><span data-stu-id="512ff-108">Port requirements</span></span>

  - <span data-ttu-id="512ff-109">Requisitos de archivos de audio</span><span class="sxs-lookup"><span data-stu-id="512ff-109">Audio file requirements</span></span>

  - <span data-ttu-id="512ff-110">Requisitos de la herramienta de configuración del grupo de respuesta</span><span class="sxs-lookup"><span data-stu-id="512ff-110">Response Group configuration tool requirements</span></span>

<div>

## <a name="hardware-requirements"></a><span data-ttu-id="512ff-111">Requisitos de hardware</span><span class="sxs-lookup"><span data-stu-id="512ff-111">Hardware Requirements</span></span>

<span data-ttu-id="512ff-112">La aplicación de grupo de respuesta tiene los mismos requisitos de hardware que los servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="512ff-112">The Response Group application has the same hardware requirements as Front End Servers.</span></span> <span data-ttu-id="512ff-113">Para obtener más información sobre los requisitos de hardware, vea [plataformas de hardware de servidor para Lync Server 2013](lync-server-2013-server-hardware-platforms.md) en la documentación sobre compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="512ff-113">For details about hardware requirements, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Supportability documentation.</span></span>

</div>

<div>

## <a name="software-requirements"></a><span data-ttu-id="512ff-114">Requisitos de software</span><span class="sxs-lookup"><span data-stu-id="512ff-114">Software Requirements</span></span>

<span data-ttu-id="512ff-115">La aplicación de grupo de respuesta tiene los mismos requisitos de sistema operativo y requisitos previos de software que los servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="512ff-115">The Response Group application has the same operating system requirements and software prerequisites as Front End Servers.</span></span> <span data-ttu-id="512ff-116">Para obtener más información sobre los requisitos de software, consulte [Server and Tools Operating System support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) en la documentación sobre compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="512ff-116">For details about software requirements, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

<span data-ttu-id="512ff-117">Si usa archivos de audio de Windows Media (. WMA) para la música del grupo de respuesta y anuncios, todos los servidores front-end o los servidores Standard Edition que ejecutan la aplicación de grupo de respuesta deben tener instalado el tiempo de ejecución de Windows Media Format para los servidores que ejecutan Windows Server 2008 R2 o Microsoft Media Foundation para los servidores que ejecutan Windows Server 2012 o Windows 2012 Server</span><span class="sxs-lookup"><span data-stu-id="512ff-117">If you use Windows Media Audio (.wma) files for Response Group music and announcements, all Front End Servers or Standard Editions servers that run the Response Group application must have the Windows Media Format Runtime installed for servers running Windows Server 2008 R2, or Microsoft Media Foundation for servers running Windows Server 2012 or Windows Server 2012 R2.</span></span> <span data-ttu-id="512ff-118">Para Windows Server 2008 R2, el tiempo de ejecución de Windows Media Format se instala como parte de la experiencia de escritorio de Windows.</span><span class="sxs-lookup"><span data-stu-id="512ff-118">For Windows Server 2008 R2, Windows Media Format Runtime is installed as part of Windows Desktop Experience.</span></span>

<span data-ttu-id="512ff-119">Para más detalles sobre los requisitos de audio, vea "Requisitos de archivos de audio" más adelante en esta sección.</span><span class="sxs-lookup"><span data-stu-id="512ff-119">For more details about audio requirements, see "Audio File Requirements" later in this section.</span></span>

</div>

<div>

## <a name="port-requirements"></a><span data-ttu-id="512ff-120">Requisitos de los puertos</span><span class="sxs-lookup"><span data-stu-id="512ff-120">Port Requirements</span></span>

<span data-ttu-id="512ff-121">La aplicación de grupo de respuesta usa los siguientes puertos:</span><span class="sxs-lookup"><span data-stu-id="512ff-121">The Response Group application uses the following ports:</span></span>

  - <span data-ttu-id="512ff-122">**Puerto 5071**     Se usa para solicitudes de escucha SIP</span><span class="sxs-lookup"><span data-stu-id="512ff-122">**Port 5071**   Used for SIP listening requests</span></span>

  - <span data-ttu-id="512ff-123">**Puerto 8404**     Se usa para las comunicaciones entre servidores</span><span class="sxs-lookup"><span data-stu-id="512ff-123">**Port 8404**   Used for interserver communications</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="512ff-124">Este puerto se usa para el servicio de coincidencia que hace coincidir y es necesario cuando la aplicación de grupo de respuesta se implementa en un grupo de servidores que tiene más de un servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="512ff-124">This port is used for the Match Making service and is required when the Response Group application is deployed in a pool that has more than one Front End Server.</span></span>

    
    </div>

<div>


> [!NOTE]  
> <span data-ttu-id="512ff-125">Estos puertos son configuraciones predeterminadas que se pueden cambiar mediante el cmdlet <STRONG>Set-CsApplicationServer</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="512ff-125">These ports are default settings that you can change by using the <STRONG>Set-CsApplicationServer</STRONG> cmdlet.</span></span> <span data-ttu-id="512ff-126">Para obtener más información sobre este cmdlet, consulte la documentación del shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="512ff-126">For details about this cmdlet, see the Lync Server Management Shell documentation.</span></span>



</div>

</div>

<div>

## <a name="audio-file-requirements"></a><span data-ttu-id="512ff-127">Requisitos de archivos de audio</span><span class="sxs-lookup"><span data-stu-id="512ff-127">Audio File Requirements</span></span>

<span data-ttu-id="512ff-128">La aplicación de grupo de respuesta admite el formato de archivo wave (. wav) y el formato de archivo de audio de Windows Media (. WMA) para mensajes de grupo de respuesta, música en espera o preguntas de respuesta interactiva de voz (IVR).</span><span class="sxs-lookup"><span data-stu-id="512ff-128">The Response Group application supports wave (.wav) file format and Windows Media audio (.wma) file format for Response Group messages, on-hold music, or interactive voice response (IVR) questions.</span></span>

<span data-ttu-id="512ff-129">El formato de archivo de audio de Windows Media requiere que el tiempo de ejecución de Windows Media Format esté instalado en los servidores front-end que ejecuten Windows Server 2008 R2 y Windows Server 2008.</span><span class="sxs-lookup"><span data-stu-id="512ff-129">The Windows Media audio file format requires that the Windows Media Format Runtime is installed on Front End Servers running Windows Server 2008 R2 and Windows Server 2008.</span></span> <span data-ttu-id="512ff-130">Para más información, vea "Requisitos de software" anteriormente en esta sección.</span><span class="sxs-lookup"><span data-stu-id="512ff-130">For more details, see "Software Requirements" earlier in this section.</span></span>

<div>

## <a name="supported-wave-file-formats"></a><span data-ttu-id="512ff-131">Formatos de archivo wave compatibles</span><span class="sxs-lookup"><span data-stu-id="512ff-131">Supported Wave File Formats</span></span>

<span data-ttu-id="512ff-132">Todos los archivos wave deben cumplir los requisitos siguientes:</span><span class="sxs-lookup"><span data-stu-id="512ff-132">All wave files must meet the following requirements:</span></span>

  - <span data-ttu-id="512ff-133">Archivo de 8 bits o de 16 bits</span><span class="sxs-lookup"><span data-stu-id="512ff-133">8-bit or 16-bit file</span></span>

  - <span data-ttu-id="512ff-134">Formato de modulación lineal por impulsos codificados (LPCM), A-Law o mu-Law</span><span class="sxs-lookup"><span data-stu-id="512ff-134">Linear pulse code modulation (LPCM), A-Law, or mu-Law format</span></span>

  - <span data-ttu-id="512ff-135">Mono o estéreo</span><span class="sxs-lookup"><span data-stu-id="512ff-135">Mono or stereo</span></span>

  - <span data-ttu-id="512ff-136">4 MB o menos</span><span class="sxs-lookup"><span data-stu-id="512ff-136">4MB or less</span></span>

<span data-ttu-id="512ff-137">Para obtener el máximo rendimiento de los archivos wave, se recomienda usar un archivo wave mono de 16 bits a 16 kHz.</span><span class="sxs-lookup"><span data-stu-id="512ff-137">For the best performance of wave files, a 16 kHz, mono, 16-bit Wave file is recommended.</span></span>

</div>

<div>

## <a name="supported-windows-media-audio-file-formats"></a><span data-ttu-id="512ff-138">Formatos de archivo de audio Windows Media admitidos</span><span class="sxs-lookup"><span data-stu-id="512ff-138">Supported Windows Media Audio File Formats</span></span>

<span data-ttu-id="512ff-139">Si usa un archivo de audio Windows Media, considere la posibilidad de usar velocidades de bits lentas y compruebe el rendimiento del sistema cuando se somete a carga.</span><span class="sxs-lookup"><span data-stu-id="512ff-139">If you use a Windows Media audio file, consider using low bit rates, and verify the performance of your system under load.</span></span>

<span data-ttu-id="512ff-140">Puede usar Microsoft Expression Encoder 4 para convertir un archivo al formato de audio de Windows Media.</span><span class="sxs-lookup"><span data-stu-id="512ff-140">You can use the Microsoft Expression Encoder 4 to convert a file to the Windows Media Audio format.</span></span> <span data-ttu-id="512ff-141">Para descargar Expression Encoder 4, mira [https://go.microsoft.com/fwlink/p/?linkId=202843](https://go.microsoft.com/fwlink/p/?linkid=202843) .</span><span class="sxs-lookup"><span data-stu-id="512ff-141">To download Expression Encoder 4, see [https://go.microsoft.com/fwlink/p/?linkId=202843](https://go.microsoft.com/fwlink/p/?linkid=202843).</span></span>

</div>

</div>

<div>

## <a name="response-group-configuration-tool-requirements"></a><span data-ttu-id="512ff-142">Requisitos para la herramienta de configuración del grupo de respuesta</span><span class="sxs-lookup"><span data-stu-id="512ff-142">Response Group Configuration Tool Requirements</span></span>

<span data-ttu-id="512ff-143">La herramienta de configuración de grupos de respuesta admite las combinaciones de sistemas operativos y exploradores Web que se describen en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="512ff-143">The Response Group Configuration Tool supports the combinations of operating systems and web browsers described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="512ff-p107">Se admiten las versiones de 32 y 64 bits de los sistemas operativos. Solamente se admiten las versiones de 32 bits de Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="512ff-p107">32-bit or 64-bit versions of the operating systems are supported. Only 32-bit versions of Internet Explorer are supported.</span></span>



</div>

### <a name="supported-operating-systems-and-web-browsers"></a><span data-ttu-id="512ff-146">Sistemas operativos y exploradores web compatibles</span><span class="sxs-lookup"><span data-stu-id="512ff-146">Supported Operating Systems and Web Browsers</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="512ff-147">Sistema operativo</span><span class="sxs-lookup"><span data-stu-id="512ff-147">Operating system</span></span></th>
<th><span data-ttu-id="512ff-148">Explorador web</span><span class="sxs-lookup"><span data-stu-id="512ff-148">Web browser</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="512ff-149">Windows Vista con Service Pack (SP) 2</span><span class="sxs-lookup"><span data-stu-id="512ff-149">Windows Vista with Service Pack (SP) 2</span></span></p></td>
<td><p><span data-ttu-id="512ff-150">Internet Explorer 7</span><span class="sxs-lookup"><span data-stu-id="512ff-150">Internet Explorer 7</span></span></p>
<p><span data-ttu-id="512ff-151">Internet Explorer 8 (modo nativo)</span><span class="sxs-lookup"><span data-stu-id="512ff-151">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="512ff-152">Internet Explorer 9 (modo nativo)</span><span class="sxs-lookup"><span data-stu-id="512ff-152">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="512ff-153">Windows 7</span><span class="sxs-lookup"><span data-stu-id="512ff-153">Windows 7</span></span></p>
<p><span data-ttu-id="512ff-154">Windows 7 con Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="512ff-154">Windows 7 with Service Pack 1</span></span></p></td>
<td><p><span data-ttu-id="512ff-155">Internet Explorer 8 (modo nativo)</span><span class="sxs-lookup"><span data-stu-id="512ff-155">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="512ff-156">Internet Explorer 9 (modo nativo)</span><span class="sxs-lookup"><span data-stu-id="512ff-156">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="512ff-157">Windows Server 2008 con SP2</span><span class="sxs-lookup"><span data-stu-id="512ff-157">Windows Server 2008 with Service Pack 2</span></span></p></td>
<td><p><span data-ttu-id="512ff-158">Internet Explorer 7</span><span class="sxs-lookup"><span data-stu-id="512ff-158">Internet Explorer 7</span></span></p>
<p><span data-ttu-id="512ff-159">Internet Explorer 8 (modo nativo)</span><span class="sxs-lookup"><span data-stu-id="512ff-159">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="512ff-160">Internet Explorer 9 (modo nativo)</span><span class="sxs-lookup"><span data-stu-id="512ff-160">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="512ff-161">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="512ff-161">Windows Server 2008 R2</span></span></p>
<p><span data-ttu-id="512ff-162">Windows Server 2008 R2 con Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="512ff-162">Windows Server 2008 R2 with Service Pack 1</span></span></p></td>
<td><p><span data-ttu-id="512ff-163">Internet Explorer 8 (modo nativo)</span><span class="sxs-lookup"><span data-stu-id="512ff-163">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="512ff-164">Internet Explorer 9 (modo nativo)</span><span class="sxs-lookup"><span data-stu-id="512ff-164">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="response-group-agent-console"></a><span data-ttu-id="512ff-165">Consola del agente del grupo de respuesta</span><span class="sxs-lookup"><span data-stu-id="512ff-165">Response Group Agent Console</span></span>

<span data-ttu-id="512ff-166">La consola de agente admite combinaciones de los sistemas operativos y los exploradores web que se describen en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="512ff-166">The agent console supports the combinations of operating systems and web browsers described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="512ff-p108">Se admiten las versiones de 32 y 64 bits de los sistemas operativos. Solamente se admiten las versiones de 32 bits de Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="512ff-p108">32-bit or 64-bit versions of the operating systems are supported. Only 32-bit versions of Internet Explorer are supported.</span></span>



</div>

### <a name="supported-operating-systems-and-web-browsers"></a><span data-ttu-id="512ff-169">Sistemas operativos y exploradores web compatibles</span><span class="sxs-lookup"><span data-stu-id="512ff-169">Supported Operating Systems and Web Browsers</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="512ff-170">Sistema operativo</span><span class="sxs-lookup"><span data-stu-id="512ff-170">Operating system</span></span></th>
<th><span data-ttu-id="512ff-171">Explorador web</span><span class="sxs-lookup"><span data-stu-id="512ff-171">Web browser</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="512ff-172">Windows Vista con Service Pack (SP) 2</span><span class="sxs-lookup"><span data-stu-id="512ff-172">Windows Vista with Service Pack (SP) 2</span></span></p></td>
<td><p><span data-ttu-id="512ff-173">Internet Explorer 7</span><span class="sxs-lookup"><span data-stu-id="512ff-173">Internet Explorer 7</span></span></p>
<p><span data-ttu-id="512ff-174">Internet Explorer 8 (modo nativo)</span><span class="sxs-lookup"><span data-stu-id="512ff-174">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="512ff-175">Internet Explorer 9 (modo nativo)</span><span class="sxs-lookup"><span data-stu-id="512ff-175">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="512ff-176">Windows 7</span><span class="sxs-lookup"><span data-stu-id="512ff-176">Windows 7</span></span></p>
<p><span data-ttu-id="512ff-177">Windows 7 con Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="512ff-177">Windows 7 with Service Pack 1</span></span></p></td>
<td><p><span data-ttu-id="512ff-178">Internet Explorer 8 (modo nativo)</span><span class="sxs-lookup"><span data-stu-id="512ff-178">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="512ff-179">Internet Explorer 9 (modo nativo)</span><span class="sxs-lookup"><span data-stu-id="512ff-179">Internet Explorer 9 (native mode)</span></span></p>
<p><span data-ttu-id="512ff-180">Firefox 10.0</span><span class="sxs-lookup"><span data-stu-id="512ff-180">Firefox 10.0</span></span></p>
<p><span data-ttu-id="512ff-181">Chrome 18.0</span><span class="sxs-lookup"><span data-stu-id="512ff-181">Chrome 18.0</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="512ff-182">Windows Server 2008 con Service Pack 2</span><span class="sxs-lookup"><span data-stu-id="512ff-182">Windows Server 2008 with Service Pack 2</span></span></p></td>
<td><p><span data-ttu-id="512ff-183">Internet Explorer 7</span><span class="sxs-lookup"><span data-stu-id="512ff-183">Internet Explorer 7</span></span></p>
<p><span data-ttu-id="512ff-184">Internet Explorer 8 (modo nativo)</span><span class="sxs-lookup"><span data-stu-id="512ff-184">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="512ff-185">Internet Explorer 9 (modo nativo)</span><span class="sxs-lookup"><span data-stu-id="512ff-185">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="512ff-186">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="512ff-186">Windows Server 2008 R2</span></span></p>
<p><span data-ttu-id="512ff-187">Windows Server 2008 R2 con Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="512ff-187">Windows Server 2008 R2 with Service Pack 1</span></span></p></td>
<td><p><span data-ttu-id="512ff-188">Internet Explorer 8 (modo nativo)</span><span class="sxs-lookup"><span data-stu-id="512ff-188">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="512ff-189">Internet Explorer 9 (modo nativo)</span><span class="sxs-lookup"><span data-stu-id="512ff-189">Internet Explorer 9 (native mode)</span></span></p>
<p><span data-ttu-id="512ff-190">Firefox 10.0</span><span class="sxs-lookup"><span data-stu-id="512ff-190">Firefox 10.0</span></span></p>
<p><span data-ttu-id="512ff-191">Chrome 18.0</span><span class="sxs-lookup"><span data-stu-id="512ff-191">Chrome 18.0</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

