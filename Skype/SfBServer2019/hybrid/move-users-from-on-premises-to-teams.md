---
title: Mover usuarios de local a los equipos
ms.author: crowe
author: CarolynRowe
manager: serdars--
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
ms.custom: ''
description: 'Resumen: Obtenga información sobre cómo migrar la configuración de usuario y mover los usuarios a los equipos.'
ms.openlocfilehash: 78f0c49fa2179b4a0aa95a993476c21fb679f489
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2018
ms.locfileid: "26293568"
---
# <a name="move-users-from-on-premises-to-teams"></a>Mover usuarios de local a los equipos

Con Skype para Business Server 2019, puede migrar los usuarios locales a los equipos, tal como se describe en este artículo.

Tenga en cuenta que después de mover los usuarios a los equipos: 
 
- Sus reuniones se migran a Skype para profesionales en línea, y sus contactos se migran a los equipos. 
- Puede unirse a reuniones de Skype a través de la Skype para el cliente enriquecido de negocio (no le pide a los usuarios para cada hora de inicio de sesión) o a través de la aplicación de las reuniones de Skype (requiere una descarga única e inicio de sesión). Cuando un usuario hace clic en un Skype para el vínculo de la reunión de negocio dentro de los equipos, se iniciará la reunión en la aplicación correspondiente.

- En el móvil, los usuarios podrán unirse a Skype existente para reuniones de negocio mediante la aplicación nativa sólo.

> [!NOTE]
> Después de que un usuario se mueve a modo de TeamsOnly, el usuario está hospedado en Skype para profesionales en línea.

## <a name="prerequisites-for-moving-on-premises-users-to-teams"></a>Requisitos previos para mover usuarios locales a los equipos 

