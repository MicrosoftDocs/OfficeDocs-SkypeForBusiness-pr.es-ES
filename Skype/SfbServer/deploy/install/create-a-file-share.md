---
title: Crear un recurso compartido de archivos en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 'Resumen: obtenga información sobre cómo crear un recurso compartido de archivos de Windows Server como parte de la instalación de Skype Empresarial Server. Descargue una prueba gratuita de Skype Empresarial Server desde el Centro de evaluación de Microsoft en: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server .'
ms.openlocfilehash: 63ed4c54154698336bea7adb87db4e81d5fd35b4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812240"
---
# <a name="create-a-file-share-in-skype-for-business-server"></a><span data-ttu-id="12b52-104">Crear un recurso compartido de archivos en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="12b52-104">Create a file share in Skype for Business Server</span></span>
 
<span data-ttu-id="12b52-105">**Resumen:** Obtenga información sobre cómo crear un recurso compartido de archivos de Windows Server como parte de la instalación de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="12b52-105">**Summary:** Learn how to create a Windows Server file share as part of the installation of Skype for Business Server.</span></span> <span data-ttu-id="12b52-106">Descargue una prueba gratuita de Skype Empresarial Server desde el Centro de evaluación de Microsoft en: [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server) .</span><span class="sxs-lookup"><span data-stu-id="12b52-106">Download a free trial of Skype for Business Server from the Microsoft Evaluation center at:[https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="12b52-107">Skype Empresarial Server requiere un recurso compartido de archivos para que los equipos de toda la topología puedan intercambiar archivos.</span><span class="sxs-lookup"><span data-stu-id="12b52-107">Skype for Business Server requires a file share so that computers throughout the topology can exchange files.</span></span> <span data-ttu-id="12b52-108">La creación de un recurso compartido de archivos es el paso 2 de 8 en el proceso de instalación de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="12b52-108">Creating a file share is step 2 of 8 in the installation process for Skype for Business Server.</span></span> <span data-ttu-id="12b52-109">Puede realizar los pasos del 1 al 5 en cualquier orden.</span><span class="sxs-lookup"><span data-stu-id="12b52-109">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="12b52-110">Sin embargo, debe realizar los pasos 6, 7 y 8 en orden y después de los pasos del 1 al 5, tal como se indica en el diagrama.</span><span class="sxs-lookup"><span data-stu-id="12b52-110">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5 as outlined in the diagram.</span></span> <span data-ttu-id="12b52-111">Para obtener más información sobre la planeación del recurso compartido de archivos, consulte Requisitos del entorno [para Skype Empresarial Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) o requisitos de servidor para Skype Empresarial Server [2019.](../../../SfBServer2019/plan/system-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="12b52-111">For planning details about file share, see [Environmental requirements for Skype for Business Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) or [Server requirements for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).</span></span>
  
![Diagrama de información general](../../media/e69de059-3040-45ab-9379-1932f9fbb37f.png)
  
## <a name="create-a-basic-file-share"></a><span data-ttu-id="12b52-113">Crear un recurso compartido de archivos básico</span><span class="sxs-lookup"><span data-stu-id="12b52-113">Create a basic file share</span></span>

<span data-ttu-id="12b52-114">Esta sección te guiará a través de la creación de un recurso compartido de archivos básico de Windows Server.</span><span class="sxs-lookup"><span data-stu-id="12b52-114">This section walks you through creating a basic Windows Server file share.</span></span> <span data-ttu-id="12b52-115">Skype Empresarial Server admite un recurso compartido de archivos básico de Windows Server.</span><span class="sxs-lookup"><span data-stu-id="12b52-115">A basic Windows Server file share is supported with Skype for Business Server.</span></span> <span data-ttu-id="12b52-116">Sin embargo, no proporciona explícitamente alta disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="12b52-116">However, it does not explicitly provide high availability.</span></span> <span data-ttu-id="12b52-117">Para un entorno de alta disponibilidad, se recomienda un recurso compartido de archivos del Sistema de archivos distribuido (DFS).</span><span class="sxs-lookup"><span data-stu-id="12b52-117">For a high availability environment, a Distributed File System (DFS) file share is recommended.</span></span> <span data-ttu-id="12b52-118">Para obtener más información acerca de un recurso compartido de archivos de alta disponibilidad y DFS, consulte [Plan for high availability and disaster recovery in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="12b52-118">For more information about a high availability file share and DFS, see [Plan for high availability and disaster recovery in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="12b52-119">Windows Server 2012 R2 ha realizado importantes avances al proporcionar soluciones de recursos compartidos de archivos como la Red de área de almacenamiento (SAN) con la plataforma Windows Server.</span><span class="sxs-lookup"><span data-stu-id="12b52-119">Windows Server 2012 R2 has made major leaps in providing Storage Area Network (SAN)-like file share solutions using the Windows Server platform.</span></span> <span data-ttu-id="12b52-120">En comparación con un dispositivo tradicional basado en SAN, una solución de almacenamiento de Windows Server 2012 R2 puede reducir los costos a la mitad con un impacto muy mínimo en el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="12b52-120">When compared to a traditional SAN-based appliance, a Windows Server 2012 R2 storage solution can cut costs in half with very minimal impact to performance.</span></span> <span data-ttu-id="12b52-121">Para obtener más información acerca de las opciones de recurso compartido de archivos en Windows Server 2012 R2, vea las white paper descargables de Almacenamiento de [Windows Server 2012 R2.](https://download.microsoft.com/download/9/4/A/94A15682-02D6-47AD-B209-79D6E2758A24/Windows_Server_2012_R2_Storage_White_Paper.pdf)</span><span class="sxs-lookup"><span data-stu-id="12b52-121">For more information about file share options in Windows Server 2012 R2, see the downloadable white paper [Windows Server 2012 R2 Storage](https://download.microsoft.com/download/9/4/A/94A15682-02D6-47AD-B209-79D6E2758A24/Windows_Server_2012_R2_Storage_White_Paper.pdf).</span></span> 
  
<span data-ttu-id="12b52-122">Vea los pasos de vídeo para **crear un recurso compartido de archivos:**</span><span class="sxs-lookup"><span data-stu-id="12b52-122">Watch the video steps for **create a file share**:</span></span>
  
> [!video https://www.microsoft.com/videoplayer/embed/dbef31be-e899-4a32-a1ca-370053284f56?autoplay=false]
  
### <a name="create-a-basic-file-share"></a><span data-ttu-id="12b52-123">Crear un recurso compartido de archivos básico</span><span class="sxs-lookup"><span data-stu-id="12b52-123">Create a basic file share</span></span>

1. <span data-ttu-id="12b52-124">Inicie sesión en el equipo que hospedará el recurso compartido de archivos.</span><span class="sxs-lookup"><span data-stu-id="12b52-124">Log on to the computer that will host the file share.</span></span>
    
2. <span data-ttu-id="12b52-125">Haga clic con el botón secundario en la carpeta que desea compartir y seleccione **Propiedades.**</span><span class="sxs-lookup"><span data-stu-id="12b52-125">Right-click the folder you plan to share, and select **Properties**.</span></span>
    
3. <span data-ttu-id="12b52-126">Seleccione la **pestaña Uso** compartido y haga clic en Uso **compartido avanzado.**</span><span class="sxs-lookup"><span data-stu-id="12b52-126">Select the **Sharing** tab, and click **Advanced Sharing**.</span></span>
    
4. <span data-ttu-id="12b52-127">Haga **clic en Compartir esta carpeta.**</span><span class="sxs-lookup"><span data-stu-id="12b52-127">Click **Share this folder**.</span></span>
    
5. <span data-ttu-id="12b52-128">Haga clic en **Permisos**.</span><span class="sxs-lookup"><span data-stu-id="12b52-128">Click **Permissions**.</span></span>
    
6. <span data-ttu-id="12b52-129">Agregue el grupo **de administradores** locales del servidor que hospeda el recurso compartido de archivos, conceda los derechos **Permitir: Control total,** Cambiar y Leer y, a continuación, haga clic en **Aceptar.**</span><span class="sxs-lookup"><span data-stu-id="12b52-129">Add the local **Administrators** group of the server hosting the file share, grant **Allow: Full Control, Change, and Read** rights, and then click **OK**.</span></span>
    
7. <span data-ttu-id="12b52-130">Vuelva **a hacer clic** en Aceptar y tome nota de la ruta de red.</span><span class="sxs-lookup"><span data-stu-id="12b52-130">Click **OK** again and take note of the network path.</span></span>
    
8. <span data-ttu-id="12b52-131">Haga **clic en Listo** para cerrar el asistente.</span><span class="sxs-lookup"><span data-stu-id="12b52-131">Click **Done** to close the wizard.</span></span>
    
     ![Pestaña De uso compartido para compartir una carpeta.](../../media/78fe8441-dead-43ed-9a04-3c7c8c657c15.png)
  
> [!NOTE]
><span data-ttu-id="12b52-133">Si el almacén de archivos está hospedado en un recurso compartido DFS, se recibirá la siguiente advertencia:</span><span class="sxs-lookup"><span data-stu-id="12b52-133">If the file store is hosted on a DFS share, the following warning will be received:</span></span>

<span data-ttu-id="12b52-134">Advertencia: no se puede tener acceso a los permisos de uso compartido para " \\ <domain> \<share> ".</span><span class="sxs-lookup"><span data-stu-id="12b52-134">Warning: Unable to access share permissions for "\\<domain>\<share>".</span></span>

><span data-ttu-id="12b52-135">Esto se espera si no es un administrador en el servidor de archivos o si se trata de un recurso compartido del Sistema de archivos distribuido (DFS).</span><span class="sxs-lookup"><span data-stu-id="12b52-135">This is expected if you are not an administrator on the file server, or if this is a Distributed File System (DFS) share.</span></span> <span data-ttu-id="12b52-136">Si los permisos de recurso compartido ya se han configurado, esta advertencia puede omitirse.</span><span class="sxs-lookup"><span data-stu-id="12b52-136">If the share permissions have already been configured, this warning can be ignored.</span></span> <span data-ttu-id="12b52-137">Si es un recurso compartido nuevo, consulte la documentación para obtener más información sobre cómo configurar manualmente los permisos de recurso compartido.</span><span class="sxs-lookup"><span data-stu-id="12b52-137">If it is a new share, refer to the documentation for details on manually configuring share permissions.</span></span>

><span data-ttu-id="12b52-138">Debido a la incapacidad de acceder a los permisos de recurso compartido en un recurso compartido DFS, Skype Empresarial Server no podrá establecer grupos explícitamente en el recurso compartido de archivos.</span><span class="sxs-lookup"><span data-stu-id="12b52-138">Due to the inability to access the share permissions on a DFS share, Skype for Business Server will not be able to explicitly set groups on the file share.</span></span> <span data-ttu-id="12b52-139">Para asegurarse de que los componentes de Skype Empresarial Server puedan tener acceso al recurso compartido de archivos con los permisos adecuados, asegúrese de que se agregan los siguientes grupos RTC con permisos de recurso compartido de nivel de lectura y cambio, además de los permisos de recurso compartido administradores locales con control total.</span><span class="sxs-lookup"><span data-stu-id="12b52-139">To ensure Skype for Business Server components can access the file share with the appropriate permissions, ensure the following RTC groups are added with Read and Change level share permissions in addition to the local Administrators with Full Control share permissions.</span></span>
* <span data-ttu-id="12b52-140">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="12b52-140">RTCHSUniversalServices</span></span>
* <span data-ttu-id="12b52-141">RTCComponentUniversalServices</span><span class="sxs-lookup"><span data-stu-id="12b52-141">RTCComponentUniversalServices</span></span>
* <span data-ttu-id="12b52-142">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="12b52-142">RTCUniversalServerAdmins</span></span>
