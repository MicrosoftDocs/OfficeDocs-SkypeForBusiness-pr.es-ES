---
title: Configurar las opciones de archivado para controlar los errores en Skype para Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 31fd4e7c-3c68-48dd-9fad-8863831accd7
description: 'Resumen: Obtenga información sobre cómo bloquear sesiones de mensajería instantánea y conferencias en el caso de un Skype para errores del servidor de negocio que podrían impedir el archivado.'
ms.openlocfilehash: 4fe63319f2b480557c73e238f2b19692df06440f
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30883021"
---
# <a name="configure-archiving-options-to-handle-failures-in-skype-for-business-server"></a><span data-ttu-id="f5154-103">Configurar las opciones de archivado para controlar los errores en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="f5154-103">Configure archiving options to handle failures in Skype for Business Server</span></span>

<span data-ttu-id="f5154-104">**Resumen:** Obtenga información sobre cómo bloquear sesiones de mensajería instantánea y conferencias en el caso de un Skype para errores del servidor de negocio que podrían impedir el archivado.</span><span class="sxs-lookup"><span data-stu-id="f5154-104">**Summary:** Learn how to block IM and conferencing sessions in the case of a Skype for Business Server failure that would prevent archiving.</span></span>
  
<span data-ttu-id="f5154-105">Si el archivado es un requisito para su organización, puede bloquear las sesiones de mensajería instantánea y conferencias en el caso de un Skype para errores del servidor de negocio que podrían impedir el archivado.</span><span class="sxs-lookup"><span data-stu-id="f5154-105">If archiving is a requirement for your organization, you can block IM and conferencing sessions in the event of a Skype for Business Server failure that would prevent archiving.</span></span> <span data-ttu-id="f5154-106">A veces se denomina modo crítico.</span><span class="sxs-lookup"><span data-stu-id="f5154-106">This is sometimes called critical mode.</span></span> <span data-ttu-id="f5154-107">Por ejemplo, si existe un problema con un servicio de almacenamiento, la mensajería instantánea se bloquearía para los usuarios cuyas comunicaciones están habilitadas para el archivado.</span><span class="sxs-lookup"><span data-stu-id="f5154-107">For example, if there is a problem with a storage service, IM would be blocked for users whose communications are enabled for archiving.</span></span> <span data-ttu-id="f5154-108">Tanto la mensajería instantánea como las conferencias se recuperan automáticamente después de que se corrijan los errores.</span><span class="sxs-lookup"><span data-stu-id="f5154-108">Both IM and conferencing automatically recover after the failures are corrected.</span></span> 
  
## <a name="configure-critical-mode-by-using-the-control-panel"></a><span data-ttu-id="f5154-109">Configurar el modo crítico con el Panel de control</span><span class="sxs-lookup"><span data-stu-id="f5154-109">Configure critical mode by using the Control Panel</span></span>

<span data-ttu-id="f5154-110">Para especificar si las sesiones de comunicación se tienen que permitir en caso de un error que no permita el archivado:</span><span class="sxs-lookup"><span data-stu-id="f5154-110">To specify whether communication sessions should be allowed in case of a failure that would prevent archiving:</span></span>
  
1. <span data-ttu-id="f5154-111">Desde una cuenta de usuario que se asigne al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="f5154-111">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="f5154-112">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="f5154-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="f5154-113">En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y, después, en **Configuración de archivado**.</span><span class="sxs-lookup"><span data-stu-id="f5154-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="f5154-114">Haga clic en el nombre de la configuración global, de sitio o de grupo de servidores adecuada en la lista de configuraciones de archivado, haga clic en **Editar** y luego haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="f5154-114">Click the name of the appropriate global, site, or pool configuration in the list of archiving configurations, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="f5154-115">Para configurar el comportamiento del archivado cuando se produzca un error, active o desactive la casilla **Bloquear sesiones de mensajería instantánea o conferencias web si no se pueden archivar**.</span><span class="sxs-lookup"><span data-stu-id="f5154-115">To set how archiving behaves when a failure occurs, select or clear the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
6. <span data-ttu-id="f5154-116">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="f5154-116">Click **Commit**.</span></span>
    
## <a name="configure-critical-mode-by-using-windows-powershell"></a><span data-ttu-id="f5154-117">Configurar el modo crítico con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f5154-117">Configure critical mode by using Windows PowerShell</span></span>

<span data-ttu-id="f5154-118">También puede especificar si se deben permitir las sesiones de comunicación en caso de un fallo que podría impedir el archivado mediante el cmdlet **Set-CsArchivingConfiguration** con el parámetro BlockOnArchiveFailure.</span><span class="sxs-lookup"><span data-stu-id="f5154-118">You can also specify whether communication sessions should be allowed in case of a failure that would prevent archiving by using the **Set-CsArchivingConfiguration** cmdlet with the BlockOnArchiveFailure parameter.</span></span>
  
<span data-ttu-id="f5154-119">Por ejemplo, el siguiente comando deshabilita la comunicación en el caso de un error de archivado:</span><span class="sxs-lookup"><span data-stu-id="f5154-119">For example, the following command disables communications in the case of an archiving failure:</span></span>
  
```
Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $True
```

<span data-ttu-id="f5154-120">El siguiente comando habilita las comunicaciones en caso de un error de archivado:</span><span class="sxs-lookup"><span data-stu-id="f5154-120">The next command enables communications in the case of an archiving failure:</span></span>
  
```
Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $False
```

<span data-ttu-id="f5154-121">Para obtener más información, vea el tema de ayuda para el cmdlet [Set-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csarchivingconfiguration?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="f5154-121">For more information, see the Help topic for the [Set-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csarchivingconfiguration?view=skype-ps) cmdlet.</span></span>
  

