---
title: Instalar requisitos previos para Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 'Resumen: obtenga información sobre los servidores y los roles de servidor que debe configurar antes de instalar Skype Empresarial Server. Descargue una prueba gratuita de Skype Empresarial Server desde el Centro de evaluación de Microsoft en: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server .'
ms.openlocfilehash: 197f2482bd6c53f3cf9814dbf6f36bb6c4bdb331
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49801720"
---
# <a name="install-prerequisites-for-skype-for-business-server"></a><span data-ttu-id="5e63f-104">Instalar requisitos previos para Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="5e63f-104">Install prerequisites for Skype for Business Server</span></span>
 
<span data-ttu-id="5e63f-105">**Resumen:** Obtenga información sobre los servidores y los roles de servidor que debe configurar antes de instalar Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="5e63f-105">**Summary:** Learn about the servers and server roles you must configure before you install Skype for Business Server.</span></span> <span data-ttu-id="5e63f-106">Descargue una versión de prueba gratuita de Skype Empresarial Server desde el Centro [de evaluación de Microsoft.](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)</span><span class="sxs-lookup"><span data-stu-id="5e63f-106">Download a free trial of Skype for Business Server from the [Microsoft Evaluation center](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="5e63f-107">La instalación de requisitos previos consiste en configurar Windows Server instalando los roles y características necesarios en cada uno de los servidores de la topología.</span><span class="sxs-lookup"><span data-stu-id="5e63f-107">Installing prerequisites consists of setting up Windows Server by installing the required roles and features on each of the servers in the topology.</span></span> <span data-ttu-id="5e63f-108">Los requisitos se basan en el rol que el servidor cumplirá en la topología.</span><span class="sxs-lookup"><span data-stu-id="5e63f-108">The requirements are based on the role the server will fulfill in the topology.</span></span> <span data-ttu-id="5e63f-109">Puede realizar los pasos del 1 al 5 en cualquier orden.</span><span class="sxs-lookup"><span data-stu-id="5e63f-109">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="5e63f-110">Sin embargo, debe realizar los pasos 6, 7 y 8 en orden y después de los pasos 1 a 5, tal como se indica en el diagrama.</span><span class="sxs-lookup"><span data-stu-id="5e63f-110">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5, as outlined in the diagram.</span></span> <span data-ttu-id="5e63f-111">La instalación de requisitos previos es el paso 1 de 8.</span><span class="sxs-lookup"><span data-stu-id="5e63f-111">Installing prerequisites is step 1 of 8.</span></span>
  
![Diagrama de información general: requisitos previos de instalación.](../../media/0a85349b-b398-4e04-8901-8f4bd25d8afe.png)
  
## <a name="setup-windows-server"></a><span data-ttu-id="5e63f-113">Configurar Windows Server</span><span class="sxs-lookup"><span data-stu-id="5e63f-113">Setup Windows Server</span></span>

<span data-ttu-id="5e63f-114">Skype Empresarial Server requiere el sistema operativo Windows Server y una serie de requisitos previos para poder instalarse.</span><span class="sxs-lookup"><span data-stu-id="5e63f-114">Skype for Business Server requires the Windows Server operating system and a number of prerequisites before it can be installed.</span></span> <span data-ttu-id="5e63f-115">Para obtener más información sobre la planeación de requisitos previos, consulte [Requisitos del servidor para Skype Empresarial Server.](../../../SfBServer2019/plan/system-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="5e63f-115">For details on planning for prerequisites, see [Server requirements for Skype for Business Server](../../../SfBServer2019/plan/system-requirements.md).</span></span> 
  
> [!TIP]
> <span data-ttu-id="5e63f-116">Este procedimiento usa Windows Server 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="5e63f-116">This procedure uses Windows Server 2012 R2.</span></span> <span data-ttu-id="5e63f-117">Si usa una versión diferente de Windows Server, el procedimiento puede ser ligeramente diferente.</span><span class="sxs-lookup"><span data-stu-id="5e63f-117">If you are using a different version of Windows Server, the procedure might be slightly different.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="5e63f-118">Antes de empezar, asegúrate de que Windows Server esté actualizado mediante Windows Update.</span><span class="sxs-lookup"><span data-stu-id="5e63f-118">Before you begin, make sure that Windows Server is up-to-date by using Windows Update.</span></span> 
  
![Windows Server actualizado.](../../media/a8d57a97-a55e-443b-b304-c534ae9a71b2.png)
  
<span data-ttu-id="5e63f-120">Vea los pasos de vídeo para **los requisitos previos de instalación:**</span><span class="sxs-lookup"><span data-stu-id="5e63f-120">Watch the video steps for **install prerequisites**:</span></span>
  
> [!video https://www.microsoft.com/videoplayer/embed/02447c2a-5b26-432f-aad6-b9b05cc93478?autoplay=false]
  
### <a name="install-required-roles-and-features-for-front-end-servers"></a><span data-ttu-id="5e63f-121">Instalar las funciones y características necesarias para los servidores front-end</span><span class="sxs-lookup"><span data-stu-id="5e63f-121">Install required roles and features for front-end servers</span></span>

<span data-ttu-id="5e63f-122">Puede instalar los roles y características necesarios con el Administrador del servidor.</span><span class="sxs-lookup"><span data-stu-id="5e63f-122">You can install the required roles and features using Server Manager.</span></span> 
    
1. <span data-ttu-id="5e63f-123">Instale las características de software de requisitos previos que se enumeran [en Los requisitos del servidor para Skype Empresarial Server.](../../../SfBServer2019/plan/system-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="5e63f-123">Install the prerequisite software features listed in [Server requirements for Skype for Business Server](../../../SfBServer2019/plan/system-requirements.md).</span></span> <span data-ttu-id="5e63f-124">El software necesario debe estar en el servidor que ejecutará Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="5e63f-124">The required software must be on the server that will run Skype for Business Server.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="5e63f-125">Windows Server 2012 R2 no instala todos los archivos de origen para las características necesarias de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="5e63f-125">Windows Server 2012 R2 does not install all of the source files for the required features by default.</span></span> <span data-ttu-id="5e63f-126">Si el servidor no está conectado a Internet, deberá insertar los medios de Windows  Server 2012 R2 y seleccionar Especificar una ruta de origen alternativa para instalar las características necesarias.</span><span class="sxs-lookup"><span data-stu-id="5e63f-126">If the server is not connected to the Internet, you will need to insert the Windows Server 2012 R2 media and select **Specify an alternate source path** in order to install the required features.</span></span> <span data-ttu-id="5e63f-127">Los archivos de origen se encuentran en el directorio sources\sxs.</span><span class="sxs-lookup"><span data-stu-id="5e63f-127">The source files are located in the sources\sxs directory.</span></span> <span data-ttu-id="5e63f-128">Por ejemplo, si los medios de Windows Server 2012 R2 están en la unidad D, se establecería la ruta de acceso en `d:\sources\sxs` .</span><span class="sxs-lookup"><span data-stu-id="5e63f-128">For example, if the Windows Server 2012 R2 media is in drive D, you would set the path to `d:\sources\sxs`.</span></span> <span data-ttu-id="5e63f-129">Es importante que tenga las actualizaciones más recientes de Windows Update.</span><span class="sxs-lookup"><span data-stu-id="5e63f-129">It is important that you have the latest updates from Windows Update.</span></span> <span data-ttu-id="5e63f-130">Si no está conectado a Internet, deberá instalar manualmente todas las actualizaciones relevantes, así como los requisitos previos de las actualizaciones necesarias.</span><span class="sxs-lookup"><span data-stu-id="5e63f-130">If you are not connected to the Internet, you will need to manually install all relevant updates as well as any prerequisites to the required updates.</span></span> 
  
1. <span data-ttu-id="5e63f-131">Cuando el cuadro de diálogo indique que la instalación se ha completado, deberá reiniciar el servidor para completar el proceso.</span><span class="sxs-lookup"><span data-stu-id="5e63f-131">When the dialog box indicates that the installation has completed, you will need to reboot the server to complete the process.</span></span>
    
1. <span data-ttu-id="5e63f-132">Ejecute **Windows Update de** nuevo para comprobar si hay actualizaciones de los roles y servicios que se instalaron.</span><span class="sxs-lookup"><span data-stu-id="5e63f-132">Run **Windows Update** again to check if there are any updates to the roles and services that were installed.</span></span>
    
1. <span data-ttu-id="5e63f-133">Si va a usar el Panel de control de Skype Empresarial Server en este servidor, también debe instalar Silverlight.</span><span class="sxs-lookup"><span data-stu-id="5e63f-133">If you will be using Skype for Business Server Control Panel on this server then you must also install Silverlight.</span></span> <span data-ttu-id="5e63f-134">Para instalar Silverlight, vea [Microsoft Silverlight](https://www.microsoft.com/silverlight/).</span><span class="sxs-lookup"><span data-stu-id="5e63f-134">To install Silverlight, see [Microsoft Silverlight](https://www.microsoft.com/silverlight/).</span></span>


> [!IMPORTANT]
> <span data-ttu-id="5e63f-135">Los requisitos previos para los servidores que realizan funciones que no son el servidor front-end, como el rol de director, chat persistente o servidor perimetral, tienen sus propios requisitos previos.</span><span class="sxs-lookup"><span data-stu-id="5e63f-135">The prerequisites for servers performing roles other than front-end server, such as the role of Director, Persistent Chat, or Edge, have their own prerequisites.</span></span> <span data-ttu-id="5e63f-136">Para obtener más información sobre los requisitos previos exactos requeridos por cada tipo de servidor, consulte Requisitos del [servidor para Skype Empresarial Server.](../../../SfBServer2019/plan/system-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="5e63f-136">For details on the exact prerequisites required by each server type, see [Server requirements for Skype for Business Server](../../../SfBServer2019/plan/system-requirements.md).</span></span> 
  

