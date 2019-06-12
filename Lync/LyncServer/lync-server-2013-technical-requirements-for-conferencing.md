---
title: 'Lync Server 2013: Requisitos técnicos para conferencias'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Technical requirements for conferencing
ms:assetid: 3c0d89e1-53e6-46d7-bf8c-491260b292ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425889(v=OCS.15)
ms:contentKeyID: 48183923
ms.date: 06/26/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 719bd7f8de6fd7356a6b2e454cc86e9aa85abd6e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850455"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="c4b90-102">Requisitos técnicos para conferencias en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c4b90-102">Technical requirements for conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c4b90-103">_**Última modificación del tema:** 2014-06-25_</span><span class="sxs-lookup"><span data-stu-id="c4b90-103">_**Topic Last Modified:** 2014-06-25_</span></span>

<span data-ttu-id="c4b90-104">Para Lync Server 2013, las conferencias de acceso telefónico local, las conferencias A/V, las conferencias de mensajería instantánea (mi) y las capacidades de conferencia web siempre se ejecutan en servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="c4b90-104">For Lync Server 2013, dial-in conferencing, A/V conferencing, instant messaging (IM) conferencing and web conferencing capabilities always run on Front End Servers.</span></span>

<span data-ttu-id="c4b90-105">En esta sección se detallan los requisitos de hardware y software de estos servidores, junto con el collocation compatible.</span><span class="sxs-lookup"><span data-stu-id="c4b90-105">This section details the hardware and software requirements for these servers, along with the supported collocation.</span></span>

<span data-ttu-id="c4b90-106">Las conferencias de acceso telefónico local son una característica que incluye una variedad de componentes.</span><span class="sxs-lookup"><span data-stu-id="c4b90-106">Dial-in conferencing is a feature that includes a variety of components.</span></span> <span data-ttu-id="c4b90-107">Algunos de los componentes son específicos de las conferencias de acceso telefónico local y otros son componentes de telefonía empresarial.</span><span class="sxs-lookup"><span data-stu-id="c4b90-107">Some of the components are specific to dial-in conferencing and some are Enterprise Voice components.</span></span> <span data-ttu-id="c4b90-108">En esta sección se describen los requisitos para los componentes específicos de las conferencias de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="c4b90-108">This section describes the requirements for the components that are specific to dial-in conferencing.</span></span> <span data-ttu-id="c4b90-109">Para obtener más información sobre los requisitos de la puerta de enlace de red telefónica conmutada (RTC) y el servidor de mediación, consulte [componente servidor de mediación en Lync server 2013](lync-server-2013-mediation-server-component.md) , así como [componentes y topologías de servidor de mediación en Lync Server 2013](lync-server-2013-components-and-topologies-for-mediation-server.md) en la planificación documentación.</span><span class="sxs-lookup"><span data-stu-id="c4b90-109">For details about Mediation Server and public switched telephone network (PSTN) gateway requirements, see [Mediation Server component in Lync Server 2013](lync-server-2013-mediation-server-component.md) and [Components and topologies for Mediation Server in Lync Server 2013](lync-server-2013-components-and-topologies-for-mediation-server.md) in the Planning documentation.</span></span>

<div>

## <a name="hardware-requirements"></a><span data-ttu-id="c4b90-110">Requisitos de hardware</span><span class="sxs-lookup"><span data-stu-id="c4b90-110">Hardware Requirements</span></span>

<span data-ttu-id="c4b90-111">Debido a que las conferencias web y A/V se colocan con el servidor front-end, los requisitos de hardware del servidor son los mismos que los servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="c4b90-111">Because web conferencing and A/V conferencing are collocated with the Front End Server, the server hardware requirements are the same as for the Front End Servers.</span></span> <span data-ttu-id="c4b90-112">Para obtener más información sobre los requisitos de hardware, vea [plataformas de hardware de servidor para Lync Server 2013](lync-server-2013-server-hardware-platforms.md) en la documentación de soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="c4b90-112">For details about hardware requirements, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Supportability documentation.</span></span> <span data-ttu-id="c4b90-113">Los siguientes componentes necesarios para las conferencias de acceso telefónico local también tienen los mismos requisitos de hardware que los servidores front-end:</span><span class="sxs-lookup"><span data-stu-id="c4b90-113">The following components required for dial-in conferencing also have the same hardware requirements as Front End Servers:</span></span>

  - <span data-ttu-id="c4b90-114">Servicio de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="c4b90-114">Application service</span></span>

  - <span data-ttu-id="c4b90-115">Aplicación Operador de conferencia</span><span class="sxs-lookup"><span data-stu-id="c4b90-115">Conferencing Attendant application</span></span>

  - <span data-ttu-id="c4b90-116">Aplicación de anuncio de conferencia</span><span class="sxs-lookup"><span data-stu-id="c4b90-116">Conferencing Announcement application</span></span>

