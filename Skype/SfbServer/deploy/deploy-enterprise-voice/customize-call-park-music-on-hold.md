---
title: Personalizar la música de espera para el estacionamiento de llamadas en Skype Empresarial 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 3d78e6f9-a4ae-49f4-a89f-4515acb49dac
description: Personalizar el parque llamada música en espera en Skype para Telefonía IP empresarial de Business Server.
ms.openlocfilehash: 5af98ee95c59f7fd945232f77d713255ca1c42d5
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="customize-call-park-music-on-hold-inskype-for-business-2015"></a><span data-ttu-id="dcee7-103">Personalizar la música de espera para el estacionamiento de llamadas en Skype Empresarial 2015</span><span class="sxs-lookup"><span data-stu-id="dcee7-103">Customize Call Park music on hold inSkype for Business 2015</span></span>
 
<span data-ttu-id="dcee7-104">Personalizar el parque llamada música en espera en Skype para Telefonía IP empresarial de Business Server.</span><span class="sxs-lookup"><span data-stu-id="dcee7-104">Customize the Call Park music on hold in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="dcee7-105">Puede especificar su propio archivo de música que se utilizará para música en espera, en lugar del archivo de música predeterminado que se incluye con Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="dcee7-105">You can specify your own music file to use for music on hold, instead of the default music file that ships with Skype for Business Server.</span></span> <span data-ttu-id="dcee7-106">Para personalizar la música en espera, utilice el cmdlet **Set-CsCallParkServiceMusicOnHoldFile** .</span><span class="sxs-lookup"><span data-stu-id="dcee7-106">To customize music on hold, use the **Set-CsCallParkServiceMusicOnHoldFile** cmdlet.</span></span>
  
> [!NOTE]
> <span data-ttu-id="dcee7-107">Si personalizar música en espera y desea que la misma música para varios sitios, debe configurar el archivo de música para cada sitio que ejecuta la aplicación llamada Park.</span><span class="sxs-lookup"><span data-stu-id="dcee7-107">If you customize music on hold and want the same music for multiple sites, you must configure the music file for each site that runs the Call Park application.</span></span> 
  
### <a name="to-customize-the-music-file"></a><span data-ttu-id="dcee7-108">Para personalizar el archivo de música</span><span class="sxs-lookup"><span data-stu-id="dcee7-108">To customize the music file</span></span>

1. <span data-ttu-id="dcee7-109">Inicie sesión en el equipo donde está instalado Skype para el Shell de administración de servidor empresarial como miembro del grupo RTCUniversalServerAdmins o con los derechos de usuario necesarios según se describe en **Configuración de permisos de delegado**.</span><span class="sxs-lookup"><span data-stu-id="dcee7-109">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="dcee7-110">Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="dcee7-110">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="dcee7-111">Ejecute:</span><span class="sxs-lookup"><span data-stu-id="dcee7-111">Run:</span></span>
    
   ```
   Set-CsCallParkServiceMusicOnHoldFile -Service <ServiceID where the Call Park application resides> -Content <Byte >
   ```

    > [!TIP]
    > <span data-ttu-id="dcee7-112">Use el cmdlet **Get-CsService** para identificar el servicio.</span><span class="sxs-lookup"><span data-stu-id="dcee7-112">Use the **Get-CsService** cmdlet to identify the service.</span></span> <span data-ttu-id="dcee7-113">Para obtener más información, consulte [Get-CsService](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="dcee7-113">For details, see [Get-CsService](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps).</span></span> 
  
    <span data-ttu-id="dcee7-114">En el ejemplo siguiente se muestra cómo obtener el contenido de un archivo, soothingmusic.wma, como matriz de bytes y asignarlo a una variable.</span><span class="sxs-lookup"><span data-stu-id="dcee7-114">The following example shows how to obtain the contents of a file, soothingmusic.wma, as a byte array and assign it to a variable.</span></span> <span data-ttu-id="dcee7-115">A continuación, el archivo de audio se asigna como el archivo de música en espera en Estacionamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="dcee7-115">Then the audio file is assigned as the music-on-hold file for Call Park.</span></span> <span data-ttu-id="dcee7-116">Para obtener más información, consulte [Set-CsCallParkServiceMusicOnHoldFile](https://docs.microsoft.com/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="dcee7-116">For details, see [Set-CsCallParkServiceMusicOnHoldFile](https://docs.microsoft.com/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps).</span></span>
    
   ```
   $a = Get-Content -ReadCount 0 -Encoding byte "C:\MoHFiles\soothingmusic.wma"
   Set-CsCallParkServiceMusicOnHoldFile -Service Redmond1-applicationserver-1 -Content $a
   ```

## <a name="see-also"></a><span data-ttu-id="dcee7-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="dcee7-117">See also</span></span>

#### 

[<span data-ttu-id="dcee7-118">Conjunto de CsCallParkServiceMusicOnHoldFile</span><span class="sxs-lookup"><span data-stu-id="dcee7-118">Set-CsCallParkServiceMusicOnHoldFile</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps)
  
[<span data-ttu-id="dcee7-119">Get-CsService</span><span class="sxs-lookup"><span data-stu-id="dcee7-119">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps)

