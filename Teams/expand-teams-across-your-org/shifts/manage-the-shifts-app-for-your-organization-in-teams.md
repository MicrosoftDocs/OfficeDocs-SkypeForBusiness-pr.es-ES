---
title: Administrar la aplicación Turnos para su organización en Microsoft Teams
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Obtenga información sobre cómo configurar y administrar la aplicación de turnos en Teams para trabajadores de los Firstline de su organización.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 134ff131307034381b97643a2bf9a3dd7fc87a7d
ms.sourcegitcommit: 10046048a670b66d93e8ac3ba7c3ebc9c3c5fc2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/20/2020
ms.locfileid: "42161863"
---
# <a name="manage-the-shifts-app-for-your-organization-in-microsoft-teams"></a>Administrar la aplicación Turnos para su organización en Microsoft Teams

> [!IMPORTANT]
> A partir del 31 de diciembre de 2019, Microsoft StaffHub se retirará. Estamos construyendo las capacidades de StaffHub en Microsoft Teams. En la actualidad, Teams incluye la aplicación de turnos para la administración de la programación, y las funciones adicionales se aplicarán a lo largo del tiempo. StaffHub dejará de funcionar para todos los usuarios el 31 de diciembre de 2019. Cualquier persona que intente abrir StaffHub recibirá un mensaje para que pueda descargar Teams. Para obtener más información, consulte [Microsoft StaffHub para que se retirará](microsoft-staffhub-to-be-retired.md).  

## <a name="overview-of-shifts"></a>Descripción general de los turnos

La aplicación turnos en Microsoft Teams mantiene a los trabajadores de los Firstline conectados y sincronizados. En primer lugar, se ha creado un teléfono móvil para una administración y comunicación rápidas y eficaces de los equipos. Turnos permite que los trabajadores de los Firstline y sus gerentes usen sus dispositivos móviles para administrar las programaciones y mantenerse en contacto. 

- Los administradores crean, actualizan y administran programaciones de turnos para Teams. Pueden enviar mensajes a una persona ("hay un derrame en el piso") o todo el equipo ("el GM regional está llegando en 20 minutos"). También pueden enviar documentos de directivas, boletines de noticias y videos. 
- Los empleados ven sus próximos turnos, pueden ver quién más está programado para el día, solicitar intercambiar o ofrecer un turno, y solicitar un tiempo. 

Es importante saber que los turnos actualmente no admiten usuarios invitados. Esto significa que los invitados de un equipo no se pueden agregar o usar programaciones de turno cuando el acceso de invitados está activado en Teams. 

## <a name="availability-of-shifts"></a>Disponibilidad de los turnos

Turnos está disponible en todas las SKU de Enterprise donde está disponible Teams.

## <a name="location-of-shifts-data"></a>Ubicación de los datos de turnos

