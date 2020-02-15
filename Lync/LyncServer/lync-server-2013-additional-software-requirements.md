---
title: 'Lync Server 2013: requisitos de software adicionales'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Additional software requirements
ms:assetid: 87b318e3-03ae-41f7-af5e-29bb294f6af0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398686(v=OCS.15)
ms:contentKeyID: 48184731
ms.date: 12/09/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4eb8bb73a94ad9fb833aa2d44b0ce6c14447b9d0
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038472"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="additional-software-requirements-for-lync-server-2013"></a><span data-ttu-id="00fba-102">Requisitos de software adicionales para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="00fba-102">Additional software requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="00fba-103">_**Última modificación del tema:** 2016-12-08_</span><span class="sxs-lookup"><span data-stu-id="00fba-103">_**Topic Last Modified:** 2016-12-08_</span></span>

<span data-ttu-id="00fba-104">Además de los requisitos de hardware y sistema operativo para las plataformas de servidor, Lync Server 2013 requiere la instalación de software adicional en los servidores que se implementan.</span><span class="sxs-lookup"><span data-stu-id="00fba-104">In addition to the hardware and operating system requirements for server platforms, Lync Server 2013 requires the installation of additional software on the servers that you deploy.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="00fba-105">Para obtener más información sobre los requisitos de plataforma para servidores que ejecutan Lync Server, consulte <A href="lync-server-2013-server-hardware-platforms.md">plataformas de hardware de servidor para Lync server 2013</A> y la <A href="lync-server-2013-server-and-tools-operating-system-support.md">compatibilidad con sistemas operativos de servidor y herramientas en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="00fba-105">For details about the platform requirements for servers running Lync Server, see <A href="lync-server-2013-server-hardware-platforms.md">Server hardware platforms for Lync Server 2013</A> and <A href="lync-server-2013-server-and-tools-operating-system-support.md">Server and tools operating system support in Lync Server 2013</A>.</span></span> <span data-ttu-id="00fba-106">Para obtener más información sobre los requisitos del sistema para equipos cliente y dispositivos, consulte <A href="lync-server-2013-planning-for-clients-and-devices.md">Planning for clients and Devices in Lync Server 2013</A> en la documentación referente a la planeación.</span><span class="sxs-lookup"><span data-stu-id="00fba-106">For details about system requirements for client computers and devices, see <A href="lync-server-2013-planning-for-clients-and-devices.md">Planning for clients and devices in Lync Server 2013</A> in the Planning documentation.</span></span> <span data-ttu-id="00fba-107">Para obtener más información sobre los requisitos de software para herramientas administrativas, consulte <A href="lync-server-2013-administrative-tools-software-requirements.md">Administrative Tools software requirements in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="00fba-107">For details about software requirements for administrative tools, see <A href="lync-server-2013-administrative-tools-software-requirements.md">Administrative tools software requirements in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="additional-software-necessary-for-all-internal-server-roles"></a><span data-ttu-id="00fba-108">Software adicional necesario para todos los roles de servidor internos</span><span class="sxs-lookup"><span data-stu-id="00fba-108">Additional Software Necessary for All Internal Server Roles</span></span>

<span data-ttu-id="00fba-109">En esta sección se enumera el software necesario en todos los roles de servidor internos, todos los roles de servidor de Lync Server excepto el servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="00fba-109">This section lists software necessary on all internal server roles, which are all Lync Server server roles except for Edge Server.</span></span> <span data-ttu-id="00fba-110">Los requisitos para los servidores perimetrales y los grupos de servidores perimetrales se enumeran más adelante en este tema, en **software adicional para servidores perimetrales**.</span><span class="sxs-lookup"><span data-stu-id="00fba-110">The requirements for the Edge Servers and Edge pools are listed later in this topic under **Additional Software for Edge Servers**.</span></span>

</div>

<div>

## <a name="windows-powershell-30"></a><span data-ttu-id="00fba-111">Windows PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="00fba-111">Windows PowerShell 3.0</span></span>

