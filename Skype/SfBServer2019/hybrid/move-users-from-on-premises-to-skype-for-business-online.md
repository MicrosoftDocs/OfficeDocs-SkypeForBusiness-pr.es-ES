---
title: Mover usuarios de local a Skype Empresarial Online
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
ms.custom: ''
description: Obtenga información sobre cómo mover los usuarios a Skype para profesionales en línea.
ms.openlocfilehash: 083f2f52fd07439d85d017db9c4b035b8ea326b6
ms.sourcegitcommit: 4dac1994b829d7a7aefc3c003eec998e011c1bd3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/13/2018
ms.locfileid: "27244000"
---
# <a name="move-users-from-on-premises-to-skype-for-business-online"></a>Mover usuarios de local a Skype Empresarial Online

Después de mover un usuario de local a Skype para profesionales en línea, el usuario interactúa con Skype para empresarial en línea para su funcionalidad. Todos los contactos que se encontraba local que estará disponibles en Skype para profesionales en línea, y se actualizan las reuniones existentes que el usuario organizó para el futuro a para que los vínculos señalan Skype para profesionales en línea. Si el usuario está habilitado para conferencias de Audio, las reuniones también incluirá las coordenadas de marcado.  Para mover usuarios de un entorno local a Skype para profesionales en línea, use el cmdlet Move-CsUser o el Skype para el Panel de Control de servidor empresarial, que son herramientas local. 

Antes de mover los usuarios, asegúrese de revisar los [requisitos previos](move-users-between-on-premises-and-cloud.md#prerequisites) para mover los usuarios a la nube.
 
## <a name="move-users-with-move-csuser"></a>Mover usuarios con Move-CsUser 

Move-CsUser está disponible desde un Skype local para la ventana de PowerShell de Shell de administración de negocio. Debe tener privilegios suficientes en ambos el entorno local, así como en el inquilino de Office 365, tal como se describe en [requiere credenciales administrativas](move-users-between-on-premises-and-cloud.md#required-administrative-credentials). Puede usar una única cuenta que tiene privilegios en ambos entornos, o puede iniciar un Skype in situ para la ventana de Shell de administración de servidor empresarial con las credenciales locales y usar el `-Credential` parámetro para especificar las credenciales para una Office 365 cuenta con la función administrativa de Office 365 es necesaria.

Para mover un usuario a online mediante Move-CsUser:

- Especifique el usuario para mover mediante el parámetro Identity.
- Especifique el destino parámetro - con el valor "sipfed.online.lync. <span>com ".
- Si no tiene una cuenta con permisos suficientes en ambos en local y Office 365, use el - parámetro de credenciales para proporcionar una cuenta con permisos suficientes en Office 365.
- Si la cuenta con permisos en Office 365 no termina en "on.microsoft. <span>com ", a continuación, debe especificar el parámetro - HostedMigrationOverrideUrl, con el valor correcto, tal como se describe en [requiere credenciales administrativas](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).

La siguiente secuencia de cmdlet puede usarse para mover un usuario a Skype para profesionales en línea y se da por supuesto la credencial de Office 365 es una cuenta independiente y se proporciona como entrada para el símbolo del sistema de Get-Credential.

```
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
 
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $cred -HostedMigrationOverrideUrl $url
```
## <a name="move-users-with-skype-for-business-server-control-panel"></a>Mover usuarios con Skype para el Panel de Control de servidor empresarial 

1. Abra el Skype para el Control de servidor empresarial aplicación de Panel.
2. En el panel de navegación izquierdo, elija **usuarios**.
3. Use **Buscar** para buscar el usuario o usuarios que le gustaría mover a Skype para profesionales en línea.
4. Seleccione los usuarios y, a continuación, en la lista desplegable **acción** encima de la lista, elija **mover usuarios seleccionados a Skype para profesionales en línea**.
5. En el asistente, haga clic en **siguiente**.
6. Si se le solicita, inicie sesión en Office 365, con una cuenta que termina en. onmicrosoft.com y tiene permisos suficientes.
7. Haga clic en **siguiente**y, a continuación, **siguiente** una vez más para mover el usuario.
8. Tenga en cuenta que los mensajes de estado sobre el éxito o el fracaso se proporcionan en la parte superior de la aplicación de Panel de Control principal, no en el asistente.

## <a name="see-also"></a>Vea también

[Move-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/move-csuser)