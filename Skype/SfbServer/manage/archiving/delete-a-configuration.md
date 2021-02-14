---
title: Eliminar una configuración de archivado en Skype Empresarial Server
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
ms.assetid: fed12cb5-2c80-476a-af3b-d55b450c5fbc
description: 'Resumen: obtenga información sobre cómo eliminar una configuración de archivado en Skype Empresarial Server.'
ms.openlocfilehash: a9d24a17ec769f5686502beb325e021c8b0f39c3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817630"
---
# <a name="delete-an-archiving-configuration-in-skype-for-business-server"></a><span data-ttu-id="5041f-103">Eliminar una configuración de archivado en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="5041f-103">Delete an archiving configuration in Skype for Business Server</span></span>

<span data-ttu-id="5041f-104">**Resumen:** Obtenga información sobre cómo eliminar una configuración de archivado en Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="5041f-104">**Summary:** Learn how to delete an archiving configuration in Skype for Business Server.</span></span>
  
<span data-ttu-id="5041f-105">Puede eliminar una configuración de sitio o de grupo, pero no puede eliminar la configuración global.</span><span class="sxs-lookup"><span data-stu-id="5041f-105">You can delete a site configuration or pool configuration, but you cannot delete the global configuration.</span></span> <span data-ttu-id="5041f-106">Si elimina la configuración global, esta se restablece automáticamente a los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="5041f-106">If you delete the global configuration, it is automatically reset to the default values.</span></span>
  
## <a name="delete-an-archiving-configuration-by-using-the-control-panel"></a><span data-ttu-id="5041f-107">Eliminar una configuración de archivado mediante el Panel de control</span><span class="sxs-lookup"><span data-stu-id="5041f-107">Delete an archiving configuration by using the Control Panel</span></span>

<span data-ttu-id="5041f-108">Para eliminar una configuración de archivado mediante el Panel de control:</span><span class="sxs-lookup"><span data-stu-id="5041f-108">To delete an archiving configuration by using the Control Panel:</span></span>
  
1. <span data-ttu-id="5041f-109">Desde una cuenta de usuario asignada al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="5041f-109">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="5041f-110">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="5041f-110">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="5041f-111">En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y, a continuación, haga clic en **Configuración de archivado**.</span><span class="sxs-lookup"><span data-stu-id="5041f-111">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="5041f-112">En la lista de configuraciones de archivado, haga clic en la configuración de sitio o de grupo que desea eliminar y, después, haga clic en **Editar** y en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="5041f-112">In the list of archiving configurations, click the site or pool configuration that you want to delete, click **Edit**, and then click **Delete**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="5041f-113">También puede hacer clic en la configuración global, pero elija esta opción solo si desea restablecer la configuración global a los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="5041f-113">You can also click the Global configuration, but choose this option only if you want to reset the Global configuration to the default values.</span></span> 
  
5. <span data-ttu-id="5041f-114">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="5041f-114">Click **Commit**.</span></span>
    
## <a name="delete-an-archiving-configuration-by-using-windows-powershell"></a><span data-ttu-id="5041f-115">Eliminar una configuración de archivado mediante Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5041f-115">Delete an archiving configuration by using Windows PowerShell</span></span>

<span data-ttu-id="5041f-116">También puede eliminar una configuración de archivado con el cmdlet **Remove-CsArchivingConfiguration.**</span><span class="sxs-lookup"><span data-stu-id="5041f-116">You can also delete an archiving configuration by using the **Remove-CsArchivingConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="5041f-117">Por ejemplo, el siguiente comando quita las opciones de configuración de archivado aplicadas al sitio Redmond.</span><span class="sxs-lookup"><span data-stu-id="5041f-117">For example, the following command removes the archiving configuration settings applied to the Redmond site.</span></span> <span data-ttu-id="5041f-118">Cuando se elimina una directiva configurada en el ámbito del sitio, los usuarios que anteriormente administraba la directiva de sitio se regirán automáticamente por la directiva de archivado global en su lugar:</span><span class="sxs-lookup"><span data-stu-id="5041f-118">When a policy configured at the site scope is deleted, users previously managed by the site policy will automatically be governed by the global archiving policy instead:</span></span>
  
```PowerShell
Remove-CsArchivingConfiguration -Identity "site:Redmond"
```

<span data-ttu-id="5041f-119">El siguiente comando quita todas las opciones de configuración de archivado aplicadas al ámbito de servicio:</span><span class="sxs-lookup"><span data-stu-id="5041f-119">The following command removes all the archiving configuration settings applied to the service scope:</span></span>
  
```PowerShell
Get-CsArchivingConfiguration -Filter "site:*" | Remove-CsArchivingConfiguration
```

<span data-ttu-id="5041f-120">El siguiente comando quita todas las opciones de configuración de archivado en las que se ha deshabilitado el archivado de Exchange:</span><span class="sxs-lookup"><span data-stu-id="5041f-120">The next command removes all the archiving configuration settings where Exchange archiving has been disabled:</span></span>
  
```PowerShell
Get-CsArchivingConfiguration | Where-Object {$_.EnableExchangeArchiving -eq $False} | Remove-CsArchivingConfiguration
```

<span data-ttu-id="5041f-121">También puede usar el cmdlet **Remove-CsArchivingConfiguration** para restablecer la configuración global a los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="5041f-121">You can also use the **Remove-CsArchivingConfiguration** cmdlet to reset the global settings to default values.</span></span> <span data-ttu-id="5041f-122">Por ejemplo, supongamos que ha habilitado el archivado de sesiones de mensajería instantánea en el nivel global; El siguiente comando restablecerá el valor predeterminado de Ninguno, que deshabilitará el archivado en el nivel global:</span><span class="sxs-lookup"><span data-stu-id="5041f-122">For example, suppose you have enabled IM session archiving at the global level; the following command will reset the value to the default of None, which will disable archiving at the global level:</span></span>
  
```PowerShell
Remove-CsArchivingConfiguration -Identity global
```

<span data-ttu-id="5041f-123">Para obtener más información, consulte el tema de ayuda del cmdlet [Remove-CsArchivingConfiguration.](https://docs.microsoft.com/powershell/module/skype/remove-csarchivingconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="5041f-123">For more information, see the help topic for the [Remove-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csarchivingconfiguration?view=skype-ps) cmdlet.</span></span>
