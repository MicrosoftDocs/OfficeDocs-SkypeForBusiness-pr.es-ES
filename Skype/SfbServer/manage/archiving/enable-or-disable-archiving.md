---
title: Habilitar o deshabilitar el archivado en Skype Empresarial Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d5aed328-e89d-4a7b-b603-15ae5c33c5dd
description: 'Resumen: Conozca cómo habilitar o deshabilitar el archivado en Skype para Business Server 2015.'
ms.openlocfilehash: ef4e24025d0f1c27b0249b4ea237a579882e74c2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="enable-or-disable-archiving-in-skype-for-business-server-2015"></a><span data-ttu-id="ccdc3-103">Habilitar o deshabilitar el archivado en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="ccdc3-103">Enable or disable archiving in Skype for Business Server 2015</span></span>

<span data-ttu-id="ccdc3-104">**Resumen:** Obtenga información acerca de cómo habilitar o deshabilitar el archivado en Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="ccdc3-104">**Summary:** Learn how to enable or disable archiving in Skype for Business Server 2015.</span></span>
  
## <a name="enable-or-disable-archiving-by-using-the-control-panel"></a><span data-ttu-id="ccdc3-105">Habilitar o deshabilitar el archivado con el Panel de control</span><span class="sxs-lookup"><span data-stu-id="ccdc3-105">Enable or disable archiving by using the Control Panel</span></span>

1. <span data-ttu-id="ccdc3-106">Desde una cuenta de usuario que se asigne al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="ccdc3-106">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="ccdc3-107">Abra una ventana del explorador y, a continuación, escriba la dirección URL de Admin para abrir el Skype para Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="ccdc3-107">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="ccdc3-108">En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y, después, en **Configuración de archivado**.</span><span class="sxs-lookup"><span data-stu-id="ccdc3-108">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="ccdc3-109">Seleccione la configuración global, de sitio o de grupo adecuada en la lista de configuraciones de archivado, haga clic en **Editar** y en **Mostrar detalles**, y luego siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="ccdc3-109">Select the appropriate global, site, or pool configuration from the list of archiving configurations, click **Edit**, click **Show details**, and then do the following:</span></span>
    
   - <span data-ttu-id="ccdc3-110">Para habilitar el archivado solo para las sesiones de mensajería instantánea (MI), haga clic en **Archivar sesiones de mensajería instantánea (MI)**.</span><span class="sxs-lookup"><span data-stu-id="ccdc3-110">To enable archiving only for instant messaging (IM) sessions, click **Archive IM sessions**.</span></span>
    
   - <span data-ttu-id="ccdc3-111">Para habilitar el archivado para las sesiones de MI y de conferencia, haga clic en **Archivar sesiones de mensajería instantánea y conferencias web**.</span><span class="sxs-lookup"><span data-stu-id="ccdc3-111">To enable archiving for both IM sessions and conferences, click **Archive IM and conferencing sessions**.</span></span>
    
   - <span data-ttu-id="ccdc3-112">Para deshabilitar el archivado para la configuración, haga clic en **Deshabilitar archivado**.</span><span class="sxs-lookup"><span data-stu-id="ccdc3-112">To disable archiving for the configuration, click **Disable archiving**.</span></span>
    
5. <span data-ttu-id="ccdc3-113">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="ccdc3-113">Click **Commit**.</span></span>
    
## <a name="enable-or-disable-archiving-by-using-windows-powershell"></a><span data-ttu-id="ccdc3-114">Habilitar o deshabilitar el archivado con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ccdc3-114">Enable or disable archiving by using Windows PowerShell</span></span>

<span data-ttu-id="ccdc3-115">También puede habilitar o deshabilitar el archivado con el cmdlet **Set-CsArchivingConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="ccdc3-115">You can also enable or disable archiving by using the **Set-CsArchivingConfiguration** cmdlet.</span></span> <span data-ttu-id="ccdc3-116">Por ejemplo, el siguiente comando modifica todas las opciones de configuración de archivado de manera que solo se archivan las sesiones de mensajería instantánea.</span><span class="sxs-lookup"><span data-stu-id="ccdc3-116">For example, the following command modifies the all of the archiving configuration settings so that only IM sessions are archived.</span></span> <span data-ttu-id="ccdc3-117">El comando llama el cmdlet **Get-CsArchivingConfiguration** sin ningún parámetro para devolver todos los valores de configuración de archiving actualmente en uso en la organización.</span><span class="sxs-lookup"><span data-stu-id="ccdc3-117">The command calls the **Get-CsArchivingConfiguration** cmdlet without any parameters in order to return all the archiving configuration settings currently in use in the organization.</span></span> <span data-ttu-id="ccdc3-118">Esta colección, a continuación, se canaliza hacia el cmdlet **Where-Object** , que selecciona únicamente los valores que la propiedad EnableArchiving es igual a (-eq) "ImAndWebConf".</span><span class="sxs-lookup"><span data-stu-id="ccdc3-118">This collection is then piped to the **Where-Object** cmdlet, which selects only those settings where the EnableArchiving property is equal to (-eq) "ImAndWebConf".</span></span> <span data-ttu-id="ccdc3-119">A continuación, la colección filtrada se canaliza hacia el cmdlet **Set-CsArchivingConfiguration** , que toma cada elemento de la colección y cambia el valor de EnableArchiving a "ImOnly":</span><span class="sxs-lookup"><span data-stu-id="ccdc3-119">The filtered collection is then piped to the **Set-CsArchivingConfiguration** cmdlet, which takes each item in the collection and changes the value of EnableArchiving to "ImOnly":</span></span>
  
```
Get-CsArchivingConfiguration | Where-Object {$_.EnableArchiving -eq "ImAndWebConf"} | Set-CsArchivingConfiguration -EnableArchiving "ImOnly"
```