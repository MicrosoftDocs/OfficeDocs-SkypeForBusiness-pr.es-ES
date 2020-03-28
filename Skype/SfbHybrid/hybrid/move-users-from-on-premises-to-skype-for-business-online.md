---
title: Mover usuarios locales a Skype para empresas Online
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
description: Obtenga información sobre cómo mover usuarios a Skype empresarial online.
ms.openlocfilehash: 6d8e8fa08c124717a0d61a758bdb60f2dd24c410
ms.sourcegitcommit: e710bb8dbbd084912cbf509896515a674ab5e19f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2020
ms.locfileid: "43033384"
---
# <a name="move-users-from-on-premises-to-skype-for-business-online"></a>Mover usuarios locales a Skype para empresas Online

Después de mover un usuario de local a Skype empresarial online, el usuario interactúa con Skype empresarial online para su funcionalidad. Los contactos que existían de forma local estarán disponibles en Skype empresarial online y las reuniones existentes organizadas por el usuario para el futuro se actualizan para que los vínculos apunten a Skype empresarial online. Si el usuario está habilitado para conferencias de audio, las reuniones también incluirán coordenadas de acceso telefónico local.  Para mover usuarios de un entorno local a Skype empresarial online, use el cmdlet Move-CsUser o el panel de control de Skype empresarial Server, ambos son herramientas locales. 

Antes de mover los usuarios, asegúrese de revisar los [requisitos previos](move-users-between-on-premises-and-cloud.md#prerequisites) para mover usuarios a la nube.
 
## <a name="move-users-with-move-csuser"></a>Mover usuarios con Move-CsUser 

Move-CsUser está disponible en una ventana local de PowerShell del shell de administración de Skype empresarial. Debe tener privilegios suficientes tanto en el entorno local como en el inquilino de Office 365, tal y como se describe en [credenciales administrativas necesarias](move-users-between-on-premises-and-cloud.md#required-administrative-credentials). Puede usar una sola cuenta que tenga privilegios en ambos entornos, o puede iniciar una ventana del shell de administración local de Skype empresarial Server con credenciales locales y usar el `-Credential` parámetro para especificar las credenciales de una cuenta de Office 365 con el rol administrativo de Office 365 necesario.

Para mover un usuario a online mediante Move-CsUser:

- Especifique el usuario que se va a mover mediante el parámetro Identity.
- Especifique el parámetro-Target con el valor "sipfed. online. Lync. <span>com ".
- Si no tiene una cuenta con permisos suficientes en local y Office 365, use el parámetro-credential para proporcionar una cuenta con permisos suficientes en Office 365.
- Si la cuenta con permisos en Office 365 no termina ". en Microsoft. <span>com ", debe especificar el parámetro-HostedMigrationOverrideUrl, con el valor correcto tal como se describe en [credenciales administrativas necesarias](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).

La siguiente secuencia de cmdlet se puede usar para mover un usuario a Skype empresarial online y asume que la credencial Office 365 es una cuenta independiente y se proporciona como entrada para el mensaje Get-Credential.

```PowerShell
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
 
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $cred -HostedMigrationOverrideUrl $url
```

Si la cuenta de administrador es MFA (multi-factor Authentication) habilitada, no especifique el parámetro-Credential. Se pedirán las credenciales al administrador.

## <a name="move-users-with-skype-for-business-server-control-panel"></a>Mover usuarios con el panel de control de Skype empresarial Server 

1. Abra la aplicación del panel de control de Skype empresarial Server.
2. En el panel de navegación izquierdo, elija **usuarios**.
3. Use **Buscar** para localizar al usuario o usuarios que desea mover a Skype empresarial online.
4. Seleccione el usuario o usuarios y, a continuación, en la lista desplegable de **acciones** situada encima de la lista, elija **mover usuarios seleccionados a Skype empresarial online**.
5. En el asistente, haga clic en **Siguiente**.
6. Si se le solicita, inicie sesión en Office 365, con una cuenta que acabe en. onmicrosoft.com y que tenga permisos suficientes.
7. Haga clic en **siguiente**y, **a continuación, otra vez** más para mover al usuario.
8. Tenga en cuenta que los mensajes de estado sobre aciertos o errores se proporcionan en la parte superior de la aplicación del panel de control principal, no en el asistente.

## <a name="see-also"></a>Consulte también

[Move-CsUser](https://docs.microsoft.com/powershell/module/skype/move-csuser)
