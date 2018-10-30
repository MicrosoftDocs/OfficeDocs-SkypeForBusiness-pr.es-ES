---
title: Configurar el modo de privacidad de presencia mejorada
TOCTitle: Configurar el modo de privacidad de presencia mejorada
ms:assetid: e7a6b873-486d-4dfb-a967-c48f61f237f3
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg399028(v=OCS.15)
ms:contentKeyID: 48277009
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurar el modo de privacidad de presencia mejorada

 

_**Última modificación del tema:** 2016-12-08_

Con el modo de privacidad de presencia mejorada, los usuarios pueden restringir su información de presencia para que solo puedan verla los contactos incluidos en su lista de contactos de Lync 2013. El parámetro EnablePrivacyMode de los cmdlets **New-CsPrivacyConfiguration** y **Set-CsPrivacyConfiguration** controla esta opción. Si EnablePrivacyMode está definido en True, la opción para restringir la información de presencia a los contactos pasa a estar disponible en las opciones de estado de Lync 2013. Si EnablePrivacyMode está definido en False, los usuarios pueden elegir si quieren permitir que todo el mundo vea siempre su información de presencia o adaptarse a los posibles cambios que el administrador realice en el modo de privacidad.

> [!IMPORTANT]  
> La configuración de privacidad de Lync 2013 y Lync 2010 no se respeta en versiones anteriores (Microsoft Office Communicator 2007 R2 o Microsoft Office Communicator 2007). Si versiones anteriores de Office Communicator pueden iniciar sesión, personas no autorizadas podrían ver información de contacto, imágenes o estados de usuario de Lync 2013. Asimismo, la configuración de privacidad de un usuario de Lync 2013 se restablece si este inicia sesión más adelante con una versión anterior de Communicator.<br />
> Por estas razones, en un escenario de migración, antes de habilitar el modo de privacidad de presencia mejorada:
> <ul>
> <li><p>Compruebe que todos los usuarios tengan Lync 2013 instalado.</p></li>
> <li><p>Defina una regla de directiva de versiones de cliente para impedir que versiones anteriores de Communicator inicien sesión.</p></li>
> </ul>


## Para habilitar el modo de privacidad de presencia mejorada

1.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

2.  Ejecute el siguiente comando:
    
        Get-CsPrivacyConfiguration | Set-CsPrivacyConfiguration -EnablePrivacyMode $True
    
    Este comando habilita el modo de privacidad para todos los parámetros de privacidad que se encuentran actualmente en uso en la organización.

## Vea también

#### Otros recursos

[Get-CsPrivacyConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsPrivacyConfiguration)  
[New-CsPrivacyConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsPrivacyConfiguration)  
[Set-CsPrivacyConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsPrivacyConfiguration)

