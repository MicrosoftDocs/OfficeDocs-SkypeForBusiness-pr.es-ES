---
title: Administrar la aplicación Turnos para su organización en Microsoft Teams
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.date: 03/08/2019
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: Obtenga información sobre cómo configurar y administrar la aplicación de turnos en los equipos firstline a los trabajadores de la organización.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 994d83645c272b2beed4752c7cdaaeaef6c9cd0f
ms.sourcegitcommit: 3d3a296f225ecbbee0b4cea67664ad7ab31ed1c2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/11/2019
ms.locfileid: "30537735"
---
# <a name="manage-the-shifts-app-for-your-organization-in-microsoft-teams"></a>Administrar la aplicación Turnos para su organización en Microsoft Teams

> [!IMPORTANT]
> Eficaces se deben retirarse el 1 de octubre de 2019, Microsoft StaffHub. Que estamos creando las capacidades de StaffHub, incluida la administración de programación y tarea, en Microsoft Teams. Funciones adicionales para los trabajadores de firstline va a desplegar a los equipos a través del tiempo. Para obtener más información, vea [Microsoft StaffHub retirarse](microsoft-staffhub-to-be-retired.md).  

## <a name="overview-of-shifts"></a>Información general de turnos
La aplicación de turnos en Microsoft Teams mantiene los trabajadores firstline conectados y sincronizados. Se basa móvil en primer lugar para la administración de tiempo rápida y eficaz y comunicación para los equipos. Turnos permite a los trabajadores de la firstline y sus directores utilizar sus dispositivos móviles para administrar las programaciones y mantenerse en contacto. 

- Los administradores creación, actualización y administración programaciones MAYÚS para los equipos. Pueden enviar mensajes a una persona ("hay un desbordamiento en el plano inferior") o todo el equipo ("el GM regional llega en 20 minutos"). También pueden enviar documentos de directivas, boletines de noticias y vídeos. 
- Los empleados ver sus próximas turnos, pueden ver quién más está programado para el día, solicitar a intercambiar u ofrecen un turno y tiempo de la solicitud desactivado. 

Es importante saber que turnos actualmente no es compatible con los usuarios invitados. Esto significa que los invitados en un equipo no puede agregarse a o usar programaciones MAYÚS cuando está activado el acceso como invitado en los equipos. 

## <a name="availability-of-shifts"></a>Disponibilidad de turnos

Turnos está disponible en todas las suscripciones a Office 365 que incluyen equipos con un par de excepciones. Las excepciones son equipos gratuitos y nos gubernamentales en la nube Comunidad (GCC). Turnos no está disponible en Office 365 gobierno de Estados Unidos o las ofertas de libre de los equipos.

Para obtener más información acerca de las licencias para los equipos, incluida una lista de suscripciones a Office 365 que incluye los equipos, vea [licencias de Office 365 para los equipos](../Office-365-licensing.md).

## <a name="location-of-shifts-data"></a>Ubicación de los datos de turnos

