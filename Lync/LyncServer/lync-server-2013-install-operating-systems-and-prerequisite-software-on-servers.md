---
title: Instalar los sistemas operativos y el software necesario como requisito previo en los servidores
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Install operating systems and prerequisite software on servers
ms:assetid: 055991e0-5aeb-43fc-a7ba-d4b02316d73b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398103(v=OCS.15)
ms:contentKeyID: 48183288
ms.date: 07/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 26a4eed86f12386b10b49d4290a4596b40c1fcc9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835010"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-operating-systems-and-prerequisite-software-on-servers-for-lync-server-2013"></a><span data-ttu-id="fabcb-102">Instalar los sistemas operativos y el software necesario como requisito previo en los servidores en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fabcb-102">Install operating systems and prerequisite software on servers for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fabcb-103">_**Última modificación del tema:** 2014-07-24_</span><span class="sxs-lookup"><span data-stu-id="fabcb-103">_**Topic Last Modified:** 2014-07-24_</span></span>

<span data-ttu-id="fabcb-104">Una vez que haya configurado el hardware y la infraestructura del sistema, tendrá que instalar los sistemas operativos de Windows y las actualizaciones correspondientes, además de todos los demás programas de requisitos previos en cada servidor que vaya a implementar.</span><span class="sxs-lookup"><span data-stu-id="fabcb-104">After you have set up the hardware and system infrastructure, you need to install the appropriate Windows operating systems and updates, in addition to all other prerequisite software on each server that you are deploying.</span></span> <span data-ttu-id="fabcb-105">Esto incluye cada rol de servidor de Lync Server 2013 y todos los servidores de infraestructura adicionales o servidores que ejecuten SQL Server que sean necesarios para su implementación.</span><span class="sxs-lookup"><span data-stu-id="fabcb-105">This includes each Lync Server 2013 server role and any additional infrastructure servers or servers running SQL Server that are required for your deployment.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="fabcb-106">En esta sección se describe la instalación de sistemas operativos y el software necesario para servidores internos.</span><span class="sxs-lookup"><span data-stu-id="fabcb-106">This section describes installation of operating systems and prerequisite software for internal servers.</span></span> <span data-ttu-id="fabcb-107">Si implementa servidores perimetrales para admitir el acceso de usuarios externos, también tendrá que instalar sistemas operativos y el software necesario para esos servidores, incluidos los servidores perimetrales y los servidores proxy inversos.</span><span class="sxs-lookup"><span data-stu-id="fabcb-107">If you are deploying Edge Servers to support external user access, you also need to install operating systems and prerequisite software for those servers, including Edge Servers and reverse proxy servers.</span></span> <span data-ttu-id="fabcb-108">Para obtener más información sobre la preparación de servidores para admitir el acceso de usuarios externos, vea preparación de la <A href="lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md">instalación de servidores en la red perimetral para Lync Server 2013</A> en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="fabcb-108">For details about preparing servers to support external user access, see <A href="lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md">Preparing for installation of servers in the perimeter network for Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="install-windows-operating-systems-on-servers"></a><span data-ttu-id="fabcb-109">Instalar sistemas operativos Windows en servidores</span><span class="sxs-lookup"><span data-stu-id="fabcb-109">Install Windows Operating Systems on Servers</span></span>

