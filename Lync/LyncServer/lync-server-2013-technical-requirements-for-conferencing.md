---
title: Lync Server 2013 requisitos técnicos para conferencias
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for conferencing
ms:assetid: 3c0d89e1-53e6-46d7-bf8c-491260b292ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425889(v=OCS.15)
ms:contentKeyID: 48183923
ms.date: 06/26/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d28afb699b63ee3523c7b5d4ae31bf9153459abf
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533947"
---
# <a name="technical-requirements-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="ed57c-102">Requisitos técnicos para conferencias en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ed57c-102">Technical requirements for conferencing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ed57c-103">_**Última modificación del tema:** 2014-06-25_</span><span class="sxs-lookup"><span data-stu-id="ed57c-103">_**Topic Last Modified:** 2014-06-25_</span></span>

<span data-ttu-id="ed57c-104">Para Lync Server 2013, las capacidades de conferencia de acceso telefónico local, conferencia A/V, Conferencia de mensajería instantánea (mi) y conferencia web siempre se ejecutan en los servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="ed57c-104">For Lync Server 2013, dial-in conferencing, A/V conferencing, instant messaging (IM) conferencing and web conferencing capabilities always run on Front End Servers.</span></span>

<span data-ttu-id="ed57c-105">En esta sección se describen detalladamente los requisitos de hardware y software de estos servidores, junto con la combinación admitida.</span><span class="sxs-lookup"><span data-stu-id="ed57c-105">This section details the hardware and software requirements for these servers, along with the supported collocation.</span></span>

<span data-ttu-id="ed57c-106">La conferencia de acceso telefónico local es una característica que incluye una variedad de componentes.</span><span class="sxs-lookup"><span data-stu-id="ed57c-106">Dial-in conferencing is a feature that includes a variety of components.</span></span> <span data-ttu-id="ed57c-107">Algunos componentes son específicos de las conferencias de acceso telefónico local y otros lo son de Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="ed57c-107">Some of the components are specific to dial-in conferencing and some are Enterprise Voice components.</span></span> <span data-ttu-id="ed57c-108">En esta sección se describen los requisitos de los componentes específicos de las conferencias de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="ed57c-108">This section describes the requirements for the components that are specific to dial-in conferencing.</span></span> <span data-ttu-id="ed57c-109">Para obtener más información sobre los requisitos del servidor de mediación y la puerta de enlace de la red telefónica conmutada (RTC), consulte [Mediation Server Component in Lync server 2013](lync-server-2013-mediation-server-component.md) , and [Components and Topologs for Mediation Server in Lync Server 2013](lync-server-2013-components-and-topologies-for-mediation-server.md) en la documentación de planeación.</span><span class="sxs-lookup"><span data-stu-id="ed57c-109">For details about Mediation Server and public switched telephone network (PSTN) gateway requirements, see [Mediation Server component in Lync Server 2013](lync-server-2013-mediation-server-component.md) and [Components and topologies for Mediation Server in Lync Server 2013](lync-server-2013-components-and-topologies-for-mediation-server.md) in the Planning documentation.</span></span>

<div>

## <a name="hardware-requirements"></a><span data-ttu-id="ed57c-110">Requisitos de hardware</span><span class="sxs-lookup"><span data-stu-id="ed57c-110">Hardware Requirements</span></span>

<span data-ttu-id="ed57c-111">Debido a que la conferencia web y la conferencia A/V se colocan con el servidor front-end, los requisitos de hardware del servidor son los mismos que para los servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="ed57c-111">Because web conferencing and A/V conferencing are collocated with the Front End Server, the server hardware requirements are the same as for the Front End Servers.</span></span> <span data-ttu-id="ed57c-112">Para obtener más información sobre los requisitos de hardware, vea [plataformas de hardware de servidor para Lync Server 2013](lync-server-2013-server-hardware-platforms.md) en la documentación sobre compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="ed57c-112">For details about hardware requirements, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Supportability documentation.</span></span> <span data-ttu-id="ed57c-113">Los siguientes componentes necesarios para las conferencias de acceso telefónico local también tienen los mismos requisitos de hardware que los servidores front-end:</span><span class="sxs-lookup"><span data-stu-id="ed57c-113">The following components required for dial-in conferencing also have the same hardware requirements as Front End Servers:</span></span>

  - <span data-ttu-id="ed57c-114">Servicio de aplicación</span><span class="sxs-lookup"><span data-stu-id="ed57c-114">Application service</span></span>

  - <span data-ttu-id="ed57c-115">Aplicación Operador de conferencia</span><span class="sxs-lookup"><span data-stu-id="ed57c-115">Conferencing Attendant application</span></span>

  - <span data-ttu-id="ed57c-116">Aplicación de anuncio de conferencia</span><span class="sxs-lookup"><span data-stu-id="ed57c-116">Conferencing Announcement application</span></span>

