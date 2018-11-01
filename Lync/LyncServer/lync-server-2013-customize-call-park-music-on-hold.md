---
title: "Personalizar música de espera para el estacionamiento de llamadas en Lync Server 2013"
TOCTitle: "Personnalis. de l’attente musicale du parcage d’appels dans Lync Server 2013"
ms:assetid: 3d78e6f9-a4ae-49f4-a89f-4515acb49dac
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ688031(v=OCS.15)
ms:contentKeyID: 49889053
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Personalización de la música de espera para el estacionamiento de llamadas en Lync Server 2013

 

_**Última modificación del tema:** 2012-09-10_

Puede especificar su propio archivo de música para utilizar como música en espera, en lugar del archivo de música predeterminado que se suministra con Lync Server 2013. Para personalizar la música en espera, utilice el cmdlet **Set-CsCallParkServiceMusicOnHoldFile**.


> [!NOTE]
> Si personaliza la música en espera y desea la misma música para varios sitios, debe configurar el archivo de música para cada sitio que ejecute el Aplicación de estacionamiento de llamadas.



## Para personalizar el archivo de música

1.  Inicie sesión en un equipo que tenga instalado el Shell de administración de Lync Server como miembro del grupo RTCUniversalServerAdmins o con los derechos de usuario necesarios que se describen en [Delegar permisos de instalación en Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

3.  Ejecute:
    
        Set-CsCallParkServiceMusicOnHoldFile -Service <ServiceID where the Call Park application resides> -Content <Byte[]>
    
    > [!TIP]  
    > Use el cmdlet <strong>Get-CsService</strong> para identificar el servicio. Para obtener más información, consulte <a href="https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsService">Get-CsService</a>.
    
    
    En el ejemplo siguiente se muestra cómo obtener el contenido de un archivo, soothingmusic.wma, como matriz de bytes y asignarlo a una variable. A continuación, el archivo de audio se asigna como el archivo de música en espera en Estacionamiento de llamadas. Para obtener más información, consulte [Set-CsCallParkServiceMusicOnHoldFile](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsCallParkServiceMusicOnHoldFile).
    
        $a = Get-Content -ReadCount 0 -Encoding byte "C:\MoHFiles\soothingmusic.wma"
        Set-CsCallParkServiceMusicOnHoldFile -Service Redmond1-applicationserver-1 -Content $a

## Vea también

#### Otros recursos

[Set-CsCallParkServiceMusicOnHoldFile](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsCallParkServiceMusicOnHoldFile)  
[Get-CsService](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsService)

