---
title: Configurar las opciones de archivado para gestionar las fallas en Skype Empresarial Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 31fd4e7c-3c68-48dd-9fad-8863831accd7
description: 'Resumen: Conozca cómo bloquear sesiones de mensajería instantánea y conferencias en el caso de un Skype Error 2015 de servidor empresariales que impedirían que el archiving.'
ms.openlocfilehash: 4ad6b8eb496555751aab31949aa3e710749e0262
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="configure-archiving-options-to-handle-failures-in-skype-for-business-server-2015"></a><span data-ttu-id="29db0-103">Configurar las opciones de archivado para gestionar las fallas en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="29db0-103">Configure archiving options to handle failures in Skype for Business Server 2015</span></span>

<span data-ttu-id="29db0-104">**Resumen:** Obtenga información sobre cómo bloquear sesiones de mensajería instantánea y conferencias en el caso de un Skype Error 2015 de servidor empresariales que impedirían que el archiving.</span><span class="sxs-lookup"><span data-stu-id="29db0-104">**Summary:** Learn how to block IM and conferencing sessions in the case of a Skype for Business Server 2015 failure that would prevent archiving.</span></span>
  
<span data-ttu-id="29db0-105">Si el archivado es un requisito para su organización, puede bloquear sesiones de mensajería instantánea y conferencias en caso de un Skype error Business Server que podrían impedir el archivado.</span><span class="sxs-lookup"><span data-stu-id="29db0-105">If archiving is a requirement for your organization, you can block IM and conferencing sessions in the event of a Skype for Business Server failure that would prevent archiving.</span></span> <span data-ttu-id="29db0-106">A veces se denomina modo crítico.</span><span class="sxs-lookup"><span data-stu-id="29db0-106">This is sometimes called critical mode.</span></span> <span data-ttu-id="29db0-107">Por ejemplo, si existe un problema con un servicio de almacenamiento, la mensajería instantánea se bloquearía para los usuarios cuyas comunicaciones están habilitadas para el archivado.</span><span class="sxs-lookup"><span data-stu-id="29db0-107">For example, if there is a problem with a storage service, IM would be blocked for users whose communications are enabled for archiving.</span></span> <span data-ttu-id="29db0-108">Tanto la mensajería instantánea como las conferencias se recuperan automáticamente después de que se corrijan los errores.</span><span class="sxs-lookup"><span data-stu-id="29db0-108">Both IM and conferencing automatically recover after the failures are corrected.</span></span> 
  
## <a name="configure-critical-mode-by-using-the-control-panel"></a><span data-ttu-id="29db0-109">Configurar el modo crítico con el Panel de control</span><span class="sxs-lookup"><span data-stu-id="29db0-109">Configure critical mode by using the Control Panel</span></span>

<span data-ttu-id="29db0-110">Para especificar si las sesiones de comunicación se tienen que permitir en caso de un error que no permita el archivado:</span><span class="sxs-lookup"><span data-stu-id="29db0-110">To specify whether communication sessions should be allowed in case of a failure that would prevent archiving:</span></span>
  
1. <span data-ttu-id="29db0-111">Desde una cuenta de usuario que se asigne al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="29db0-111">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="29db0-112">Abra una ventana del explorador y, a continuación, escriba la dirección URL de Admin para abrir el Skype para Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="29db0-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="29db0-113">En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y, después, en **Configuración de archivado**.</span><span class="sxs-lookup"><span data-stu-id="29db0-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="29db0-114">Haga clic en el nombre de la configuración global, de sitio o de grupo de servidores adecuada en la lista de configuraciones de archivado, haga clic en **Editar** y luego haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="29db0-114">Click the name of the appropriate global, site, or pool configuration in the list of archiving configurations, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="29db0-115">Para configurar el comportamiento del archivado cuando se produzca un error, active o desactive la casilla **Bloquear sesiones de mensajería instantánea o conferencias web si no se pueden archivar**.</span><span class="sxs-lookup"><span data-stu-id="29db0-115">To set how archiving behaves when a failure occurs, select or clear the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
6. <span data-ttu-id="29db0-116">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="29db0-116">Click **Commit**.</span></span>
    
## <a name="configure-critical-mode-by-using-windows-powershell"></a><span data-ttu-id="29db0-117">Configurar el modo crítico con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="29db0-117">Configure critical mode by using Windows PowerShell</span></span>

<span data-ttu-id="29db0-118">También puede especificar si se deben permitir las sesiones de comunicación en caso de errores que podrían impedir el archivado mediante el cmdlet **Set-CsArchivingConfiguration** con el parámetro BlockOnArchiveFailure.</span><span class="sxs-lookup"><span data-stu-id="29db0-118">You can also specify whether communication sessions should be allowed in case of a failure that would prevent archiving by using the **Set-CsArchivingConfiguration** cmdlet with the BlockOnArchiveFailure parameter.</span></span>
  
<span data-ttu-id="29db0-119">Por ejemplo, el siguiente comando deshabilita la comunicación en el caso de un error de archivado:</span><span class="sxs-lookup"><span data-stu-id="29db0-119">For example, the following command disables communications in the case of an archiving failure:</span></span>
  
```
Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $True
```

<span data-ttu-id="29db0-120">El siguiente comando habilita las comunicaciones en caso de un error de archivado:</span><span class="sxs-lookup"><span data-stu-id="29db0-120">The next command enables communications in the case of an archiving failure:</span></span>
  
```
Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $False
```

<span data-ttu-id="29db0-121">Para obtener más información, vea el tema de ayuda para el cmdlet [Set-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csarchivingconfiguration?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="29db0-121">For more information, see the Help topic for the [Set-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csarchivingconfiguration?view=skype-ps) cmdlet.</span></span>
  

