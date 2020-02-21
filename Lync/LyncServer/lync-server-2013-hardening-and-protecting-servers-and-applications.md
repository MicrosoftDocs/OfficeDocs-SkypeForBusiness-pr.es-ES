---
title: 'Lync Server 2013: refuerzo y protección de servidores y aplicaciones'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hardening and protecting servers and applications for Lync Server 2013
ms:assetid: 9ca2b233-26f1-4d72-96e7-81a82c727806
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518331(v=OCS.15)
ms:contentKeyID: 62625491
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e2a8de372a8ca0ae6ec8c80a147eb74ffb01d0a7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214736"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="hardening-and-protecting-servers-and-applications-for-lync-server-2013"></a><span data-ttu-id="24254-102">Protección y protección de servidores y aplicaciones para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="24254-102">Hardening and protecting servers and applications for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="24254-103">_**Última modificación del tema:** 2013-12-05_</span><span class="sxs-lookup"><span data-stu-id="24254-103">_**Topic Last Modified:** 2013-12-05_</span></span>

<span data-ttu-id="24254-104">Debe proteger el sistema operativo y las aplicaciones de acuerdo con los procedimientos recomendados correspondientes al componente en cuestión.</span><span class="sxs-lookup"><span data-stu-id="24254-104">You should harden and protect your operating system and applications according to best practices for that specific component.</span></span> <span data-ttu-id="24254-105">En esta sección se explica cómo proteger los servidores de aplicaciones y el uso de la directiva de grupo para implementar bloqueos de seguridad.</span><span class="sxs-lookup"><span data-stu-id="24254-105">This section describes how to harden application servers and use Group Policy to implement security lockdowns.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="24254-106">También puede reforzar y proteger las bases de datos que se usan para la implementación de Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="24254-106">You can also harden and protect the databases used for you Microsoft Lync Server 2013 deployment.</span></span> <span data-ttu-id="24254-107">Para obtener más información, consulte <A href="lync-server-2013-hardening-and-protecting-databases.md">refuerzo y protección de las bases de datos de Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="24254-107">For details, see <A href="lync-server-2013-hardening-and-protecting-databases.md">Hardening and protecting the databases of Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="securing-application-servers"></a><span data-ttu-id="24254-108">Proteger los servidores de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="24254-108">Securing Application Servers</span></span>

<span data-ttu-id="24254-p103">En el caso de los servidores de aplicaciones, deben protegerse el sistema operativo y las aplicaciones. Así, un equipo con Windows Server 2008 dedicado a ejecutar Microsoft Internet Security and Acceleration (ISA) Server 2006 se debe proteger tanto desde el punto vista del sistema operativo como de las aplicaciones. Reducir el número de servicios que se ejecutan y ofrecen en un servidor debe ser un objetivo primordial.</span><span class="sxs-lookup"><span data-stu-id="24254-p103">For applications servers, the operating system and the application should be hardened. For example, a Windows Server 2008 computer dedicated to running Microsoft Internet Security and Acceleration (ISA) Server 2006 should be hardened from the operating system and from the application perspective. Minimizing the number of services running and provided by the server should be a primary goal.</span></span>

</div>

<div>

## <a name="securing-virtual-servers"></a><span data-ttu-id="24254-112">Proteger los servidores virtuales</span><span class="sxs-lookup"><span data-stu-id="24254-112">Securing Virtual Servers</span></span>

