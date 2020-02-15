---
title: 'Lync Server 2013: requisitos previos del complemento Lync VDI'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync VDI plug-in prerequisites
ms:assetid: da25a976-7624-4dfc-b332-9c4db4ee78da
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205304(v=OCS.15)
ms:contentKeyID: 48185552
ms.date: 03/07/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d1e5434ed445bf19d2aaeea146ba0edb7dcac04c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030193"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-vdi-plug-in-prerequisites-in-lync-server-2013"></a><span data-ttu-id="69b2c-102">Requisitos previos del complemento Lync VDI en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="69b2c-102">Lync VDI plug-in prerequisites in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="69b2c-103">_**Última modificación del tema:** 2017-03-07_</span><span class="sxs-lookup"><span data-stu-id="69b2c-103">_**Topic Last Modified:** 2017-03-07_</span></span>

<span data-ttu-id="69b2c-104">En un entorno de infraestructura de escritorio virtual (VDI), las máquinas virtuales y el equipo local del usuario deben cumplir los requisitos descritos en esta sección.</span><span class="sxs-lookup"><span data-stu-id="69b2c-104">In a virtual desktop infrastructure (VDI) environment, the virtual machines and the user’s local computer must meet the requirements outlined in this section.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="69b2c-p101">Consulte al proveedor de soluciones de virtualización para obtener más información sobre la instalación y la implementación del entorno virtualizado. Para más información sobre la implementación de un entorno virtualizado en función de los servicios de Hyper-V y de escritorio remoto, consulte los artículos siguientes en la biblioteca de TechNet de Microsoft:</span><span class="sxs-lookup"><span data-stu-id="69b2c-p101">Refer to your virtualization solution provider for details about how to install and deploy the virtualized environment. For information about deploying a virtualized environment based on Hyper-V and Remote Desktop Services, see the following articles in the Microsoft TechNet Library:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="69b2c-107">Hyper-V en<A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=247514">https://go.microsoft.com/fwlink/p/?linkid=247514</A></span><span class="sxs-lookup"><span data-stu-id="69b2c-107">Hyper-V at <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=247514">https://go.microsoft.com/fwlink/p/?linkid=247514</A></span></span></P>
> <LI>
> <P><span data-ttu-id="69b2c-108">Servicios de escritorio remoto en Windows&nbsp;Server&nbsp;2008 R2 en<A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=247513">https://go.microsoft.com/fwlink/p/?linkid=247513</A></span><span class="sxs-lookup"><span data-stu-id="69b2c-108">Remote Desktop Services in Windows Server&nbsp;2008&nbsp;R2 at <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=247513">https://go.microsoft.com/fwlink/p/?linkid=247513</A></span></span></P></LI></UL>



</div>

<span data-ttu-id="69b2c-109">A continuación aparecen los requisitos para las máquinas virtuales que se ejecutan en el equipo del centro de datos:</span><span class="sxs-lookup"><span data-stu-id="69b2c-109">The following are requirements for the virtual machines running on the data center computer:</span></span>

  - <span data-ttu-id="69b2c-110">Las máquinas virtuales deben configurarse con Windows 10, Windows 8,1, Windows 8, Windows 7 o Windows Server 2008 R2 con los últimos Service Packs.</span><span class="sxs-lookup"><span data-stu-id="69b2c-110">Virtual machines must be configured with Windows 10, Windows 8.1, Windows 8, Windows 7, or Windows Server 2008 R2 with the latest service packs.</span></span>