<span data-ttu-id="c4b90-117">Los requisitos de hardware para el servidor front-end son los mismos que para otros muchos roles de servidor de Lync Server 2013 se describen en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="c4b90-117">The hardware requirements for Front End Server are the same as for many other server roles in Lync Server 2013 are outlined in the following table.</span></span>

</div>

<div>

## <a name="software-requirements"></a><span data-ttu-id="c4b90-118">Requisitos de software</span><span class="sxs-lookup"><span data-stu-id="c4b90-118">Software Requirements</span></span>

<span data-ttu-id="c4b90-119">Debido a que las conferencias web y A/V se colocan con el servidor front-end, los requisitos de software del servidor son los mismos que los servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="c4b90-119">Because web conferencing and A/V conferencing are collocated with the Front End Server, the server software requirements are the same as for the Front End Servers.</span></span> <span data-ttu-id="c4b90-120">Para obtener más información sobre los requisitos de software, vea [compatibilidad del sistema operativo servidor y herramientas en Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) en la documentación de soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="c4b90-120">For details about software requirements, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

<span data-ttu-id="c4b90-121">Para las conferencias web, Lync Server 2013 también requiere Office Web Apps y Office Web Apps Server (anteriormente conocido como servidor WAC) para controlar presentaciones de PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="c4b90-121">For web conferencing, Lync Server 2013 also requires Office Web Apps and the Office Web Apps Server (formerly known as WAC Server) to handle PowerPoint presentations.</span></span> <span data-ttu-id="c4b90-122">Para obtener más información, vea [configurar la integración con Office Web Apps Server y Lync server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="c4b90-122">For details, see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

<span data-ttu-id="c4b90-123">Para las conferencias de acceso telefónico local, servicio de aplicaciones, operador de conferencias y aplicación de anuncio de Conferencia tienen los mismos requisitos del sistema operativo que los servidores de aplicaciones para el usuario.</span><span class="sxs-lookup"><span data-stu-id="c4b90-123">For dial-in conferencing, Application service, Conferencing Attendant application, and Conferencing Announcement application have the same operating system requirements as Front End Servers.</span></span> <span data-ttu-id="c4b90-124">Para obtener más información sobre los requisitos de software, vea [compatibilidad del sistema operativo servidor y herramientas en Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) en la documentación de soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="c4b90-124">For details about software requirements, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

<span data-ttu-id="c4b90-125">El Asistente de conferencia y la aplicación de anuncio de conferencia requieren que Windows Media Format Runtime esté instalado en los servidores frontales.</span><span class="sxs-lookup"><span data-stu-id="c4b90-125">Conferencing Attendant application and Conferencing Announcement application require that Windows Media Format Runtime is installed on Front End Servers.</span></span> <span data-ttu-id="c4b90-126">El tiempo de ejecución de Windows Media Format es necesario para reproducir archivos de audio de Windows Media (WMA) que se usan para música en espera, nombres grabados y avisos.</span><span class="sxs-lookup"><span data-stu-id="c4b90-126">The Windows Media Format Runtime is required to play Windows Media audio (WMA) files that are used for music on hold, recorded names, and prompts.</span></span> <span data-ttu-id="c4b90-127">Excepto en el caso de Windows Server 2012 y Windows Server 2012 R2, el tiempo de ejecución de Windows Media Format se instala automáticamente como parte de la experiencia de escritorio de Windows al ejecutar el programa de instalación, pero es posible que tenga que reiniciar el equipo.</span><span class="sxs-lookup"><span data-stu-id="c4b90-127">Except for Windows Server 2012 and Windows Server 2012 R2, the Windows Media Format Runtime is installed automatically as part of the Windows Desktop Experience when you run Setup, but you might need to restart the computer.</span></span> <span data-ttu-id="c4b90-128">Por lo tanto, le recomendamos que instale como parte de la experiencia de escritorio de Windows, que incluye el Windows Media Format Runtime antes de ejecutar el programa de instalación.</span><span class="sxs-lookup"><span data-stu-id="c4b90-128">Therefore, we recommend that you install as part of the Windows Desktop Experience, which includes Windows Media Format Runtime before you run Setup.</span></span> <span data-ttu-id="c4b90-129">Windows Server 2012 y Windows Server 2012 R2 requieren Microsoft Media Foundation.</span><span class="sxs-lookup"><span data-stu-id="c4b90-129">Windows Server 2012 and Windows Server 2012 R2 requires Microsoft Media Foundation.</span></span>

</div>

<div>

## <a name="port-requirements-for-dial-in-conferencing"></a><span data-ttu-id="c4b90-130">Requisitos de puerto para las conferencias de acceso telefónico local</span><span class="sxs-lookup"><span data-stu-id="c4b90-130">Port Requirements for dial-in conferencing</span></span>

<span data-ttu-id="c4b90-131">En la siguiente tabla se describen los puertos que usan las conferencias de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="c4b90-131">The following table describes the ports that are used by dial-in conferencing.</span></span> <span data-ttu-id="c4b90-132">Si usa un equilibrador de carga, asegúrese de que el equilibrador de carga está configurado para los puertos usados por todas las aplicaciones que se ejecutarán en el grupo.</span><span class="sxs-lookup"><span data-stu-id="c4b90-132">If you use a load balancer, ensure that the load balancer is configured for the ports used by any applications that will run in the pool.</span></span>

<span data-ttu-id="c4b90-133">Estos puertos son configuraciones predeterminadas que se pueden cambiar con el cmdlet **Set-CsApplicationServer**.</span><span class="sxs-lookup"><span data-stu-id="c4b90-133">These ports are default settings that you can change by using the **Set-CsApplicationServer** cmdlet.</span></span> <span data-ttu-id="c4b90-134">Para obtener más información sobre este cmdlet, consulte la documentación del shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c4b90-134">For details about this cmdlet, see the Lync Server Management Shell documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c4b90-135">Todas las instancias de la misma aplicación de un grupo usan el mismo puerto de escucha de SIP.</span><span class="sxs-lookup"><span data-stu-id="c4b90-135">All instances of the same application in a pool use the same SIP listening port.</span></span>



</div>

### <a name="ports-used-by-dial-in-conferencing"></a><span data-ttu-id="c4b90-136">Puertos usados por las conferencias de acceso telefónico local</span><span class="sxs-lookup"><span data-stu-id="c4b90-136">Ports used by dial-in conferencing</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c4b90-137">Número de puerto</span><span class="sxs-lookup"><span data-stu-id="c4b90-137">Port number</span></span></th>
<th><span data-ttu-id="c4b90-138">Descripción</span><span class="sxs-lookup"><span data-stu-id="c4b90-138">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c4b90-139">5072</span><span class="sxs-lookup"><span data-stu-id="c4b90-139">5072</span></span></p></td>
<td><p><span data-ttu-id="c4b90-140">Usado por la aplicación de operador de conferencia para solicitudes de escucha de SIP</span><span class="sxs-lookup"><span data-stu-id="c4b90-140">Used by Conferencing Attendant application for SIP listening requests</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4b90-141">5073</span><span class="sxs-lookup"><span data-stu-id="c4b90-141">5073</span></span></p></td>
<td><p><span data-ttu-id="c4b90-142">Usado por la aplicación de anuncios de conferencias para solicitudes de escucha de SIP</span><span class="sxs-lookup"><span data-stu-id="c4b90-142">Used by Conferencing Announcement application for SIP listening requests</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="supported-clients-for-dial-in-conferencing"></a><span data-ttu-id="c4b90-143">Clientes compatibles con conferencias de acceso telefónico local</span><span class="sxs-lookup"><span data-stu-id="c4b90-143">Supported Clients for Dial-In Conferencing</span></span>

<span data-ttu-id="c4b90-144">Puede usar el siguiente cliente para programar conferencias locales que admitan el acceso telefónico:</span><span class="sxs-lookup"><span data-stu-id="c4b90-144">You can use the following client to schedule on-premises conferences that support dial-in access:</span></span>

  - <span data-ttu-id="c4b90-145">Complemento de reunión en línea para Lync 2013 (se instala automáticamente al instalar Lync 2013 o asistente)</span><span class="sxs-lookup"><span data-stu-id="c4b90-145">Online Meeting Add-in for Lync 2013 (installed automatically when you install Lync 2013 or Attendee)</span></span>

</div>

<div>

## <a name="dial-in-conferencing-settings-page-requirements"></a><span data-ttu-id="c4b90-146">Requisitos de la página de configuración de la Conferencia de acceso telefónico local</span><span class="sxs-lookup"><span data-stu-id="c4b90-146">Dial-in Conferencing Settings page Requirements</span></span>

<span data-ttu-id="c4b90-147">La página de configuración de la Conferencia de acceso telefónico local admite las combinaciones de sistemas operativos y exploradores Web que se describen en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="c4b90-147">The Dial-in Conferencing Settings page supports the combinations of operating systems and web browsers described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c4b90-148">se admiten las versiones de 32 y 64 bits de los sistemas operativos.</span><span class="sxs-lookup"><span data-stu-id="c4b90-148">32-bit and 64-bit versions of the operating systems are supported.</span></span>



</div>

### <a name="supported-operating-systems-and-web-browsers"></a><span data-ttu-id="c4b90-149">Sistemas operativos y exploradores web compatibles</span><span class="sxs-lookup"><span data-stu-id="c4b90-149">Supported Operating Systems and Web Browsers</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c4b90-150">Sistema operativo</span><span class="sxs-lookup"><span data-stu-id="c4b90-150">Operating system</span></span></th>
<th><span data-ttu-id="c4b90-151">Explorador web</span><span class="sxs-lookup"><span data-stu-id="c4b90-151">Web browser</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c4b90-152">Windows 7</span><span class="sxs-lookup"><span data-stu-id="c4b90-152">Windows 7</span></span></p></td>
<td><p><span data-ttu-id="c4b90-153">Internet Explorer 9</span><span class="sxs-lookup"><span data-stu-id="c4b90-153">Internet Explorer 9</span></span></p>
<p><span data-ttu-id="c4b90-154">Internet Explorer 8</span><span class="sxs-lookup"><span data-stu-id="c4b90-154">Internet Explorer 8</span></span></p>
<p><span data-ttu-id="c4b90-155">Firefox</span><span class="sxs-lookup"><span data-stu-id="c4b90-155">Firefox</span></span></p></td>
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
<td><p><span data-ttu-id="c4b90-156">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="c4b90-156">Windows Server 2008 R2</span></span></p></td>
<td><p><span data-ttu-id="c4b90-157">Internet Explorer 9</span><span class="sxs-lookup"><span data-stu-id="c4b90-157">Internet Explorer 9</span></span></p>
<p><span data-ttu-id="c4b90-158">Internet Explorer 8</span><span class="sxs-lookup"><span data-stu-id="c4b90-158">Internet Explorer 8</span></span></p>
<p><span data-ttu-id="c4b90-159">Internet Explorer 7</span><span class="sxs-lookup"><span data-stu-id="c4b90-159">Internet Explorer 7</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4b90-160">Mac OS</span><span class="sxs-lookup"><span data-stu-id="c4b90-160">Mac OS</span></span></p></td>
<td><p><span data-ttu-id="c4b90-161">Firefox</span><span class="sxs-lookup"><span data-stu-id="c4b90-161">Firefox</span></span></p>
<p><span data-ttu-id="c4b90-162">Safari</span><span class="sxs-lookup"><span data-stu-id="c4b90-162">Safari</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="audio-file-requirements-for-dial-in-conferencing"></a><span data-ttu-id="c4b90-163">Requisitos de los archivos de audio para las conferencias de acceso telefónico local</span><span class="sxs-lookup"><span data-stu-id="c4b90-163">Audio File Requirements for dial-in conferencing</span></span>

<span data-ttu-id="c4b90-164">Lync Server 2013 no admite la personalización de mensajes de voz y de música para conferencias de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="c4b90-164">Lync Server 2013 does not support customization of voice prompts and music for dial-in conferencing.</span></span> <span data-ttu-id="c4b90-165">Sin embargo, si tiene una gran necesidad comercial que le exija cambiar los archivos de audio predeterminados, consulte el artículo 961177 de Microsoft Knowledge base, [Cómo personalizar las solicitudes de voz o los archivos de música para conferencias de audio de acceso telefónico local en Microsoft Office Communications Server 2007 R2](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=961177).</span><span class="sxs-lookup"><span data-stu-id="c4b90-165">However, if you have a strong business need that requires you to change the default audio files, see Microsoft Knowledge Base article 961177, [How to customize voice prompts or music files for dial-in audio conferencing in Microsoft Office Communications Server 2007 R2](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=961177).</span></span>

<span data-ttu-id="c4b90-166">También puede usar la herramienta de administración de [avisos de voz personalizadas del operador de conferencias de Microsoft Lync Server](http://go.microsoft.com/fwlink/p/?linkid=396880) , que permite a los administradores reemplazar los avisos de voz predeterminados que se usan cuando una persona que llama a la reunión se une a una reunión de Lync con avisos personalizados para proporcionar una una experiencia de reunión diferente.</span><span class="sxs-lookup"><span data-stu-id="c4b90-166">You can also use the [Microsoft Lync Server Conferencing Attendant Custom Voice Prompts](http://go.microsoft.com/fwlink/p/?linkid=396880) management utility, which enables administrators to replace the default voice prompts used when a phone caller joins a Lync meeting with custom prompts to provide a different meeting entry experience.</span></span> <span data-ttu-id="c4b90-167">Las solicitudes de voz personalizadas se pueden instalar en un servidor que ejecute Lync Server 2010 o Lync Server 2013, Enterprise o Standard.</span><span class="sxs-lookup"><span data-stu-id="c4b90-167">The custom voice prompts can be installed on a server that is running Lync Server 2010 or Lync Server 2013, either Enterprise or Standard Edition.</span></span>

<span data-ttu-id="c4b90-168">El operador de conferencia y la aplicación de anuncio de Conferencia tienen los siguientes requisitos de música en espera, nombre grabado y archivos de solicitud de audio:</span><span class="sxs-lookup"><span data-stu-id="c4b90-168">Conferencing Attendant application and Conferencing Announcement application have the following requirements for music on hold, recorded name, and audio prompt files:</span></span>

  - <span data-ttu-id="c4b90-169">Formato de archivo de audio de Windows Media (WMA)</span><span class="sxs-lookup"><span data-stu-id="c4b90-169">Windows Media Audio (WMA) file format</span></span>

  - <span data-ttu-id="c4b90-170">Mono de 16 bits</span><span class="sxs-lookup"><span data-stu-id="c4b90-170">16-bit mono</span></span>

  - <span data-ttu-id="c4b90-171">48 kbps CBR 2 pasos (velocidad de bits constante)</span><span class="sxs-lookup"><span data-stu-id="c4b90-171">48 kbps 2-pass CBR (constant bit rate)</span></span>

  - <span data-ttu-id="c4b90-172">Nivel de voz a -24DB</span><span class="sxs-lookup"><span data-stu-id="c4b90-172">Speech level at -24DB</span></span>

</div>

<div>

## <a name="user-requirements-for-dial-in-conferencing"></a><span data-ttu-id="c4b90-173">Requisitos de usuario para las conferencias de acceso telefónico local</span><span class="sxs-lookup"><span data-stu-id="c4b90-173">User Requirements for Dial-In Conferencing</span></span>

<span data-ttu-id="c4b90-174">Los usuarios de conferencias de acceso telefónico local necesitan tener un número de teléfono único o una extensión asignada a su cuenta.</span><span class="sxs-lookup"><span data-stu-id="c4b90-174">Dial-in conferencing users must have a unique phone number or extension assigned to their account.</span></span> <span data-ttu-id="c4b90-175">Este requisito admite la autenticación durante las conferencias de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="c4b90-175">This requirement supports authentication during dial-in conferencing.</span></span> <span data-ttu-id="c4b90-176">Los usuarios empresariales (es decir, los usuarios que tienen credenciales de servicios de dominio de Active Directory y cuentas de Lync Server dentro de su organización) escriben su número de teléfono (o extensión) y un número de identificación personal (PIN) para llamar a conferencias como un usuario autenticado.</span><span class="sxs-lookup"><span data-stu-id="c4b90-176">Enterprise users (that is, users who have Active Directory Domain Services credentials and Lync Server accounts within your organization) enter their phone number (or extension) and a personal identification number (PIN) to dial in to conferences as an authenticated user.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

