---
title: Personalizar la música de estacionamiento de llamadas en espera de Skype empresarial
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3d78e6f9-a4ae-49f4-a89f-4515acb49dac
description: Personalizar la música de estacionamiento de llamadas en espera en la voz empresarial de Skype empresarial Server.
ms.openlocfilehash: f071b83e155e2ddfb057619eb95773e4386b67c0
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2020
ms.locfileid: "41001010"
---
# <a name="customize-call-park-music-on-hold-inskype-for-business"></a><span data-ttu-id="ddc74-103">Personalizar la música de estacionamiento de llamadas en espera de Skype empresarial</span><span class="sxs-lookup"><span data-stu-id="ddc74-103">Customize Call Park music on hold inSkype for Business</span></span>
 
<span data-ttu-id="ddc74-104">Personalizar la música de estacionamiento de llamadas en espera en la voz empresarial de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="ddc74-104">Customize the Call Park music on hold in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="ddc74-105">Puede especificar su propio archivo de música para usar en la música en espera, en lugar del archivo de música predeterminado que se incluye con Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="ddc74-105">You can specify your own music file to use for music on hold, instead of the default music file that ships with Skype for Business Server.</span></span> <span data-ttu-id="ddc74-106">Para personalizar la música en espera, utilice el cmdlet **Set-CsCallParkServiceMusicOnHoldFile**.</span><span class="sxs-lookup"><span data-stu-id="ddc74-106">To customize music on hold, use the **Set-CsCallParkServiceMusicOnHoldFile** cmdlet.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ddc74-107">Si personaliza la música en espera y quiere la misma música para varios sitios, debe configurar el archivo de música para cada sitio que ejecute la aplicación estacionamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="ddc74-107">If you customize music on hold and want the same music for multiple sites, you must configure the music file for each site that runs the Call Park application.</span></span> 
  
### <a name="to-customize-the-music-file"></a><span data-ttu-id="ddc74-108">Para personalizar el archivo de música</span><span class="sxs-lookup"><span data-stu-id="ddc74-108">To customize the music file</span></span>

1. <span data-ttu-id="ddc74-109">Inicie sesión en el equipo donde está instalado el shell de administración de Skype empresarial Server como miembro del grupo RTCUniversalServerAdmins o con los derechos de usuario necesarios, como se describe en **permisos de configuración de delegado**.</span><span class="sxs-lookup"><span data-stu-id="ddc74-109">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="ddc74-110">Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="ddc74-110">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="ddc74-111">Ejecute:</span><span class="sxs-lookup"><span data-stu-id="ddc74-111">Run:</span></span>
    
   ```powershell
   Set-CsCallParkServiceMusicOnHoldFile -Service <ServiceID where the Call Park application resides> -Content <Byte >
   ```

    > [!TIP]
    > <span data-ttu-id="ddc74-112">Use el cmdlet **Get-CsService** para identificar el servicio.</span><span class="sxs-lookup"><span data-stu-id="ddc74-112">Use the **Get-CsService** cmdlet to identify the service.</span></span> <span data-ttu-id="ddc74-113">Para obtener más información, vea [Get-CsService](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="ddc74-113">For details, see [Get-CsService](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps).</span></span> 
  
    <span data-ttu-id="ddc74-114">En el ejemplo siguiente se muestra cómo obtener el contenido de un archivo, soothingmusic.wma, como matriz de bytes y asignarlo a una variable.</span><span class="sxs-lookup"><span data-stu-id="ddc74-114">The following example shows how to obtain the contents of a file, soothingmusic.wma, as a byte array and assign it to a variable.</span></span> <span data-ttu-id="ddc74-115">A continuación, el archivo de audio se asigna como el archivo de música en espera en Estacionamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="ddc74-115">Then the audio file is assigned as the music-on-hold file for Call Park.</span></span> <span data-ttu-id="ddc74-116">Para obtener más información, consulte [set-CsCallParkServiceMusicOnHoldFile](https://docs.microsoft.com/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="ddc74-116">For details, see [Set-CsCallParkServiceMusicOnHoldFile](https://docs.microsoft.com/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps).</span></span>
    
   ```powershell
   $a = Get-Content -ReadCount 0 -Encoding byte "C:\MoHFiles\soothingmusic.wma"
   Set-CsCallParkServiceMusicOnHoldFile -Service Redmond1-applicationserver-1 -Content $a
   ```

## <a name="see-also"></a><span data-ttu-id="ddc74-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="ddc74-117">See also</span></span>

[<span data-ttu-id="ddc74-118">Set-CsCallParkServiceMusicOnHoldFile</span><span class="sxs-lookup"><span data-stu-id="ddc74-118">Set-CsCallParkServiceMusicOnHoldFile</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps)
  
[<span data-ttu-id="ddc74-119">Get-CsService</span><span class="sxs-lookup"><span data-stu-id="ddc74-119">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps)
