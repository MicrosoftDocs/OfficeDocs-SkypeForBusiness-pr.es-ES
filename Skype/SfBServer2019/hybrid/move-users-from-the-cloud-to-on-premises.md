---
title: Mover usuarios de la nube para local
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
ms.custom: ''
description: Obtenga información sobre cómo mover usuarios de Skype para empresarial en línea para local.
ms.openlocfilehash: fadb3a485cac691a97f0786aea78000b6b48c344
ms.sourcegitcommit: 4dac1994b829d7a7aefc3c003eec998e011c1bd3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/13/2018
ms.locfileid: "27247731"
---
# <a name="move-users-from-the-cloud-to-on-premises"></a>Mover usuarios de la nube para local 

Si es necesario, puede mover un usuario que se migró anteriormente desde local a la nube (si usa Skype para profesionales en línea o sólo los equipos) de vuelta al local. Para mover los usuarios desde cualquier Skype para el modo en línea de negocio o TeamsOnly a una implementación local de Skype para Business Server, use el cmdlet Move-CsUser o el Skype para el Panel de Control de servidor empresarial, que son herramientas local. Al mover un usuario de vuelta a una implementación local, debe decidir qué grupo de servidores al que mover el usuario.

> [!Important]
> Si el usuario estaba previamente en modo de TeamsOnly y está utilizando una versión anterior a Skype para Business Server 2015 con CU8, también debe quitar la asignación de modo TeamsOnly de TeamsUpgradePolicy de dicho usuario. Local de los usuarios no deben tener modo = TeamsOnly.  Las versiones posteriores de Skype para Business Server quitan automáticamente esta asignación. Para obtener más detalles, vea [Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/grant-csteamsupgradepolicy).

## <a name="prerequisites"></a>Requisitos previos

- La organización debe tener Azure Connect AD configurado correctamente y se está sincronizando los todos los atributos relevantes para el usuario, tal como se describe en [Configurar Azure AD conectar](configure-azure-ad-connect.md).
- El usuario que se van a mover desde back online a local ya debe existir en el Active Directory local.
- Skype para entornos híbridos de negocio debe configurarse como se describe en [Configurar Skype para entornos híbridos de negocio](configure-federation-with-skype-for-business-online.md).

## <a name="moving-users-back-to-on-premises"></a>Mover a los usuarios hacer una copia local

Una vez que mover un usuario de la nube volver a local:

- El usuario interactúa con su Skype para la implementación de servidor empresarial para su funcionalidad. 
- Todos los contactos que se encontraba en Skype para profesionales en línea que se migran a Skype para Business Server. Actualmente, los contactos que se encuentran en los equipos no se migran a local.
- Si el usuario utiliza también los equipos, no tendrá la capacidad para interoperar con Skype para usuarios profesionales ni podrán comunicarse con los usuarios de organizaciones federadas.
- Reuniones en Skype para profesionales en línea son *no* automáticamente volver a migrar a local. Los usuarios deben cualquiera volver a programar sus reuniones o, si lo desea, use la [Herramienta de migración de la reunión](https://support.office.com/en-us/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4).

### <a name="move-users-with-move-csuser"></a>Mover usuarios con Move-CsUser

Move-CsUser está disponible desde un Skype local para la ventana de PowerShell de Shell de administración de negocio. Debe tener privilegios suficientes en el entorno local así como el inquilino de Office 365, tal como se describe en [requiere credenciales administrativas](move-users-between-on-premises-and-cloud.md#required-administrative-credentials). Puede usar una única cuenta que tiene privilegios en ambos entornos, o puede iniciar un Skype in situ para la ventana de Shell de administración de servidor empresarial con las credenciales locales y usar el `-Credential` parámetro para especificar las credenciales para una Office 365 cuenta con la función administrativa de Office 365 es necesaria.

Para mover a un usuario local con Move-CsUser:

- Especifique el usuario para mover mediante el parámetro Identity.
- Especifique el destino parámetro - con el nombre de dominio completo del grupo de servidores local que desee que se va a hospedar el usuario.
- Si no tiene una cuenta con permisos suficientes en ambos en local y Office 365, use el - parámetro de credenciales para proporcionar una cuenta con permisos suficientes en Office 365.
- Si la cuenta con permisos en Office 365 no termina en "on.microsoft.com", debe especificar el parámetro - HostedMigrationOverrideUrl, con el valor correcto, tal como se describe en [requiere credenciales administrativas](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).

La siguiente secuencia de cmdlet puede usarse para mover un usuario a Skype para Business Server y se da por supuesto la credencial de Office 365 es una cuenta independiente y se proporciona como entrada para el símbolo del sistema de Get-Credential.

```
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
Move-CsUser -Identity username@contoso.com -Target pool.corp.contoso.com -Credential $cred -HostedMigrationOverrideUrl $url
```

### <a name="move-users-with-the-skype-for-business-server-control-panel"></a>Mover a los usuarios con el Skype para el Panel de Control de servidor empresarial

1. Abra el Skype para el Control de servidor empresarial aplicación de Panel.
2. En el panel de navegación izquierdo, elija **usuarios**.
3. Use **Buscar** para buscar el usuario o usuarios que le gustaría retroceder al local.
4. Seleccione los usuarios y, a continuación, en la lista desplegable **acción** encima de la lista, elija **mover usuarios seleccionados a local**.
5. En el asistente, seleccione el grupo de usuario que va a hospedar el usuario y haga clic en **siguiente**.
6. Si se le solicita, inicie sesión en Office 365, con una cuenta que termina en. onmicrosoft.com y tiene permisos suficientes.
7. Haga clic en **siguiente**y, a continuación, **siguiente** una vez más para mover el usuario.
8. Tenga en cuenta que los mensajes de estado sobre el éxito o el fracaso se proporcionan en la parte superior de la aplicación de Panel de Control principal, no en el asistente.

### <a name="removing-teamsonly-mode"></a>Eliminación de modo TeamsOnly

Si está usando una versión anterior a Skype para 2015 empresarial con CU8 y el usuario se va a mover volver a local en modo de TeamsOnly, debe quitar la instancia de UpgradeToTeams de `TeamsUpgradePolicy` antes de mover el usuario local. Puede conceder explícitamente una directiva con un modo diferente o simplemente quitar la asignación de directivas existentes para que el usuario use la directiva global (siempre que la directiva global de su inquilino no es UpgradeToTeams).

Para quitar la asignación del usuario de TeamsUpgradePolicy, ejecute el siguiente cmdlet desde un Skype para la ventana de PowerShell en línea de negocio:

`Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName $null`

Como alternativa, para asignar otra instancia de TeamsUpgradePolicy que no tiene modo = TeamsOnly, puede especificar el nombre de la instancia que desee como el valor del parámetro PolicyName en el cmdlet. Para ver una lista de instancias disponibles de TeamsUpgradePolicy, ejecute Get-CsTeamsUpgradePolicy.


## <a name="see-also"></a>Vea también

[Move-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/move-csuser)