---
title: Instalar los sistemas operativos y el software necesario como requisito previo en los servidores
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install operating systems and prerequisite software on servers
ms:assetid: 055991e0-5aeb-43fc-a7ba-d4b02316d73b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398103(v=OCS.15)
ms:contentKeyID: 48183288
ms.date: 07/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 266e8b049bd5de97fbb8f8d5d1e89b7280db3d4f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197153"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="install-operating-systems-and-prerequisite-software-on-servers-for-lync-server-2013"></a><span data-ttu-id="176bc-102">Instalar los sistemas operativos y el software necesario como requisito previo en los servidores para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="176bc-102">Install operating systems and prerequisite software on servers for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="176bc-103">_**Última modificación del tema:** 2014-07-24_</span><span class="sxs-lookup"><span data-stu-id="176bc-103">_**Topic Last Modified:** 2014-07-24_</span></span>

<span data-ttu-id="176bc-104">Una vez configurado el hardware y la infraestructura del sistema, deberá instalar los sistemas operativos de Windows adecuados y sus actualizaciones, además de todo el software necesario como requisito previo en cada uno de los servidores que esté implementando.</span><span class="sxs-lookup"><span data-stu-id="176bc-104">After you have set up the hardware and system infrastructure, you need to install the appropriate Windows operating systems and updates, in addition to all other prerequisite software on each server that you are deploying.</span></span> <span data-ttu-id="176bc-105">Esto incluye todos los roles de servidor de Lync Server 2013 y los servidores de infraestructura adicionales o los servidores que ejecutan SQL Server que son necesarios para la implementación.</span><span class="sxs-lookup"><span data-stu-id="176bc-105">This includes each Lync Server 2013 server role and any additional infrastructure servers or servers running SQL Server that are required for your deployment.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="176bc-106">En esta sección se describe la instalación de sistemas operativos y el software que es requisito previo para los servidores internos.</span><span class="sxs-lookup"><span data-stu-id="176bc-106">This section describes installation of operating systems and prerequisite software for internal servers.</span></span> <span data-ttu-id="176bc-107">Si va a implementar servidores perimetrales para admitir el acceso de usuarios externos, también tendrá que instalar los sistemas operativos y el software necesario como requisito previo para esos servidores, incluidos los servidores perimetrales y los servidores proxy inversos.</span><span class="sxs-lookup"><span data-stu-id="176bc-107">If you are deploying Edge Servers to support external user access, you also need to install operating systems and prerequisite software for those servers, including Edge Servers and reverse proxy servers.</span></span> <span data-ttu-id="176bc-108">Para obtener información detallada sobre la preparación de servidores para admitir el acceso de usuarios externos, consulte preparación de la <A href="lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md">instalación de servidores en la red perimetral para Lync Server 2013</A> en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="176bc-108">For details about preparing servers to support external user access, see <A href="lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md">Preparing for installation of servers in the perimeter network for Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="install-windows-operating-systems-on-servers"></a><span data-ttu-id="176bc-109">Instalar sistemas operativos Windows en servidores</span><span class="sxs-lookup"><span data-stu-id="176bc-109">Install Windows Operating Systems on Servers</span></span>