<span data-ttu-id="fabcb-110">En cada servidor que va a implementar, instale el sistema operativo Windows adecuado de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="fabcb-110">On each server that you are deploying, install the appropriate Windows operating system as follows:</span></span>

  - <span data-ttu-id="fabcb-111">**Servidores que ejecutan Lync Server 2013**   para obtener más información sobre los requisitos del sistema operativo para servidores que ejecutan Lync Server 2013, vea [compatibilidad del sistema operativo servidor y herramientas en Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) en la documentación de soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="fabcb-111">**Servers running Lync Server 2013**   For details about the operating system requirements for servers running Lync Server 2013, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

  - <span data-ttu-id="fabcb-112">**Servidores de bases de datos**   para obtener información sobre los requisitos del sistema operativo para servidores de bases de datos, como la base de datos back-end, la base de datos archivada y la base de datos de supervisión, consulte la documentación de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="fabcb-112">**Database servers**   For details about operating system requirements for database servers, including the back-end database, Archiving database, and Monitoring database, see the SQL Server documentation.</span></span> <span data-ttu-id="fabcb-113">Para SQL Server 2012, consulte los libros en línea de SQL Server [http://go.microsoft.com/fwlink/p/?linkId=218015](http://go.microsoft.com/fwlink/p/?linkid=218015)2012 en.</span><span class="sxs-lookup"><span data-stu-id="fabcb-113">For SQL Server 2012, see the SQL Server 2012 Books Online at [http://go.microsoft.com/fwlink/p/?linkId=218015](http://go.microsoft.com/fwlink/p/?linkid=218015).</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="fabcb-114">Si está instalando Lync Server 2013 en Windows Server&nbsp;2008&nbsp;R2 con SP1, primero debe instalar la actualización que se describe en el artículo 2646886 de Microsoft Knowledge base, "Fix: el montón de daños se produce cuando un módulo llama al método InsertEntityBody en IIS 7,5 ", at <A class=uri href="http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=2646886"> http://go.microsoft.com/fwlink/p/?linkid=3052&amp; kbid = 2646886</A>.</span><span class="sxs-lookup"><span data-stu-id="fabcb-114">If you are installing Lync Server 2013 on Windows Server&nbsp;2008&nbsp;R2 with SP1, you must first install the update described in the Microsoft Knowledge Based article 2646886, “FIX: Heap corruption occurs when a module calls the InsertEntityBody method in IIS 7.5”, at <A class=uri href="http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=2646886">http://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=2646886</A>.</span></span><BR><span data-ttu-id="fabcb-115">También debe modificar el registro según se describe en el artículo de KB, los <A href="http://go.microsoft.com/fwlink/p/?linkid=506893">identificadores de eventos 32402, 61045 se registran en los servidores front-end de Lync server 2013 que se instalan en Windows server 2012 R2</A>.</span><span class="sxs-lookup"><span data-stu-id="fabcb-115">You must also modify the registry as described in the KB article, <A href="http://go.microsoft.com/fwlink/p/?linkid=506893">Event IDs 32402, 61045 are logged in Lync Server 2013 Front End servers that are installed in Windows Server 2012 R2</A>.</span></span>



</div>

</div>

<div>

## <a name="install-windows-update-on-servers"></a><span data-ttu-id="fabcb-116">Instalar Windows Update en servidores</span><span class="sxs-lookup"><span data-stu-id="fabcb-116">Install Windows Update on Servers</span></span>

<span data-ttu-id="fabcb-117">Instale las actualizaciones siguientes desde Windows Update en cada servidor:</span><span class="sxs-lookup"><span data-stu-id="fabcb-117">Install the following updates from Windows Update on each server:</span></span>

  - <span data-ttu-id="fabcb-118">**Windows Update para servidores que ejecutan Lync Server 2013**   para obtener más información sobre las actualizaciones de Windows Update necesarias para servidores que ejecutan Lync Server 2013, consulte [requisitos de software adicionales para Lync Server 2013](lync-server-2013-additional-software-requirements.md) en la planeación documentación.</span><span class="sxs-lookup"><span data-stu-id="fabcb-118">**Windows Update for servers running Lync Server 2013**   For details about the updates from Windows Update that are required for servers running Lync Server 2013, see [Additional software requirements for Lync Server 2013](lync-server-2013-additional-software-requirements.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="fabcb-119">**Servidores de base de datos**   para obtener información sobre las actualizaciones de Windows Update necesarias para los servidores de bases de datos, como la base de datos back-end, la base de datos de archivado y la base de datos de supervisión, consulte la documentación 2012 de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="fabcb-119">**Database servers**   For details about the updates from Windows Update that are required for database servers, including the back-end database, Archiving database, and Monitoring database, see the SQL Server 2012 documentation.</span></span> <span data-ttu-id="fabcb-120">Para SQL Server 2012, consulte los libros en línea de SQL Server [http://go.microsoft.com/fwlink/p/?linkId=218015](http://go.microsoft.com/fwlink/p/?linkid=218015)2012 en.</span><span class="sxs-lookup"><span data-stu-id="fabcb-120">For SQL Server 2012, see the SQL Server 2012 Books Online at [http://go.microsoft.com/fwlink/p/?linkId=218015](http://go.microsoft.com/fwlink/p/?linkid=218015).</span></span>

</div>

<div>

## <a name="install-other-prerequisite-software-on-servers"></a><span data-ttu-id="fabcb-121">Instalar otro software necesario en los servidores</span><span class="sxs-lookup"><span data-stu-id="fabcb-121">Install Other Prerequisite Software on Servers</span></span>

<span data-ttu-id="fabcb-122">Lync Server 2013 requiere la instalación del siguiente software adicional en los servidores:</span><span class="sxs-lookup"><span data-stu-id="fabcb-122">Lync Server 2013 requires the installation of the following additional software on servers:</span></span>

  - <span data-ttu-id="fabcb-123">**Requisitos previos de software para servidores que ejecutan Lync Server 2013**   los requisitos de software adicionales para servidores que ejecutan Lync Server 2013 dependen del rol de servidor que se implemente.</span><span class="sxs-lookup"><span data-stu-id="fabcb-123">**Prerequisite software for servers running Lync Server 2013**   The additional software prerequisites for servers running Lync Server 2013 depend on the server role being deployed.</span></span> <span data-ttu-id="fabcb-124">Para obtener más información sobre los requisitos de software específicos para cada servidor, consulte [requisitos de software adicionales para Lync server 2013](lync-server-2013-additional-software-requirements.md) en la documentación de planeación.</span><span class="sxs-lookup"><span data-stu-id="fabcb-124">For details about the specific software requirements for each server, see [Additional software requirements for Lync Server 2013](lync-server-2013-additional-software-requirements.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="fabcb-125">**Windows Identity Foundation**   Lync Server 2013 requiere la instalación de Windows Identity Foundation para poder admitir los escenarios de autenticación de servidor a servidor.</span><span class="sxs-lookup"><span data-stu-id="fabcb-125">**Windows Identity Foundation**   Lync Server 2013 requires the installation of Windows Identity Foundation in order to support server-to-server authentication scenarios.</span></span> <span data-ttu-id="fabcb-126">Para comprobar que ya se ha instalado en el equipo, vaya a panel de control, haga clic en **programas y características**, **vea actualizaciones instaladas**y busque en **Microsoft Windows**.</span><span class="sxs-lookup"><span data-stu-id="fabcb-126">To verify that it has already been installed on your computer, go to Control Panel, click **Programs and Features**, **View installed updates**, and look under **Microsoft Windows**.</span></span> <span data-ttu-id="fabcb-127">Para obtener más información sobre cómo instalar Windows Identity [http://go.microsoft.com/fwlink/p/?linkId=204657](http://go.microsoft.com/fwlink/p/?linkid=204657)Foundation, consulte.</span><span class="sxs-lookup"><span data-stu-id="fabcb-127">For details about installing Windows Identity Foundation, see [http://go.microsoft.com/fwlink/p/?linkId=204657](http://go.microsoft.com/fwlink/p/?linkid=204657).</span></span>

  - <span data-ttu-id="fabcb-128">**Microsoft .NET Framework 4,5**   se necesita la edición de 64 bits de Microsoft .NET Framework 4,5 para Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fabcb-128">**Microsoft .NET Framework 4.5**   The 64-bit edition of Microsoft .NET Framework 4.5 is required for Lync Server 2013.</span></span>

  - <span data-ttu-id="fabcb-129">**Requisitos previos de software para servidores**   de bases de datos para obtener información sobre la actualización de Windows Update requerida para servidores de bases de datos, como la base de datos back-end, la base [http://go.microsoft.com/fwlink/p/?linkId=218015](http://go.microsoft.com/fwlink/p/?linkid=218015)de datos de archivado y la base de datos de supervisión, consulte la documentación de SQL Server 2012 en</span><span class="sxs-lookup"><span data-stu-id="fabcb-129">**Prerequisite software for database servers**   For details about the Windows Update required for database servers, including the back-end database, Archiving database, and Monitoring database, see the SQL Server 2012 documentation at [http://go.microsoft.com/fwlink/p/?linkId=218015](http://go.microsoft.com/fwlink/p/?linkid=218015).</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="fabcb-130">Lync Server 2013 instala automáticamente Microsoft SQL Server 2012 Express en cada servidor Standard Edition y en cada servidor que ejecuta Lync Server 2013 en el que se encuentra el almacén de configuración local.</span><span class="sxs-lookup"><span data-stu-id="fabcb-130">Lync Server 2013 automatically installs Microsoft SQL Server 2012 Express on each Standard Edition server and each server running Lync Server 2013 on which the local configuration store is located.</span></span>

    
    </div>

  - <span data-ttu-id="fabcb-131">**Windows Media Format Runtime**   todos los servidores front-end y los servidores Standard Edition en los que se van a implementar las conferencias deben tener instalado el Windows Media Format Runtime.</span><span class="sxs-lookup"><span data-stu-id="fabcb-131">**Windows Media Format Runtime**   All Front End Servers and Standard Edition servers where conferencing will be deployed must have the Windows Media Format Runtime installed.</span></span> <span data-ttu-id="fabcb-132">El tiempo de ejecución de Windows Media Format es necesario para ejecutar los archivos de audio de Windows Media (. WMA) que las aplicaciones de los grupos estacionamiento, anuncio y respuesta de llamadas se reproducen para anuncios y música.</span><span class="sxs-lookup"><span data-stu-id="fabcb-132">The Windows Media Format Runtime is required to run the Windows Media Audio (.wma) files that the Call Park, Announcement, and Response Group applications play for announcements and music.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="fabcb-133">Para Windows Server 2012 y Windows Server 2012 R2, el tiempo de ejecución de Windows Media Format se instala con Microsoft Media Foundation.</span><span class="sxs-lookup"><span data-stu-id="fabcb-133">For Windows Server 2012 and Windows Server 2012 R2 the Windows Media Format Runtime installs with Microsoft Media Foundation.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="fabcb-134">Para Windows Server&nbsp;2008 y windows Server&nbsp;2008&nbsp;R2, el tiempo de ejecución de Windows Media Format se instala como parte de la experiencia de escritorio de Windows.</span><span class="sxs-lookup"><span data-stu-id="fabcb-134">For Windows Server&nbsp;2008 and Windows Server&nbsp;2008&nbsp;R2 the Windows Media Format Runtime installs as part of the Windows Desktop Experience.</span></span> <span data-ttu-id="fabcb-135">Se recomienda instalar la experiencia de escritorio de Windows antes de instalar Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fabcb-135">It is recommended that you install Windows Desktop Experience before you install Lync Server 2013.</span></span> <span data-ttu-id="fabcb-136">Si Lync Server 2013 no encuentra este software en el servidor, le pedirá que lo instale y, a continuación, deberá reiniciar el servidor para completar la instalación.</span><span class="sxs-lookup"><span data-stu-id="fabcb-136">If Lync Server 2013 does not find this software on the server, it will prompt you to install it, and then you must restart the server to complete installation.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

