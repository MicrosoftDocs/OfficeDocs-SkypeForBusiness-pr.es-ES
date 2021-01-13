---
title: Habilitar o deshabilitar el archivado en Skype Empresarial Server
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
ms.assetid: d5aed328-e89d-4a7b-b603-15ae5c33c5dd
description: 'Resumen: obtenga información sobre cómo habilitar o deshabilitar el archivado en Skype Empresarial Server.'
ms.openlocfilehash: 6d8f6f24bd4b10f7d33a00e218a494d6e8a823d1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817600"
---
# <a name="enable-or-disable-archiving-in-skype-for-business-server"></a><span data-ttu-id="40b2b-103">Habilitar o deshabilitar el archivado en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="40b2b-103">Enable or disable archiving in Skype for Business Server</span></span>

<span data-ttu-id="40b2b-104">**Resumen:** Obtenga información sobre cómo habilitar o deshabilitar el archivado en Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="40b2b-104">**Summary:** Learn how to enable or disable archiving in Skype for Business Server.</span></span>
  
## <a name="enable-or-disable-archiving-by-using-the-control-panel"></a><span data-ttu-id="40b2b-105">Habilitar o deshabilitar el archivado mediante el Panel de control</span><span class="sxs-lookup"><span data-stu-id="40b2b-105">Enable or disable archiving by using the Control Panel</span></span>

1. <span data-ttu-id="40b2b-106">Desde una cuenta de usuario asignada al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="40b2b-106">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="40b2b-107">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="40b2b-107">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="40b2b-108">En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y, a continuación, haga clic en **Configuración de archivado**.</span><span class="sxs-lookup"><span data-stu-id="40b2b-108">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="40b2b-109">Seleccione la configuración global, de sitio o de grupo adecuada en la lista de configuraciones de archivado, haga clic en **Editar** y en **Mostrar detalles**, y luego siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="40b2b-109">Select the appropriate global, site, or pool configuration from the list of archiving configurations, click **Edit**, click **Show details**, and then do the following:</span></span>
    
   - <span data-ttu-id="40b2b-110">Para habilitar el archivado solamente para las sesiones de MI, haga clic en **Archivar sesiones de mensajería instantánea**.</span><span class="sxs-lookup"><span data-stu-id="40b2b-110">To enable archiving only for instant messaging (IM) sessions, click **Archive IM sessions**.</span></span>
    
   - <span data-ttu-id="40b2b-111">Para habilitar el archivado para las sesiones de mensajería instantánea y para las conferencias, haga clic en **Archivar sesiones de mensajería instantánea y conferencias web**.</span><span class="sxs-lookup"><span data-stu-id="40b2b-111">To enable archiving for both IM sessions and conferences, click **Archive IM and conferencing sessions**.</span></span>
    
   - <span data-ttu-id="40b2b-112">Para deshabilitar el archivado para la configuración, haga clic **en Deshabilitar archivado.**</span><span class="sxs-lookup"><span data-stu-id="40b2b-112">To disable archiving for the configuration, click **Disable archiving**.</span></span>
    
5. <span data-ttu-id="40b2b-113">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="40b2b-113">Click **Commit**.</span></span>
    
## <a name="enable-or-disable-archiving-by-using-windows-powershell"></a><span data-ttu-id="40b2b-114">Habilite o deshabilite el archivado mediante Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="40b2b-114">Enable or disable archiving by using Windows PowerShell</span></span>

<span data-ttu-id="40b2b-115">También puede habilitar o deshabilitar el archivado con el cmdlet **Set-CsArchivingConfiguration.**</span><span class="sxs-lookup"><span data-stu-id="40b2b-115">You can also enable or disable archiving by using the **Set-CsArchivingConfiguration** cmdlet.</span></span> <span data-ttu-id="40b2b-116">Por ejemplo, el siguiente comando modifica todas las opciones de configuración de archivado para que solo se archiven las sesiones de mensajería instantánea.</span><span class="sxs-lookup"><span data-stu-id="40b2b-116">For example, the following command modifies the all of the archiving configuration settings so that only IM sessions are archived.</span></span> <span data-ttu-id="40b2b-117">El comando llama al cmdlet **Get-CsArchivingConfiguration** sin ningún parámetro para devolver todas las opciones de configuración de archivado actualmente en uso en la organización.</span><span class="sxs-lookup"><span data-stu-id="40b2b-117">The command calls the **Get-CsArchivingConfiguration** cmdlet without any parameters in order to return all the archiving configuration settings currently in use in the organization.</span></span> <span data-ttu-id="40b2b-118">A continuación, esta colección se canaliza al cmdlet **Where-Object,** que selecciona solo las configuraciones en las que la propiedad EnableArchiving es igual a (-eq) "ImAndWebConf".</span><span class="sxs-lookup"><span data-stu-id="40b2b-118">This collection is then piped to the **Where-Object** cmdlet, which selects only those settings where the EnableArchiving property is equal to (-eq) "ImAndWebConf".</span></span> <span data-ttu-id="40b2b-119">A continuación, la recopilación filtrada se canaliza al cmdlet **Set-CsArchivingConfiguration,** que toma cada elemento de la colección y cambia el valor de EnableArchiving a "ImOnly":</span><span class="sxs-lookup"><span data-stu-id="40b2b-119">The filtered collection is then piped to the **Set-CsArchivingConfiguration** cmdlet, which takes each item in the collection and changes the value of EnableArchiving to "ImOnly":</span></span>
  
```PowerShell
Get-CsArchivingConfiguration | Where-Object {$_.EnableArchiving -eq "ImAndWebConf"} | Set-CsArchivingConfiguration -EnableArchiving "ImOnly"
```
