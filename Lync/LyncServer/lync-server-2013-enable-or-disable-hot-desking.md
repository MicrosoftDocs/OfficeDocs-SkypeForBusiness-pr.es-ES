---
title: Habilitar o deshabilitar los terminales compartidos
TOCTitle: Habilitar o deshabilitar los terminales compartidos
ms:assetid: 93a7fed6-f61a-4b41-9336-a8320afa87cf
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ994057(v=OCS.15)
ms:contentKeyID: 52061684
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Habilitar o deshabilitar los terminales compartidos

 

_**Última modificación del tema:** 2013-02-20_

Puede configurar teléfonos de área común como *teléfonos “hot-desk”*. Con los teléfonos hot-desk, los usuarios pueden iniciar sesión en su propia cuenta de usuario y, después de iniciar sesión, usar las características de Lync Server y su propia configuración de perfil de usuario. El hot-desk se administra con directivas de cliente: para habilitar o deshabilitar el hot-desk, es necesario cambiar las directivas de cliente que se usan en los teléfonos de área común. Para más información sobre cómo determinar las directivas de conferencia que se han asignado a sus teléfonos de área común, consulte [Ver la información del teléfono de área común](lync-server-2013-view-common-area-phone-information.md).

Use el parámetro EnableHotdesking del cmdlet **New-CSClientPolicy** o el cmdlet **Set-CSClientPolicy** para habilitar o deshabilitar el hot-desk en un teléfono del modo siguiente. Ejecute estos cmdlets desde el Shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para más información sobre el uso de una conexión remota de Windows PowerShell a Lync Server, consulte el artículo del blog sobre Windows PowerShell de Lync Server "Inicio rápido: Administración de Microsoft Lync Server 2010 con PowerShell remoto" en [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).


## Activación de hot-desk

  - Para habilitar el hot-desk en un teléfono de área común, es necesario cambiar la directiva de cliente que se ha asignado a ese teléfono (o grupo de teléfonos).
    
    Una vez identificada la directiva que hay que cambiar, el paso siguiente es usar el cmdlet **Set-CsClientPolicy** para establecer el parámetro EnableHotdesking en True. Por ejemplo:
    
        Set-CsClientPolicy -Identity "CommonAreaPhonePolicy" - EnableHotdesking $True

  - Si lo desea, puede usar el cmdlet **New-CsClientPolicy** para crear una directiva nueva que habilite el hot-desk. Por ejemplo:
    
        New-CsClientPolicy -Identity "NewCommonAreaPhonePolicy" - EnableHotdesking $True

> [!IMPORTANT]  
> Después de crear esta directiva, habrá que asignarla a los teléfonos de área común apropiados. Para más información, consulte <a href="lync-server-2013-assign-policies-to-a-common-area-phone.md">Asignar directivas a un teléfono de área común</a>.



## Desactivación de hot-desk

  - Para deshabilitar el hot-desk en un teléfono de área común, restablezca el parámetro EnableHotdesking del cmdlet **Set-CsClientPolicy** al valor predeterminado de False. Por ejemplo:
    
        Set-CsClientPolicy -Identity "CommonAreaPhonePolicy" - EnableHotdesking $False

Para más información, consulte los temas de ayuda referentes al cmdlet [New-CsClientPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsClientPolicy) y al cmdlet [Set-CsClientPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClientPolicy).

