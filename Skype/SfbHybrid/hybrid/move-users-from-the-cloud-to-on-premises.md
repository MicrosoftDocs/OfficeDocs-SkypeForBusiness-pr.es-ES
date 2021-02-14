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
description: Obtenga información sobre cómo mover usuarios de Skype Empresarial Online a local.
ms.openlocfilehash: 64a5561fda35669be6ce7718c3ec037dcb8b9264
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221340"
---
# <a name="move-users-from-the-cloud-to-on-premises"></a>Mover usuarios de la nube a local 

Si es necesario, puede mover un usuario que se migró previamente de local a la nube (ya sea usando Skype Empresarial Online o Solo Teams) de nuevo a local. Para volver a mover usuarios del modo Skype Empresarial Online o TeamsOnly a una implementación local de Skype Empresarial Server, use el cmdlet Move-CsUser o el Panel de control de Skype Empresarial Server, que son herramientas locales. Cuando mueve un usuario de vuelta a una implementación local, debe decidir a qué grupo mover el usuario.

> [!Important]
> Si el usuario estaba anteriormente en modo TeamsOnly y está usando una versión anterior a Skype Empresarial Server 2015 con CU8, también debe quitar la asignación de modo TeamsOnly de TeamsUpgradePolicy para ese usuario. Los usuarios locales no deben tener mode= TeamsOnly.  Las versiones posteriores de Skype Empresarial Server quitan automáticamente esta asignación. Para obtener más información, [vea Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy).

## <a name="prerequisites"></a>Requisitos previos

- La organización debe tener Azure AD Connect configurado correctamente y estar sincronizando todos los atributos relevantes para el usuario, como se describe en [Configurar Azure AD Connect](configure-azure-ad-connect.md).
- El usuario que se va a mover de nuevo en línea a local ya debe existir en Active Directory local.
- Skype Empresarial híbrido debe configurarse, como se describe en [Configurar Skype Empresarial híbrido.](configure-federation-with-skype-for-business-online.md)

## <a name="moving-users-back-to-on-premises"></a>Mover a los usuarios de nuevo a la implementación local

Una vez que mueva un usuario de la nube de vuelta a la implementación local:

- El usuario interactúa con la implementación de Skype Empresarial Server para su funcionalidad. 
- Los contactos que existían en Skype Empresarial Online o Teams se migran a Skype Empresarial Server. Los dos conjuntos de contactos se combinan y, a continuación, se migran de nuevo a local.  Además, los contactos que ya existen en Teams permanecen en Teams.
- Si el usuario también usa Teams, no podrá interoperar con usuarios de Skype Empresarial ni podrá comunicarse con usuarios de organizaciones federadas.
- Las reuniones en Skype Empresarial Online *no* se migran automáticamente de nuevo a local. Los usuarios deben volver a programar sus reuniones o, si lo desean, usar la Herramienta [de migración de reuniones.](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)

### <a name="move-users-with-move-csuser"></a>Mover usuarios con Move-CsUser

Move-CsUser está disponible desde una ventana local de PowerShell del Shell de administración de Skype Empresarial. Debe tener privilegios suficientes tanto en el entorno local como en la organización de servicios en la nube (Microsoft 365 u Office 365), como se describe en Credenciales administrativas [necesarias.](move-users-between-on-premises-and-cloud.md#required-administrative-credentials) Puede usar una sola cuenta que tenga privilegios en ambos entornos o puede iniciar una ventana local del Shell de administración de Skype Empresarial Server con credenciales locales y usar el parámetro para especificar las credenciales de una cuenta de `-Credential` Microsoft 365 u Office 365 con el rol administrativo necesario.

Para mover un usuario a local mediante Move-CsUser:

- Especifique el usuario que se moverá mediante el parámetro Identity.
- Especifique el parámetro -Target con el nombre de dominio completo del grupo local deseado que hospedará al usuario.
- Si no tiene una cuenta con permisos suficientes tanto en el servicio local como en el servicio en la nube (Microsoft 365 u Office 365), use el parámetro -credential para proporcionar a una cuenta permisos suficientes en Microsoft 365 u Office 365.
- Si la cuenta con permisos en Microsoft 365 u Office 365 no termina en "on.microsoft.com", debe especificar el parámetro -HostedMigrationOverrideUrl, con el valor correcto como se describe en Credenciales administrativas [necesarias.](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)

La siguiente secuencia de cmdlets se puede usar para mover un usuario a Skype Empresarial Server y se supone que la credencial de Microsoft 365 u Office 365 es una cuenta independiente y se proporciona como entrada para el mensaje Get-Credential usuario.

```PowerShell
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
Move-CsUser -Identity username@contoso.com -Target pool.corp.contoso.com -Credential $cred -HostedMigrationOverrideUrl $url
```

### <a name="move-users-with-the-skype-for-business-server-control-panel"></a>Mover usuarios con el Panel de control de Skype Empresarial Server

1. Abra la aplicación Panel de control de Skype Empresarial Server.
2. En el panel de navegación izquierdo, elija **Usuarios.**
3. Use **Buscar** para localizar los usuarios a los que desea volver a la implementación local.
4. Seleccione los usuarios y, a  continuación, en el desplegable Acción situado encima de la lista, elija Mover usuarios seleccionados **a local.**
5. En el asistente, seleccione el grupo de usuarios que hospedará al usuario y haga clic en **Siguiente.**
6. Si se le solicita, inicie sesión en Microsoft 365 u Office 365 con una cuenta que termine en .onmicrosoft.com y tenga permisos suficientes.
7. Haga **clic en** Siguiente y, a **continuación,** en Siguiente una vez más para mover el usuario.
8. Tenga en cuenta que los mensajes de estado relacionados con el éxito o el error se proporcionan en la parte superior de la aplicación principal del Panel de control, no en el asistente.

### <a name="removing-teamsonly-mode"></a>Quitar el modo TeamsOnly

Si está usando una versión anterior a Skype Empresarial 2015 con CU8 y el usuario se está trasladando de nuevo a local en modo TeamsOnly, debe quitar la instancia UpgradeToTeams antes de mover el usuario `TeamsUpgradePolicy` localmente. Puede conceder explícitamente una directiva con un modo diferente o simplemente quitar la asignación de directiva existente para que ese usuario use la directiva global (siempre que la directiva global de su espacio empresarial no sea UpgradeToTeams).

Para quitar la asignación del usuario de TeamsUpgradePolicy, ejecute el siguiente cmdlet desde una ventana de PowerShell de Skype Empresarial Online:

`Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName $null`

Como alternativa, para asignar otra instancia de TeamsUpgradePolicy que no tiene mode=TeamsOnly, puede especificar el nombre de la instancia deseada como el valor del parámetro PolicyName en el cmdlet. Para ver una lista de las instancias disponibles de TeamsUpgradePolicy, ejecute Get-CsTeamsUpgradePolicy.


## <a name="see-also"></a>Vea también

[Move-CsUser](https://docs.microsoft.com/powershell/module/skype/move-csuser)
