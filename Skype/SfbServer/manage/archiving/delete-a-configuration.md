---
title: Eliminar una configuración de archivado en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fed12cb5-2c80-476a-af3b-d55b450c5fbc
description: 'Resumen: Aprenda a eliminar una configuración de archivado en Skype empresarial Server.'
ms.openlocfilehash: 22da9464a4bb6b17c6d4b9aa63ad8990a9152c38
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992377"
---
# <a name="delete-an-archiving-configuration-in-skype-for-business-server"></a><span data-ttu-id="2c795-103">Eliminar una configuración de archivado en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="2c795-103">Delete an archiving configuration in Skype for Business Server</span></span>

<span data-ttu-id="2c795-104">**Resumen:** Aprenda a eliminar una configuración de archivado en Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="2c795-104">**Summary:** Learn how to delete an archiving configuration in Skype for Business Server.</span></span>
  
<span data-ttu-id="2c795-p101">Es posible eliminar una configuración de sitio o de grupo, pero no puede eliminar la configuración global. Si elimina la configuración global, esta se restablece automáticamente a sus valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="2c795-p101">You can delete a site configuration or pool configuration, but you cannot delete the global configuration. If you delete the global configuration, it is automatically reset to the default values.</span></span>
  
## <a name="delete-an-archiving-configuration-by-using-the-control-panel"></a><span data-ttu-id="2c795-107">Eliminar la configuración de archivado con el Panel de control</span><span class="sxs-lookup"><span data-stu-id="2c795-107">Delete an archiving configuration by using the Control Panel</span></span>

<span data-ttu-id="2c795-108">Para eliminar la configuración de archivado con el Panel de control:</span><span class="sxs-lookup"><span data-stu-id="2c795-108">To delete an archiving configuration by using the Control Panel:</span></span>
  
1. <span data-ttu-id="2c795-109">Desde una cuenta de usuario que se asigne al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="2c795-109">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="2c795-110">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="2c795-110">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="2c795-111">En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y, después, en **Configuración de archivado**.</span><span class="sxs-lookup"><span data-stu-id="2c795-111">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="2c795-112">En la lista de configuraciones de archivado, haga clic en la configuración de sitio o de grupo que desea eliminar y, luego, haga clic en **Editar** y en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="2c795-112">In the list of archiving configurations, click the site or pool configuration that you want to delete, click **Edit**, and then click **Delete**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="2c795-113">También puede hacer clic en la configuración global, pero seleccione esta opción solo si desea restablecer la configuración global a los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="2c795-113">You can also click the Global configuration, but choose this option only if you want to reset the Global configuration to the default values.</span></span> 
  
5. <span data-ttu-id="2c795-114">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="2c795-114">Click **Commit**.</span></span>
    
## <a name="delete-an-archiving-configuration-by-using-windows-powershell"></a><span data-ttu-id="2c795-115">Eliminar una configuración de archivado con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="2c795-115">Delete an archiving configuration by using Windows PowerShell</span></span>

<span data-ttu-id="2c795-116">También puede eliminar una configuración de archivado mediante el cmdlet **Remove-CsArchivingConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="2c795-116">You can also delete an archiving configuration by using the **Remove-CsArchivingConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="2c795-p102">Por ejemplo, el siguiente comando quita las opciones de configuración del archivado aplicadas al sitio de Redmond. Cuando se elimina una directiva configurada en el ámbito de sitio, los usuarios a los que anteriormente administraba esta directiva de sitio se regirán de forma automática por la directiva de archivado global:</span><span class="sxs-lookup"><span data-stu-id="2c795-p102">For example, the following command removes the archiving configuration settings applied to the Redmond site. When a policy configured at the site scope is deleted, users previously managed by the site policy will automatically be governed by the global archiving policy instead:</span></span>
  
```PowerShell
Remove-CsArchivingConfiguration -Identity "site:Redmond"
```

<span data-ttu-id="2c795-119">El siguiente comando quita todas las opciones de configuración de archivado aplicadas al ámbito de servicio:</span><span class="sxs-lookup"><span data-stu-id="2c795-119">The following command removes all the archiving configuration settings applied to the service scope:</span></span>
  
```PowerShell
Get-CsArchivingConfiguration -Filter "site:*" | Remove-CsArchivingConfiguration
```

<span data-ttu-id="2c795-120">El siguiente comando quita todas las opciones de configuración de archivado en las que se deshabilitó el archivado de Exchange:</span><span class="sxs-lookup"><span data-stu-id="2c795-120">The next command removes all the archiving configuration settings where Exchange archiving has been disabled:</span></span>
  
```PowerShell
Get-CsArchivingConfiguration | Where-Object {$_.EnableExchangeArchiving -eq $False} | Remove-CsArchivingConfiguration
```

<span data-ttu-id="2c795-121">También puede usar el cmdlet **Remove-CsArchivingConfiguration** para restablecer la configuración global a los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="2c795-121">You can also use the **Remove-CsArchivingConfiguration** cmdlet to reset the global settings to default values.</span></span> <span data-ttu-id="2c795-122">Por ejemplo, si ha habilitado el archivado de las sesiones de mensajería instantánea de forma global, el siguiente comando restablecerá el valor al valor Ninguno predeterminado, y así se deshabilitará el archivado de manera global:</span><span class="sxs-lookup"><span data-stu-id="2c795-122">For example, suppose you have enabled IM session archiving at the global level; the following command will reset the value to the default of None, which will disable archiving at the global level:</span></span>
  
```PowerShell
Remove-CsArchivingConfiguration -Identity global
```

<span data-ttu-id="2c795-123">Para obtener más información, consulte el tema de ayuda para el cmdlet [Remove-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csarchivingconfiguration?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="2c795-123">For more information, see the help topic for the [Remove-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csarchivingconfiguration?view=skype-ps) cmdlet.</span></span>
