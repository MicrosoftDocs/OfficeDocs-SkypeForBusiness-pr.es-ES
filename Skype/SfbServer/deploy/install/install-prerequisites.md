---
title: Instalación de requisitos previos de Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2ef91a1e-2899-44c8-8e2c-527cb9114a0a
description: 'Resumen: Obtenga información sobre los servidores y roles de servidor que debe configurar antes de instalar Skype empresarial Server. Descargue una versión de prueba gratuita de Skype empresarial Server del centro de evaluación de Microsoft https://www.microsoft.com/evalcenter/evaluate-skype-for-business-serveren:.'
ms.openlocfilehash: fedcebe601d21f0e581795c264ed26c6e90716bd
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42018261"
---
# <a name="install-prerequisites-for-skype-for-business-server"></a><span data-ttu-id="0e039-104">Instalación de requisitos previos de Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="0e039-104">Install prerequisites for Skype for Business Server</span></span>
 
<span data-ttu-id="0e039-105">**Resumen:** Obtenga información sobre los servidores y las funciones de servidor que debe configurar antes de instalar Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="0e039-105">**Summary:** Learn about the servers and server roles you must configure before you install Skype for Business Server.</span></span> <span data-ttu-id="0e039-106">Descargue una versión de prueba gratuita de Skype empresarial Server del [centro de evaluación de Microsoft](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span><span class="sxs-lookup"><span data-stu-id="0e039-106">Download a free trial of Skype for Business Server from the [Microsoft Evaluation center](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="0e039-107">La instalación de los requisitos previos consiste en la configuración de Windows Server mediante la instalación de los roles y las características necesarios en cada uno de los servidores de la topología.</span><span class="sxs-lookup"><span data-stu-id="0e039-107">Installing prerequisites consists of setting up Windows Server by installing the required roles and features on each of the servers in the topology.</span></span> <span data-ttu-id="0e039-108">Los requisitos se basan en el rol que el servidor va a cumplir en la topología.</span><span class="sxs-lookup"><span data-stu-id="0e039-108">The requirements are based on the role the server will fulfill in the topology.</span></span> <span data-ttu-id="0e039-109">Puede realizar los pasos del 1 al 5 en cualquier orden.</span><span class="sxs-lookup"><span data-stu-id="0e039-109">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="0e039-110">Sin embargo, debe realizar los pasos 6, 7 y 8 en orden, y después de los pasos del 1 al 5, tal y como se describe en el diagrama.</span><span class="sxs-lookup"><span data-stu-id="0e039-110">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5, as outlined in the diagram.</span></span> <span data-ttu-id="0e039-111">La instalación de los requisitos previos es el paso 1 de 8.</span><span class="sxs-lookup"><span data-stu-id="0e039-111">Installing prerequisites is step 1 of 8.</span></span>
  
![Diagrama de información general: instalación de requisitos previos.](../../media/0a85349b-b398-4e04-8901-8f4bd25d8afe.png)
  
## <a name="setup-windows-server"></a><span data-ttu-id="0e039-113">Configurar Windows Server</span><span class="sxs-lookup"><span data-stu-id="0e039-113">Setup Windows Server</span></span>

<span data-ttu-id="0e039-114">Skype empresarial Server requiere el sistema operativo Windows Server y una serie de requisitos previos antes de que se pueda instalar.</span><span class="sxs-lookup"><span data-stu-id="0e039-114">Skype for Business Server requires the Windows Server operating system and a number of prerequisites before it can be installed.</span></span> <span data-ttu-id="0e039-115">Para obtener más información sobre la planeación de requisitos previos, vea [Server Requirements for Skype for Business Server](../../../SfBServer2019/plan/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0e039-115">For details on planning for prerequisites, see [Server requirements for Skype for Business Server](../../../SfBServer2019/plan/system-requirements.md).</span></span> 
  
> [!TIP]
> <span data-ttu-id="0e039-116">Este procedimiento usa Windows Server 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="0e039-116">This procedure uses Windows Server 2012 R2.</span></span> <span data-ttu-id="0e039-117">Si usa una versión diferente de Windows Server, es posible que el procedimiento sea ligeramente diferente.</span><span class="sxs-lookup"><span data-stu-id="0e039-117">If you are using a different version of Windows Server, the procedure might be slightly different.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="0e039-118">Antes de empezar, asegúrese de que Windows Server está actualizado mediante Windows Update.</span><span class="sxs-lookup"><span data-stu-id="0e039-118">Before you begin, make sure that Windows Server is up-to-date by using Windows Update.</span></span> 
  
![Windows Server actualizado.](../../media/a8d57a97-a55e-443b-b304-c534ae9a71b2.png)
  
<span data-ttu-id="0e039-120">Vea los pasos del vídeo para **instalar los requisitos previos**:</span><span class="sxs-lookup"><span data-stu-id="0e039-120">Watch the video steps for **install prerequisites**:</span></span>
  
> [!video https://www.microsoft.com/videoplayer/embed/02447c2a-5b26-432f-aad6-b9b05cc93478?autoplay=false]
  
### <a name="install-required-roles-and-features-for-front-end-servers"></a><span data-ttu-id="0e039-121">Instalar los roles y las características necesarios para los servidores front-end</span><span class="sxs-lookup"><span data-stu-id="0e039-121">Install required roles and features for front-end servers</span></span>

<span data-ttu-id="0e039-122">Puede instalar los roles y las características necesarios mediante el administrador del servidor.</span><span class="sxs-lookup"><span data-stu-id="0e039-122">You can install the required roles and features using Server Manager.</span></span> 
    
1. <span data-ttu-id="0e039-123">Instale las características de software necesarias que se indican en [Server Requirements for Skype for Business Server](../../../SfBServer2019/plan/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0e039-123">Install the prerequisite software features listed in [Server requirements for Skype for Business Server](../../../SfBServer2019/plan/system-requirements.md).</span></span> <span data-ttu-id="0e039-124">El software necesario debe estar en el servidor que va a ejecutar Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="0e039-124">The required software must be on the server that will run Skype for Business Server.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="0e039-125">Windows Server 2012 R2 no instala de forma predeterminada todos los archivos de origen para las características necesarias.</span><span class="sxs-lookup"><span data-stu-id="0e039-125">Windows Server 2012 R2 does not install all of the source files for the required features by default.</span></span> <span data-ttu-id="0e039-126">Si el servidor no está conectado a Internet, deberá insertar el medio de Windows Server 2012 R2 y seleccionar **especificar una ruta de acceso de origen alternativa** para instalar las características necesarias.</span><span class="sxs-lookup"><span data-stu-id="0e039-126">If the server is not connected to the Internet, you will need to insert the Windows Server 2012 R2 media and select **Specify an alternate source path** in order to install the required features.</span></span> <span data-ttu-id="0e039-127">Los archivos de origen se encuentran en el directorio sources\sxs</span><span class="sxs-lookup"><span data-stu-id="0e039-127">The source files are located in the sources\sxs directory.</span></span> <span data-ttu-id="0e039-128">Por ejemplo, si el medio de Windows Server 2012 R2 está en la unidad D, establezca la ruta de `d:\sources\sxs`acceso en.</span><span class="sxs-lookup"><span data-stu-id="0e039-128">For example, if the Windows Server 2012 R2 media is in drive D, you would set the path to `d:\sources\sxs`.</span></span> <span data-ttu-id="0e039-129">Es importante que tenga las actualizaciones más recientes de Windows Update.</span><span class="sxs-lookup"><span data-stu-id="0e039-129">It is important that you have the latest updates from Windows Update.</span></span> <span data-ttu-id="0e039-130">Si no está conectado a Internet, tendrá que instalar manualmente todas las actualizaciones relevantes, así como los requisitos previos de las actualizaciones necesarias.</span><span class="sxs-lookup"><span data-stu-id="0e039-130">If you are not connected to the Internet, you will need to manually install all relevant updates as well as any prerequisites to the required updates.</span></span> 
  
1. <span data-ttu-id="0e039-131">Cuando el cuadro de diálogo indique que la instalación ha finalizado, tendrá que reiniciar el servidor para completar el proceso.</span><span class="sxs-lookup"><span data-stu-id="0e039-131">When the dialog box indicates that the installation has completed, you will need to reboot the server to complete the process.</span></span>
    
1. <span data-ttu-id="0e039-132">Vuelva a ejecutar **Windows Update** para comprobar si hay actualizaciones de los roles y servicios que se instalaron.</span><span class="sxs-lookup"><span data-stu-id="0e039-132">Run **Windows Update** again to check if there are any updates to the roles and services that were installed.</span></span>
    
1. <span data-ttu-id="0e039-133">Si va a usar el panel de control de Skype empresarial Server en este servidor, también debe instalar Silverlight.</span><span class="sxs-lookup"><span data-stu-id="0e039-133">If you will be using Skype for Business Server Control Panel on this server then you must also install Silverlight.</span></span> <span data-ttu-id="0e039-134">Para instalar Silverlight, consulte [Microsoft Silverlight](https://www.microsoft.com/silverlight/).</span><span class="sxs-lookup"><span data-stu-id="0e039-134">To install Silverlight, see [Microsoft Silverlight](https://www.microsoft.com/silverlight/).</span></span>


> [!IMPORTANT]
> <span data-ttu-id="0e039-135">Los requisitos previos para los servidores que realizan roles que no son servidores front-end, como el rol de Director, chat persistente o Edge, tienen sus propios requisitos previos.</span><span class="sxs-lookup"><span data-stu-id="0e039-135">The prerequisites for servers performing roles other than front-end server, such as the role of Director, Persistent Chat, or Edge, have their own prerequisites.</span></span> <span data-ttu-id="0e039-136">Para obtener más información sobre los requisitos previos exactos necesarios para cada tipo de servidor, vea [Server Requirements for Skype for Business Server](../../../SfBServer2019/plan/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0e039-136">For details on the exact prerequisites required by each server type, see [Server requirements for Skype for Business Server](../../../SfBServer2019/plan/system-requirements.md).</span></span> 
  

