---
title: Personaliza la música de estacionamiento de llamadas en espera inSkype para la empresa
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3d78e6f9-a4ae-49f4-a89f-4515acb49dac
description: Personalizar el estacionamiento de música en espera en Skype para Business Server Enterprise Voice.
ms.openlocfilehash: e0d1f49a1385eb185f7abb12edb467abb221a411
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "21001255"
---
# <a name="customize-call-park-music-on-hold-inskype-for-business"></a>Personaliza la música de estacionamiento de llamadas en espera inSkype para la empresa
 
Personalizar el estacionamiento de música en espera en Skype para Business Server Enterprise Voice.
  
Puede especificar su propio archivo de música que se usará para la música en espera, en lugar del archivo de música predeterminado que se distribuye con Skype para Business Server. Para personalizar la música en espera, use el cmdlet **Set-CsCallParkServiceMusicOnHoldFile** .
  
> [!NOTE]
> Si personaliza la música en espera y desea usar la misma música para varios sitios, debe configurar el archivo de música para cada sitio que se ejecuta la aplicación de estacionamiento de llamadas. 
  
### <a name="to-customize-the-music-file"></a>Para personalizar el archivo de música

1. Inicie sesión en el equipo donde está instalado Skype para Shell de administración de servidor empresarial como un miembro del grupo RTCUniversalServerAdmins o con los derechos de usuario necesarios, tal como se describe en **Delegar permisos de instalación**.
    
2. Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.
    
3. Ejecute:
    
   ```
   Set-CsCallParkServiceMusicOnHoldFile -Service <ServiceID where the Call Park application resides> -Content <Byte >
   ```

    > [!TIP]
    > Use el cmdlet **Get-CsService** para identificar el servicio. Para obtener información detallada, vea [Get-CsService](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps). 
  
    En el ejemplo siguiente se muestra cómo obtener el contenido de un archivo, soothingmusic.wma, como matriz de bytes y asignarlo a una variable. A continuación, el archivo de audio se asigna como el archivo de música en espera en Estacionamiento de llamadas. Para obtener información detallada, vea [Set-CsCallParkServiceMusicOnHoldFile](https://docs.microsoft.com/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps).
    
   ```
   $a = Get-Content -ReadCount 0 -Encoding byte "C:\MoHFiles\soothingmusic.wma"
   Set-CsCallParkServiceMusicOnHoldFile -Service Redmond1-applicationserver-1 -Content $a
   ```

## <a name="see-also"></a>Vea también

[Set-CsCallParkServiceMusicOnHoldFile](https://docs.microsoft.com/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps)
  
[Get-CsService](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps)