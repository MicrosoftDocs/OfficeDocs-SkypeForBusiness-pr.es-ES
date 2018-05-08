---
title: Crear un recurso compartido de archivos en Skype Empresarial Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 053076b0-441c-44d9-8dbc-7a36d8ecafe4
description: 'Resumen: Obtenga información sobre cómo crear un recurso compartido de archivos de Windows Server como parte de la instalación de Skype para Business Server 2015. Descargue una versión de prueba gratuita de Skype para Business Server 2015 desde el Evaluation de Microsoft center en: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server.'
ms.openlocfilehash: 5f91a18a744e73cd65f58efef071978604653b27
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="create-a-file-share-in-skype-for-business-server-2015"></a><span data-ttu-id="a97d2-104">Crear un recurso compartido de archivos en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="a97d2-104">Create a file share in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="a97d2-105">**Resumen:** Obtenga información sobre cómo crear un recurso compartido de archivos de Windows Server como parte de la instalación de Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="a97d2-105">**Summary:** Learn how to create a Windows Server file share as part of the installation of Skype for Business Server 2015.</span></span> <span data-ttu-id="a97d2-106">Descargue una versión de prueba gratuita de Skype para Business Server 2015 desde el Evaluation de Microsoft center en:[https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span><span class="sxs-lookup"><span data-stu-id="a97d2-106">Download a free trial of Skype for Business Server 2015 from the Microsoft Evaluation center at:[https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="a97d2-107">Skype para Business Server requiere un recurso compartido de archivos para que los equipos en toda la topología pueden intercambiar archivos.</span><span class="sxs-lookup"><span data-stu-id="a97d2-107">Skype for Business Server requires a file share so that computers throughout the topology can exchange files.</span></span> <span data-ttu-id="a97d2-108">Creación de un recurso compartido de archivos es el paso 2 de 8 en el proceso de instalación de Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="a97d2-108">Creating a file share is step 2 of 8 in the installation process for Skype for Business Server 2015.</span></span> <span data-ttu-id="a97d2-109">Se pueden realizar los pasos del 1 al 5 en cualquier orden.</span><span class="sxs-lookup"><span data-stu-id="a97d2-109">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="a97d2-110">Sin embargo, debe realizar los pasos 6, 7 y 8 en orden y después de los pasos del 1 al 5 tal como se indica en el diagrama.</span><span class="sxs-lookup"><span data-stu-id="a97d2-110">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5 as outlined in the diagram.</span></span> <span data-ttu-id="a97d2-111">Para la planeación de obtener información detallada sobre el recurso compartido de archivos, vea [requisitos de entorno para Skype para Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a97d2-111">For planning details about file share, see [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md).</span></span>
  
![Diagrama de información general](../../media/e69de059-3040-45ab-9379-1932f9fbb37f.png)
  
## <a name="create-a-basic-file-share"></a><span data-ttu-id="a97d2-113">Crear un recurso compartido de archivos básico</span><span class="sxs-lookup"><span data-stu-id="a97d2-113">Create a basic file share</span></span>

<span data-ttu-id="a97d2-114">En esta sección le guiará a través de la creación de un recurso compartido básico de Windows Server.</span><span class="sxs-lookup"><span data-stu-id="a97d2-114">This section walks you through creating a basic Windows Server file share.</span></span> <span data-ttu-id="a97d2-115">Un recurso compartido de Windows Server básico es compatible con Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="a97d2-115">A basic Windows Server file share is supported with Skype for Business Server.</span></span> <span data-ttu-id="a97d2-116">Sin embargo, no explícitamente proporciona una alta disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="a97d2-116">However, it does not explicitly provide high availability.</span></span> <span data-ttu-id="a97d2-117">Para un entorno de alta disponibilidad, se recomienda un recurso compartido de archivos de sistema de archivos distribuido (DFS).</span><span class="sxs-lookup"><span data-stu-id="a97d2-117">For a high availability environment, a Distributed File System (DFS) file share is recommended.</span></span> <span data-ttu-id="a97d2-118">Para obtener más información acerca de un recurso compartido de archivos de alta disponibilidad y DFS, consulte [Plan de alta disponibilidad y recuperación ante desastres en Skype para Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="a97d2-118">For more information about a high availability file share and DFS, see [Plan for high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="a97d2-119">Se han realizado importantes avances en Windows Server 2012 R2 a fin de proporcionar soluciones de recursos compartidos de archivos similares a la red de área de almacenamiento (SAN) con la plataforma de Windows Server.</span><span class="sxs-lookup"><span data-stu-id="a97d2-119">Windows Server 2012 R2 has made major leaps in providing Storage Area Network (SAN)-like file share solutions using the Windows Server platform.</span></span> <span data-ttu-id="a97d2-120">Cuando se la compara con un dispositivo basado en SAN tradicional, una solución de almacenamiento de Windows Server 2012 R2 puede reducir los costes a la mitad con un impacto muy mínimo en el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="a97d2-120">When compared to a traditional SAN-based appliance, a Windows Server 2012 R2 storage solution can cut costs in half with very minimal impact to performance.</span></span> <span data-ttu-id="a97d2-121">Para obtener más información acerca de las opciones del recurso compartido de archivo en Windows Server 2012 R2, vea el [Almacenamiento de Windows Server 2012 R2](https://download.microsoft.com/download/9/4/A/94A15682-02D6-47AD-B209-79D6E2758A24/Windows_Server_2012_R2_Storage_White_Paper.pdf)notas del producto descargables.</span><span class="sxs-lookup"><span data-stu-id="a97d2-121">For more information about file share options in Windows Server 2012 R2, see the downloadable white paper [Windows Server 2012 R2 Storage](https://download.microsoft.com/download/9/4/A/94A15682-02D6-47AD-B209-79D6E2758A24/Windows_Server_2012_R2_Storage_White_Paper.pdf).</span></span> 
  
<span data-ttu-id="a97d2-122">Vea los pasos del vídeo para **crear un recurso compartido de archivos**:</span><span class="sxs-lookup"><span data-stu-id="a97d2-122">Watch the video steps for **create a file share**:</span></span>
  
> [!video https://www.microsoft.com/en-us/videoplayer/embed/dbef31be-e899-4a32-a1ca-370053284f56?autoplay=false]
  
### <a name="create-a-basic-file-share"></a><span data-ttu-id="a97d2-123">Crear un recurso compartido de archivos básico</span><span class="sxs-lookup"><span data-stu-id="a97d2-123">Create a basic file share</span></span>

1. <span data-ttu-id="a97d2-124">Inicie sesión en el equipo que hospedará el recurso compartido de archivos.</span><span class="sxs-lookup"><span data-stu-id="a97d2-124">Log on to the computer that will host the file share.</span></span>
    
2. <span data-ttu-id="a97d2-125">Haga clic con el botón secundario en la carpeta que desea compartir y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="a97d2-125">Right-click the folder you plan to share, and select **Properties**.</span></span>
    
3. <span data-ttu-id="a97d2-126">Seleccione la pestaña **Uso compartido** y haga clic en **Uso compartido avanzado**.</span><span class="sxs-lookup"><span data-stu-id="a97d2-126">Select the **Sharing** tab, and click **Advanced Sharing**.</span></span>
    
4. <span data-ttu-id="a97d2-127">Haga clic en **Compartir esta carpeta**.</span><span class="sxs-lookup"><span data-stu-id="a97d2-127">Click **Share this folder**.</span></span>
    
5. <span data-ttu-id="a97d2-128">Haga clic en **Permisos**.</span><span class="sxs-lookup"><span data-stu-id="a97d2-128">Click **Permissions**.</span></span>
    
6. <span data-ttu-id="a97d2-129">Agregue el grupo **Administradores** local del servidor que aloja el recurso compartido de archivos, conceda derechos **Permitir: Control total, Cambiar y Leer** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a97d2-129">Add the local **Administrators** group of the server hosting the file share, grant **Allow: Full Control, Change, and Read** rights, and then click **OK**.</span></span>
    
7. <span data-ttu-id="a97d2-130">Haga clic en **Aceptar** nuevamente y tome nota de la ruta de acceso a la red.</span><span class="sxs-lookup"><span data-stu-id="a97d2-130">Click **OK** again and take note of the network path.</span></span>
    
8. <span data-ttu-id="a97d2-131">Haga clic en **Listo** para cerrar el asistente.</span><span class="sxs-lookup"><span data-stu-id="a97d2-131">Click **Done** to close the wizard.</span></span>
    
     ![Pestaña Uso compartido para compartir una carpeta.](../../media/78fe8441-dead-43ed-9a04-3c7c8c657c15.png)
  

