---
title: Mover usuarios de la nube a local
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.custom: ''
description: Obtenga información sobre cómo mover usuarios de Skype empresarial online a local.
ms.openlocfilehash: 0add74a2480f4caed493e6e448427aa2462db714
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2020
ms.locfileid: "43779676"
---
# <a name="move-users-from-the-cloud-to-on-premises"></a>Mover usuarios de la nube a local 

Si es necesario, puede mover a un usuario que se migró previamente desde una ubicación local a la nube (ya sea para usar Skype empresarial online o Teams) de nuevo en local. Para mover usuarios de Skype empresarial online o de modo de TeamsOnly a una implementación local de Skype empresarial Server, use el cmdlet Move-CsUser o el panel de control de Skype empresarial Server, ambos son herramientas locales de. Cuando se mueve a un usuario de nuevo a una implementación local, se debe decidir a qué grupo de servidores se va a mover el usuario.

> [!Important]
> Si el usuario estaba anteriormente en modo TeamsOnly y está usando una versión anterior a la versión de Skype empresarial Server 2015 con CU8, también debe quitar la asignación del modo TeamsOnly de TeamsUpgradePolicy para ese usuario. Los usuarios locales no deben tener Mode = TeamsOnly.  Las versiones posteriores de Skype empresarial Server quitan automáticamente esta asignación. Para obtener más información, consulte [Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy).

## <a name="prerequisites"></a>Requisitos previos

- La organización debe tener Azure AD Connect correctamente configurado y sincronizar todos los atributos relevantes para el usuario, como se describe en [Configure Azure ad Connect](configure-azure-ad-connect.md).
- El usuario que se va a mover de nuevo a local ya debe existir en Active Directory local.
- Es necesario configurar Skype empresarial híbrido, tal y como se describe en [configurar Skype empresarial híbrido](configure-federation-with-skype-for-business-online.md).

## <a name="moving-users-back-to-on-premises"></a>Mover usuarios de nuevo a local

Una vez que se mueve a un usuario de la nube de nuevo a local:

- El usuario interactúa con la implementación de Skype empresarial Server para obtener su funcionalidad. 
- Los contactos que existían en Skype empresarial online o en Microsoft Teams, se migran a Skype empresarial Server. Los dos conjuntos de contactos se combinan y, a continuación, se migran de nuevo a local.  Además, los contactos que ya están preexistentes en Microsoft Teams permanecen en Microsoft Teams.
- Si el usuario también usa Teams, no podrá interoperar con los usuarios de Skype empresarial, ni podrá comunicarse con los usuarios de organizaciones federadas.
- Las reuniones en Skype empresarial online *no* se migran automáticamente de nuevo a local. Los usuarios deben reprogramar sus reuniones o, si lo desea, usar la [herramienta de migración de reuniones](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4).

### <a name="move-users-with-move-csuser"></a>Mover usuarios con Move-CsUser

Move-CsUser está disponible en una ventana local de PowerShell del shell de administración de Skype empresarial. Debe tener privilegios suficientes tanto en el entorno local como en la organización de Office 365, tal y como se describe en [credenciales administrativas necesarias](move-users-between-on-premises-and-cloud.md#required-administrative-credentials). Puede usar una sola cuenta que tenga privilegios en ambos entornos, o puede iniciar una ventana del shell de administración local de Skype empresarial Server con credenciales locales y usar el `-Credential` parámetro para especificar las credenciales de una cuenta de Office 365 con el rol administrativo de Office 365 necesario.

Para mover un usuario a local mediante Move-CsUser:

- Especifique el usuario que se va a mover mediante el parámetro Identity.
- Especifique el parámetro-Target con el nombre de dominio completo del grupo de servidores local deseado en el que se va a hospedar al usuario.
- Si no tiene una cuenta con permisos suficientes tanto en local como en Office 365, use el parámetro-credential para proporcionar una cuenta con permisos suficientes en Office 365.
- Si la cuenta con permisos en Office 365 no termina en "on.microsoft.com", debe especificar el parámetro-HostedMigrationOverrideUrl, con el valor correcto tal como se describe en [required Administrative Credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).

La siguiente secuencia de cmdlet puede usarse para mover un usuario a Skype empresarial Server y se supone que la credencial Office 365 es una cuenta independiente y se proporciona como entrada para el mensaje Get-Credential.

```PowerShell
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
Move-CsUser -Identity username@contoso.com -Target pool.corp.contoso.com -Credential $cred -HostedMigrationOverrideUrl $url
```

### <a name="move-users-with-the-skype-for-business-server-control-panel"></a>Mover usuarios con el panel de control de Skype empresarial Server

1. Abra la aplicación del panel de control de Skype empresarial Server.
2. En el panel de navegación izquierdo, elija **usuarios**.
3. Use **Buscar** para localizar al usuario o usuarios a los que desea retroceder en el entorno local.
4. Seleccione los usuarios y, a continuación, en la lista desplegable **acción** situada encima de la lista, elija **mover usuarios seleccionados a local**.
5. En el asistente, seleccione el grupo de usuarios que va a hospedar al usuario y haga clic en **siguiente**.
6. Si se le solicita, inicie sesión en Office 365, con una cuenta que acabe en. onmicrosoft.com y que tenga permisos suficientes.
7. Haga clic en **siguiente**y, **a continuación, otra vez** más para mover al usuario.
8. Tenga en cuenta que los mensajes de estado sobre aciertos o errores se proporcionan en la parte superior de la aplicación del panel de control principal, no en el asistente.

### <a name="removing-teamsonly-mode"></a>Eliminación del modo TeamsOnly

Si usa una versión anterior a Skype empresarial 2015 con CU8 y el usuario se va a mover de nuevo a local en el modo TeamsOnly, debe quitar la instancia de UpgradeToTeams de antes de `TeamsUpgradePolicy` mover el usuario local. Puede conceder explícitamente una directiva con un modo diferente o simplemente quitar la asignación de directiva existente para que el usuario Use la directiva global (siempre que la directiva global de su inquilino no sea UpgradeToTeams).

Para quitar la asignación del usuario de TeamsUpgradePolicy, ejecute el siguiente cmdlet desde una ventana de PowerShell de Skype empresarial online:

`Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName $null`

Como alternativa, para asignar otra instancia de TeamsUpgradePolicy que no tiene Mode = TeamsOnly, puede especificar el nombre de la instancia deseada como el valor del parámetro PolicyName en el cmdlet. Para ver una lista de las instancias de TeamsUpgradePolicy disponibles, ejecute Get-CsTeamsUpgradePolicy.


## <a name="see-also"></a>Ver también

[Move-CsUser](https://docs.microsoft.com/powershell/module/skype/move-csuser)