Mayús los datos están almacenados actualmente en Azure en centros de datos en Norteamérica, Europa occidental y Asia Pacífico. Para obtener más información sobre dónde se almacenan los datos, vea ¿ [dónde están mis datos](http://o365datacentermap.azurewebsites.net/)?

## <a name="set-up-shifts"></a>Configurar turnos

### <a name="enable-or-disable-shifts-in-your-organization"></a>Habilitar o deshabilitar turnos en su organización

Turnos está habilitado de forma predeterminada para todos los usuarios de los equipos de su organización. Puede desactivar o activar la aplicación en el nivel de organización en la página [Administrar aplicaciones](../../manage-apps.md) del centro de administración de Microsoft Teams.

1. En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a **aplicaciones** > de Teams**Manage apps** .
2. En la lista de aplicaciones, realice una de las siguientes acciones:

    - Para desactivar los turnos de su organización, busque la aplicación turnos, selecciónela y haga clic en **bloquear**.
    - Para activar los turnos de su organización, busque la aplicación turnos, selecciónela y, a continuación, haga clic en **permitir**.

### <a name="enable-or-disable-shifts-for-specific-users-in-your-organization"></a>Habilitar o deshabilitar turnos para usuarios específicos de su organización

Para permitir o bloquear a determinados usuarios de su organización el uso de turnos, asegúrese de que la opción turnos está activada para su organización en la página [Administrar aplicaciones](../../manage-apps.md) y, después, cree una directiva de permisos de aplicaciones personalizada y asígnela a esos usuarios. Para obtener más información, vea [Administrar directivas de permisos de aplicaciones en Teams](../../teams-app-permission-policies.md).

### <a name="use-the-firstlineworker-app-setup-policy-to-pin-shifts-to-teams"></a>Use la Directiva de configuración de la aplicación de FirstlineWorker para anclar turnos a teams

Las directivas de configuración de la aplicación le permiten personalizar Teams para resaltar las aplicaciones más importantes para los usuarios de su organización. Las aplicaciones establecidas en una directiva se anclan a la barra&mdash;de la aplicación, que se encuentra en el costado del cliente de escritorio de Teams y en&mdash;la parte inferior de los clientes móviles de Teams donde los usuarios puedan acceder a ellas de forma rápida y fácil. 
 
Teams incluye una directiva de configuración de aplicaciones de FirstlineWorker integrada que puede asignar a los trabajadores de los Firstline de su organización. De forma predeterminada, la Directiva incluye las aplicaciones actividad, turnos, chat y llamadas. 

Para ver la Directiva de FirstlineWorker, en el navegación izquierdo del centro de administración de Microsoft Teams, vaya a**directivas de configuración**de la aplicación de **aplicación** > de Teams.

![Captura de pantalla de la Directiva de configuración de la aplicación de FirstlineWorker](../../media/firstline-worker-app-setup-policy.png "Captura de pantalla de la Directiva de configuración de la aplicación de FirstlineWorker en el centro de administración de Microsoft Teams")

#### <a name="assign-the-firstlineworker-policy-to-individual-users"></a>Asignar la Directiva FirstlineWorker a usuarios individuales

1. En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a **usuarios**y, a continuación, haga clic en el usuario.
2. Junto a **directivas asignadas**, elija **Editar**.
3. En **Directiva de configuración de la aplicación de Teams**, seleccione **FirstlineWorker**y, después, haga clic en **Guardar**.

#### <a name="assign-the-firstlineworker-app-setup-policy-to-user-members-of-a-group"></a>Asignar la Directiva de configuración de la aplicación de FirstlineWorker a los miembros del usuario de un grupo

Puede asignar la Directiva de configuración de la aplicación de FirstlineWorker a los miembros de usuario de un grupo, como un grupo de seguridad, conectándose al módulo de Azure Active Directory PowerShell para Graph y al módulo de PowerShell de Skype empresarial. Para obtener más información sobre cómo usar PowerShell para administrar equipos, consulte [información general de Teams PowerShell](../../teams-powershell-overview.md).

En este ejemplo, asignamos la Directiva de configuración de la aplicación FirstlineWorker a todos los miembros del usuario del grupo de equipo de Contoso los Firstline.

> [!NOTE]
> Asegúrese de conectarse primero al módulo de Azure Active Directory PowerShell para Graph y al módulo de PowerShell de Skype empresarial siguiendo los pasos de [conectar a todos los servicios de Office 365 en una sola ventana de Windows PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).

Obtén la GroupObjectId del grupo en particular.
```PowerShell
$group = Get-AzureADGroup -SearchString "Contoso Firstline Team"
```
Obtener los miembros del grupo especificado.
```PowerShell
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
Asigne la Directiva de configuración de la aplicación de FirstlineWorker a todos los miembros del grupo.
```PowerShell
$members | ForEach-Object {Grant-CsTeamsAppSetupPolicy -PolicyName "FirstlineWorker" -Identity $_.EmailAddress}
``` 
Según el número de miembros del grupo, este comando puede demorar varios minutos en ejecutarse.

## <a name="related-topics"></a>Temas relacionados
- [Desplaza la ayuda para los trabajadores de los Firstline](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