<span data-ttu-id="176bc-110">En cada servidor que vaya a implementar, instale el sistema operativo Windows adecuado de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="176bc-110">On each server that you are deploying, install the appropriate Windows operating system as follows:</span></span>

  - <span data-ttu-id="176bc-111">**Servidores que ejecutan Lync Server 2013**   para obtener más información sobre los requisitos del sistema operativo para servidores que ejecutan Lync Server 2013, consulte [compatibilidad con sistemas operativos de servidor y herramientas en Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) en la documentación sobre compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="176bc-111">**Servers running Lync Server 2013**   For details about the operating system requirements for servers running Lync Server 2013, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

  - <span data-ttu-id="176bc-112">**Servidores de bases de datos**   para obtener información sobre los requisitos del sistema operativo para servidores de bases de datos, incluida la base de datos back-end, la base de datos de archivado y la base de datos de supervisión, consulte la documentación de SQL Server</span><span class="sxs-lookup"><span data-stu-id="176bc-112">**Database servers**   For details about operating system requirements for database servers, including the back-end database, Archiving database, and Monitoring database, see the SQL Server documentation.</span></span> <span data-ttu-id="176bc-113">Para SQL Server 2012, consulte los libros en pantalla de SQL Server [https://go.microsoft.com/fwlink/p/?linkId=218015](https://go.microsoft.com/fwlink/p/?linkid=218015)2012 en.</span><span class="sxs-lookup"><span data-stu-id="176bc-113">For SQL Server 2012, see the SQL Server 2012 Books Online at [https://go.microsoft.com/fwlink/p/?linkId=218015](https://go.microsoft.com/fwlink/p/?linkid=218015).</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="176bc-114">Si va a instalar Lync Server 2013 en Windows Server&nbsp;2008&nbsp;R2 con SP1, debe instalar primero la actualización que se describe en el artículo 2646886 de Microsoft Knowledge base, "Fix: los daños en el montón se producen cuando un módulo llama al método al InsertEntityBody en IIS 7,5", en <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=2646886"> https://go.microsoft.com/fwlink/p/?linkid=3052&amp; kbid = 2646886</A>.</span><span class="sxs-lookup"><span data-stu-id="176bc-114">If you are installing Lync Server 2013 on Windows Server&nbsp;2008&nbsp;R2 with SP1, you must first install the update described in the Microsoft Knowledge Based article 2646886, “FIX: Heap corruption occurs when a module calls the InsertEntityBody method in IIS 7.5”, at <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=2646886">https://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=2646886</A>.</span></span><BR><span data-ttu-id="176bc-115">También debe modificar el registro como se describe en el artículo de KB, <A href="https://go.microsoft.com/fwlink/p/?linkid=506893">se registran los identificadores de evento 32402 y 61045 en los servidores front-end de Lync Server 2013 que están instalados en Windows server 2012 R2</A>.</span><span class="sxs-lookup"><span data-stu-id="176bc-115">You must also modify the registry as described in the KB article, <A href="https://go.microsoft.com/fwlink/p/?linkid=506893">Event IDs 32402, 61045 are logged in Lync Server 2013 Front End servers that are installed in Windows Server 2012 R2</A>.</span></span>



</div>

</div>

<div>

## <a name="install-windows-update-on-servers"></a><span data-ttu-id="176bc-116">Instalar Windows Update en los servidores</span><span class="sxs-lookup"><span data-stu-id="176bc-116">Install Windows Update on Servers</span></span>

<span data-ttu-id="176bc-117">Instale las siguientes actualizaciones desde Windows Update en cada servidor:</span><span class="sxs-lookup"><span data-stu-id="176bc-117">Install the following updates from Windows Update on each server:</span></span>

  - <span data-ttu-id="176bc-118">**Windows Update para los servidores que ejecutan Lync Server 2013**   para obtener más información sobre las actualizaciones de Windows Update que son necesarias para los servidores que ejecutan Lync Server 2013, consulte [Additional software Requirements for Lync Server 2013](lync-server-2013-additional-software-requirements.md) en la documentación referente a la planeación.</span><span class="sxs-lookup"><span data-stu-id="176bc-118">**Windows Update for servers running Lync Server 2013**   For details about the updates from Windows Update that are required for servers running Lync Server 2013, see [Additional software requirements for Lync Server 2013](lync-server-2013-additional-software-requirements.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="176bc-119">**Servidores de bases de datos**   para obtener información detallada sobre las actualizaciones de Windows Update que son necesarias para los servidores de bases de datos, incluida la base de datos back-end, la base de datos de archivado y la base de datos de supervisión, consulte la documentación de SQL Server 2012.</span><span class="sxs-lookup"><span data-stu-id="176bc-119">**Database servers**   For details about the updates from Windows Update that are required for database servers, including the back-end database, Archiving database, and Monitoring database, see the SQL Server 2012 documentation.</span></span> <span data-ttu-id="176bc-120">Para SQL Server 2012, consulte los libros en pantalla de SQL Server [https://go.microsoft.com/fwlink/p/?linkId=218015](https://go.microsoft.com/fwlink/p/?linkid=218015)2012 en.</span><span class="sxs-lookup"><span data-stu-id="176bc-120">For SQL Server 2012, see the SQL Server 2012 Books Online at [https://go.microsoft.com/fwlink/p/?linkId=218015](https://go.microsoft.com/fwlink/p/?linkid=218015).</span></span>

</div>

<div>

## <a name="install-other-prerequisite-software-on-servers"></a><span data-ttu-id="176bc-121">Instalar otro software necesario como requisito previo en los servidores</span><span class="sxs-lookup"><span data-stu-id="176bc-121">Install Other Prerequisite Software on Servers</span></span>

<span data-ttu-id="176bc-122">Lync Server 2013 requiere la instalación del siguiente software adicional en los servidores:</span><span class="sxs-lookup"><span data-stu-id="176bc-122">Lync Server 2013 requires the installation of the following additional software on servers:</span></span>

  - <span data-ttu-id="176bc-123">**Requisitos previos de software para servidores que ejecutan Lync Server 2013**   los requisitos previos de software adicionales para los servidores que ejecutan Lync Server 2013 dependen de la función del servidor que se está implementando.</span><span class="sxs-lookup"><span data-stu-id="176bc-123">**Prerequisite software for servers running Lync Server 2013**   The additional software prerequisites for servers running Lync Server 2013 depend on the server role being deployed.</span></span> <span data-ttu-id="176bc-124">Para obtener más información sobre los requisitos de software específicos para cada servidor, consulte [requisitos de software adicionales para Lync server 2013](lync-server-2013-additional-software-requirements.md) en la documentación referente a la planeación.</span><span class="sxs-lookup"><span data-stu-id="176bc-124">For details about the specific software requirements for each server, see [Additional software requirements for Lync Server 2013](lync-server-2013-additional-software-requirements.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="176bc-125">**Windows Identity Foundation**   Lync Server 2013 requiere la instalación de Windows Identity Foundation para poder admitir escenarios de autenticación de servidor a servidor.</span><span class="sxs-lookup"><span data-stu-id="176bc-125">**Windows Identity Foundation**   Lync Server 2013 requires the installation of Windows Identity Foundation in order to support server-to-server authentication scenarios.</span></span> <span data-ttu-id="176bc-126">Para comprobar que ya se ha instalado en el equipo, vaya al panel de control, haga clic en **programas y características**, **vea actualizaciones instaladas**y busque en **Microsoft Windows**.</span><span class="sxs-lookup"><span data-stu-id="176bc-126">To verify that it has already been installed on your computer, go to Control Panel, click **Programs and Features**, **View installed updates**, and look under **Microsoft Windows**.</span></span> <span data-ttu-id="176bc-127">Para obtener más información sobre cómo instalar Windows Identity [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657)Foundation, consulte.</span><span class="sxs-lookup"><span data-stu-id="176bc-127">For details about installing Windows Identity Foundation, see [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657).</span></span>

  - <span data-ttu-id="176bc-128">**Microsoft .NET Framework 4,5**   la edición de 64 bits de Microsoft .NET Framework 4,5 es necesaria para Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="176bc-128">**Microsoft .NET Framework 4.5**   The 64-bit edition of Microsoft .NET Framework 4.5 is required for Lync Server 2013.</span></span>

  - <span data-ttu-id="176bc-129">**Requisitos previos de software para servidores**   de bases de datos para obtener información sobre la actualización de Windows necesaria para los servidores de bases de datos, incluida la base de datos back-end, la base [https://go.microsoft.com/fwlink/p/?linkId=218015](https://go.microsoft.com/fwlink/p/?linkid=218015)de datos de archivado y la base de datos de supervisión, consulte la documentación de SQL Server 2012 en</span><span class="sxs-lookup"><span data-stu-id="176bc-129">**Prerequisite software for database servers**   For details about the Windows Update required for database servers, including the back-end database, Archiving database, and Monitoring database, see the SQL Server 2012 documentation at [https://go.microsoft.com/fwlink/p/?linkId=218015](https://go.microsoft.com/fwlink/p/?linkid=218015).</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="176bc-130">Lync Server 2013 instala automáticamente Microsoft SQL Server 2012 Express en cada servidor Standard Edition y en cada servidor que ejecuta Lync Server 2013 en el que se encuentra el almacén de configuración local.</span><span class="sxs-lookup"><span data-stu-id="176bc-130">Lync Server 2013 automatically installs Microsoft SQL Server 2012 Express on each Standard Edition server and each server running Lync Server 2013 on which the local configuration store is located.</span></span>

    
    </div>

  - <span data-ttu-id="176bc-131">**El tiempo de ejecución**   de Windows Media Format todos los servidores front-end y los servidores Standard Edition en los que se va a implementar la Conferencia deben tener instalado el tiempo de ejecución de Windows Media Format.</span><span class="sxs-lookup"><span data-stu-id="176bc-131">**Windows Media Format Runtime**   All Front End Servers and Standard Edition servers where conferencing will be deployed must have the Windows Media Format Runtime installed.</span></span> <span data-ttu-id="176bc-132">Este software es necesario para ejecutar los archivos de Windows Media Audio (.wma) que reproducen las aplicaciones de estacionamiento de llamadas, anuncio y grupo de respuesta para los anuncios y la música.</span><span class="sxs-lookup"><span data-stu-id="176bc-132">The Windows Media Format Runtime is required to run the Windows Media Audio (.wma) files that the Call Park, Announcement, and Response Group applications play for announcements and music.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="176bc-133">Para Windows Server 2012 y Windows Server 2012 R2, el tiempo de ejecución de Windows Media Format se instala con Microsoft Media Foundation.</span><span class="sxs-lookup"><span data-stu-id="176bc-133">For Windows Server 2012 and Windows Server 2012 R2 the Windows Media Format Runtime installs with Microsoft Media Foundation.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="176bc-134">Para Windows Server&nbsp;2008 y windows Server&nbsp;2008&nbsp;R2, el tiempo de ejecución de Windows Media Format se instala como parte de la experiencia de escritorio de Windows.</span><span class="sxs-lookup"><span data-stu-id="176bc-134">For Windows Server&nbsp;2008 and Windows Server&nbsp;2008&nbsp;R2 the Windows Media Format Runtime installs as part of the Windows Desktop Experience.</span></span> <span data-ttu-id="176bc-135">Se recomienda instalar la experiencia de escritorio de Windows antes de instalar Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="176bc-135">It is recommended that you install Windows Desktop Experience before you install Lync Server 2013.</span></span> <span data-ttu-id="176bc-136">Si Lync Server 2013 no encuentra este software en el servidor, se le pedirá que lo instale y, a continuación, deberá reiniciar el servidor para completar la instalación.</span><span class="sxs-lookup"><span data-stu-id="176bc-136">If Lync Server 2013 does not find this software on the server, it will prompt you to install it, and then you must restart the server to complete installation.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