<span data-ttu-id="00fba-112">Cada servidor que ejecuta Lync Server 2013 debe tener instalada la versión correcta de Windows PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="00fba-112">Each server running Lync Server 2013 must have the correct release of Windows PowerShell 3.0 installed.</span></span> <span data-ttu-id="00fba-113">Para obtener más información, consulte [Installing Windows PowerShell 3,0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).</span><span class="sxs-lookup"><span data-stu-id="00fba-113">For details, see [Installing Windows PowerShell 3.0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).</span></span>

</div>

<div>

## <a name="microsoft-net-framework-45"></a><span data-ttu-id="00fba-114">Microsoft .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="00fba-114">Microsoft .NET Framework 4.5</span></span>

<span data-ttu-id="00fba-115">Lync Server requiere Microsoft .NET Framework 4,5 en todos los roles de servidor interno y en cualquier equipo en el que vaya a ejecutar las herramientas administrativas de Lync Server o Microsoft Lync Server 2013, herramienta de planeación.</span><span class="sxs-lookup"><span data-stu-id="00fba-115">Lync Server requires Microsoft .NET Framework 4.5 on all internal server roles and on any computer where you will run the Lync Server administrative tools or Microsoft Lync Server 2013, Planning Tool.</span></span> <span data-ttu-id="00fba-116">Para Lync Server 2013, debe instalar manualmente la edición de 64 bits de Microsoft .NET Framework 4,5 en el servidor antes de instalar Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="00fba-116">For Lync Server 2013, you must manually install the 64-bit edition of Microsoft .NET Framework 4.5 on the server prior to installing Lync Server 2013.</span></span> <span data-ttu-id="00fba-117">Para instalarlo manualmente, descargue Microsoft .NET 4,5 Framework desde el centro de descarga de Microsoft en[https://go.microsoft.com/fwlink/p/?LinkId=268529](https://go.microsoft.com/fwlink/p/?linkid=268529)</span><span class="sxs-lookup"><span data-stu-id="00fba-117">To manually install it, download the Microsoft .NET 4.5 Framework from the Microsoft Download Center at [https://go.microsoft.com/fwlink/p/?LinkId=268529](https://go.microsoft.com/fwlink/p/?linkid=268529)</span></span>

<div>

## <a name="installing-microsoft-net-framework-45-on-servers-running-windows-server-2012"></a><span data-ttu-id="00fba-118">Instalación de Microsoft .NET Framework 4,5 en servidores que ejecutan Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="00fba-118">Installing Microsoft .NET Framework 4.5 on Servers Running Windows Server 2012</span></span>

<span data-ttu-id="00fba-119">Al instalar Microsoft .NET Framework 4,5 en servidores que van a ejecutar Lync Server 2013 y Windows Server 2012, debe realizar un paso adicional.</span><span class="sxs-lookup"><span data-stu-id="00fba-119">When you install Microsoft .NET Framework 4.5 on servers that will run Lync Server 2013 and Windows Server 2012, you must perform one additional step.</span></span> <span data-ttu-id="00fba-120">Una vez instalado .NET Framework 4,5, use el administrador del servidor para instalar la activación HTTP.</span><span class="sxs-lookup"><span data-stu-id="00fba-120">After .NET Framework 4.5 is installed, use Server Manager to install HTTP Activation.</span></span>

<span data-ttu-id="00fba-121">**Para instalar la activación HTTP de .NET 4,5 en Windows Server 2012**</span><span class="sxs-lookup"><span data-stu-id="00fba-121">**To Install .NET 4.5 HTTP Activation on Windows Server 2012**</span></span>

1.  <span data-ttu-id="00fba-122">En el menú **Inicio** , haga clic en **programas**, seleccione **herramientas administrativas**y, a continuación, haga clic en **Administrador de servidores**.</span><span class="sxs-lookup"><span data-stu-id="00fba-122">From the **Start** menu, click **Programs**, then click **Administrative Tools**, then click **Server Manager**.</span></span>

2.  <span data-ttu-id="00fba-123">En Administrador del servidor, en **Resumen de características**, elija **Agregar características**.</span><span class="sxs-lookup"><span data-stu-id="00fba-123">In Server Manager, under **Features Summary**, choose **Add Features**.</span></span>

3.  <span data-ttu-id="00fba-124">Expanda **.NET Framework 4,5**.</span><span class="sxs-lookup"><span data-stu-id="00fba-124">Expand **.NET Framework 4.5**.</span></span>

4.  <span data-ttu-id="00fba-125">Seleccione **activación de WCF** si aún no está seleccionada.</span><span class="sxs-lookup"><span data-stu-id="00fba-125">Select **WCF Activation** if it isn’t already selected.</span></span> <span data-ttu-id="00fba-126">A continuación, seleccione **activación http**.</span><span class="sxs-lookup"><span data-stu-id="00fba-126">Then select **HTTP Activation**.</span></span>

5.  <span data-ttu-id="00fba-127">Haga clic en **siguiente** y siga las instrucciones para finalizar la instalación.</span><span class="sxs-lookup"><span data-stu-id="00fba-127">Click **Next** and follow the prompts to finish the installation.</span></span>

</div>

</div>

<div>

## <a name="windows-identity-foundation"></a><span data-ttu-id="00fba-128">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="00fba-128">Windows Identity Foundation</span></span>

<span data-ttu-id="00fba-129">**Windows Identity Foundation** en Lync Server 2013 requiere la instalación de Windows Identity Foundation para admitir escenarios de autenticación de servidor a servidor.</span><span class="sxs-lookup"><span data-stu-id="00fba-129">**Windows Identity Foundation** in Lync Server 2013 requires the installation of Windows Identity Foundation in order to support server to server authentication scenarios.</span></span> <span data-ttu-id="00fba-130">Windows Server 2008 R2 y Windows Server 2012 requieren diferentes procedimientos para instalar la base de identidad de Windows.</span><span class="sxs-lookup"><span data-stu-id="00fba-130">Windows Server 2008 R2 and Windows Server 2012 require different procedures to install the Windows Identify Foundation.</span></span> <span data-ttu-id="00fba-131">Seleccione el sistema operativo del servidor de la siguiente lista:</span><span class="sxs-lookup"><span data-stu-id="00fba-131">Select your server operating system from the following list:</span></span>

  - <span data-ttu-id="00fba-132">Windows Server 2008 R2 para Windows Server 2008 R2, puede comprobar si ya se ha instalado en el equipo.</span><span class="sxs-lookup"><span data-stu-id="00fba-132">Windows Server 2008 R2   For Windows Server 2008 R2, you check to see if it has already been installed on your computer.</span></span> <span data-ttu-id="00fba-133">Para ello, vaya a **Agregar o quitar programas**, **vea actualizaciones instaladas**y busque en **Windows** la entrada **Windows Identity Foundation (KB974405)**.</span><span class="sxs-lookup"><span data-stu-id="00fba-133">To do this, go to **Add/Remove Programs**, **View Installed Updates**, and look under **Windows** for the entry **Windows Identity Foundation (KB974405)**.</span></span> <span data-ttu-id="00fba-134">Para obtener más información sobre cómo instalar Windows Identity [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657)Foundation, consulte.</span><span class="sxs-lookup"><span data-stu-id="00fba-134">For details about installing Windows Identity Foundation, see [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657).</span></span>

  - <span data-ttu-id="00fba-135">Windows Server 2012 para Windows Server 2012, use el **Administrador de servidores** para instalar Windows Identity Foundation.</span><span class="sxs-lookup"><span data-stu-id="00fba-135">Windows Server 2012   For Windows Server 2012, you use **Server Manager** to install the Windows Identity Foundation.</span></span> <span data-ttu-id="00fba-136">En el **Asistente para agregar roles y características**del administrador del servidor, seleccione **características**.</span><span class="sxs-lookup"><span data-stu-id="00fba-136">In the Server Manager **Add Roles and Features Wizard**, select **Features**.</span></span> <span data-ttu-id="00fba-137">Seleccione **Windows Identity Foundation 3,5** en la lista.</span><span class="sxs-lookup"><span data-stu-id="00fba-137">Select **Windows Identity Foundation 3.5** from the list.</span></span> <span data-ttu-id="00fba-138">Haga clic en **siguiente**y, a continuación, en **instalar**.</span><span class="sxs-lookup"><span data-stu-id="00fba-138">Click **Next**, then click **Install**.</span></span>

</div>

<div>

## <a name="additional-software-for-all-front-end-servers-and-standard-edition-servers"></a><span data-ttu-id="00fba-139">Software adicional para todos los servidores front-end y servidores Standard Edition</span><span class="sxs-lookup"><span data-stu-id="00fba-139">Additional Software for All Front End Servers and Standard Edition Servers</span></span>

<span data-ttu-id="00fba-140">Todos los servidores front-end y los servidores Standard Edition también deben ejecutar Internet Information Services (IIS) con determinados módulos.</span><span class="sxs-lookup"><span data-stu-id="00fba-140">All Front End Servers and Standard Edition servers must also run Internet Information Services (IIS) with certain modules.</span></span> <span data-ttu-id="00fba-141">Además, todos los servidores front-end y los servidores Standard Edition en los que se implementan las conferencias, la aplicación de estacionamiento de llamadas, el anuncio o los grupos de respuesta deben ejecutar el tiempo de ejecución de Windows Media Format.</span><span class="sxs-lookup"><span data-stu-id="00fba-141">Additionally, all Front End Servers and Standard Edition servers where conferencing, Call Park application, Announcement, or Response Groups are deployed must run Windows Media Format Runtime.</span></span>

<div>

## <a name="internet-information-services-iis"></a><span data-ttu-id="00fba-142">Internet Information Services (IIS)</span><span class="sxs-lookup"><span data-stu-id="00fba-142">Internet Information Services (IIS)</span></span>

<span data-ttu-id="00fba-143">Los servidores front-end y los servidores Standard Edition deben ejecutar Internet Information Services (IIS), con los siguientes módulos:</span><span class="sxs-lookup"><span data-stu-id="00fba-143">Front End Servers and Standard Edition servers must run Internet Information Services (IIS), with the following modules:</span></span>

  - <span data-ttu-id="00fba-144">Contenido estático</span><span class="sxs-lookup"><span data-stu-id="00fba-144">Static Content</span></span>

  - <span data-ttu-id="00fba-145">Documento predeterminado</span><span class="sxs-lookup"><span data-stu-id="00fba-145">Default Document</span></span>

  - <span data-ttu-id="00fba-146">Errores HTTP</span><span class="sxs-lookup"><span data-stu-id="00fba-146">HTTP Errors</span></span>

  - <span data-ttu-id="00fba-147">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="00fba-147">ASP.NET</span></span>

  - <span data-ttu-id="00fba-148">Extensibilidad de .NET</span><span class="sxs-lookup"><span data-stu-id="00fba-148">.NET Extensibility</span></span>

  - <span data-ttu-id="00fba-149">Extensiones de Internet Server API (ISAPI)</span><span class="sxs-lookup"><span data-stu-id="00fba-149">Internet Server API (ISAPI) Extensions</span></span>

  - <span data-ttu-id="00fba-150">Filtros ISAPI</span><span class="sxs-lookup"><span data-stu-id="00fba-150">ISAPI Filters</span></span>

  - <span data-ttu-id="00fba-151">Registro HTTP</span><span class="sxs-lookup"><span data-stu-id="00fba-151">HTTP Logging</span></span>

  - <span data-ttu-id="00fba-152">Herramientas de registro</span><span class="sxs-lookup"><span data-stu-id="00fba-152">Logging Tools</span></span>

  - <span data-ttu-id="00fba-153">Seguimiento</span><span class="sxs-lookup"><span data-stu-id="00fba-153">Tracing</span></span>

  - <span data-ttu-id="00fba-154">Autenticación de Windows</span><span class="sxs-lookup"><span data-stu-id="00fba-154">Windows Authentication</span></span>

  - <span data-ttu-id="00fba-155">Filtro de solicitudes</span><span class="sxs-lookup"><span data-stu-id="00fba-155">Request Filtering</span></span>

  - <span data-ttu-id="00fba-156">Compresión de contenido estático</span><span class="sxs-lookup"><span data-stu-id="00fba-156">Static Content Compression</span></span>

  - <span data-ttu-id="00fba-157">Compresión de contenido dinámico</span><span class="sxs-lookup"><span data-stu-id="00fba-157">Dynamic Content Compression</span></span>

  - <span data-ttu-id="00fba-158">Consola de administración de IIS</span><span class="sxs-lookup"><span data-stu-id="00fba-158">IIS Management Console</span></span>

  - <span data-ttu-id="00fba-159">Scripts y herramientas de administración de IIS</span><span class="sxs-lookup"><span data-stu-id="00fba-159">IIS Management Scripts and Tools</span></span>

  - <span data-ttu-id="00fba-160">Autenticación anónima (se instala de forma predeterminada al instalar IIS).</span><span class="sxs-lookup"><span data-stu-id="00fba-160">Anonymous Authentication (this is installed by default when IIS is installed.)</span></span>

  - <span data-ttu-id="00fba-161">Autenticación por asignación de certificados de clientes</span><span class="sxs-lookup"><span data-stu-id="00fba-161">Client Certificate Mapping Authentication</span></span>

</div>

<div>

## <a name="windows-media-format-runtime-and-windows-desktop-experience"></a><span data-ttu-id="00fba-162">Tiempo de ejecución de Windows Media Format y experiencia de escritorio de Windows</span><span class="sxs-lookup"><span data-stu-id="00fba-162">Windows Media Format Runtime and Windows Desktop Experience</span></span>

<span data-ttu-id="00fba-163">**Experiencia de escritorio de Windows** Todos los servidores front-end y los servidores Standard Edition en los que se va a implementar la Conferencia deben tener instalado el tiempo de ejecución de Windows Media Format, que, excepto Windows Server 2012, se instala como parte de la experiencia del escritorio de Windows.</span><span class="sxs-lookup"><span data-stu-id="00fba-163">**Windows Desktop Experience** All Front End Servers and Standard Edition servers where conferencing will be deployed must have the Windows Media Format Runtime installed, which, except for Windows Server 2012 is installed as part of the Windows desktop experience.</span></span> <span data-ttu-id="00fba-164">Windows Server 2012 requiere Microsoft Media Foundation.</span><span class="sxs-lookup"><span data-stu-id="00fba-164">Windows Server 2012 requires Microsoft Media Foundation.</span></span> <span data-ttu-id="00fba-165">Este software es necesario para ejecutar los archivos de Windows Media Audio (.wma) que reproducen las aplicaciones de estacionamiento de llamadas, anuncio y grupo de respuesta para los anuncios y la música.</span><span class="sxs-lookup"><span data-stu-id="00fba-165">The Windows Media Format Runtime is required to run the Windows Media Audio (.wma) files that the Call Park, Announcement, and Response Group applications play for announcements and music.</span></span>

<span data-ttu-id="00fba-166">Le recomendamos que instale la experiencia de escritorio de Windows antes de instalar Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="00fba-166">We recommend that you install Windows desktop experience before you install Lync Server 2013.</span></span> <span data-ttu-id="00fba-167">Si Lync Server 2013 no encuentra este software en el servidor, se le pedirá que lo instale y, a continuación, deberá reiniciar el servidor para completar la instalación.</span><span class="sxs-lookup"><span data-stu-id="00fba-167">If Lync Server 2013 does not find this software on the server, it will prompt you to install it, and then you must restart the server to complete installation.</span></span>

</div>

</div>

<div>

## <a name="additional-software-for-front-end-servers-and-standard-edition-servers-running-on-windows-server-2012"></a><span data-ttu-id="00fba-168">Software adicional para servidores front-end y servidores Standard Edition que se ejecutan en Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="00fba-168">Additional Software for Front End Servers and Standard Edition Servers Running on Windows Server 2012</span></span>

<span data-ttu-id="00fba-169">Los servidores front-end requieren .NET 3,5, que no está instalado de forma predeterminada en Windows Server 2012.</span><span class="sxs-lookup"><span data-stu-id="00fba-169">Front End Servers require .NET 3.5, which is not installed by default on Windows Server 2012.</span></span> <span data-ttu-id="00fba-170">Para instalarlo, coloque los medios de instalación de Windows Server 2012 en la unidad D y escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="00fba-170">To install it, put your Windows Server 2012 installation media in Drive D and type the following:</span></span>

    Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Desktop-Experience, Telnet-Client, BITS -Source D:\sources\sxs

<span data-ttu-id="00fba-171">Para obtener más información sobre cómo instalar .NET 3,5 en servidores que ejecutan Windows Server 2012, consulte "consideraciones de implementación <https://go.microsoft.com/fwlink/p/?linkid=275032>de Microsoft .net Framework 3,5" en.</span><span class="sxs-lookup"><span data-stu-id="00fba-171">For details about installing .NET 3.5 on servers running Windows Server 2012, see "Microsoft .NET Framework 3.5 Deployment Considerations" at <https://go.microsoft.com/fwlink/p/?linkid=275032>.</span></span>

</div>

<div>

## <a name="additional-software-for-directors"></a><span data-ttu-id="00fba-172">Software adicional para directores</span><span class="sxs-lookup"><span data-stu-id="00fba-172">Additional Software for Directors</span></span>

<span data-ttu-id="00fba-173">Los directores deben ejecutar Internet Information Services (IIS), con los siguientes módulos:</span><span class="sxs-lookup"><span data-stu-id="00fba-173">Directors must run Internet Information Services (IIS), with the following modules:</span></span>

  - <span data-ttu-id="00fba-174">Contenido estático</span><span class="sxs-lookup"><span data-stu-id="00fba-174">Static Content</span></span>

  - <span data-ttu-id="00fba-175">Documento predeterminado</span><span class="sxs-lookup"><span data-stu-id="00fba-175">Default Document</span></span>

  - <span data-ttu-id="00fba-176">Errores HTTP</span><span class="sxs-lookup"><span data-stu-id="00fba-176">HTTP Errors</span></span>

  - <span data-ttu-id="00fba-177">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="00fba-177">ASP.NET</span></span>

  - <span data-ttu-id="00fba-178">Extensibilidad de .NET</span><span class="sxs-lookup"><span data-stu-id="00fba-178">.NET Extensibility</span></span>

  - <span data-ttu-id="00fba-179">Extensiones de Internet Server API (ISAPI)</span><span class="sxs-lookup"><span data-stu-id="00fba-179">Internet Server API (ISAPI) Extensions</span></span>

  - <span data-ttu-id="00fba-180">Filtros ISAPI</span><span class="sxs-lookup"><span data-stu-id="00fba-180">ISAPI Filters</span></span>

  - <span data-ttu-id="00fba-181">Registro HTTP</span><span class="sxs-lookup"><span data-stu-id="00fba-181">HTTP Logging</span></span>

  - <span data-ttu-id="00fba-182">Herramientas de registro</span><span class="sxs-lookup"><span data-stu-id="00fba-182">Logging Tools</span></span>

  - <span data-ttu-id="00fba-183">Seguimiento</span><span class="sxs-lookup"><span data-stu-id="00fba-183">Tracing</span></span>

  - <span data-ttu-id="00fba-184">Autenticación de Windows</span><span class="sxs-lookup"><span data-stu-id="00fba-184">Windows Authentication</span></span>

  - <span data-ttu-id="00fba-185">Filtro de solicitudes</span><span class="sxs-lookup"><span data-stu-id="00fba-185">Request Filtering</span></span>

  - <span data-ttu-id="00fba-186">Compresión de contenido estático</span><span class="sxs-lookup"><span data-stu-id="00fba-186">Static Content Compression</span></span>

  - <span data-ttu-id="00fba-187">Consola de administración de IIS</span><span class="sxs-lookup"><span data-stu-id="00fba-187">IIS Management Console</span></span>

  - <span data-ttu-id="00fba-188">Scripts y herramientas de administración de IIS</span><span class="sxs-lookup"><span data-stu-id="00fba-188">IIS Management Scripts and Tools</span></span>

  - <span data-ttu-id="00fba-189">Autenticación anónima (se instala de forma predeterminada al instalar IIS)</span><span class="sxs-lookup"><span data-stu-id="00fba-189">Anonymous Authentication (This is installed by default when IIS is installed.)</span></span>

  - <span data-ttu-id="00fba-190">Autenticación por asignación de certificados de clientes</span><span class="sxs-lookup"><span data-stu-id="00fba-190">Client Certificate Mapping Authentication</span></span>

</div>

<div>

## <a name="additional-software-for-persistent-chat-front-end-servers"></a><span data-ttu-id="00fba-191">Software adicional para servidores front-end de chat persistente</span><span class="sxs-lookup"><span data-stu-id="00fba-191">Additional Software for Persistent Chat Front End Servers</span></span>

<span data-ttu-id="00fba-192">Los servidores front-end de chat persistente deben ejecutar Message Queuing (también conocido como MSMQ), que es un componente de Windows Server.</span><span class="sxs-lookup"><span data-stu-id="00fba-192">Persistent Chat Front End Servers must run Message Queuing (also known as MSMQ), which is a component of Windows Server.</span></span>

<span data-ttu-id="00fba-193">Para obtener información sobre cómo habilitar MSMQ, [haga clic aquí.](https://technet.microsoft.com/library/cc771474.aspx)</span><span class="sxs-lookup"><span data-stu-id="00fba-193">For information on enabling MSMQ, [click here.](https://technet.microsoft.com/library/cc771474.aspx)</span></span>

</div>

<div>

## <a name="additional-software-for-edge-servers"></a><span data-ttu-id="00fba-194">Software adicional para servidores perimetrales</span><span class="sxs-lookup"><span data-stu-id="00fba-194">Additional Software for Edge Servers</span></span>

<span data-ttu-id="00fba-195">Los servidores perimetrales requieren el siguiente software:</span><span class="sxs-lookup"><span data-stu-id="00fba-195">Edge Servers require the following software:</span></span>

  - <span data-ttu-id="00fba-196">Cada servidor que ejecuta Lync Server 2013 debe tener instalada la versión correcta de Windows PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="00fba-196">Each server running Lync Server 2013 must have the correct release of Windows PowerShell 3.0 installed.</span></span> <span data-ttu-id="00fba-197">Para obtener más información, consulte [Installing Windows PowerShell 3,0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).</span><span class="sxs-lookup"><span data-stu-id="00fba-197">For details, see [Installing Windows PowerShell 3.0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).</span></span>

  - <span data-ttu-id="00fba-198">Lync Server requiere Microsoft .NET Framework 4,5.</span><span class="sxs-lookup"><span data-stu-id="00fba-198">Lync Server requires Microsoft .NET Framework 4.5.</span></span> <span data-ttu-id="00fba-199">Para Lync Server 2013 instalado en Windows Server 2008 R2, debe instalar manualmente la edición de 64 bits de Microsoft .NET Framework 4,5 en el servidor antes de instalar Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="00fba-199">For Lync Server 2013 installed on Windows Server 2008 R2, you must manually install the 64-bit edition of Microsoft .NET Framework 4.5 on the server prior to installing Lync Server 2013.</span></span> <span data-ttu-id="00fba-200">Para instalarlo manualmente, descargue Microsoft .NET 4,5 Framework desde el centro de descarga de Microsoft en[https://go.microsoft.com/fwlink/p/?LinkId=268529](https://go.microsoft.com/fwlink/p/?linkid=268529)</span><span class="sxs-lookup"><span data-stu-id="00fba-200">To manually install it, download the Microsoft .NET 4.5 Framework from the Microsoft Download Center at [https://go.microsoft.com/fwlink/p/?LinkId=268529](https://go.microsoft.com/fwlink/p/?linkid=268529)</span></span>

  - <span data-ttu-id="00fba-201">**Windows Identity Foundation** en Lync Server 2013 requiere la instalación de Windows Identity Foundation para admitir escenarios de autenticación de servidor a servidor.</span><span class="sxs-lookup"><span data-stu-id="00fba-201">**Windows Identity Foundation** in Lync Server 2013 requires the installation of Windows Identity Foundation in order to support server to server authentication scenarios.</span></span> <span data-ttu-id="00fba-202">Windows Server 2008 R2 y Windows Server 2012 requieren diferentes procedimientos para instalar la base de identidad de Windows.</span><span class="sxs-lookup"><span data-stu-id="00fba-202">Windows Server 2008 R2 and Windows Server 2012 require different procedures to install the Windows Identify Foundation.</span></span> <span data-ttu-id="00fba-203">Seleccione el sistema operativo del servidor de la siguiente lista:</span><span class="sxs-lookup"><span data-stu-id="00fba-203">Select your server operating system from the following list:</span></span>
    
      - <span data-ttu-id="00fba-204">Windows Server 2008 R2 para Windows Server 2008 R2, puede comprobar si ya se ha instalado en el equipo.</span><span class="sxs-lookup"><span data-stu-id="00fba-204">Windows Server 2008 R2   For Windows Server 2008 R2, you check to see if it has already been installed on your computer.</span></span> <span data-ttu-id="00fba-205">Para ello, vaya a **Agregar o quitar programas**, **vea actualizaciones instaladas**y busque en **Windows** la entrada **Windows Identity Foundation (KB974405)**.</span><span class="sxs-lookup"><span data-stu-id="00fba-205">To do this, go to **Add/Remove Programs**, **View Installed Updates**, and look under **Windows** for the entry **Windows Identity Foundation (KB974405)**.</span></span> <span data-ttu-id="00fba-206">Para obtener más información sobre cómo instalar Windows Identity [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657)Foundation, consulte.</span><span class="sxs-lookup"><span data-stu-id="00fba-206">For details about installing Windows Identity Foundation, see [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657).</span></span>
    
      - <span data-ttu-id="00fba-207">Windows Server 2012 para Windows Server 2012, use el **Administrador de servidores** para instalar Windows Identity Foundation.</span><span class="sxs-lookup"><span data-stu-id="00fba-207">Windows Server 2012   For Windows Server 2012, you use **Server Manager** to install the Windows Identity Foundation.</span></span> <span data-ttu-id="00fba-208">En el **Asistente para agregar roles y características**del administrador del servidor, seleccione **características**.</span><span class="sxs-lookup"><span data-stu-id="00fba-208">In the Server Manager **Add Roles and Features Wizard**, select **Features**.</span></span> <span data-ttu-id="00fba-209">Seleccione **Windows Identity Foundation 3,5** en la lista.</span><span class="sxs-lookup"><span data-stu-id="00fba-209">Select **Windows Identity Foundation 3.5** from the list.</span></span> <span data-ttu-id="00fba-210">Haga clic en **siguiente**y, a continuación, en **instalar**.</span><span class="sxs-lookup"><span data-stu-id="00fba-210">Click **Next**, then click **Install**.</span></span>

</div>

<div>

## <a name="do-not-install-layered-socket-providers-on-media-servers"></a><span data-ttu-id="00fba-211">No instale proveedores de sockets por niveles en servidores multimedia</span><span class="sxs-lookup"><span data-stu-id="00fba-211">Do Not Install Layered Socket Providers on Media Servers</span></span>

<span data-ttu-id="00fba-212">No instale ningún software de cliente de Microsoft Internet Security and Acceleration (ISA) Server o cualquier otro software de proveedores de servicios por niveles (LSP) Winsock en cualquier servidor front-end o servidor de mediación independiente.</span><span class="sxs-lookup"><span data-stu-id="00fba-212">Do not install any Microsoft Internet Security and Acceleration (ISA) Server client software, or any other Winsock Layered Service Providers (LSP) software, on any Front End Servers or stand-alone Mediation Servers.</span></span> <span data-ttu-id="00fba-213">La instalación de este software podría causar un rendimiento deficiente del tráfico de medios.</span><span class="sxs-lookup"><span data-stu-id="00fba-213">Installing this software could cause poor media traffic performance.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="00fba-214">Vea también</span><span class="sxs-lookup"><span data-stu-id="00fba-214">See Also</span></span>


[<span data-ttu-id="00fba-215">Requisitos de software de herramientas administrativas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="00fba-215">Administrative tools software requirements in Lync Server 2013</span></span>](lync-server-2013-administrative-tools-software-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

