---
title: 'Lync Server 2013: Reforzar y proteger los servidores y las aplicaciones'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Hardening and protecting servers and applications for Lync Server 2013
ms:assetid: 9ca2b233-26f1-4d72-96e7-81a82c727806
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518331(v=OCS.15)
ms:contentKeyID: 62625491
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 00fea9bd192dedaf16567209798f12c7bff23e6a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835090"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hardening-and-protecting-servers-and-applications-for-lync-server-2013"></a><span data-ttu-id="abc5e-102">Reforzar y proteger los servidores y las aplicaciones de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="abc5e-102">Hardening and protecting servers and applications for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="abc5e-103">_**Última modificación del tema:** 2013-12-05_</span><span class="sxs-lookup"><span data-stu-id="abc5e-103">_**Topic Last Modified:** 2013-12-05_</span></span>

<span data-ttu-id="abc5e-104">Debe proteger y proteger el sistema operativo y las aplicaciones según los procedimientos recomendados para ese componente específico.</span><span class="sxs-lookup"><span data-stu-id="abc5e-104">You should harden and protect your operating system and applications according to best practices for that specific component.</span></span> <span data-ttu-id="abc5e-105">En esta sección se describe cómo reforzar los servidores de aplicaciones y usar la Directiva de grupo para implementar bloqueos de seguridad.</span><span class="sxs-lookup"><span data-stu-id="abc5e-105">This section describes how to harden application servers and use Group Policy to implement security lockdowns.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="abc5e-106">También puede reforzar y proteger las bases de datos que se usan para la implementación de Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="abc5e-106">You can also harden and protect the databases used for you Microsoft Lync Server 2013 deployment.</span></span> <span data-ttu-id="abc5e-107">Para obtener más información, consulte <A href="lync-server-2013-hardening-and-protecting-databases.md">refuerzo y protección de las bases de datos de Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="abc5e-107">For details, see <A href="lync-server-2013-hardening-and-protecting-databases.md">Hardening and protecting the databases of Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="securing-application-servers"></a><span data-ttu-id="abc5e-108">Proteger servidores de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="abc5e-108">Securing Application Servers</span></span>

<span data-ttu-id="abc5e-109">En el caso de los servidores de aplicaciones, se debe reforzar el sistema operativo y la aplicación.</span><span class="sxs-lookup"><span data-stu-id="abc5e-109">For applications servers, the operating system and the application should be hardened.</span></span> <span data-ttu-id="abc5e-110">Por ejemplo, un equipo Windows Server 2008 dedicado a ejecutar Microsoft Internet Security and Acceleration (ISA) Server 2006 debe reforzarse desde el sistema operativo y desde la perspectiva de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="abc5e-110">For example, a Windows Server 2008 computer dedicated to running Microsoft Internet Security and Acceleration (ISA) Server 2006 should be hardened from the operating system and from the application perspective.</span></span> <span data-ttu-id="abc5e-111">Minimizar la cantidad de servicios que se ejecutan y proporcionados por el servidor debe ser un objetivo principal.</span><span class="sxs-lookup"><span data-stu-id="abc5e-111">Minimizing the number of services running and provided by the server should be a primary goal.</span></span>

</div>

<div>

## <a name="securing-virtual-servers"></a><span data-ttu-id="abc5e-112">Proteger servidores virtuales</span><span class="sxs-lookup"><span data-stu-id="abc5e-112">Securing Virtual Servers</span></span>

