---
title: Administrar las opciones de archivado en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 50399f26-58a3-4ce2-8229-32a8cafc7733
description: 'Resumen: obtenga información sobre cómo configurar las opciones de archivado para Skype Empresarial Server.'
ms.openlocfilehash: ee0145ac0896e1bbb8d18c6a51116f2ddd75ee05
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817540"
---
# <a name="manage-archiving-options-in-skype-for-business-server"></a><span data-ttu-id="8b57e-103">Administrar las opciones de archivado en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="8b57e-103">Manage archiving options in Skype for Business Server</span></span>

<span data-ttu-id="8b57e-104">**Resumen:** Obtenga información sobre cómo configurar las opciones de archivado para Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="8b57e-104">**Summary:** Learn how to configure archiving options for Skype for Business Server.</span></span>
  
<span data-ttu-id="8b57e-105">Inicialmente, configure el archivado en la implementación, pero puede cambiar, agregar y eliminar configuraciones después de la implementación.</span><span class="sxs-lookup"><span data-stu-id="8b57e-105">You initially configure archiving at deployment, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="8b57e-106">Las opciones de archivado determinan si:</span><span class="sxs-lookup"><span data-stu-id="8b57e-106">Archiving options determine whether to:</span></span> 
  
- <span data-ttu-id="8b57e-107">Habilitar o deshabilitar el archivado</span><span class="sxs-lookup"><span data-stu-id="8b57e-107">Enable or disable archiving</span></span>
    
- <span data-ttu-id="8b57e-108">Archivar sesiones de mensajería instantánea</span><span class="sxs-lookup"><span data-stu-id="8b57e-108">Archive IM sessions</span></span>
    
- <span data-ttu-id="8b57e-109">Archivar sesiones de conferencia web</span><span class="sxs-lookup"><span data-stu-id="8b57e-109">Archive web conferencing sessions</span></span>
    
- <span data-ttu-id="8b57e-110">Bloquear la actividad cuando el archivado no está disponible</span><span class="sxs-lookup"><span data-stu-id="8b57e-110">Block activity when archiving is not available</span></span>
    
- <span data-ttu-id="8b57e-111">Usar la integración de Exchange</span><span class="sxs-lookup"><span data-stu-id="8b57e-111">Use Exchange integration</span></span>
    
- <span data-ttu-id="8b57e-112">Configurar la depuración y exportación de datos</span><span class="sxs-lookup"><span data-stu-id="8b57e-112">Set up purging and exporting of data</span></span>
    
<span data-ttu-id="8b57e-113">Puede especificar opciones de configuración en los siguientes niveles:</span><span class="sxs-lookup"><span data-stu-id="8b57e-113">You can specify configuration options at the following levels:</span></span>
  
- <span data-ttu-id="8b57e-114">Configuración de nivel global que se crea de forma predeterminada al implementar Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="8b57e-114">Global-level configuration that is created by default when you deploy Skype for Business Server</span></span>
    
- <span data-ttu-id="8b57e-115">Configuraciones de nivel de sitio opcionales que especifican cómo se implementa el archivado para un sitio específico</span><span class="sxs-lookup"><span data-stu-id="8b57e-115">Optional site-level configurations that specify how archiving is implemented for a specific site</span></span>
    
- <span data-ttu-id="8b57e-116">Configuraciones opcionales de nivel de grupo que especifican cómo se implementa el archivado para un grupo específico</span><span class="sxs-lookup"><span data-stu-id="8b57e-116">Optional pool-level configurations that specify how archiving is implemented for a specific pool</span></span>
    
<span data-ttu-id="8b57e-117">Puede eliminar una configuración de sitio o de grupo, pero no puede eliminar la configuración global.</span><span class="sxs-lookup"><span data-stu-id="8b57e-117">You can delete a site configuration or pool configuration, but you cannot delete the global configuration.</span></span> <span data-ttu-id="8b57e-118">Si elimina la configuración global, esta se restablece automáticamente a los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="8b57e-118">If you delete the global configuration, it is automatically reset to the default values.</span></span> <span data-ttu-id="8b57e-119">Para obtener más información sobre cómo se implementan las configuraciones de archivado y la jerarquía de las configuraciones de archivado, consulte [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).</span><span class="sxs-lookup"><span data-stu-id="8b57e-119">For details about how archiving configurations are implemented and the hierarchy of archiving configurations, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).</span></span>
  
