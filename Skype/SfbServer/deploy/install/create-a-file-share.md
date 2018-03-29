---
title: Crear un recurso compartido de archivos en Skype Empresarial Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 053076b0-441c-44d9-8dbc-7a36d8ecafe4
description: 'Resumen: Conozca cómo crear un recurso compartido de archivos de Windows Server como parte de la instalación de Skype para Business Server 2015. Descargue una prueba gratuita de Skype para Business Server 2015 desde el centro de Evaluation de Microsoft en: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server.'
ms.openlocfilehash: 697325cbe7616ca82734895e1af4922aeb580068
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="create-a-file-share-in-skype-for-business-server-2015"></a><span data-ttu-id="8c875-104">Crear un recurso compartido de archivos en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="8c875-104">Create a file share in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="8c875-105">**Resumen:** Aprenda a crear un recurso compartido de archivos de Windows Server como parte de la instalación de Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="8c875-105">**Summary:** Learn how to create a Windows Server file share as part of the installation of Skype for Business Server 2015.</span></span> <span data-ttu-id="8c875-106">Descargue una prueba gratuita de Skype para Business Server 2015 desde el centro de Evaluation de Microsoft en:[https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span><span class="sxs-lookup"><span data-stu-id="8c875-106">Download a free trial of Skype for Business Server 2015 from the Microsoft Evaluation center at:[https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="8c875-107">Skype para Business Server requiere un recurso compartido de archivos para que los equipos de toda la topología pueden intercambiar archivos.</span><span class="sxs-lookup"><span data-stu-id="8c875-107">Skype for Business Server requires a file share so that computers throughout the topology can exchange files.</span></span> <span data-ttu-id="8c875-108">Crear un recurso compartido de archivo es el paso 2 de 8 en el proceso de instalación de Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="8c875-108">Creating a file share is step 2 of 8 in the installation process for Skype for Business Server 2015.</span></span> <span data-ttu-id="8c875-109">Puede realizar los pasos 1 a 5 en cualquier orden.</span><span class="sxs-lookup"><span data-stu-id="8c875-109">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="8c875-110">Sin embargo, debe realizar los pasos 6, 7 y 8 en orden y después los pasos del 1 al 5 como se indica en el diagrama.</span><span class="sxs-lookup"><span data-stu-id="8c875-110">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5 as outlined in the diagram.</span></span> <span data-ttu-id="8c875-111">Para planear los detalles sobre el recurso compartido de archivos, consulte [los requisitos ambientales para Skype para Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8c875-111">For planning details about file share, see [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md).</span></span>
  
![Diagrama de información general](../../media/e69de059-3040-45ab-9379-1932f9fbb37f.png)
  
## <a name="create-a-basic-file-share"></a><span data-ttu-id="8c875-113">Crear un recurso compartido de archivos básico</span><span class="sxs-lookup"><span data-stu-id="8c875-113">Create a basic file share</span></span>

<span data-ttu-id="8c875-114">Esta sección le guiará a través de la creación de un archivo compartido básico de Windows Server.</span><span class="sxs-lookup"><span data-stu-id="8c875-114">This section walks you through creating a basic Windows Server file share.</span></span> <span data-ttu-id="8c875-115">Un archivo compartido básico de Windows Server es compatible con Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="8c875-115">A basic Windows Server file share is supported with Skype for Business Server.</span></span> <span data-ttu-id="8c875-116">Sin embargo, no explícitamente proporciona alta disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="8c875-116">However, it does not explicitly provide high availability.</span></span> <span data-ttu-id="8c875-117">Para un entorno de alta disponibilidad, se recomienda un recurso compartido de archivos de sistema de archivos distribuido (DFS).</span><span class="sxs-lookup"><span data-stu-id="8c875-117">For a high availability environment, a Distributed File System (DFS) file share is recommended.</span></span> <span data-ttu-id="8c875-118">Para obtener más información acerca de un recurso compartido de archivos de alta disponibilidad y DFS, vea [Planear la alta disponibilidad y recuperación ante desastres en Skype para Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="8c875-118">For more information about a high availability file share and DFS, see [Plan for high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="8c875-119">Se han realizado importantes avances en Windows Server 2012 R2 a fin de proporcionar soluciones de recursos compartidos de archivos similares a la red de área de almacenamiento (SAN) con la plataforma de Windows Server.</span><span class="sxs-lookup"><span data-stu-id="8c875-119">Windows Server 2012 R2 has made major leaps in providing Storage Area Network (SAN)-like file share solutions using the Windows Server platform.</span></span> <span data-ttu-id="8c875-120">Cuando se la compara con un dispositivo basado en SAN tradicional, una solución de almacenamiento de Windows Server 2012 R2 puede reducir los costes a la mitad con un impacto muy mínimo en el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="8c875-120">When compared to a traditional SAN-based appliance, a Windows Server 2012 R2 storage solution can cut costs in half with very minimal impact to performance.</span></span> <span data-ttu-id="8c875-121">Para obtener más información acerca de las opciones de recurso compartido de archivo en Windows Server 2012 R2, consulte el documento descargable [Almacenamiento de R2 de Windows Server 2012](https://download.microsoft.com/download/9/4/A/94A15682-02D6-47AD-B209-79D6E2758A24/Windows_Server_2012_R2_Storage_White_Paper.pdf).</span><span class="sxs-lookup"><span data-stu-id="8c875-121">For more information about file share options in Windows Server 2012 R2, see the downloadable white paper [Windows Server 2012 R2 Storage](https://download.microsoft.com/download/9/4/A/94A15682-02D6-47AD-B209-79D6E2758A24/Windows_Server_2012_R2_Storage_White_Paper.pdf).</span></span> 
  
<span data-ttu-id="8c875-122">Vea los pasos del vídeo para **crear un recurso compartido de archivos**:</span><span class="sxs-lookup"><span data-stu-id="8c875-122">Watch the video steps for **create a file share**:</span></span>
  
![Su explorador no admite vídeo. Instale Microsoft Silverlight, Adobe Flash Player o Internet Explorer 9.](../../media/MSN_Video_Widget.gif)
  
### <a name="create-a-basic-file-share"></a><span data-ttu-id="8c875-125">Crear un recurso compartido de archivos básico</span><span class="sxs-lookup"><span data-stu-id="8c875-125">Create a basic file share</span></span>

1. <span data-ttu-id="8c875-126">Inicie sesión en el equipo que hospedará el recurso compartido de archivos.</span><span class="sxs-lookup"><span data-stu-id="8c875-126">Log on to the computer that will host the file share.</span></span>
    
2. <span data-ttu-id="8c875-127">Haga clic con el botón secundario en la carpeta que desea compartir y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="8c875-127">Right-click the folder you plan to share, and select **Properties**.</span></span>
    
3. <span data-ttu-id="8c875-128">Seleccione la pestaña **Uso compartido** y haga clic en **Uso compartido avanzado**.</span><span class="sxs-lookup"><span data-stu-id="8c875-128">Select the **Sharing** tab, and click **Advanced Sharing**.</span></span>
    
4. <span data-ttu-id="8c875-129">Haga clic en **Compartir esta carpeta**.</span><span class="sxs-lookup"><span data-stu-id="8c875-129">Click **Share this folder**.</span></span>
    
5. <span data-ttu-id="8c875-130">Haga clic en **Permisos**.</span><span class="sxs-lookup"><span data-stu-id="8c875-130">Click **Permissions**.</span></span>
    
6. <span data-ttu-id="8c875-131">Agregue el grupo **Administradores** local del servidor que aloja el recurso compartido de archivos, conceda derechos **Permitir: Control total, Cambiar y Leer** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="8c875-131">Add the local **Administrators** group of the server hosting the file share, grant **Allow: Full Control, Change, and Read** rights, and then click **OK**.</span></span>
    
7. <span data-ttu-id="8c875-132">Haga clic en **Aceptar** nuevamente y tome nota de la ruta de acceso a la red.</span><span class="sxs-lookup"><span data-stu-id="8c875-132">Click **OK** again and take note of the network path.</span></span>
    
8. <span data-ttu-id="8c875-133">Haga clic en **Listo** para cerrar el asistente.</span><span class="sxs-lookup"><span data-stu-id="8c875-133">Click **Done** to close the wizard.</span></span>
    
     ![Pestaña Uso compartido para compartir una carpeta.](../../media/78fe8441-dead-43ed-9a04-3c7c8c657c15.png)
  