<span data-ttu-id="24254-113">Las instantáneas del servidor virtual contienen copias de los discos de datos del servidor y también contienen volcados de datos en memoria, que pueden contener datos criptográficos confidenciales que podrían dar lugar a ataques.</span><span class="sxs-lookup"><span data-stu-id="24254-113">Virtual server snapshots contain copies of the server’s data disks and also contain dumps of in-memory data, both of which can contain sensitive cryptographic data that might lead to attacks.</span></span> <span data-ttu-id="24254-114">Para los servidores de producción implementados mediante la virtualización, debe deshabilitar todas las instantáneas del servidor o administrarlas de manera controlada.</span><span class="sxs-lookup"><span data-stu-id="24254-114">For production servers implemented using virtualization, you should disable all server snapshots or manage them in a very controlled manner.</span></span> <span data-ttu-id="24254-115">Para obtener más información sobre cómo proteger los servidores virtuales Hyper-V, consulte la guía de seguridad de [https://go.microsoft.com/fwlink/p/?LinkId=214176](https://go.microsoft.com/fwlink/p/?linkid=214176)Hyper-v en:.</span><span class="sxs-lookup"><span data-stu-id="24254-115">For details about securing Hyper-V virtual servers, see the Hyper-V Security Guide at: [https://go.microsoft.com/fwlink/p/?LinkId=214176](https://go.microsoft.com/fwlink/p/?linkid=214176).</span></span>

</div>

<div>

## <a name="group-policy"></a><span data-ttu-id="24254-116">Directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="24254-116">Group Policy</span></span>

<span data-ttu-id="24254-p105">En Windows Server 2008 y Windows Server 2008 R2, la directiva de grupo permite la administración de la configuración de escritorio basada en directorios. La directiva de grupo puede servir para implementar bloqueos de seguridad, que se logra definiendo la configuración de equipo y usuario de los siguientes elementos en un objeto de la directiva de grupo (GPO):</span><span class="sxs-lookup"><span data-stu-id="24254-p105">In Windows Server 2008 and Windows Server 2008 R2, Group Policy provides directory-based desktop configuration management. You can use Group Policy to implement security lockdowns by defining Computer and User settings within a Group Policy object (GPO) for the following:</span></span>

  - <span data-ttu-id="24254-119">Directivas basadas en el Registro</span><span class="sxs-lookup"><span data-stu-id="24254-119">Registry-based policies</span></span>

  - <span data-ttu-id="24254-120">Seguridad</span><span class="sxs-lookup"><span data-stu-id="24254-120">Security</span></span>

  - <span data-ttu-id="24254-121">Instalación de software</span><span class="sxs-lookup"><span data-stu-id="24254-121">Software installation</span></span>

  - <span data-ttu-id="24254-122">Scripts</span><span class="sxs-lookup"><span data-stu-id="24254-122">Scripts</span></span>

  - <span data-ttu-id="24254-123">Redirección de carpetas</span><span class="sxs-lookup"><span data-stu-id="24254-123">Folder redirection</span></span>

  - <span data-ttu-id="24254-124">Servicios de instalación remota</span><span class="sxs-lookup"><span data-stu-id="24254-124">Remote installation services</span></span>

<span data-ttu-id="24254-125">Para proporcionar una interfaz de usuario para que el Administrador configure estas opciones, se incluyen plantillas administrativas con versiones de sistema operativo, versiones de Service Pack y algunas aplicaciones, incluido Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="24254-125">To provide a user interface for the administrator to configure these settings, administrative templates are shipped with operating system releases, service pack releases, and some applications, including Lync Server 2013.</span></span>

<span data-ttu-id="24254-126">El archivo Communicator. adm es una plantilla administrativa que se incluye con Lync Server 2013, se instala en el directorio%\\WINDIR\\ % inf y proporciona una interfaz a la configuración de la Directiva de grupo.</span><span class="sxs-lookup"><span data-stu-id="24254-126">The Communicator.adm file is an administrative template that ships with Lync Server 2013, is installed to the %windir%\\inf\\ directory, and provides an interface to the Group Policy settings.</span></span> <span data-ttu-id="24254-127">Cada valor de configuración de Communicator.adm se corresponde con un valor del Registro que afecta al comportamiento de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="24254-127">Each setting in Communicator.adm corresponds to a setting in the registry that affects application behavior.</span></span>

<span data-ttu-id="24254-128">Se puede obtener acceso a esta configuración desde GPedit.dll, que está disponible en la consola Usuarios y equipos de Active Directory y en la Consola de administración de directivas de grupo (GPMC).</span><span class="sxs-lookup"><span data-stu-id="24254-128">The settings can be accessed from GPedit.dll, which is available from the Active Directory Users and Computers console and the Group Policy Management Console (GPMC).</span></span>

</div>

<div>

## <a name="group-policy-security-settings"></a><span data-ttu-id="24254-129">Configuración de seguridad de la directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="24254-129">Group Policy Security Settings</span></span>

<span data-ttu-id="24254-130">La directiva de grupo contiene una configuración de seguridad para un GPO en Configuración del equipo/Configuración de Windows/Configuración de seguridad si se obtiene acceso desde GPedit.dll.</span><span class="sxs-lookup"><span data-stu-id="24254-130">Group Policy contains security settings for a GPO under Computer Configuration/Windows Settings/Security Settings when accessed from GPedit.dll.</span></span> <span data-ttu-id="24254-131">Puede importar plantillas de seguridad para definir la configuración de seguridad del GPO.</span><span class="sxs-lookup"><span data-stu-id="24254-131">You can import security templates to configure security settings for the GPO.</span></span> <span data-ttu-id="24254-132">La guía de seguridad de Windows Server [https://go.microsoft.com/fwlink/p/?LinkId=145186](https://go.microsoft.com/fwlink/p/?linkid=145186) 2008 en y el kit de herramientas de administración de cumplimiento [https://go.microsoft.com/fwlink/p/?LinkId=211882](https://go.microsoft.com/fwlink/p/?linkid=211882) de seguridad de Windows Server 2008 R2 incluyen una serie de plantillas de ejemplo que puede modificar para satisfacer sus necesidades.</span><span class="sxs-lookup"><span data-stu-id="24254-132">The Windows Server 2008 Security Guide at [https://go.microsoft.com/fwlink/p/?LinkId=145186](https://go.microsoft.com/fwlink/p/?linkid=145186) and the Windows Server 2008 R2 Security Compliance Management Toolkit at [https://go.microsoft.com/fwlink/p/?LinkId=211882](https://go.microsoft.com/fwlink/p/?linkid=211882) contain a number of sample templates that you can modify to meet your needs.</span></span>

</div>

<div>

## <a name="best-practices"></a><span data-ttu-id="24254-133">Procedimientos recomendados</span><span class="sxs-lookup"><span data-stu-id="24254-133">Best Practices</span></span>

  - <span data-ttu-id="24254-134">Proteja todos los sistemas operativos y aplicaciones del servidor.</span><span class="sxs-lookup"><span data-stu-id="24254-134">Harden all server operating systems and applications.</span></span>

  - <span data-ttu-id="24254-135">Proteja las instantáneas de servidor y mejore la seguridad de todos los servidores virtuales.</span><span class="sxs-lookup"><span data-stu-id="24254-135">Protect server snapshots and enhance the security of all virtual servers.</span></span>

  - <span data-ttu-id="24254-136">Use la directiva de grupo para implementar bloqueos de seguridad.</span><span class="sxs-lookup"><span data-stu-id="24254-136">Use Group Policy to implement security lockdowns.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