## <a name="configure-archiving-options-by-using-the-control-panel"></a><span data-ttu-id="8b57e-120">Configurar las opciones de archivado mediante el Panel de control</span><span class="sxs-lookup"><span data-stu-id="8b57e-120">Configure archiving options by using the Control Panel</span></span>

<span data-ttu-id="8b57e-121">Puede configurar las opciones de archivado mediante el Panel de control de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="8b57e-121">You can configure archiving options by using the Control Panel as follows:</span></span>
  
1. <span data-ttu-id="8b57e-122">Desde una cuenta de usuario asignada al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="8b57e-122">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="8b57e-123">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="8b57e-123">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="8b57e-124">En la barra de navegación izquierda, haga clic en **Configuración de archivado.**</span><span class="sxs-lookup"><span data-stu-id="8b57e-124">In the left navigation bar, click **Archiving Configuration**.</span></span>
    
## <a name="configure-archiving-options-by-using-windows-powershell"></a><span data-ttu-id="8b57e-125">Configure las opciones de archivado mediante Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8b57e-125">Configure archiving options by using Windows PowerShell</span></span>

<span data-ttu-id="8b57e-126">También puede configurar las opciones de archivado mediante los cmdlets Windows PowerShell que se enumeran en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="8b57e-126">You can also configure archiving options by using the Windows PowerShell cmdlets listed in the following table.</span></span> <span data-ttu-id="8b57e-127">Para obtener más información sobre la sintaxis, incluidos todos los parámetros disponibles, consulte Shell de administración [de Skype Empresarial Server.](../management-shell.md)</span><span class="sxs-lookup"><span data-stu-id="8b57e-127">For details about syntax, including all available parameters, see [Skype for Business Server Management Shell](../management-shell.md).</span></span>
  

|<span data-ttu-id="8b57e-128">**Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="8b57e-128">**Cmdlet**</span></span>|<span data-ttu-id="8b57e-129">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="8b57e-129">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8b57e-130">Get-CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="8b57e-130">Get-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="8b57e-131">Devuelve información sobre las opciones de configuración de archivado de la organización.</span><span class="sxs-lookup"><span data-stu-id="8b57e-131">Returns information about the archiving configuration settings in your organization.</span></span>  <br/> |
|<span data-ttu-id="8b57e-132">New-CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="8b57e-132">New-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="8b57e-133">Crea un nuevo conjunto de configuraciones de mensajería instantánea (MI), que se pueden usar para habilitar o deshabilitar el almacenamiento automático de sesiones de mensajería instantánea y para bloquear los mensajes instantáneos que no se pueden archivar.</span><span class="sxs-lookup"><span data-stu-id="8b57e-133">Creates a new set of instant messaging (IM) settings, which can be used to enable or disable the automatic saving of IM sessions, and to block any instant messages that cannot be archived.</span></span>  <br/> |
|<span data-ttu-id="8b57e-134">Remove-CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="8b57e-134">Remove-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="8b57e-135">Quita la colección especificada de opciones de archivado que se usan para habilitar o deshabilitar el almacenamiento automático de sesiones de mensajería instantánea (MI) y, opcionalmente, para bloquear cualquier mensaje instantáneo que no se pueda archivar.</span><span class="sxs-lookup"><span data-stu-id="8b57e-135">Removes the specified collection of archiving settings that are used to enable or disable the automatic saving of instant messaging (IM) sessions, and to optionally block any instant message that cannot be archived.</span></span>  <br/> |
|<span data-ttu-id="8b57e-136">Set-CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="8b57e-136">Set-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="8b57e-137">Modifica una colección existente de opciones de configuración de archivado de mensajería instantánea (MI).</span><span class="sxs-lookup"><span data-stu-id="8b57e-137">Modifies an existing collection of instant messaging (IM) archiving configuration options.</span></span>  <br/> |