<span data-ttu-id="ed57c-117">Los requisitos de hardware para el servidor front-end son los mismos que para muchas otras funciones de servidor en Lync Server 2013 se describen en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="ed57c-117">The hardware requirements for Front End Server are the same as for many other server roles in Lync Server 2013 are outlined in the following table.</span></span>

</div>

<div>

## <a name="software-requirements"></a><span data-ttu-id="ed57c-118">Requisitos de software</span><span class="sxs-lookup"><span data-stu-id="ed57c-118">Software Requirements</span></span>

<span data-ttu-id="ed57c-119">Debido a que la conferencia web y la conferencia A/V se colocan con el servidor front-end, los requisitos de software del servidor son los mismos que para los servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="ed57c-119">Because web conferencing and A/V conferencing are collocated with the Front End Server, the server software requirements are the same as for the Front End Servers.</span></span> <span data-ttu-id="ed57c-120">Para obtener más información sobre los requisitos de software, consulte [Server and Tools Operating System support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) en la documentación sobre compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="ed57c-120">For details about software requirements, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

<span data-ttu-id="ed57c-121">Para las conferencias web, Lync Server 2013 también requiere Office Web Apps y Office Web Apps Server (antes conocido como servidor WAC) para controlar las presentaciones de PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="ed57c-121">For web conferencing, Lync Server 2013 also requires Office Web Apps and the Office Web Apps Server (formerly known as WAC Server) to handle PowerPoint presentations.</span></span> <span data-ttu-id="ed57c-122">Para obtener más información, consulte [Configuring Integration with Office Web Apps Server y Lync server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="ed57c-122">For details, see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

<span data-ttu-id="ed57c-123">Para las conferencias de acceso telefónico local, el servicio de aplicación, la aplicación operador de conferencia y la aplicación anuncio de Conferencia tienen los mismos requisitos de sistema operativo que los servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="ed57c-123">For dial-in conferencing, Application service, Conferencing Attendant application, and Conferencing Announcement application have the same operating system requirements as Front End Servers.</span></span> <span data-ttu-id="ed57c-124">Para obtener más información sobre los requisitos de software, consulte [Server and Tools Operating System support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) en la documentación sobre compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="ed57c-124">For details about software requirements, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

<span data-ttu-id="ed57c-125">La aplicación operador de conferencia y la aplicación anuncio de conferencia requieren que el tiempo de ejecución de Windows Media Format esté instalado en los servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="ed57c-125">Conferencing Attendant application and Conferencing Announcement application require that Windows Media Format Runtime is installed on Front End Servers.</span></span> <span data-ttu-id="ed57c-126">El tiempo de ejecución de Windows Media Format es necesario para reproducir archivos audio de Windows Media (WMA) que se usan para la música en espera, nombres registrados y avisos.</span><span class="sxs-lookup"><span data-stu-id="ed57c-126">The Windows Media Format Runtime is required to play Windows Media audio (WMA) files that are used for music on hold, recorded names, and prompts.</span></span> <span data-ttu-id="ed57c-127">Excepto en el caso de Windows Server 2012 y Windows Server 2012 R2, el tiempo de ejecución de Windows Media Format se instala automáticamente como parte de la experiencia del escritorio de Windows al ejecutar el programa de instalación, pero es posible que deba reiniciar el equipo.</span><span class="sxs-lookup"><span data-stu-id="ed57c-127">Except for Windows Server 2012 and Windows Server 2012 R2, the Windows Media Format Runtime is installed automatically as part of the Windows Desktop Experience when you run Setup, but you might need to restart the computer.</span></span> <span data-ttu-id="ed57c-128">Por lo tanto, recomendamos que instale como parte de la experiencia de escritorio de Windows, que incluye el tiempo de ejecución de Windows Media Format antes de ejecutar el programa de instalación.</span><span class="sxs-lookup"><span data-stu-id="ed57c-128">Therefore, we recommend that you install as part of the Windows Desktop Experience, which includes Windows Media Format Runtime before you run Setup.</span></span> <span data-ttu-id="ed57c-129">Windows Server 2012 y Windows Server 2012 R2 requieren Microsoft Media Foundation.</span><span class="sxs-lookup"><span data-stu-id="ed57c-129">Windows Server 2012 and Windows Server 2012 R2 requires Microsoft Media Foundation.</span></span>

</div>

<div>

## <a name="port-requirements-for-dial-in-conferencing"></a><span data-ttu-id="ed57c-130">Requisitos de puerto para conferencias de acceso telefónico local</span><span class="sxs-lookup"><span data-stu-id="ed57c-130">Port Requirements for dial-in conferencing</span></span>

<span data-ttu-id="ed57c-p107">En la tabla siguiente se describen los puertos usados por las conferencias de acceso telefónico local. Si usa un equilibrador de carga, asegúrese de que está configurado para los puertos usados por las aplicaciones que se ejecutarán en el grupo.</span><span class="sxs-lookup"><span data-stu-id="ed57c-p107">The following table describes the ports that are used by dial-in conferencing. If you use a load balancer, ensure that the load balancer is configured for the ports used by any applications that will run in the pool.</span></span>

<span data-ttu-id="ed57c-133">Estos puertos son configuraciones predeterminadas que se pueden cambiar mediante el cmdlet **Set-CsApplicationServer**.</span><span class="sxs-lookup"><span data-stu-id="ed57c-133">These ports are default settings that you can change by using the **Set-CsApplicationServer** cmdlet.</span></span> <span data-ttu-id="ed57c-134">Para obtener más información sobre este cmdlet, consulte la documentación del shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ed57c-134">For details about this cmdlet, see the Lync Server Management Shell documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ed57c-135">Todas las instancias de la misma aplicación en un grupo de servidores usan el mismo puerto de escucha de SIP.</span><span class="sxs-lookup"><span data-stu-id="ed57c-135">All instances of the same application in a pool use the same SIP listening port.</span></span>



</div>

### <a name="ports-used-by-dial-in-conferencing"></a><span data-ttu-id="ed57c-136">Puertos usados por las conferencias de acceso telefónico local</span><span class="sxs-lookup"><span data-stu-id="ed57c-136">Ports used by dial-in conferencing</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ed57c-137">Número de puerto</span><span class="sxs-lookup"><span data-stu-id="ed57c-137">Port number</span></span></th>
<th><span data-ttu-id="ed57c-138">Descripción</span><span class="sxs-lookup"><span data-stu-id="ed57c-138">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ed57c-139">5072</span><span class="sxs-lookup"><span data-stu-id="ed57c-139">5072</span></span></p></td>
<td><p><span data-ttu-id="ed57c-140">Usado por la aplicación de operador de conferencia para solicitudes de escucha SIP</span><span class="sxs-lookup"><span data-stu-id="ed57c-140">Used by Conferencing Attendant application for SIP listening requests</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed57c-141">5073</span><span class="sxs-lookup"><span data-stu-id="ed57c-141">5073</span></span></p></td>
<td><p><span data-ttu-id="ed57c-142">Usada por la aplicación de anuncio de conferencia para solicitudes de escucha SIP</span><span class="sxs-lookup"><span data-stu-id="ed57c-142">Used by Conferencing Announcement application for SIP listening requests</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="supported-clients-for-dial-in-conferencing"></a><span data-ttu-id="ed57c-143">Clientes admitidos para conferencias de acceso telefónico local</span><span class="sxs-lookup"><span data-stu-id="ed57c-143">Supported Clients for Dial-In Conferencing</span></span>

<span data-ttu-id="ed57c-144">Puede usar al siguiente cliente para programar conferencias locales que admiten el acceso telefónico local:</span><span class="sxs-lookup"><span data-stu-id="ed57c-144">You can use the following client to schedule on-premises conferences that support dial-in access:</span></span>

  - <span data-ttu-id="ed57c-145">Complemento para reunión en línea para Lync 2013 (se instala automáticamente al instalar Lync 2013 o asistente)</span><span class="sxs-lookup"><span data-stu-id="ed57c-145">Online Meeting Add-in for Lync 2013 (installed automatically when you install Lync 2013 or Attendee)</span></span>

</div>

<div>

## <a name="dial-in-conferencing-settings-page-requirements"></a><span data-ttu-id="ed57c-146">Requisitos de la página de configuración de conferencia de acceso telefónico local</span><span class="sxs-lookup"><span data-stu-id="ed57c-146">Dial-in Conferencing Settings page Requirements</span></span>

<span data-ttu-id="ed57c-147">La página de configuración de la Conferencia de acceso telefónico local admite las combinaciones de sistemas operativos y exploradores Web que se describen en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="ed57c-147">The Dial-in Conferencing Settings page supports the combinations of operating systems and web browsers described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ed57c-148">Las versiones de 32 bits y 64 bits de los sistemas operativos son compatibles.</span><span class="sxs-lookup"><span data-stu-id="ed57c-148">32-bit and 64-bit versions of the operating systems are supported.</span></span>



</div>

### <a name="supported-operating-systems-and-web-browsers"></a><span data-ttu-id="ed57c-149">Sistemas operativos y exploradores web compatibles</span><span class="sxs-lookup"><span data-stu-id="ed57c-149">Supported Operating Systems and Web Browsers</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ed57c-150">Sistema operativo</span><span class="sxs-lookup"><span data-stu-id="ed57c-150">Operating system</span></span></th>
<th><span data-ttu-id="ed57c-151">Explorador web</span><span class="sxs-lookup"><span data-stu-id="ed57c-151">Web browser</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ed57c-152">Windows 7</span><span class="sxs-lookup"><span data-stu-id="ed57c-152">Windows 7</span></span></p></td>
<td><p><span data-ttu-id="ed57c-153">Internet Explorer 9</span><span class="sxs-lookup"><span data-stu-id="ed57c-153">Internet Explorer 9</span></span></p>
<p><span data-ttu-id="ed57c-154">Internet Explorer 8</span><span class="sxs-lookup"><span data-stu-id="ed57c-154">Internet Explorer 8</span></span></p>
<p><span data-ttu-id="ed57c-155">Firefox</span><span class="sxs-lookup"><span data-stu-id="ed57c-155">Firefox</span></span></p></td>
</tr>
<tr class="even">
<td> </td>
<td> </td>
</tr>
<tr class="odd">
<td> </td>
<td> </td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed57c-156">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="ed57c-156">Windows Server 2008 R2</span></span></p></td>
<td><p><span data-ttu-id="ed57c-157">Internet Explorer 9</span><span class="sxs-lookup"><span data-stu-id="ed57c-157">Internet Explorer 9</span></span></p>
<p><span data-ttu-id="ed57c-158">Internet Explorer 8</span><span class="sxs-lookup"><span data-stu-id="ed57c-158">Internet Explorer 8</span></span></p>
<p><span data-ttu-id="ed57c-159">Internet Explorer 7</span><span class="sxs-lookup"><span data-stu-id="ed57c-159">Internet Explorer 7</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed57c-160">Mac OS</span><span class="sxs-lookup"><span data-stu-id="ed57c-160">Mac OS</span></span></p></td>
<td><p><span data-ttu-id="ed57c-161">Firefox</span><span class="sxs-lookup"><span data-stu-id="ed57c-161">Firefox</span></span></p>
<p><span data-ttu-id="ed57c-162">Safari</span><span class="sxs-lookup"><span data-stu-id="ed57c-162">Safari</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="audio-file-requirements-for-dial-in-conferencing"></a><span data-ttu-id="ed57c-163">Requisitos de archivo de audio para conferencias de acceso telefónico local</span><span class="sxs-lookup"><span data-stu-id="ed57c-163">Audio File Requirements for dial-in conferencing</span></span>

<span data-ttu-id="ed57c-164">Lync Server 2013 no admite la personalización de mensajes de voz y la música para conferencias de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="ed57c-164">Lync Server 2013 does not support customization of voice prompts and music for dial-in conferencing.</span></span> <span data-ttu-id="ed57c-165">Sin embargo, si tiene una gran necesidad empresarial que requiera cambiar los archivos de audio predeterminados, consulte el artículo de Microsoft Knowledge Base 961177, [How to Customize Voice prompts or files Music for Dial-in audioconferencia in Microsoft Office Communications Server 2007 R2](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=961177).</span><span class="sxs-lookup"><span data-stu-id="ed57c-165">However, if you have a strong business need that requires you to change the default audio files, see Microsoft Knowledge Base article 961177, [How to customize voice prompts or music files for dial-in audio conferencing in Microsoft Office Communications Server 2007 R2](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=961177).</span></span>

<span data-ttu-id="ed57c-166">También puede usar la herramienta de administración de [mensajes de voz personalizados del operador de conferencia de Microsoft Lync Server](https://go.microsoft.com/fwlink/p/?linkid=396880) , que permite a los administradores reemplazar los mensajes de voz predeterminados que se usan cuando un autor de llamada de teléfono se une a una reunión de Lync con mensajes personalizados para proporcionar una experiencia de entrada de reunión diferente.</span><span class="sxs-lookup"><span data-stu-id="ed57c-166">You can also use the [Microsoft Lync Server Conferencing Attendant Custom Voice Prompts](https://go.microsoft.com/fwlink/p/?linkid=396880) management utility, which enables administrators to replace the default voice prompts used when a phone caller joins a Lync meeting with custom prompts to provide a different meeting entry experience.</span></span> <span data-ttu-id="ed57c-167">Los mensajes de voz personalizados pueden instalarse en un servidor que ejecute Lync Server 2010 o Lync Server 2013, ya sea Enterprise o Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="ed57c-167">The custom voice prompts can be installed on a server that is running Lync Server 2010 or Lync Server 2013, either Enterprise or Standard Edition.</span></span>

<span data-ttu-id="ed57c-168">La aplicación operador de conferencia y la aplicación anuncio de Conferencia tienen los siguientes requisitos para los archivos de música en espera, nombre grabado y mensajes de audio:</span><span class="sxs-lookup"><span data-stu-id="ed57c-168">Conferencing Attendant application and Conferencing Announcement application have the following requirements for music on hold, recorded name, and audio prompt files:</span></span>

  - <span data-ttu-id="ed57c-169">Formato de archivo de audio de Windows Media (WMA)</span><span class="sxs-lookup"><span data-stu-id="ed57c-169">Windows Media Audio (WMA) file format</span></span>

  - <span data-ttu-id="ed57c-170">Mono de 16 bits</span><span class="sxs-lookup"><span data-stu-id="ed57c-170">16-bit mono</span></span>

  - <span data-ttu-id="ed57c-171">48 kbps CBR 2 pasos (velocidad de bits constante)</span><span class="sxs-lookup"><span data-stu-id="ed57c-171">48 kbps 2-pass CBR (constant bit rate)</span></span>

  - <span data-ttu-id="ed57c-172">Nivel de voz a -24DB</span><span class="sxs-lookup"><span data-stu-id="ed57c-172">Speech level at -24DB</span></span>

</div>

<div>

## <a name="user-requirements-for-dial-in-conferencing"></a><span data-ttu-id="ed57c-173">Requisitos de usuario para conferencias de acceso telefónico local</span><span class="sxs-lookup"><span data-stu-id="ed57c-173">User Requirements for Dial-In Conferencing</span></span>

<span data-ttu-id="ed57c-174">Los usuarios de conferencias de acceso telefónico local deben tener un número de teléfono único o una extensión asignada a su cuenta.</span><span class="sxs-lookup"><span data-stu-id="ed57c-174">Dial-in conferencing users must have a unique phone number or extension assigned to their account.</span></span> <span data-ttu-id="ed57c-175">Este requisito admite la autenticación durante las conferencias de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="ed57c-175">This requirement supports authentication during dial-in conferencing.</span></span> <span data-ttu-id="ed57c-176">Los usuarios empresariales (es decir, los usuarios que tienen credenciales de servicios de dominio de Active Directory y cuentas de Lync Server en la organización) escriben su número de teléfono (o extensión) y un número de identificación personal (PIN) para llamar a conferencias como un usuario autenticado.</span><span class="sxs-lookup"><span data-stu-id="ed57c-176">Enterprise users (that is, users who have Active Directory Domain Services credentials and Lync Server accounts within your organization) enter their phone number (or extension) and a personal identification number (PIN) to dial in to conferences as an authenticated user.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

