---
title: Administrar las opciones de archivado en Skype para Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 50399f26-58a3-4ce2-8229-32a8cafc7733
description: 'Resumen: Obtenga información sobre cómo configurar las opciones de archivado para Skype para Business Server.'
ms.openlocfilehash: db0fbe113f38065e85419b05d39fd0176b5ba845
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32232371"
---
# <a name="manage-archiving-options-in-skype-for-business-server"></a><span data-ttu-id="470f3-103">Administrar las opciones de archivado en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="470f3-103">Manage archiving options in Skype for Business Server</span></span>

<span data-ttu-id="470f3-104">**Resumen:** Obtenga información sobre cómo configurar las opciones de archivado para Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="470f3-104">**Summary:** Learn how to configure archiving options for Skype for Business Server.</span></span>
  
<span data-ttu-id="470f3-105">Configura inicialmente el archivado en la implementación, pero puede cambiar, agregar o eliminar la configuración tras la implementación.</span><span class="sxs-lookup"><span data-stu-id="470f3-105">You initially configure archiving at deployment, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="470f3-106">Las opciones de archivado determinan si:</span><span class="sxs-lookup"><span data-stu-id="470f3-106">Archiving options determine whether to:</span></span> 
  
- <span data-ttu-id="470f3-107">Habilitar o deshabilitar el archivado</span><span class="sxs-lookup"><span data-stu-id="470f3-107">Enable or disable archiving</span></span>
    
- <span data-ttu-id="470f3-108">Archivar sesiones de mensajería instantánea (MI)</span><span class="sxs-lookup"><span data-stu-id="470f3-108">Archive IM sessions</span></span>
    
- <span data-ttu-id="470f3-109">Archivar sesiones de conferencia web</span><span class="sxs-lookup"><span data-stu-id="470f3-109">Archive web conferencing sessions</span></span>
    
- <span data-ttu-id="470f3-110">Bloquear la actividad cuando el archivado no está disponible</span><span class="sxs-lookup"><span data-stu-id="470f3-110">Block activity when archiving is not available</span></span>
    
- <span data-ttu-id="470f3-111">Usar la integración de Exchange</span><span class="sxs-lookup"><span data-stu-id="470f3-111">Use Exchange integration</span></span>
    
- <span data-ttu-id="470f3-112">Configurar la purga y la exportación de datos</span><span class="sxs-lookup"><span data-stu-id="470f3-112">Set up purging and exporting of data</span></span>
    
<span data-ttu-id="470f3-113">Puede especificar las opciones de configuración en los siguientes niveles:</span><span class="sxs-lookup"><span data-stu-id="470f3-113">You can specify configuration options at the following levels:</span></span>
  
- <span data-ttu-id="470f3-114">Configuración de nivel global que se crea de forma predeterminada al implementar Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="470f3-114">Global-level configuration that is created by default when you deploy Skype for Business Server</span></span>
    
- <span data-ttu-id="470f3-115">En la configuración de sitio opcional, que especifica cómo se implementa el archivado para un sitio específico</span><span class="sxs-lookup"><span data-stu-id="470f3-115">Optional site-level configurations that specify how archiving is implemented for a specific site</span></span>
    
- <span data-ttu-id="470f3-116">Configuraciones opcionales de nivel de grupo de servidores que especifican cómo se implementa el archivado para un grupo de servidores específico</span><span class="sxs-lookup"><span data-stu-id="470f3-116">Optional pool-level configurations that specify how archiving is implemented for a specific pool</span></span>
    
<span data-ttu-id="470f3-117">Es posible eliminar una configuración de sitio o de grupo, pero no puede eliminar la configuración global.</span><span class="sxs-lookup"><span data-stu-id="470f3-117">You can delete a site configuration or pool configuration, but you cannot delete the global configuration.</span></span> <span data-ttu-id="470f3-118">Si elimina la configuración global, esta se restablece automáticamente a sus valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="470f3-118">If you delete the global configuration, it is automatically reset to the default values.</span></span> <span data-ttu-id="470f3-119">Para obtener información detallada acerca de cómo se implementan las configuraciones de archivado y la jerarquía de directivas, consulte [Plan para el archivado en Skype para Business Server](../../plan-your-deployment/archiving/archiving.md).</span><span class="sxs-lookup"><span data-stu-id="470f3-119">For details about how archiving configurations are implemented and the hierarchy of archiving configurations, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).</span></span>
  