Datos de turnos actualmente se almacenan en Azure en centros de datos en Norteamérica, Europa occidental y Asia Pacífico. Para obtener más información acerca de dónde se almacenan los datos, vea [¿dónde están mis datos](http://o365datacentermap.azurewebsites.net/)?

## <a name="set-up-shifts"></a>Configurar los turnos

### <a name="enable-or-disable-shifts-in-your-organization"></a>Habilitar o deshabilitar turnos de su organización

Turnos está habilitado de forma predeterminada para todos los usuarios de los equipos de la organización. Puede activar o desactivar en la aplicación para su organización en el centro de administración de Microsoft 365.

1. Inicie sesión en el centro de administración de Microsoft 365 con su cuenta de administración de Office 365.
2. Vaya a **configuración** > **complementos & de servicios** > **Equipos de Microsoft**. 
3. En **configuración de todo el inquilino**, seleccione **aplicaciones**y, a continuación, en **Aplicaciones de valor predeterminado**, desactive o Active la casilla de verificación **turnos** para activar o desactivar en la aplicación. 

    ![Captura de pantalla de la sección de aplicaciones predeterminado] (../media/firstline-worker-enable-disable-shifts.png "Captura de pantalla de la sección de aplicaciones predeterminado en el centro de administración de Microsoft 365, que muestra la lista de aplicaciones, como las aplicaciones de turnos")

### <a name="use-the-firstlineworker-app-setup-policy-to-pin-shifts-to-teams"></a>Usar la directiva de FirstLineWorker aplicación del programa de instalación a turnos de pin a los equipos

> [!INCLUDE [Preview customer token](../includes/preview-feature.md)]

Las directivas de aplicación del programa de instalación le permiten personalizar equipos para resaltar las aplicaciones que son más importantes para los usuarios de su organización. Las aplicaciones que se establezca en una directiva se anclan a la barra de la aplicación&mdash;la barra en el lado del cliente de escritorio de los equipos y en la parte inferior de los clientes móviles de equipos&mdash;donde los usuarios pueden rápida y fácilmente tener acceso a ellas. 
 
Los equipos incluye una directiva del programa de instalación de aplicación FirstLineWorker integrada que puede asignar a los trabajadores de firstline en su organización. De forma predeterminada, la directiva incluye las aplicaciones de actividad, turnos, Chat y llamadas. 

Para ver la directiva de FirstLineWorker, en la izquierda del centro de administración de Microsoft Teams, vaya a la **aplicación de los equipos** > **las directivas de aplicación del programa de instalación**.

![Captura de pantalla de la directiva de configuración de aplicación FirstLineWorker en el centro de administración de equipos de Microsoft] (../media/firstline-worker-app-setup-policy.png "Captura de pantalla de la directiva de configuración de aplicación FirstLineWorker en el centro de administración de equipos de Microsoft")

#### <a name="assign-the-firstlineworker-policy-to-individual-users"></a>Asigne la directiva FirstLineWorker a usuarios individuales

1. En la izquierda el centro de administración de Microsoft Teams, vaya a **los usuarios**y, a continuación, haga clic en el usuario.
2. Junto a **las directivas asignadas**, elija **Editar**.
3. En **el programa de instalación de los equipos de aplicación de directiva**, seleccione **FirstLineWorker**y, a continuación, elija **Guardar**.

#### <a name="assign-the-firstlineworker-app-setup-policy-to-users-in-a-group"></a>Asignar la directiva de configuración de aplicación FirstLineWorker a los usuarios en un grupo

Puede asignar la directiva de FirstLineWorker aplicación del programa de instalación para los usuarios de un grupo, como un grupo de seguridad, conectándose a Azure Active Directory PowerShell para el módulo de gráfico y la Skype para el módulo de PowerShell de negocio. Para obtener más información acerca del uso de PowerShell para administrar los equipos, vea [Información general de los equipos de PowerShell](../teams-powershell-overview.md).

En este ejemplo, asignamos la directiva de configuración de aplicación FirstLineWorker a todos los usuarios de Contoso Firstline del grupo.

> [!NOTE]
> Asegúrese de que primero se conecta a Azure Active Directory PowerShell para el módulo de gráfico y Skype para el módulo de PowerShell de negocio siguiendo los pasos descritos en [Conectar a todos los servicios de Office 365 en una sola ventana de Windows PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).

Obtener la GroupObjectId de un grupo en particular.
```
$group = Get-AzureADGroup -SearchString "Contoso Firstline Team"
```
Obtener a los miembros del grupo especificado.
```
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
Asignar a todos los usuarios en el grupo a la directiva de FirstLineWorker aplicación del programa de instalación.
```
$members | ForEach-Object { Grant-CsTeamsAppSetupPolicy -PolicyName "FirstLineWorker" -Identity $_.EmailAddress}
``` 
Según la cantidad de los miembros del grupo, este comando puede tardar varios minutos en ejecutarse.

## <a name="related-topics"></a>Temas relacionados
- [Ayuda de turnos de trabajadores firstline y directores](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)