En esta sección se describe los requisitos previos para mover los usuarios locales a los equipos. Debe:
- [Configurar conectividad híbrida](#set-up-hybrid-connectivity) (si no lo ha hecho ya)
- [Notifique a los usuarios de la mover a los equipos](#notify-your-users-of-the-move-to-teams) (opcional)
- [Asegúrese de que los usuarios tienen una licencia válida](#make-sure-your-users-have-a-valid-license)
- [Debe tener en cuenta los requisitos de configuración de voz](#voice-configuration-requirements)
- [Asignar una directiva de actualización de los equipos](#assign-a-teams-upgrade-policy) (opcional)

## <a name="set-up-hybrid-connectivity"></a>Configurar conectividad híbrida
Antes de migrar los usuarios, si aún no lo ha hecho, debe asegurarse de que ha configurado la conectividad híbrida entre su Skype para entorno local de Business Server y Skype para profesionales en línea. Conectividad híbrida requiere la sincronización de Active Directory, configuración de federación y así sucesivamente. Para obtener más información, vea [Planear la conectividad híbrida](plan-hybrid-connectivity.md) y [conectividad de la configuración híbrida](configure-hybrid-connectivity.md).

## <a name="notify-your-users-of-the-move-to-teams"></a>Notifique a los usuarios de la mover a los equipos 
Esto es un paso opcional, pero que se deben tener en cuenta. Para notificar a los usuarios de la actualización de los equipos pendiente, puede usar los cmdlets de TeamsUpgradePolicy y TeamsUpgradeConfiguration local. También puede configurar la descarga automática silenciosa de los equipos en segundo plano antes de la actualización (solo para clientes de Win32). 

Por ejemplo, para notificar a los usuarios que se van a actualizar a los equipos, use el cmdlet de TeamsUpgradePolicy local con el parámetro - NotifySbUser. Puede establecer la directiva en un nivel global, de sitio, grupo o usuario. El comando siguiente, se crea y concede una directiva de nivel de usuario:
 
```
New-CsTeamsUpgradePolicy -Identity UpgradeNotice -NotifySfbUser $true 
Grant-CsTeamsUpgradePolicy -Identity user01 -PolicyName “UpgradeNotice”
```

Puede comprobar esta directiva mediante el cmdlet Get-csTeamsUpgradePolicy.

Los usuarios verán una notificación de la inminente mover a los equipos. Se produce la notificación en Win32, Mac, Mobile y clientes Web (con la versión correcta).

Puede especificar la descarga automática de los equipos (para los clientes de Win32) para los usuarios que se está actualizando mediante el cmdlet de TeamsUpgradeConfiguration de local con el parámetro DownloadTeams. Establecer esta directiva en el nivel de inquilino, y que se pueden aplicar en un sitio global y del nivel de grupo de servidores. Por ejemplo, el comando siguiente establece la directiva en el nivel de sitio:

```
New-CsTeamsUpgradeConfiguration -Identity “site:redmond1” 
```

De forma predeterminada, el valor de DownloadTeams es True, pero también se debe establecer NotifySfbUser en True para habilitar los equipos para un usuario determinado. 

## <a name="make-sure-your-users-have-a-valid-license"></a>Asegúrese de que los usuarios tienen una licencia válida  
Antes de la migración, el usuario local se debe proporcionar una licencia válida, como se indica a continuación:

-   Usuario debe tener una licencia de los equipos.
-   Si el usuario está configurado para usar local Enterprise Voice, deben tener una licencia de voz en línea al mover. 
-   Si el usuario está configurado para conferencias de acceso telefónico local, deben tener una licencia para el sistema telefónico (nube PBX).

## <a name="voice-configuration-requirements"></a>Requisitos de configuración de voz

Si los usuarios local tienen voz local, tiene dos opciones:

-  **Migrar los usuarios con funciones de telefonía.** Los usuarios pueden realizar y recibir llamadas con el cliente de los equipos.  Puede elegir llamar a planeación de Microsoft o enrutamiento directo para conectarse a los servicios de telefonía para los equipos.  

    -  Llamar a planeación de Microsoft proporciona una solución de voz totalmente la en nube. Para obtener más información acerca de una llamada a planeación de Microsoft, consulte (vínculo próximamente). 
    -  Enrutamiento directo le permite usar prácticamente cualquier tronco RTC y se puede configurar la interoperabilidad entre equipos de telefonía que pertenecen al cliente y el sistema de teléfono de Microsoft.  Para obtener más información, vea [Planear el enrutamiento directo](https://docs.microsoft.com/en-us/MicrosoftTeams/direct-routing-plan) y [Configurar el enrutamiento directo](https://docs.microsoft.com/en-us/MicrosoftTeams/direct-routing-configure).

-  **Migrar los usuarios sin funciones de telefonía.** Si migra a los usuarios sin mantener funciones de telefonía, asegúrese de que los usuarios tienen licencias adecuadas en la nube. 

## <a name="assign-a-teams-upgrade-policy"></a>Asignar una directiva de actualización de los equipos  
Puede usar herramientas en línea para administrar las directivas de usuario, por ejemplo, para controlar el enrutamiento de los mensajes entrantes y las llamadas. Para obtener más información, vea (vínculo próximamente).

## <a name="move-on-premises-users-to-teams"></a>Mover usuarios locales a los equipos

Puede mover los usuarios locales a los equipos mediante el uso de los cmdlets de PowerShell o mediante el Skype para el Panel de Control de Business Server 2019.

### <a name="move-users-by-using-powershell"></a>Mover usuarios mediante el uso de PowerShell
Para mover los usuarios a los equipos mediante el uso de PowerShell, debe usar el cmdlet Move-CsUser con el parámetro moveToTeams como se indica a continuación:

```
Move-CsUser -Identity user0 -Target sipfed.online.lync.com -moveToTeams -credentials $cred. 
```

($cred = get-credenciales. Debe proporcionar credenciales de administrador de Office 365.)

> [!NOTE]
> Este comando establece la TeamsInteropPolicy a los equipos y la TeamsUpgradePolicy al modo de TeamsOnly. 
 
Una vez realizada correctamente la mover a los equipos, Skype del usuario para Business client mostrará el mensaje siguiente: 

![Se ha completado correctamente la migración a los mensajes de los equipos](../media/teams-upgrade-complete-message.png)

Tenga en cuenta que Skype para la empresa ya no estará disponible para el usuario excepto al unirse a una reunión. 

En algunos casos poco frecuentes, al mover los usuarios a los equipos, es posible que desee invalidar la conferencia de acceso telefónico y la funcionalidad de voz en nube. Puede hacerlo mediante el uso de los siguientes parámetros con el comando Move-CsUser:
- **BypassAudioConferencingCheck:** Si un usuario tiene telefónico habilitado para local, el usuario también debe tener una licencia de AudioConf asignada en Office 365 antes de migrar. Una vez que se migran a la nube, el usuario se aprovisionará para conferencias de audio en la nube. Si, por alguna razón, desea mover a un usuario a la nube, pero no use la funcionalidad de conferencia de audio, se puede invalidar mediante la especificación de este parámetro.
- **ByPassEnterpriseVoice:** Si un usuario tiene Enterprise Voice habilitado para local, el usuario debe tener una licencia de Enterprise Voice asignada en Office 365 antes de migrar. Después de la migración a la nube, el usuario se aprovisionará para voz en la nube. Si, por alguna razón, desea mover a un usuario a la nube, pero no usar la funcionalidad de voz de la nube, se puede invalidar la voz de la nube mediante la especificación de este parámetro.
 
### <a name="move-users-by-using-the-skype-for-business-server-control-panel"></a>Mover usuarios mediante el Skype para el Panel de Control de servidor empresarial 

Para mover los usuarios a los equipos mediante el Skype para el Panel de Control:

1. Abra el Skype para el Panel de Control e inicie sesión su cuenta de Office 365.

2. Seleccione **los usuarios** en el panel de navegación izquierdo y seleccione los usuarios a migrar. 
     
3. En el menú **acción** , elija **mover usuarios seleccionados a los equipos**. 

    ![Al hacer clic en siguiente para confirmar la migración](../media/migration-confirmation.png)
    
4. Haga clic en **siguiente** para confirmar la migración. 

Después de que el usuario se mueva a los equipos, verá las confirmaciones similar al siguiente:

![Mover la confirmación de los usuarios](../media/move-user-confirmation.png)
<br/><br/>
![Mensaje que se han movido a los usuarios](../media/users-moved-successfully.png)

Si el movimiento no se realizó correctamente, verá un mensaje similar al siguiente:

![Mensajes que no se pudo mover el usuario](../media/users-not-moved.png)
