---
title: Mover usuarios locales a Skype Empresarial Online
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
description: Obtenga información sobre cómo mover usuarios a Skype Empresarial Online.
ms.openlocfilehash: 8c028044fe8c4b808a419503091f9ecf767cfe4d
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237966"
---
# <a name="move-users-from-on-premises-to-skype-for-business-online"></a>Mover usuarios locales a Skype Empresarial Online

Después de mover un usuario local a Skype Empresarial Online, el usuario interactúa con Skype Empresarial Online para su funcionalidad. Los contactos que existían localmente estarán disponibles en Skype Empresarial Online y las reuniones existentes que el usuario haya organizado para el futuro se actualizarán para que los vínculos apunten a Skype Empresarial Online. Si el usuario está habilitado para Audioconferencia, las reuniones también incluirán coordenadas de acceso telefónico local.  Para mover usuarios de un entorno local a Skype Empresarial Online, use el cmdlet Move-CsUser o el Panel de control de Skype Empresarial Server, que son herramientas locales. 

[!INCLUDE [sfbo-retirement-skype](../../Hub/includes/sfbo-retirement.md)]

Antes de mover usuarios, asegúrese de revisar los [requisitos previos](move-users-between-on-premises-and-cloud.md#prerequisites) para mover usuarios a la nube.
 
## <a name="move-users-with-move-csuser"></a>Mover usuarios con Move-CsUser 

Move-CsUser está disponible desde una ventana de PowerShell Skype Empresarial shell de administración local. Debe tener privilegios suficientes tanto en el entorno local como en la organización Microsoft 365/Office 365, como se describe en [Credenciales administrativas necesarias.](move-users-between-on-premises-and-cloud.md#required-administrative-credentials) Puede usar una sola cuenta que tenga privilegios en ambos entornos o puede iniciar una ventana local del Shell de administración de Skype Empresarial Server con credenciales locales y usar el parámetro para especificar las credenciales de una cuenta de Microsoft 365 o Office 365 con el rol administrativo `-Credential` necesario.

Para mover un usuario a línea mediante Move-CsUser:

- Especifique el usuario que se moverá mediante el parámetro Identity.
- Especifique el parámetro -Target con el valor "sipfed.online.lync. <span> com".
- Si no tiene una cuenta con permisos suficientes tanto en el entorno local como en el Office 365, use el parámetro -credential para proporcionar a una cuenta permisos suficientes en Office 365.
- Si la cuenta con permisos en Office 365 no termina en ".onmicrosoft. <span> com", a continuación, debe especificar el parámetro -HostedMigrationOverrideUrl, con el valor correcto como se describe en [Credenciales administrativas necesarias](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).

La siguiente secuencia de cmdlets se puede usar para mover un usuario a Skype Empresarial Online. Se supone que la credencial Microsoft 365 o Office 365 es una cuenta independiente y se proporciona como entrada para el Get-Credential solicitud.

```PowerShell
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
 
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $cred -HostedMigrationOverrideUrl $url
```

Si la cuenta de administrador está habilitada para MFA (autenticación multifactor), no especifique el parámetro -Credential. Se pedirá al administrador credenciales.

## <a name="move-users-with-skype-for-business-server-control-panel"></a>Mover usuarios con Skype Empresarial Server panel de control 

1. Abre la aplicación Skype Empresarial Server panel de control.
2. En la navegación izquierda, elija **Usuarios**.
3. Use **Buscar** para localizar los usuarios que desea mover a Skype Empresarial Online.
4. Seleccione los usuarios y, a  continuación, en el desplegable Acción situado encima de la lista, elija Mover usuarios seleccionados **a Skype Empresarial Online**.
5. En el asistente, haga clic en **Siguiente**.
6. Si se le solicita, inicie sesión Microsoft 365 o Office 365 una cuenta que termine en .onmicrosoft.com y tenga permisos suficientes.
7. Haga **clic en** Siguiente y, a continuación, en Siguiente una vez más para mover al usuario. 
8. Ten en cuenta que los mensajes de estado relacionados con el éxito o el error se proporcionan en la parte superior de la aplicación principal del Panel de control, no en el asistente.

## <a name="see-also"></a>Vea también

[Move-CsUser](/powershell/module/skype/move-csuser)