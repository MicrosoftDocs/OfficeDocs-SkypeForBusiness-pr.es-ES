---
title: Personalizar la música de estacionamiento de llamadas en espera de Skype empresarial
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3d78e6f9-a4ae-49f4-a89f-4515acb49dac
description: Personalizar la música de estacionamiento de llamadas en espera en la voz empresarial de Skype empresarial Server.
ms.openlocfilehash: 4111bcc42a3820e3957f526e360264aa7d098d05
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286179"
---
# <a name="customize-call-park-music-on-hold-inskype-for-business"></a>Personalizar la música de estacionamiento de llamadas en espera de Skype empresarial
 
Personalizar la música de estacionamiento de llamadas en espera en la voz empresarial de Skype empresarial Server.
  
Puede especificar su propio archivo de música para usar en la música en espera, en lugar del archivo de música predeterminado que se incluye con Skype empresarial Server. Para personalizar la música en espera, utilice el cmdlet **Set-CsCallParkServiceMusicOnHoldFile**.
  
> [!NOTE]
> Si personaliza la música en espera y quiere la misma música para varios sitios, debe configurar el archivo de música para cada sitio que ejecute la aplicación estacionamiento de llamadas. 
  
### <a name="to-customize-the-music-file"></a>Para personalizar el archivo de música

1. Inicie sesión en el equipo donde está instalado el shell de administración de Skype empresarial Server como miembro del grupo RTCUniversalServerAdmins o con los derechos de usuario necesarios, como se describe en **permisos de configuración de delegado**.
    
2. Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.
    
3. Ejecute:
    
   ```
   Set-CsCallParkServiceMusicOnHoldFile -Service <ServiceID where the Call Park application resides> -Content <Byte >
   ```

    > [!TIP]
    > Use el cmdlet **Get-CsService** para identificar el servicio. Para obtener más información, vea [Get-CsService](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps). 
  
    En el ejemplo siguiente se muestra cómo obtener el contenido de un archivo, soothingmusic.wma, como matriz de bytes y asignarlo a una variable. A continuación, el archivo de audio se asigna como el archivo de música en espera en Estacionamiento de llamadas. Para obtener más información, consulte [set-CsCallParkServiceMusicOnHoldFile](https://docs.microsoft.com/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps).
    
   ```
   $a = Get-Content -ReadCount 0 -Encoding byte "C:\MoHFiles\soothingmusic.wma"
   Set-CsCallParkServiceMusicOnHoldFile -Service Redmond1-applicationserver-1 -Content $a
   ```

## <a name="see-also"></a>Vea también

[Set-CsCallParkServiceMusicOnHoldFile](https://docs.microsoft.com/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps)
  
[Get-CsService](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps)