<span data-ttu-id="69b2c-111">A continuación se indican los requisitos para el usuario y el equipo local del usuario:</span><span class="sxs-lookup"><span data-stu-id="69b2c-111">The following are requirements for the user and the user’s local computer:</span></span>

  - <span data-ttu-id="69b2c-112">El usuario debe estar alojado en Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="69b2c-112">The user must be homed on Lync Server 2013.</span></span>

  - <span data-ttu-id="69b2c-113">El equipo local debe ejecutar Windows Embedded Standard 7 con SP1, Windows 7 con SP1, Windows 8, Windows 8,1 Embedded o Windows 8,1 (no incrustado).</span><span class="sxs-lookup"><span data-stu-id="69b2c-113">The local computer must be running Windows Embedded Standard 7 with SP1, Windows 7 with SP1, Windows 8, Windows 8.1 Embedded, or Windows 8.1 (not embedded).</span></span>

  - <span data-ttu-id="69b2c-114">Si usa servicios de escritorio remoto, el bits de complemento de VDI de Lync (es decir, si la aplicación es de 32 bits o de 64 bits) debe coincidir con los bits del sistema operativo del equipo local.</span><span class="sxs-lookup"><span data-stu-id="69b2c-114">If you are using Remote Desktop Services, the Lync VDI plug-in bitness (that is, whether the application is 32-bit or 64-bit) must match the local computer’s operating system bitness.</span></span> <span data-ttu-id="69b2c-115">No es necesario que coincidan el valor de bits del sistema operativo del equipo local y del sistema operativo de la máquina virtual.</span><span class="sxs-lookup"><span data-stu-id="69b2c-115">The bitness of the operating system on the local computer and the operating system on the virtual machine do not need to match.</span></span> <span data-ttu-id="69b2c-116">Si usa otra plataforma u otra solución de virtualización, consulte a su proveedor de soluciones de virtualización para informarse de los requisitos del valor de bits.</span><span class="sxs-lookup"><span data-stu-id="69b2c-116">If you are using another virtualization solution or platform, refer to guidance from your virtualization solution provider about bitness requirements.</span></span>

  - <span data-ttu-id="69b2c-117">El equipo local debe ejecutar la última versión del cliente de escritorio remoto.</span><span class="sxs-lookup"><span data-stu-id="69b2c-117">The local computer must be running the latest version of the remote desktop client.</span></span> <span data-ttu-id="69b2c-118">Instale las últimas actualizaciones de cliente de los servicios de escritorio remoto de Microsoft o el último software cliente de escritorio remoto del proveedor de soluciones de virtualización.</span><span class="sxs-lookup"><span data-stu-id="69b2c-118">Install the latest updates of Remote Desktop Services client from Microsoft or the latest remote desktop client software from your virtualization solution provider.</span></span> <span data-ttu-id="69b2c-119">Para obtener las actualizaciones más recientes de servicios de [https://go.microsoft.com/fwlink/p/?LinkId=268032](https://go.microsoft.com/fwlink/p/?linkid=268032)escritorio remoto, consulte.</span><span class="sxs-lookup"><span data-stu-id="69b2c-119">For the latest Remote Desktop Services updates, see [https://go.microsoft.com/fwlink/p/?LinkId=268032](https://go.microsoft.com/fwlink/p/?linkid=268032).</span></span>

  - <span data-ttu-id="69b2c-120">En el PC local, configure el cliente de escritorio remoto para que el audio se reproduzca en el PC local y que la grabación remota esté deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="69b2c-120">On the local computer, the remote desktop client settings must be configured so that audio plays on the local computer and remote recording is disabled.</span></span> <span data-ttu-id="69b2c-121">Para configurar estas opciones para conexión a escritorio remoto en Windows, consulte la sección siguiente, "para configurar las opciones de conexión a escritorio remoto".</span><span class="sxs-lookup"><span data-stu-id="69b2c-121">To configure these settings for Remote Desktop Connection in Windows, see the next section, "To configure Remote Desktop Connection settings."</span></span>

<div>

## <a name="to-configure-remote-desktop-connection-settings"></a><span data-ttu-id="69b2c-122">Configuración de los parámetros de conexión al escritorio remoto</span><span class="sxs-lookup"><span data-stu-id="69b2c-122">To configure Remote Desktop Connection settings</span></span>

<span data-ttu-id="69b2c-123">Para preparar la conexión a escritorio remoto en Windows para el complemento de VDI de Lync, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="69b2c-123">To prepare Remote Desktop Connection in Windows for the Lync VDI plug-in, follow these steps.</span></span>

1.  <span data-ttu-id="69b2c-124">Si el equipo local ejecuta Windows 8, omita este paso.</span><span class="sxs-lookup"><span data-stu-id="69b2c-124">If the local computer is running Windows 8, skip this step.</span></span> <span data-ttu-id="69b2c-125">Si el equipo local ejecuta Windows 7 con SP1, instale la versión más reciente de Windows 8 del cliente de servicios de escritorio remoto, [https://go.microsoft.com/fwlink/p/?LinkId=268032](https://go.microsoft.com/fwlink/p/?linkid=268032)disponible en.</span><span class="sxs-lookup"><span data-stu-id="69b2c-125">If the local computer is running Windows 7 with SP1, install the latest Windows 8 version of the Remote Desktop Services client, available at [https://go.microsoft.com/fwlink/p/?LinkId=268032](https://go.microsoft.com/fwlink/p/?linkid=268032).</span></span>

2.  <span data-ttu-id="69b2c-126">Inicie el cliente de servicios de escritorio remoto haciendo clic en **Iniciar** y después en **Conexión a escritorio remoto**.</span><span class="sxs-lookup"><span data-stu-id="69b2c-126">Start the Remote Desktop Services client by clicking **Start**, and then clicking **Remote Desktop Connection**.</span></span>

3.  <span data-ttu-id="69b2c-127">Haga clic en **Opciones**.</span><span class="sxs-lookup"><span data-stu-id="69b2c-127">Click **Options**.</span></span>

4.  <span data-ttu-id="69b2c-128">Haga clic en la pestaña **Recursos locales**. En **Audio remoto**, haga clic en **Configuración** y haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="69b2c-128">Click the **Local Resources** tab. Under **Remote audio**, click **Settings**, and then do the following:</span></span>
    
      - <span data-ttu-id="69b2c-129">En **Reproducción de audio remota**, seleccione **Reproducir en este equipo**.</span><span class="sxs-lookup"><span data-stu-id="69b2c-129">Under **Remote audio playback**, select **Play on this computer**.</span></span>
    
      - <span data-ttu-id="69b2c-130">En **Grabación de audio remota**, seleccione **No grabar**.</span><span class="sxs-lookup"><span data-stu-id="69b2c-130">Under **Remote audio recording**, select **Do not record**.</span></span>
    
      - <span data-ttu-id="69b2c-131">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="69b2c-131">Click **OK**.</span></span>

5.  <span data-ttu-id="69b2c-132">Haga clic en la pestaña **Experiencia**. En **Rendimiento**, desactive la casilla **Almacenamiento en caché persistente de mapas de bits**.</span><span class="sxs-lookup"><span data-stu-id="69b2c-132">Click the **Experience** tab. Under **Performance**, clear the **Persistent bitmap caching** check box.</span></span>

6.  <span data-ttu-id="69b2c-133">Haga clic en la pestaña **General**. En **Equipo**, escriba el nombre de la máquina virtual y haga clic en **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="69b2c-133">Click the **General** tab. In **Computer**, type the name of the virtual machine, and then click **Connect**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

