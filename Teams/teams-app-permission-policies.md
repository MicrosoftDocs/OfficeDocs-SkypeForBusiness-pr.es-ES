---
title: Administrar directivas de permisos de aplicación en Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 3/18/2019
ms.reviewer: lajin
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
ROBOTS: NOINDEX, NOFOLLOW
description: Obtenga más información sobre las directivas de permisos de aplicaciones en Microsoft Teams y cómo usarlas para controlar qué aplicaciones están disponibles para los usuarios de su organización.
f1keywords:
- ms.teamsadmincenter.apppolicies.overview
ms.openlocfilehash: fac559fb492155af9953beb74c2fac1526f01432
ms.sourcegitcommit: 55da03c85237b43b848e7ff9b427304c2d9e568f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2019
ms.locfileid: "34681924"
---
# <a name="manage-app-permission-policies-in-microsoft-teams"></a>Administrar directivas de permisos de aplicación en Microsoft Teams

> [!INCLUDE [feature coming soon](includes/new-feature-coming-soon-article.md)]

> [!NOTE]
> Para obtener el método de administración de aplicaciones actual en Microsoft Teams, vea [administrar la configuración de Microsoft Teams para su organización](https://docs.microsoft.com/MicrosoftTeams/enable-features-office-365).

Como administrador, puede usar las directivas de permisos de aplicaciones para controlar qué aplicaciones están disponibles para los usuarios de Microsoft Teams de su organización. Puede permitir o bloquear todas las aplicaciones o aplicaciones específicas publicadas por Microsoft, terceros y su organización. Cuando bloquea una aplicación, los usuarios no pueden instalarla desde la tienda de aplicaciones de Teams.

Administre las directivas de permisos de aplicaciones en el centro de administración de Microsoft Teams. Puede aplicar la configuración de toda la organización, usar la directiva global (predeterminada para toda la organización) y crear y asignar directivas personalizadas a usuarios individuales o a usuarios de un grupo.  

![Captura de pantalla de la Directiva de permisos de aplicaciones](media/app-permission-policies.png)

> [!NOTE]
> Los usuarios de la organización obtendrán automáticamente la directiva global a menos que cree y asigne una directiva personalizada. La configuración de la aplicación en toda la organización reemplaza la directiva global y las directivas personalizadas que cree y asigne a los usuarios.

Supongamos, por ejemplo, que desea bloquear todas las aplicaciones de terceros y permitir aplicaciones específicas de Microsoft para el equipo de RRHH de su organización. Crearía una directiva personalizada denominada Directiva de permisos de aplicaciones de RRHH, establecerla para que bloquee y permitir las aplicaciones que quiera y, después, asignarla a los usuarios del equipo de RRHH.

## <a name="manage-org-wide-app-settings"></a>Administrar la configuración de la aplicación en toda la organización

Use la configuración de la aplicación en toda la organización para controlar qué aplicaciones están disponibles en toda la organización. La configuración de la aplicación en toda la organización rige el comportamiento de todos los usuarios y anula cualquier otra directiva de permisos de aplicación asignada a los usuarios. La configuración de la aplicación en toda la organización se aplicará inmediatamente y podrá usarlas para controlar aplicaciones malintencionadas o problemáticas.

1. En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a**directivas de permisos**de la **aplicación** > Teams.
2. Seleccione **configuración de toda la organización**. Puede establecer la configuración que desee en el panel. 
![Captura de pantalla de la configuración de la aplicación de toda la organización](media/app-permission-policies-org-wide-settings.png)
3. En **aplicaciones de terceros**, desactive o Active esta configuración para controlar el acceso a las aplicaciones de terceros:

    - **Permitir aplicaciones de terceros en Teams**: controla si los usuarios pueden usar aplicaciones de terceros.
    - **Permitir que todas las aplicaciones de terceros se publiquen en la tienda de forma predeterminada**: controla si las nuevas aplicaciones de terceros publicadas en la tienda de aplicaciones de Teams se encuentran disponibles automáticamente en Teams. Solo puede establecer esta opción si permite aplicaciones de terceros.

4. En **aplicaciones personalizadas**, desactive o desactive la **opción permitir la interacción con aplicaciones personalizadas**. Esta configuración controla si los usuarios pueden interactuar con aplicaciones personalizadas (transferidas). Tenga en cuenta que esto es diferente de permitir que los ** usuarios carguen aplicaciones personalizadas.
5. En **aplicaciones bloqueadas**, busque y agregue las aplicaciones que desea bloquear en toda la organización. Puede elegir aplicaciones del catálogo de aplicaciones de inquilino o de la tienda de aplicaciones de Teams.
6. Haga clic en **Guardar** para que la configuración de la aplicación de toda la organización surta efecto.

## <a name="create-a-custom-app-permission-policy"></a>Crear una directiva de permisos de aplicaciones personalizada

Si desea controlar las aplicaciones que están disponibles para los distintos grupos de usuarios de su organización, cree y asigne una o varias directivas de permisos de aplicaciones personalizadas. Puede crear y asignar directivas personalizadas distintas basándose en si las aplicaciones son publicadas por Microsoft, por terceros o por su organización. Es importante saber que después de crear una directiva personalizada, no puede cambiarla si las aplicaciones de terceros se deshabilitan en la configuración de toda la organización. 

1. En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a**directivas de permisos**de la **aplicación** > Teams.
2. Seleccione **nueva Directiva**.
    ![Captura de pantalla de nueva Directiva de permisos de aplicación](media/app-permission-policies-new-policy.png)
3. Escriba un nombre descriptivo para la Directiva.
4. En aplicaciones de **Microsoft**, **aplicaciones**de terceros y **aplicaciones de inquilino**, seleccione una de las siguientes opciones:

    - **Permitir todas las aplicaciones**
    - **Permitir aplicaciones específicas y bloquear a todos los demás**
    - **Bloquear aplicaciones específicas y permitir a todos los demás**
    - **Bloquear todas las aplicaciones**

5. Si seleccionó **permitir aplicaciones específicas y bloquear a otras personas**, agregue las aplicaciones que quiera permitir:

    1. Seleccione **permitir aplicaciones**.
    1. Busque las aplicaciones que desea permitir y, a continuación, haga clic en **Agregar**. Los resultados de la búsqueda se filtran para el publicador de la aplicación (aplicaciones de**Microsoft**, **aplicaciones de terceros**o **aplicaciones de inquilino**).
    1. Cuando haya elegido la lista de aplicaciones, haga clic en **permitir**.

6. De forma similar, si seleccionaste **bloquear aplicaciones específicas y permitir a todos los demás**, busca y agrega las aplicaciones que deseas bloquear.
7. Haga clic en **Guardar **.

## <a name="edit-an-app-permission-policy"></a>Editar una directiva de permisos de aplicación

Puede usar el centro de administración de Microsoft Teams para editar una directiva, incluyendo la directiva global (opción predeterminada de toda la organización) y las directivas personalizadas que cree. 

1. En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a**directivas de permisos**de la **aplicación** > Teams.
2. Seleccione la Directiva que desea editar.
3. Desde aquí, realice los cambios que desee. Puede administrar la configuración basándose en el editor de la aplicación y agregar y quitar aplicaciones en función de la configuración permitir o bloquear.
4. Haga clic en **Guardar **.

## <a name="assign-a-custom-app-permission-policy-to-users"></a>Asignar una directiva de permisos de aplicación personalizada a los usuarios

Puede usar el centro de administración de Microsoft Teams para asignar una directiva personalizada a usuarios individuales o el módulo de PowerShell de Skype empresarial para asignar una directiva personalizada a varios usuarios, como todos los usuarios de un grupo de seguridad o de un grupo de distribución.

> [!IMPORTANT]
> Le recomendamos usar PowerShell solo para asignar directivas a los usuarios. Use el centro de administración de Microsoft Teams para crear, editar y administrar directivas.

### <a name="assign-a-custom-app-permission-policy-to-individual-users"></a>Asignar una directiva de permisos de aplicación personalizada a usuarios individuales

1. En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a **usuarios**y, a continuación, haga clic en el usuario.
2. Junto a **directivas asignadas**, elija **Editar**.
3. En **Directiva de permisos de aplicaciones**, seleccione la Directiva de permisos de aplicación que desea asignar y, a continuación, elija **Guardar**.

    ![App-Setup-Permission-Assign-Policy. png](media/app-permission-policies-assign-policy.png)

También puede asignar una directiva de permisos de aplicaciones a uno o más usuarios de la siguiente manera:

1. Vaya al **Centro** > de administración de Microsoft Teams**directivas de permisos**de**aplicaciones** > de Teams.
2. Seleccione la Directiva haciendo clic a la izquierda del nombre de la Directiva.
3. Seleccione **administrar usuarios**.
4. En el panel **administrar usuarios** , busque el usuario por nombre para mostrar o por nombre de usuario, seleccione el nombre y, después, haga clic en **Agregar**. Repita este paso para cada usuario que desee agregar.
5. Cuando haya terminado de agregar usuarios, seleccione **Guardar**.
 

### <a name="assign-a-custom-app-permission-policy-to-users-in-a-group"></a>Asignar una directiva de permisos de aplicación personalizada a los usuarios de un grupo

Es posible que desee asignar una directiva de permisos de aplicación personalizada a varios usuarios que ya haya identificado. Por ejemplo, es posible que desee asignar una directiva a todos los usuarios de un grupo de seguridad. Para ello, puede conectarse al módulo de Azure Active Directory PowerShell para Graph y al módulo de PowerShell de Skype empresarial. Para obtener más información sobre cómo usar PowerShell para administrar equipos, consulte [información general de Teams PowerShell](teams-powershell-overview.md).

En este ejemplo, asignamos una directiva de permisos de aplicaciones personalizada denominada Directiva de permisos de aplicaciones de RRHH a todos los usuarios del grupo de proyectos de RRHH de Contoso Pharmaceuticals.  

> [!NOTE]
> Asegúrese de conectarse primero al módulo de Azure Active Directory PowerShell para Graph y al módulo de PowerShell de Skype empresarial siguiendo los pasos de [conectar a todos los servicios de Office 365 en una sola ventana de Windows PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).

Obtén la GroupObjectId del grupo en particular.
```
$group = Get-AzureADGroup -SearchString "Contoso Pharmaceuticals HR Project"
```
Obtener los miembros del grupo especificado.
```
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
Asignar todos los usuarios del grupo a una directiva de permisos de la aplicación determinada. En este ejemplo, es la Directiva de permisos de la aplicación de RRHH.
```
$members | ForEach-Object { Grant-CsTeamsAppPermissionPolicy -PolicyName "HR App Permission Policy" -Identity $_.EmailAddress}
``` 
Según el número de miembros del grupo, este comando puede demorar varios minutos en ejecutarse.

## <a name="faq"></a>Preguntas frecuentes

### <a name="working-with-app-permission-policies"></a>Trabajar con directivas de permisos de aplicaciones

#### <a name="can-i-control-line-of-business-lob-apps"></a>¿Puedo controlar las aplicaciones de línea de negocio (LOB)?

Sí, puede usar las directivas de permisos de aplicaciones para controlar el despliegue y la distribución de aplicaciones personalizadas (LOB).

#### <a name="how-do-app-permission-policies-relate-to-pinned-apps-and-app-setup-policies"></a>¿Cómo se relacionan las directivas de permisos de aplicaciones con las aplicaciones fijas y las directivas de configuración de aplicaciones?

Puede usar las directivas de configuración de la aplicación junto con directivas de permisos de la aplicación. Las aplicaciones previamente ancladas se seleccionan en el conjunto de aplicaciones habilitadas para un usuario. Además, si un usuario tiene una directiva de permisos de la aplicación que bloquea una aplicación en la Directiva de configuración de la aplicación, esa aplicación no aparecerá en Teams.

#### <a name="can-i-use-app-permission-policies-to-restrict-uploading-custom-apps-also-known-as-sideloading"></a>¿Puedo usar directivas de permisos de aplicaciones para restringir la carga de aplicaciones personalizadas (también conocidas como de prueba de prueba)?

Para obtener más información sobre cómo restringir la carga de aplicaciones personalizadas, consulte [administrar las directivas y la configuración de la aplicación personalizada en Teams](teams-custom-app-policies-and-settings.md).

#### <a name="how-long-does-it-take-for-policy-changes-to-take-effect"></a>¿Cuánto tiempo se tarda en aplicar los cambios de Directiva?

Después de modificar la directiva global o de asignar una directiva a los usuarios, los cambios pueden tardar hasta 24 horas en surtir efecto. La configuración de la aplicación en toda la organización surte efecto de inmediato.

#### <a name="does-blocking-an-app-apply-to-teams-mobile-clients"></a>¿El bloqueo de una aplicación se aplica a los clientes móviles de Teams?

Sí, cuando bloquea una aplicación, dicha aplicación se bloquea en todos los clientes de Teams.  

### <a name="user-experience"></a>Experiencia de usuario

#### <a name="what-does-a-user-experience-when-an-app-is-blocked"></a>¿Qué es una experiencia de usuario cuando se bloquea una aplicación?

Los usuarios no pueden interactuar con una aplicación bloqueada ni con sus funciones, como bots, pestañas y extensiones de mensajería. En un contexto compartido, como un chat de grupo o de equipo, los bots pueden enviar mensajes a todos los participantes de ese contexto. Teams indica al usuario Cuándo se bloquea una aplicación. 

Por ejemplo, cuando una aplicación está bloqueada, los usuarios no pueden realizar ninguna de las siguientes acciones:

- Agregar la aplicación personalmente o a un chat o un equipo
- Enviar mensajes al bot de la aplicación
- Realizar acciones de botón que envían información a la aplicación, como mensajes accionables  
- Ver la pestaña de la aplicación
- Configurar conectores para recibir notificaciones
- Usar la extensión de mensajería de la aplicación

 ## <a name="related-topics"></a>Temas relacionados
- [Configurar la administración para aplicaciones en Teams](admin-settings.md)
- [Administrar directivas de configuración de aplicación en Teams](teams-app-setup-policies.md)
- [Administrar configuración y directivas de aplicación personalizadas en Teams](teams-custom-app-policies-and-settings.md)
