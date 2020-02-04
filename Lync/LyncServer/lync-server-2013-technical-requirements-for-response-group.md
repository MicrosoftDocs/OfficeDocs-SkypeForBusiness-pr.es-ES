---
title: 'Lync Server 2013: Requisitos técnicos para grupos de respuesta'
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
ms.openlocfilehash: b7ab381a70a8a6d69170959fbaf488982887d765
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746530"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-response-group-in-lync-server-2013"></a><span data-ttu-id="8d917-102">Requisitos técnicos para grupos de respuesta en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8d917-102">Technical requirements for Response Group in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8d917-103">_**Última modificación del tema:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="8d917-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="8d917-104">En esta sección se describen los siguientes requisitos técnicos para la aplicación de grupo de respuesta:</span><span class="sxs-lookup"><span data-stu-id="8d917-104">This section describes the following technical requirements for the Response Group application:</span></span>

  - <span data-ttu-id="8d917-105">Requisitos de hardware</span><span class="sxs-lookup"><span data-stu-id="8d917-105">Hardware requirements</span></span>

  - <span data-ttu-id="8d917-106">Requisitos de software</span><span class="sxs-lookup"><span data-stu-id="8d917-106">Software requirements</span></span>

  - <span data-ttu-id="8d917-107">Requisitos de los puertos</span><span class="sxs-lookup"><span data-stu-id="8d917-107">Port requirements</span></span>

  - <span data-ttu-id="8d917-108">Requisitos de los archivos de audio</span><span class="sxs-lookup"><span data-stu-id="8d917-108">Audio file requirements</span></span>

  - <span data-ttu-id="8d917-109">Requisitos de la herramienta de configuración de grupos de respuesta</span><span class="sxs-lookup"><span data-stu-id="8d917-109">Response Group configuration tool requirements</span></span>

<div>

## <a name="hardware-requirements"></a><span data-ttu-id="8d917-110">Requisitos de hardware</span><span class="sxs-lookup"><span data-stu-id="8d917-110">Hardware Requirements</span></span>

<span data-ttu-id="8d917-111">La aplicación de grupo de respuesta tiene los mismos requisitos de hardware que los servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="8d917-111">The Response Group application has the same hardware requirements as Front End Servers.</span></span> <span data-ttu-id="8d917-112">Para obtener más información sobre los requisitos de hardware, vea [plataformas de hardware de servidor para Lync Server 2013](lync-server-2013-server-hardware-platforms.md) en la documentación de soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="8d917-112">For details about hardware requirements, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Supportability documentation.</span></span>

</div>

<div>

## <a name="software-requirements"></a><span data-ttu-id="8d917-113">Requisitos de software</span><span class="sxs-lookup"><span data-stu-id="8d917-113">Software Requirements</span></span>

<span data-ttu-id="8d917-114">La aplicación de grupo de respuesta tiene los mismos requisitos del sistema operativo y requisitos previos de software que los servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="8d917-114">The Response Group application has the same operating system requirements and software prerequisites as Front End Servers.</span></span> <span data-ttu-id="8d917-115">Para obtener más información sobre los requisitos de software, vea [compatibilidad del sistema operativo servidor y herramientas en Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) en la documentación de soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="8d917-115">For details about software requirements, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

<span data-ttu-id="8d917-116">Si usa archivos de audio de Windows Media (. WMA) para la música de grupo de respuesta y anuncios, todos los servidores de aplicaciones para el usuario o ediciones Standard que ejecuten la aplicación de grupo de respuesta deben tener instalado el Windows Media Format Runtime para servidores con Windows Server 2008 R2 o Microsoft Media Foundation para servidores que ejecutan Windows Server 2012 o Windows Server 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="8d917-116">If you use Windows Media Audio (.wma) files for Response Group music and announcements, all Front End Servers or Standard Editions servers that run the Response Group application must have the Windows Media Format Runtime installed for servers running Windows Server 2008 R2, or Microsoft Media Foundation for servers running Windows Server 2012 or Windows Server 2012 R2.</span></span> <span data-ttu-id="8d917-117">Para Windows Server 2008 R2, Windows Media Format Runtime se instala como parte de la experiencia de escritorio de Windows.</span><span class="sxs-lookup"><span data-stu-id="8d917-117">For Windows Server 2008 R2, Windows Media Format Runtime is installed as part of Windows Desktop Experience.</span></span>

