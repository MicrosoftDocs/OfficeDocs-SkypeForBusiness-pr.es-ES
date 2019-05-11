---
title: Instalar los requisitos previos de Skype para Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2ef91a1e-2899-44c8-8e2c-527cb9114a0a
description: 'Resumen: Obtenga información sobre los servidores y roles de servidor que debe configurar antes de instalar Skype para Business Server. Descargue una versión de prueba gratuita de Skype para Business Server desde el Evaluation de Microsoft center en: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server.'
ms.openlocfilehash: 6a5b6728f65d1f541687cb55811157531c70456d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33891813"
---
# <a name="install-prerequisites-for-skype-for-business-server"></a><span data-ttu-id="82d9c-104">Instalar los requisitos previos de Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="82d9c-104">Install prerequisites for Skype for Business Server</span></span>
 
<span data-ttu-id="82d9c-105">**Resumen:** Obtenga información acerca de los servidores y roles de servidor que debe configurar antes de instalar Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="82d9c-105">**Summary:** Learn about the servers and server roles you must configure before you install Skype for Business Server.</span></span> <span data-ttu-id="82d9c-106">Descargue una versión de prueba gratuita de Skype para Business Server desde el [Centro de evaluación de Microsoft](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span><span class="sxs-lookup"><span data-stu-id="82d9c-106">Download a free trial of Skype for Business Server from the [Microsoft Evaluation center](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="82d9c-107">Instalación de requisitos previos se compone de la configuración de Windows Server mediante la instalación de las características y los roles necesarios en cada uno de los servidores de la topología.</span><span class="sxs-lookup"><span data-stu-id="82d9c-107">Installing prerequisites consists of setting up Windows Server by installing the required roles and features on each of the servers in the topology.</span></span> <span data-ttu-id="82d9c-108">Los requisitos se basan en la función que se va a cumplir con el servidor en la topología.</span><span class="sxs-lookup"><span data-stu-id="82d9c-108">The requirements are based on the role the server will fulfill in the topology.</span></span> <span data-ttu-id="82d9c-109">Se pueden realizar los pasos del 1 al 5 en cualquier orden.</span><span class="sxs-lookup"><span data-stu-id="82d9c-109">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="82d9c-110">Sin embargo, debe realizar los pasos 6, 7 y 8 en orden y después de los pasos del 1 al 5, tal como se indica en el diagrama.</span><span class="sxs-lookup"><span data-stu-id="82d9c-110">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5, as outlined in the diagram.</span></span> <span data-ttu-id="82d9c-111">Instalación de requisitos previos es el paso 1 de 8.</span><span class="sxs-lookup"><span data-stu-id="82d9c-111">Installing prerequisites is step 1 of 8.</span></span>
  
![Diagrama de información general: requisitos previos de instalación.](../../media/0a85349b-b398-4e04-8901-8f4bd25d8afe.png)
  
## <a name="setup-windows-server"></a><span data-ttu-id="82d9c-113">Configurar Windows Server</span><span class="sxs-lookup"><span data-stu-id="82d9c-113">Setup Windows Server</span></span>

<span data-ttu-id="82d9c-114">Skype para Business Server requiere el sistema operativo Windows Server y un número de requisitos previos antes de que se puede instalar.</span><span class="sxs-lookup"><span data-stu-id="82d9c-114">Skype for Business Server requires the Windows Server operating system and a number of prerequisites before it can be installed.</span></span> <span data-ttu-id="82d9c-115">Para obtener información detallada acerca de cómo planear los requisitos previos, vea [requisitos de servidor para Skype para Business Server](../../../SfBServer2019/plan/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="82d9c-115">For details on planning for prerequisites, see [Server requirements for Skype for Business Server](../../../SfBServer2019/plan/system-requirements.md).</span></span> 
  
> [!TIP]
> <span data-ttu-id="82d9c-116">Este procedimiento utiliza Windows Server 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="82d9c-116">This procedure uses Windows Server 2012 R2.</span></span> <span data-ttu-id="82d9c-117">Es posible que el procedimiento sea un poco diferente si usa una versión de Windows Server distinta.</span><span class="sxs-lookup"><span data-stu-id="82d9c-117">If you are using a different version of Windows Server, the procedure might be slightly different.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="82d9c-118">Antes de empezar, asegúrese de que el servidor de Windows está actualizado mediante el uso de Windows Update.</span><span class="sxs-lookup"><span data-stu-id="82d9c-118">Before you begin, make sure that Windows Server is up-to-date by using Windows Update.</span></span> 
  
![Windows Server actualizado.](../../media/a8d57a97-a55e-443b-b304-c534ae9a71b2.png)
  
<span data-ttu-id="82d9c-120">Vea los pasos del vídeo para **instalar los requisitos previos**:</span><span class="sxs-lookup"><span data-stu-id="82d9c-120">Watch the video steps for **install prerequisites**:</span></span>
  
> [!video https://www.microsoft.com/en-us/videoplayer/embed/02447c2a-5b26-432f-aad6-b9b05cc93478?autoplay=false]
  
### <a name="install-required-roles-and-features-for-front-end-servers"></a><span data-ttu-id="82d9c-121">Instalar las características y los roles necesarios para los servidores front-end</span><span class="sxs-lookup"><span data-stu-id="82d9c-121">Install required roles and features for front-end servers</span></span>

<span data-ttu-id="82d9c-122">Puede instalar los roles necesarios y las características de con el administrador del servidor.</span><span class="sxs-lookup"><span data-stu-id="82d9c-122">You can install the required roles and features using Server Manager.</span></span> 
    
1. <span data-ttu-id="82d9c-123">Instalar las características de software necesario como requisito previo que aparecen en los [requisitos de servidor para Skype para Business Server](../../../SfBServer2019/plan/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="82d9c-123">Install the prerequisite software features listed in [Server requirements for Skype for Business Server](../../../SfBServer2019/plan/system-requirements.md).</span></span> <span data-ttu-id="82d9c-124">Debe ser el software necesario en el servidor que ejecutará Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="82d9c-124">The required software must be on the server that will run Skype for Business Server.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="82d9c-125">De forma predeterminada, Windows Server 2012 R2 no instala todos los archivos de origen de las características necesarias.</span><span class="sxs-lookup"><span data-stu-id="82d9c-125">Windows Server 2012 R2 does not install all of the source files for the required features by default.</span></span> <span data-ttu-id="82d9c-126">Si el servidor no está conectado a Internet, necesitará insertar el disco de Windows Server 2012 R2 y seleccionar **Especifique una ruta de acceso de origen alternativa** para instalar las características necesarias.</span><span class="sxs-lookup"><span data-stu-id="82d9c-126">If the server is not connected to the Internet, you will need to insert the Windows Server 2012 R2 media and select **Specify an alternate source path** in order to install the required features.</span></span> <span data-ttu-id="82d9c-127">Los archivos de origen se encuentran en el directorio sources\sxs.</span><span class="sxs-lookup"><span data-stu-id="82d9c-127">The source files are located in the sources\sxs directory.</span></span> <span data-ttu-id="82d9c-128">Por ejemplo, si los medios de Windows Server 2012 R2 se encuentra en la unidad D, establecería la ruta de acceso `d:\sources\sxs`.</span><span class="sxs-lookup"><span data-stu-id="82d9c-128">For example, if the Windows Server 2012 R2 media is in drive D, you would set the path to `d:\sources\sxs`.</span></span> <span data-ttu-id="82d9c-129">Es importante que disponga de las últimas actualizaciones de Windows Update.</span><span class="sxs-lookup"><span data-stu-id="82d9c-129">It is important that you have the latest updates from Windows Update.</span></span> <span data-ttu-id="82d9c-130">Si no se encuentra conectado a Internet, necesitará instalar todas las actualizaciones relevantes de manera manual, así como también todos los requisitos previos de las actualizaciones necesarias.</span><span class="sxs-lookup"><span data-stu-id="82d9c-130">If you are not connected to the Internet, you will need to manually install all relevant updates as well as any prerequisites to the required updates.</span></span> 
  
1. <span data-ttu-id="82d9c-131">Cuando el cuadro de diálogo indica que se ha completado la instalación, necesitará reiniciar el servidor para completar el proceso.</span><span class="sxs-lookup"><span data-stu-id="82d9c-131">When the dialog box indicates that the installation has completed, you will need to reboot the server to complete the process.</span></span>
    
1. <span data-ttu-id="82d9c-132">Ejecute **Windows Update** nuevamente para comprobar si hay actualizaciones de los roles y los servicios que se instalaron.</span><span class="sxs-lookup"><span data-stu-id="82d9c-132">Run **Windows Update** again to check if there are any updates to the roles and services that were installed.</span></span>
    
1. <span data-ttu-id="82d9c-133">Si va a usar Skype para el Panel de Control de servidor empresarial en este servidor, a continuación, también debe instalar Silverlight.</span><span class="sxs-lookup"><span data-stu-id="82d9c-133">If you will be using Skype for Business Server Control Panel on this server then you must also install Silverlight.</span></span> <span data-ttu-id="82d9c-134">Para instalar Silverlight, vea [Microsoft Silverlight](https://www.microsoft.com/silverlight/).</span><span class="sxs-lookup"><span data-stu-id="82d9c-134">To install Silverlight, see [Microsoft Silverlight](https://www.microsoft.com/silverlight/).</span></span>


> [!IMPORTANT]
> <span data-ttu-id="82d9c-135">Los servidores que desempeñan roles distintos del de servidor front-end (como el rol de director, chat persistente o servidor perimetral) tienen sus propios requisitos previos.</span><span class="sxs-lookup"><span data-stu-id="82d9c-135">The prerequisites for servers performing roles other than front-end server, such as the role of Director, Persistent Chat, or Edge, have their own prerequisites.</span></span> <span data-ttu-id="82d9c-136">Para obtener información detallada sobre los requisitos previos exactos necesarios para cada tipo de servidor, vea [requisitos de servidor para Skype para Business Server](../../../SfBServer2019/plan/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="82d9c-136">For details on the exact prerequisites required by each server type, see [Server requirements for Skype for Business Server](../../../SfBServer2019/plan/system-requirements.md).</span></span> 
  

