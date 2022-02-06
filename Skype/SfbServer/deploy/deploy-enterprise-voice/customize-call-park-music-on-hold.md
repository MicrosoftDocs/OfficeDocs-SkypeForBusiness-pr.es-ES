---
title: Personalizar la música de estacionamiento de llamadas en espera enSkype para empresas
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection:
  - IT_Skype16
  - Strat_SB_Admin
ms.custom: null
ms.assetid: 3d78e6f9-a4ae-49f4-a89f-4515acb49dac
description: Personalice la música de estacionamiento de llamadas en espera en Skype Empresarial Server Telefonía IP empresarial.
---

# <a name="customize-call-park-music-on-hold-inskype-for-business"></a>Personalizar la música de estacionamiento de llamadas en espera enSkype para empresas
 
Personalice la música de estacionamiento de llamadas en espera en Skype Empresarial Server Telefonía IP empresarial.
  
Puede especificar su propio archivo de música para usarlo para la música en espera, en lugar del archivo de música predeterminado que se incluye con Skype Empresarial Server. Para personalizar la música en espera, utilice el cmdlet **Set-CsCallParkServiceMusicOnHoldFile**.
  
> [!NOTE]
> Si personaliza la música en espera y desea la misma música para varios sitios, debe configurar el archivo de música para cada sitio que ejecute la aplicación estacionamiento de llamadas. 
  
### <a name="to-customize-the-music-file"></a>Para personalizar el archivo de música

1. Inicie sesión en el equipo en el que Skype Empresarial Server Shell de administración esté instalado como miembro del grupo RTCUniversalServerAdmins o con los derechos de usuario necesarios, tal como se describe en Permisos de configuración **delegados**.
    
2. Inicie el Shell Skype Empresarial Server administración: haga clic en **Inicio, todos** los **programas,** **Skype Empresarial 2015** y, a continuación, haga clic **en Skype Empresarial Server Shell de administración**.
    
3. Ejecute: 
    
   ```powershell
   Set-CsCallParkServiceMusicOnHoldFile -Service <ServiceID where the Call Park application resides> -Content <Byte >
   ```

    > [!TIP]
    > Use el cmdlet **Get-CsService** para identificar el servicio. Para obtener más información, [vea Get-CsService](/powershell/module/skype/get-csservice?view=skype-ps). 
  
    En el ejemplo siguiente se muestra cómo obtener el contenido de un archivo, soothingmusic.wma, como matriz de bytes y asignarlo a una variable. A continuación, el archivo de audio se asigna como el archivo de música en espera en Estacionamiento de llamadas. Para obtener más información, [vea Set-CsCallParkServiceMusicOnHoldFile](/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps).
    
   ```powershell
   $a = Get-Content -ReadCount 0 -Encoding byte "C:\MoHFiles\soothingmusic.wma"
   Set-CsCallParkServiceMusicOnHoldFile -Service Redmond1-applicationserver-1 -Content $a
   ```

## <a name="see-also"></a>Vea también

[Set-CsCallParkServiceMusicOnHoldFile](/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps)
  
[Get-CsService](/powershell/module/skype/get-csservice?view=skype-ps)