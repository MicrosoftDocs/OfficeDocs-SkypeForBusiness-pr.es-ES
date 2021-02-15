---
title: Personalizar la música en espera del estacionamiento de llamadas enSkype para empresas
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3d78e6f9-a4ae-49f4-a89f-4515acb49dac
description: Personalice la música en espera del estacionamiento de llamadas en Skype Empresarial Server Telefonía IP empresarial.
ms.openlocfilehash: 766b51895acda27c0558352968d21a39764b13a6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49837080"
---
# <a name="customize-call-park-music-on-hold-inskype-for-business"></a>Personalizar la música en espera del estacionamiento de llamadas enSkype para empresas
 
Personalice la música en espera del estacionamiento de llamadas en Skype Empresarial Server Telefonía IP empresarial.
  
Puede especificar su propio archivo de música para usarlo para la música en espera, en lugar del archivo de música predeterminado que se incluye con Skype Empresarial Server. Para personalizar la música en espera, utilice el cmdlet **Set-CsCallParkServiceMusicOnHoldFile**.
  
> [!NOTE]
> Si personaliza la música en espera y desea la misma música para varios sitios, debe configurar el archivo de música para cada sitio que ejecute la aplicación Estacionamiento de llamadas. 
  
### <a name="to-customize-the-music-file"></a>Para personalizar el archivo de música

1. Inicie sesión en el equipo donde está instalado el Shell de administración de Skype Empresarial Server como miembro del grupo RTCUniversalServerAdmins o con los derechos de usuario necesarios, tal como se describe en Permisos de configuración **delegados.**
    
2. Inicie el Shell de administración de Skype Empresarial Server: Haga clic en **Inicio,** en Todos los **programas,** en Skype Empresarial **2015** y, a continuación, en Shell de administración de Skype Empresarial **Server.**
    
3. Ejecute:
    
   ```powershell
   Set-CsCallParkServiceMusicOnHoldFile -Service <ServiceID where the Call Park application resides> -Content <Byte >
   ```

    > [!TIP]
    > Use el cmdlet **Get-CsService** para identificar el servicio. Para obtener más información, [consulte Get-CsService](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps). 
  
    En el ejemplo siguiente se muestra cómo obtener el contenido de un archivo, soothingmusic.wma, como matriz de bytes y asignarlo a una variable. A continuación, el archivo de audio se asigna como el archivo de música en espera en Estacionamiento de llamadas. Para obtener más información, [vea Set-CsCallParkServiceMusicOnHoldFile](https://docs.microsoft.com/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps).
    
   ```powershell
   $a = Get-Content -ReadCount 0 -Encoding byte "C:\MoHFiles\soothingmusic.wma"
   Set-CsCallParkServiceMusicOnHoldFile -Service Redmond1-applicationserver-1 -Content $a
   ```

## <a name="see-also"></a>Vea también

[Set-CsCallParkServiceMusicOnHoldFile](https://docs.microsoft.com/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps)
  
[Get-CsService](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps)