<span data-ttu-id="8d917-118">Para obtener más información sobre los requisitos de audio, consulte "requisitos de archivos de audio" más adelante en esta sección.</span><span class="sxs-lookup"><span data-stu-id="8d917-118">For more details about audio requirements, see "Audio File Requirements" later in this section.</span></span>

</div>

<div>

## <a name="port-requirements"></a><span data-ttu-id="8d917-119">Requisitos de los puertos</span><span class="sxs-lookup"><span data-stu-id="8d917-119">Port Requirements</span></span>

<span data-ttu-id="8d917-120">La aplicación de grupo de respuesta usa los siguientes puertos:</span><span class="sxs-lookup"><span data-stu-id="8d917-120">The Response Group application uses the following ports:</span></span>

  - <span data-ttu-id="8d917-121">**Puerto 5071**   usado para solicitudes de escucha de SIP</span><span class="sxs-lookup"><span data-stu-id="8d917-121">**Port 5071**   Used for SIP listening requests</span></span>

  - <span data-ttu-id="8d917-122">**Puerto 8404**   usado para comunicaciones entre servidores</span><span class="sxs-lookup"><span data-stu-id="8d917-122">**Port 8404**   Used for interserver communications</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8d917-123">Este puerto se usa para hacer coincidir el servicio y es necesario cuando la aplicación de grupo de respuesta se implementa en un grupo que tiene más de un servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="8d917-123">This port is used for the Match Making service and is required when the Response Group application is deployed in a pool that has more than one Front End Server.</span></span>

    
    </div>

<div>


> [!NOTE]  
> <span data-ttu-id="8d917-124">Estos puertos son configuraciones predeterminadas que se pueden cambiar con el cmdlet <STRONG>Set-CsApplicationServer</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="8d917-124">These ports are default settings that you can change by using the <STRONG>Set-CsApplicationServer</STRONG> cmdlet.</span></span> <span data-ttu-id="8d917-125">Para obtener más información sobre este cmdlet, consulte la documentación del shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8d917-125">For details about this cmdlet, see the Lync Server Management Shell documentation.</span></span>



</div>

</div>

<div>

## <a name="audio-file-requirements"></a><span data-ttu-id="8d917-126">Requisitos de archivos de audio</span><span class="sxs-lookup"><span data-stu-id="8d917-126">Audio File Requirements</span></span>

<span data-ttu-id="8d917-127">La aplicación de grupo de respuesta admite el formato de archivo de onda (. wav) y el formato de archivo de audio de Windows Media (. WMA) para preguntas de mensajes de grupo de respuesta, música en espera o respuesta de voz interactiva (IVR).</span><span class="sxs-lookup"><span data-stu-id="8d917-127">The Response Group application supports wave (.wav) file format and Windows Media audio (.wma) file format for Response Group messages, on-hold music, or interactive voice response (IVR) questions.</span></span>

<span data-ttu-id="8d917-128">El formato de archivo de audio de Windows Media requiere que el Windows Media Format Runtime esté instalado en los servidores front-end que ejecutan Windows Server 2008 R2 y Windows Server 2008.</span><span class="sxs-lookup"><span data-stu-id="8d917-128">The Windows Media audio file format requires that the Windows Media Format Runtime is installed on Front End Servers running Windows Server 2008 R2 and Windows Server 2008.</span></span> <span data-ttu-id="8d917-129">Para obtener más información, mira "Requisitos de software" anteriormente en esta sección.</span><span class="sxs-lookup"><span data-stu-id="8d917-129">For more details, see "Software Requirements" earlier in this section.</span></span>

<div>

## <a name="supported-wave-file-formats"></a><span data-ttu-id="8d917-130">Formatos de archivo wave compatibles</span><span class="sxs-lookup"><span data-stu-id="8d917-130">Supported Wave File Formats</span></span>

<span data-ttu-id="8d917-131">Todos los archivos wave necesitan cumplir los requisitos siguientes:</span><span class="sxs-lookup"><span data-stu-id="8d917-131">All wave files must meet the following requirements:</span></span>

  - <span data-ttu-id="8d917-132">Archivo de 8 bits o de 16 bits</span><span class="sxs-lookup"><span data-stu-id="8d917-132">8-bit or 16-bit file</span></span>

  - <span data-ttu-id="8d917-133">Formato de modulación lineal por impulsos codificados (LPCM), A-Law o mu-Law</span><span class="sxs-lookup"><span data-stu-id="8d917-133">Linear pulse code modulation (LPCM), A-Law, or mu-Law format</span></span>

  - <span data-ttu-id="8d917-134">Mono o estéreo</span><span class="sxs-lookup"><span data-stu-id="8d917-134">Mono or stereo</span></span>

  - <span data-ttu-id="8d917-135">4 MB o menos</span><span class="sxs-lookup"><span data-stu-id="8d917-135">4MB or less</span></span>

<span data-ttu-id="8d917-136">Para obtener el máximo rendimiento de los archivos wave, recomendamos usar un archivo wave mono de 16 bits a 16 kHz.</span><span class="sxs-lookup"><span data-stu-id="8d917-136">For the best performance of wave files, a 16 kHz, mono, 16-bit Wave file is recommended.</span></span>

</div>

<div>

## <a name="supported-windows-media-audio-file-formats"></a><span data-ttu-id="8d917-137">Formatos de archivo de audio de Windows Media compatibles</span><span class="sxs-lookup"><span data-stu-id="8d917-137">Supported Windows Media Audio File Formats</span></span>

<span data-ttu-id="8d917-138">Si usas un archivo de audio de Windows Media, considera la posibilidad de usar velocidades de bits lentas y comprueba el rendimiento del sistema cuando se somete a carga.</span><span class="sxs-lookup"><span data-stu-id="8d917-138">If you use a Windows Media audio file, consider using low bit rates, and verify the performance of your system under load.</span></span>

