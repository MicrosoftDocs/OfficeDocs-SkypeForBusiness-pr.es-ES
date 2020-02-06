---
title: Crear un recurso compartido de archivos en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
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
ms.assetid: 053076b0-441c-44d9-8dbc-7a36d8ecafe4
description: 'Resumen: Aprenda a crear un recurso compartido de archivos de Windows Server como parte de la instalación de Skype empresarial Server. Descargue una prueba gratuita de Skype empresarial Server en el centro de evaluación de Microsoft en https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server:.'
ms.openlocfilehash: 57d1bc348d1fed7a0dc8297723d41d3d90888710
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41790188"
---
# <a name="create-a-file-share-in-skype-for-business-server"></a><span data-ttu-id="1abf5-104">Crear un recurso compartido de archivos en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="1abf5-104">Create a file share in Skype for Business Server</span></span>
 
<span data-ttu-id="1abf5-105">**Resumen:** Aprenda a crear un recurso compartido de archivos de Windows Server como parte de la instalación de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="1abf5-105">**Summary:** Learn how to create a Windows Server file share as part of the installation of Skype for Business Server.</span></span> <span data-ttu-id="1abf5-106">Descargue una prueba gratuita de Skype empresarial Server en el centro de evaluación de Microsoft en[https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server):.</span><span class="sxs-lookup"><span data-stu-id="1abf5-106">Download a free trial of Skype for Business Server from the Microsoft Evaluation center at:[https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="1abf5-107">Skype empresarial Server requiere un recurso compartido de archivos para que los equipos de toda la topología puedan intercambiar archivos.</span><span class="sxs-lookup"><span data-stu-id="1abf5-107">Skype for Business Server requires a file share so that computers throughout the topology can exchange files.</span></span> <span data-ttu-id="1abf5-108">La creación de un recurso compartido de archivos es el paso 2 de 8 en el proceso de instalación de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="1abf5-108">Creating a file share is step 2 of 8 in the installation process for Skype for Business Server.</span></span> <span data-ttu-id="1abf5-109">Puede realizar los pasos 1 a 5 en cualquier orden.</span><span class="sxs-lookup"><span data-stu-id="1abf5-109">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="1abf5-110">Sin embargo, debe realizar los pasos 6, 7 y 8 en orden, y después de los pasos 1 a 5, tal como se indica en el diagrama.</span><span class="sxs-lookup"><span data-stu-id="1abf5-110">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5 as outlined in the diagram.</span></span> <span data-ttu-id="1abf5-111">Para obtener información sobre cómo planear el uso compartido de archivos, consulte [requisitos ambientales para Skype empresarial Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) o [requisitos del servidor para skype empresarial Server 2019](../../../SfBServer2019/plan/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1abf5-111">For planning details about file share, see [Environmental requirements for Skype for Business Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) or [Server requirements for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).</span></span>
  
![Diagrama de información general](../../media/e69de059-3040-45ab-9379-1932f9fbb37f.png)
  
## <a name="create-a-basic-file-share"></a><span data-ttu-id="1abf5-113">Crear un recurso compartido de archivos básico</span><span class="sxs-lookup"><span data-stu-id="1abf5-113">Create a basic file share</span></span>

<span data-ttu-id="1abf5-114">En esta sección se explica cómo crear un recurso compartido de archivos de Windows Server básico.</span><span class="sxs-lookup"><span data-stu-id="1abf5-114">This section walks you through creating a basic Windows Server file share.</span></span> <span data-ttu-id="1abf5-115">Un recurso compartido de archivos de Windows Server básico es compatible con Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="1abf5-115">A basic Windows Server file share is supported with Skype for Business Server.</span></span> <span data-ttu-id="1abf5-116">Sin embargo, no proporciona de forma explícita alta la disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="1abf5-116">However, it does not explicitly provide high availability.</span></span> <span data-ttu-id="1abf5-117">Para un entorno de alta disponibilidad, se recomienda un recurso compartido de archivos del sistema de archivos distribuido (DFS).</span><span class="sxs-lookup"><span data-stu-id="1abf5-117">For a high availability environment, a Distributed File System (DFS) file share is recommended.</span></span> <span data-ttu-id="1abf5-118">Para obtener más información sobre un recurso compartido de archivos y DFS de alta disponibilidad, consulte [planear la alta disponibilidad y la recuperación ante desastres en Skype empresarial Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="1abf5-118">For more information about a high availability file share and DFS, see [Plan for high availability and disaster recovery in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="1abf5-119">Se han realizado importantes avances en Windows Server 2012 R2 a fin de proporcionar soluciones de recursos compartidos de archivos similares a la red de área de almacenamiento (SAN) con la plataforma de Windows Server.</span><span class="sxs-lookup"><span data-stu-id="1abf5-119">Windows Server 2012 R2 has made major leaps in providing Storage Area Network (SAN)-like file share solutions using the Windows Server platform.</span></span> <span data-ttu-id="1abf5-120">Cuando se la compara con un dispositivo basado en SAN tradicional, una solución de almacenamiento de Windows Server 2012 R2 puede reducir los costes a la mitad con un impacto muy mínimo en el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="1abf5-120">When compared to a traditional SAN-based appliance, a Windows Server 2012 R2 storage solution can cut costs in half with very minimal impact to performance.</span></span> <span data-ttu-id="1abf5-121">Para obtener más información sobre las opciones de uso compartido de archivos en Windows Server 2012 R2, consulte el documento en el que se puede descargar el [almacenamiento de Windows server 2012 R2](https://download.microsoft.com/download/9/4/A/94A15682-02D6-47AD-B209-79D6E2758A24/Windows_Server_2012_R2_Storage_White_Paper.pdf).</span><span class="sxs-lookup"><span data-stu-id="1abf5-121">For more information about file share options in Windows Server 2012 R2, see the downloadable white paper [Windows Server 2012 R2 Storage](https://download.microsoft.com/download/9/4/A/94A15682-02D6-47AD-B209-79D6E2758A24/Windows_Server_2012_R2_Storage_White_Paper.pdf).</span></span> 
  
<span data-ttu-id="1abf5-122">Vea los pasos del vídeo para **crear un recurso compartido de archivos**:</span><span class="sxs-lookup"><span data-stu-id="1abf5-122">Watch the video steps for **create a file share**:</span></span>
  
> [!video https://www.microsoft.com/en-us/videoplayer/embed/dbef31be-e899-4a32-a1ca-370053284f56?autoplay=false]
  
### <a name="create-a-basic-file-share"></a><span data-ttu-id="1abf5-123">Crear un recurso compartido de archivos básico</span><span class="sxs-lookup"><span data-stu-id="1abf5-123">Create a basic file share</span></span>

1. <span data-ttu-id="1abf5-124">Inicie sesión en el equipo que hospedará el recurso compartido de archivos.</span><span class="sxs-lookup"><span data-stu-id="1abf5-124">Log on to the computer that will host the file share.</span></span>
    
2. <span data-ttu-id="1abf5-125">Haga clic con el botón secundario en la carpeta que desea compartir y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="1abf5-125">Right-click the folder you plan to share, and select **Properties**.</span></span>
    
3. <span data-ttu-id="1abf5-126">Seleccione la pestaña **Uso compartido** y haga clic en **Uso compartido avanzado**.</span><span class="sxs-lookup"><span data-stu-id="1abf5-126">Select the **Sharing** tab, and click **Advanced Sharing**.</span></span>
    
4. <span data-ttu-id="1abf5-127">Haga clic en **Compartir esta carpeta**.</span><span class="sxs-lookup"><span data-stu-id="1abf5-127">Click **Share this folder**.</span></span>
    
5. <span data-ttu-id="1abf5-128">Haga clic en **Permisos**.</span><span class="sxs-lookup"><span data-stu-id="1abf5-128">Click **Permissions**.</span></span>
    
6. <span data-ttu-id="1abf5-129">Agregue el grupo **Administradores** local del servidor que aloja el recurso compartido de archivos, conceda derechos **Permitir: Control total, Cambiar y Leer** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1abf5-129">Add the local **Administrators** group of the server hosting the file share, grant **Allow: Full Control, Change, and Read** rights, and then click **OK**.</span></span>
    
7. <span data-ttu-id="1abf5-130">Haga clic en **Aceptar** nuevamente y tome nota de la ruta de acceso a la red.</span><span class="sxs-lookup"><span data-stu-id="1abf5-130">Click **OK** again and take note of the network path.</span></span>
    
8. <span data-ttu-id="1abf5-131">Haga clic en **Listo** para cerrar el asistente.</span><span class="sxs-lookup"><span data-stu-id="1abf5-131">Click **Done** to close the wizard.</span></span>
    
     ![Pestaña Uso compartido para compartir una carpeta.](../../media/78fe8441-dead-43ed-9a04-3c7c8c657c15.png)
  
> [!NOTE]
><span data-ttu-id="1abf5-133">Si el almacén de archivos está hospedado en un recurso compartido DFS, se recibirá la siguiente ADVERTENCIA:</span><span class="sxs-lookup"><span data-stu-id="1abf5-133">If the file store is hosted on a DFS share, the following warning will be received:</span></span>

<span data-ttu-id="1abf5-134">ADVERTENCIA: no se puede acceder a los permisos\\<domain>\<de uso compartido para "compartir>".</span><span class="sxs-lookup"><span data-stu-id="1abf5-134">Warning: Unable to access share permissions for "\\<domain>\<share>".</span></span>

><span data-ttu-id="1abf5-135">Esto es lo que se espera si no es un administrador en el servidor de archivos o si se trata de un recurso compartido de sistema de archivos distribuido (DFS).</span><span class="sxs-lookup"><span data-stu-id="1abf5-135">This is expected if you are not an administrator on the file server, or if this is a Distributed File System (DFS) share.</span></span> <span data-ttu-id="1abf5-136">Si los permisos de uso compartido ya se han configurado, esta advertencia se puede ignorar.</span><span class="sxs-lookup"><span data-stu-id="1abf5-136">If the share permissions have already been configured, this warning can be ignored.</span></span> <span data-ttu-id="1abf5-137">Si se trata de un nuevo recurso compartido, consulte la documentación para obtener más información sobre cómo configurar manualmente los permisos de uso compartido.</span><span class="sxs-lookup"><span data-stu-id="1abf5-137">If it is a new share, refer to the documentation for details on manually configuring share permissions.</span></span>

><span data-ttu-id="1abf5-138">Debido a la incapacidad de acceder a los permisos de uso compartido en un recurso compartido DFS, Skype empresarial Server no podrá establecer grupos de forma explícita en el recurso compartido de archivos.</span><span class="sxs-lookup"><span data-stu-id="1abf5-138">Due to the inability to access the share permissions on a DFS share, Skype for Business Server will not be able to explicitly set groups on the file share.</span></span> <span data-ttu-id="1abf5-139">Para asegurarse de que los componentes de Skype empresarial Server pueden acceder al recurso compartido de archivos con los permisos adecuados, asegúrese de que los siguientes grupos de RTC se agregan con permisos de uso compartido de nivel de lectura y lectura, además de los administradores locales con el uso compartido de control total permisos.</span><span class="sxs-lookup"><span data-stu-id="1abf5-139">To ensure Skype for Business Server components can access the file share with the appropriate permissions, ensure the following RTC groups are added with Read and Change level share permissions in addition to the local Administrators with Full Control share permissions.</span></span>
* <span data-ttu-id="1abf5-140">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="1abf5-140">RTCHSUniversalServices</span></span>
* <span data-ttu-id="1abf5-141">RTCComponentUniversalServices</span><span class="sxs-lookup"><span data-stu-id="1abf5-141">RTCComponentUniversalServices</span></span>
* <span data-ttu-id="1abf5-142">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="1abf5-142">RTCUniversalServerAdmins</span></span>