## <a name="configure-archiving-options-by-using-the-control-panel"></a><span data-ttu-id="470f3-120">Configurar las opciones de archivado con el Panel de control</span><span class="sxs-lookup"><span data-stu-id="470f3-120">Configure archiving options by using the Control Panel</span></span>

<span data-ttu-id="470f3-121">Puede configurar las opciones de archivado con el Panel de control de esta manera:</span><span class="sxs-lookup"><span data-stu-id="470f3-121">You can configure archiving options by using the Control Panel as follows:</span></span>
  
1. <span data-ttu-id="470f3-122">Desde una cuenta de usuario que se asigne al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="470f3-122">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="470f3-123">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="470f3-123">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="470f3-124">En la barra de navegación izquierda, haga clic en **Configuración de archivado**.</span><span class="sxs-lookup"><span data-stu-id="470f3-124">In the left navigation bar, click **Archiving Configuration**.</span></span>
    
## <a name="configure-archiving-options-by-using-windows-powershell"></a><span data-ttu-id="470f3-125">Configurar las opciones de archivado con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="470f3-125">Configure archiving options by using Windows PowerShell</span></span>

<span data-ttu-id="470f3-126">También puede configurar las opciones de archivado con los cmdlets de Windows PowerShell que se enumeran en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="470f3-126">You can also configure archiving options by using the Windows PowerShell cmdlets listed in the following table.</span></span> <span data-ttu-id="470f3-127">Para obtener información detallada sobre la sintaxis, incluidos todos los parámetros disponibles, vea [Skype para Shell de administración de servidor empresarial](../management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="470f3-127">For details about syntax, including all available parameters, see [Skype for Business Server Management Shell](../management-shell.md).</span></span>
  

|<span data-ttu-id="470f3-128">**Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="470f3-128">**Cmdlet**</span></span>|<span data-ttu-id="470f3-129">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="470f3-129">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="470f3-130">Get-CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="470f3-130">Get-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="470f3-131">Devuelve información sobre las opciones de configuración de archivado en la organización.</span><span class="sxs-lookup"><span data-stu-id="470f3-131">Returns information about the archiving configuration settings in your organization.</span></span>  <br/> |
|<span data-ttu-id="470f3-132">New-CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="470f3-132">New-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="470f3-133">Crea un nuevo conjunto de configuraciones de mensajería instantánea (MI) que se pueden usar para habilitar o deshabilitar el guardado automático de las sesiones de mensajería instantánea (MI) y para bloquear todos los mensajes instantáneos que no se pueden archivar.</span><span class="sxs-lookup"><span data-stu-id="470f3-133">Creates a new set of instant messaging (IM) settings, which can be used to enable or disable the automatic saving of IM sessions, and to block any instant messages that cannot be archived.</span></span>  <br/> |
|<span data-ttu-id="470f3-134">Remove-CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="470f3-134">Remove-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="470f3-135">Quita la recopilación especificada de la configuración del archivado que se usa para habilitar o deshabilitar el guardado automático de las sesiones de mensajería instantánea (MI), así como para bloquear de forma opcional todos los mensajes instantáneos que no se pueden archivar.</span><span class="sxs-lookup"><span data-stu-id="470f3-135">Removes the specified collection of archiving settings that are used to enable or disable the automatic saving of instant messaging (IM) sessions, and to optionally block any instant message that cannot be archived.</span></span>  <br/> |
|<span data-ttu-id="470f3-136">Set-CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="470f3-136">Set-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="470f3-137">Modifica una recopilación existente de opciones de configuración de archivado de mensajería instantánea (MI).</span><span class="sxs-lookup"><span data-stu-id="470f3-137">Modifies an existing collection of instant messaging (IM) archiving configuration options.</span></span>  <br/> |