<span data-ttu-id="8d917-139">Puedes usar Microsoft Expression Encoder 4 para convertir un archivo al formato de audio de Windows Media.</span><span class="sxs-lookup"><span data-stu-id="8d917-139">You can use the Microsoft Expression Encoder 4 to convert a file to the Windows Media Audio format.</span></span> <span data-ttu-id="8d917-140">Para descargar Expression Encoder 4, consulte [http://go.microsoft.com/fwlink/p/?linkId=202843](http://go.microsoft.com/fwlink/p/?linkid=202843).</span><span class="sxs-lookup"><span data-stu-id="8d917-140">To download Expression Encoder 4, see [http://go.microsoft.com/fwlink/p/?linkId=202843](http://go.microsoft.com/fwlink/p/?linkid=202843).</span></span>

</div>

</div>

<div>

## <a name="response-group-configuration-tool-requirements"></a><span data-ttu-id="8d917-141">Requisitos para la herramienta de configuración del grupo de respuesta</span><span class="sxs-lookup"><span data-stu-id="8d917-141">Response Group Configuration Tool Requirements</span></span>

<span data-ttu-id="8d917-142">La herramienta de configuración de grupos de respuesta admite las combinaciones de sistemas operativos y exploradores Web que se describen en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="8d917-142">The Response Group Configuration Tool supports the combinations of operating systems and web browsers described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8d917-p107">Se admiten las versiones de 32 y 64 bits de los sistemas operativos. Solamente se admiten las versiones de 32 bits de Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="8d917-p107">32-bit or 64-bit versions of the operating systems are supported. Only 32-bit versions of Internet Explorer are supported.</span></span>



</div>

### <a name="supported-operating-systems-and-web-browsers"></a><span data-ttu-id="8d917-145">Sistemas operativos y exploradores web compatibles</span><span class="sxs-lookup"><span data-stu-id="8d917-145">Supported Operating Systems and Web Browsers</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8d917-146">Sistema operativo</span><span class="sxs-lookup"><span data-stu-id="8d917-146">Operating system</span></span></th>
<th><span data-ttu-id="8d917-147">Explorador web</span><span class="sxs-lookup"><span data-stu-id="8d917-147">Web browser</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8d917-148">Windows Vista con Service Pack (SP) 2</span><span class="sxs-lookup"><span data-stu-id="8d917-148">Windows Vista with Service Pack (SP) 2</span></span></p></td>
<td><p><span data-ttu-id="8d917-149">Internet Explorer 7</span><span class="sxs-lookup"><span data-stu-id="8d917-149">Internet Explorer 7</span></span></p>
<p><span data-ttu-id="8d917-150">Internet Explorer 8 (modo nativo)</span><span class="sxs-lookup"><span data-stu-id="8d917-150">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="8d917-151">Internet Explorer 9 (modo nativo)</span><span class="sxs-lookup"><span data-stu-id="8d917-151">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d917-152">Windows 7</span><span class="sxs-lookup"><span data-stu-id="8d917-152">Windows 7</span></span></p>
<p><span data-ttu-id="8d917-153">Windows 7 con Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="8d917-153">Windows 7 with Service Pack 1</span></span></p></td>
<td><p><span data-ttu-id="8d917-154">Internet Explorer 8 (modo nativo)</span><span class="sxs-lookup"><span data-stu-id="8d917-154">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="8d917-155">Internet Explorer 9 (modo nativo)</span><span class="sxs-lookup"><span data-stu-id="8d917-155">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d917-156">Windows Server 2008 con Service Pack 2</span><span class="sxs-lookup"><span data-stu-id="8d917-156">Windows Server 2008 with Service Pack 2</span></span></p></td>
<td><p><span data-ttu-id="8d917-157">Internet Explorer 7</span><span class="sxs-lookup"><span data-stu-id="8d917-157">Internet Explorer 7</span></span></p>
<p><span data-ttu-id="8d917-158">Internet Explorer 8 (modo nativo)</span><span class="sxs-lookup"><span data-stu-id="8d917-158">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="8d917-159">Internet Explorer 9 (modo nativo)</span><span class="sxs-lookup"><span data-stu-id="8d917-159">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d917-160">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="8d917-160">Windows Server 2008 R2</span></span></p>
<p><span data-ttu-id="8d917-161">Windows Server 2008 R2 con Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="8d917-161">Windows Server 2008 R2 with Service Pack 1</span></span></p></td>
<td><p><span data-ttu-id="8d917-162">Internet Explorer 8 (modo nativo)</span><span class="sxs-lookup"><span data-stu-id="8d917-162">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="8d917-163">Internet Explorer 9 (modo nativo)</span><span class="sxs-lookup"><span data-stu-id="8d917-163">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="response-group-agent-console"></a><span data-ttu-id="8d917-164">Consola del agente del grupo de respuesta</span><span class="sxs-lookup"><span data-stu-id="8d917-164">Response Group Agent Console</span></span>

<span data-ttu-id="8d917-165">La consola del agente admite combinaciones de los sistemas operativos y los exploradores web que se describen en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="8d917-165">The agent console supports the combinations of operating systems and web browsers described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8d917-p108">Se admiten las versiones de 32 y 64 bits de los sistemas operativos. Solamente se admiten las versiones de 32 bits de Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="8d917-p108">32-bit or 64-bit versions of the operating systems are supported. Only 32-bit versions of Internet Explorer are supported.</span></span>



</div>

### <a name="supported-operating-systems-and-web-browsers"></a><span data-ttu-id="8d917-168">Sistemas operativos y exploradores web compatibles</span><span class="sxs-lookup"><span data-stu-id="8d917-168">Supported Operating Systems and Web Browsers</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8d917-169">Sistema operativo</span><span class="sxs-lookup"><span data-stu-id="8d917-169">Operating system</span></span></th>
<th><span data-ttu-id="8d917-170">Explorador web</span><span class="sxs-lookup"><span data-stu-id="8d917-170">Web browser</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8d917-171">Windows Vista con Service Pack (SP) 2</span><span class="sxs-lookup"><span data-stu-id="8d917-171">Windows Vista with Service Pack (SP) 2</span></span></p></td>
<td><p><span data-ttu-id="8d917-172">Internet Explorer 7</span><span class="sxs-lookup"><span data-stu-id="8d917-172">Internet Explorer 7</span></span></p>
<p><span data-ttu-id="8d917-173">Internet Explorer 8 (modo nativo)</span><span class="sxs-lookup"><span data-stu-id="8d917-173">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="8d917-174">Internet Explorer 9 (modo nativo)</span><span class="sxs-lookup"><span data-stu-id="8d917-174">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d917-175">Windows 7</span><span class="sxs-lookup"><span data-stu-id="8d917-175">Windows 7</span></span></p>
<p><span data-ttu-id="8d917-176">Windows 7 con Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="8d917-176">Windows 7 with Service Pack 1</span></span></p></td>
<td><p><span data-ttu-id="8d917-177">Internet Explorer 8 (modo nativo)</span><span class="sxs-lookup"><span data-stu-id="8d917-177">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="8d917-178">Internet Explorer 9 (modo nativo)</span><span class="sxs-lookup"><span data-stu-id="8d917-178">Internet Explorer 9 (native mode)</span></span></p>
<p><span data-ttu-id="8d917-179">Firefox 10.0</span><span class="sxs-lookup"><span data-stu-id="8d917-179">Firefox 10.0</span></span></p>
<p><span data-ttu-id="8d917-180">Chrome 18.0</span><span class="sxs-lookup"><span data-stu-id="8d917-180">Chrome 18.0</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d917-181">Windows Server 2008 con Service Pack 2</span><span class="sxs-lookup"><span data-stu-id="8d917-181">Windows Server 2008 with Service Pack 2</span></span></p></td>
<td><p><span data-ttu-id="8d917-182">Internet Explorer 7</span><span class="sxs-lookup"><span data-stu-id="8d917-182">Internet Explorer 7</span></span></p>
<p><span data-ttu-id="8d917-183">Internet Explorer 8 (modo nativo)</span><span class="sxs-lookup"><span data-stu-id="8d917-183">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="8d917-184">Internet Explorer 9 (modo nativo)</span><span class="sxs-lookup"><span data-stu-id="8d917-184">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d917-185">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="8d917-185">Windows Server 2008 R2</span></span></p>
<p><span data-ttu-id="8d917-186">Windows Server 2008 R2 con Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="8d917-186">Windows Server 2008 R2 with Service Pack 1</span></span></p></td>
<td><p><span data-ttu-id="8d917-187">Internet Explorer 8 (modo nativo)</span><span class="sxs-lookup"><span data-stu-id="8d917-187">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="8d917-188">Internet Explorer 9 (modo nativo)</span><span class="sxs-lookup"><span data-stu-id="8d917-188">Internet Explorer 9 (native mode)</span></span></p>
<p><span data-ttu-id="8d917-189">Firefox 10.0</span><span class="sxs-lookup"><span data-stu-id="8d917-189">Firefox 10.0</span></span></p>
<p><span data-ttu-id="8d917-190">Chrome 18.0</span><span class="sxs-lookup"><span data-stu-id="8d917-190">Chrome 18.0</span></span></p></td>
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