<span data-ttu-id="abc5e-113">Las instantáneas de Virtual Server contienen copias de los discos de datos del servidor y también contienen volcados de datos en memoria, que pueden contener datos criptográficos confidenciales, que podrían conducir a ataques.</span><span class="sxs-lookup"><span data-stu-id="abc5e-113">Virtual server snapshots contain copies of the server’s data disks and also contain dumps of in-memory data, both of which can contain sensitive cryptographic data that might lead to attacks.</span></span> <span data-ttu-id="abc5e-114">Para los servidores de producción implementados mediante la virtualización, debe deshabilitar todas las instantáneas del servidor o administrarlas de una manera controlada.</span><span class="sxs-lookup"><span data-stu-id="abc5e-114">For production servers implemented using virtualization, you should disable all server snapshots or manage them in a very controlled manner.</span></span> <span data-ttu-id="abc5e-115">Para obtener detalles sobre la protección de servidores virtuales Hyper-V, consulte la guía de seguridad de Hyper [http://go.microsoft.com/fwlink/p/?LinkId=214176](http://go.microsoft.com/fwlink/p/?linkid=214176)-v en:.</span><span class="sxs-lookup"><span data-stu-id="abc5e-115">For details about securing Hyper-V virtual servers, see the Hyper-V Security Guide at: [http://go.microsoft.com/fwlink/p/?LinkId=214176](http://go.microsoft.com/fwlink/p/?linkid=214176).</span></span>

</div>

<div>

## <a name="group-policy"></a><span data-ttu-id="abc5e-116">Directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="abc5e-116">Group Policy</span></span>

<span data-ttu-id="abc5e-117">En Windows Server 2008 y Windows Server 2008 R2, la Directiva de grupo proporciona administración de la configuración de escritorio basada en directorios.</span><span class="sxs-lookup"><span data-stu-id="abc5e-117">In Windows Server 2008 and Windows Server 2008 R2, Group Policy provides directory-based desktop configuration management.</span></span> <span data-ttu-id="abc5e-118">Puede usar la Directiva de grupo para implementar bloqueos de seguridad definiendo la configuración del usuario y del equipo dentro de un objeto de directiva de grupo (GPO) para lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="abc5e-118">You can use Group Policy to implement security lockdowns by defining Computer and User settings within a Group Policy object (GPO) for the following:</span></span>

  - <span data-ttu-id="abc5e-119">Directivas basadas en el registro</span><span class="sxs-lookup"><span data-stu-id="abc5e-119">Registry-based policies</span></span>

  - <span data-ttu-id="abc5e-120">Seguridad</span><span class="sxs-lookup"><span data-stu-id="abc5e-120">Security</span></span>

  - <span data-ttu-id="abc5e-121">Instalación de software</span><span class="sxs-lookup"><span data-stu-id="abc5e-121">Software installation</span></span>

  - <span data-ttu-id="abc5e-122">Scripts</span><span class="sxs-lookup"><span data-stu-id="abc5e-122">Scripts</span></span>

  - <span data-ttu-id="abc5e-123">Redireccionamiento de carpetas</span><span class="sxs-lookup"><span data-stu-id="abc5e-123">Folder redirection</span></span>

  - <span data-ttu-id="abc5e-124">Servicios de instalación remota</span><span class="sxs-lookup"><span data-stu-id="abc5e-124">Remote installation services</span></span>

<span data-ttu-id="abc5e-125">Para proporcionar una interfaz de usuario para que el Administrador configure estas opciones, las plantillas administrativas se incluyen con las versiones del sistema operativo, versiones de Service Pack y algunas aplicaciones, entre las que se incluyen Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="abc5e-125">To provide a user interface for the administrator to configure these settings, administrative templates are shipped with operating system releases, service pack releases, and some applications, including Lync Server 2013.</span></span>

<span data-ttu-id="abc5e-126">El archivo Communicator. adm es una plantilla administrativa que se incluye con Lync Server 2013, se instala en el directorio%\\WINDIR\\ % inf y proporciona una interfaz para la configuración de directiva de grupo.</span><span class="sxs-lookup"><span data-stu-id="abc5e-126">The Communicator.adm file is an administrative template that ships with Lync Server 2013, is installed to the %windir%\\inf\\ directory, and provides an interface to the Group Policy settings.</span></span> <span data-ttu-id="abc5e-127">Cada configuración de Communicator. adm corresponde a una configuración del registro que afecta al comportamiento de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="abc5e-127">Each setting in Communicator.adm corresponds to a setting in the registry that affects application behavior.</span></span>

<span data-ttu-id="abc5e-128">Se puede acceder a la configuración desde GPedit. dll, que está disponible en la consola de usuarios y equipos de Active Directory y en la consola de administración de directivas de grupo (GPMC).</span><span class="sxs-lookup"><span data-stu-id="abc5e-128">The settings can be accessed from GPedit.dll, which is available from the Active Directory Users and Computers console and the Group Policy Management Console (GPMC).</span></span>

</div>

<div>

## <a name="group-policy-security-settings"></a><span data-ttu-id="abc5e-129">Configuración de seguridad de la Directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="abc5e-129">Group Policy Security Settings</span></span>

<span data-ttu-id="abc5e-130">La Directiva de grupo contiene la configuración de seguridad de un GPO en configuración del equipo/Configuración de Windows/configuración de seguridad cuando se accede a él desde GPedit. dll.</span><span class="sxs-lookup"><span data-stu-id="abc5e-130">Group Policy contains security settings for a GPO under Computer Configuration/Windows Settings/Security Settings when accessed from GPedit.dll.</span></span> <span data-ttu-id="abc5e-131">Puede importar plantillas de seguridad para configurar las opciones de seguridad del GPO.</span><span class="sxs-lookup"><span data-stu-id="abc5e-131">You can import security templates to configure security settings for the GPO.</span></span> <span data-ttu-id="abc5e-132">La guía de seguridad de Windows Server [http://go.microsoft.com/fwlink/p/?LinkId=145186](http://go.microsoft.com/fwlink/p/?linkid=145186) 2008, que se encuentra en el windows Server 2008 R2 [http://go.microsoft.com/fwlink/p/?LinkId=211882](http://go.microsoft.com/fwlink/p/?linkid=211882) Security Compliance Management Toolkit, incluye un número de plantillas de ejemplo que puede modificar para satisfacer sus necesidades.</span><span class="sxs-lookup"><span data-stu-id="abc5e-132">The Windows Server 2008 Security Guide at [http://go.microsoft.com/fwlink/p/?LinkId=145186](http://go.microsoft.com/fwlink/p/?linkid=145186) and the Windows Server 2008 R2 Security Compliance Management Toolkit at [http://go.microsoft.com/fwlink/p/?LinkId=211882](http://go.microsoft.com/fwlink/p/?linkid=211882) contain a number of sample templates that you can modify to meet your needs.</span></span>

</div>

<div>

## <a name="best-practices"></a><span data-ttu-id="abc5e-133">Procedimientos recomendados</span><span class="sxs-lookup"><span data-stu-id="abc5e-133">Best Practices</span></span>

  - <span data-ttu-id="abc5e-134">Proteger todos los sistemas operativos de servidor y las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="abc5e-134">Harden all server operating systems and applications.</span></span>

  - <span data-ttu-id="abc5e-135">Proteger las instantáneas del servidor y mejorar la seguridad de todos los servidores virtuales.</span><span class="sxs-lookup"><span data-stu-id="abc5e-135">Protect server snapshots and enhance the security of all virtual servers.</span></span>

  - <span data-ttu-id="abc5e-136">Use directivas de grupo para implementar bloqueos de seguridad.</span><span class="sxs-lookup"><span data-stu-id="abc5e-136">Use Group Policy to implement security lockdowns.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

