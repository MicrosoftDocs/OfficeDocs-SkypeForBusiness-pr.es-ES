---
title: Administrar directivas de permisos de aplicación en Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 3/05/2019
ms.reviewer: larryjin
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Obtenga información sobre las directivas de permisos de aplicación en Microsoft Teams y cómo usarlos para controlar qué aplicaciones están disponibles para los usuarios de su organización.
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 47a4d3a444a0685e0a1ff568332bdc426752af4c
ms.sourcegitcommit: d90beb625c2d12616fb9aee39b6dd1c2d4c12947
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "30411384"
---
# <a name="manage-app-permission-policies-in-microsoft-teams"></a>Administrar directivas de permisos de aplicación en Microsoft Teams

> [!INCLUDE [Preview customer token](includes/preview-feature.md)]

Como administrador, puede usar las directivas de permisos de aplicación para controlar qué aplicaciones están disponibles para los usuarios de Microsoft Teams en su organización. Puede permitir o bloquear todas las aplicaciones o aplicaciones específicas, publicadas por Microsoft, terceros y su organización. Cuando se bloquea una aplicación, los usuarios son no se puede instalar desde el almacén de aplicación de los equipos.

Administrar directivas de permisos de aplicación en el centro de administración de Microsoft Teams. Puede aplicar toda la configuración de la organización, use la directiva global (valor predeterminado de toda la organización) y crear y asignar directivas personalizadas a usuarios individuales o a los usuarios en un grupo.  

![Captura de pantalla de directiva de permisos de aplicación](media/app-permission-policies.png)

> [!NOTE]
> Los usuarios de su organización obtendrá automáticamente la directiva global, a menos que se cree y asigne una directiva personalizada. La configuración de aplicaciones de toda la organización invalida la directiva global y cualquier directiva personalizada que cree y asigne a los usuarios.

Por ejemplo, supongamos que desea bloquear todas las aplicaciones de terceros y permitir que aplicaciones específicas de Microsoft para el equipo de recursos humanos de su organización. ¿Crear una directiva personalizada denominada directiva de permisos de aplicación de recursos humanos, configurarla para bloquear y permitir que las aplicaciones que desee y, a continuación, se asigna a los usuarios en el equipo de recursos humanos.


## <a name="manage-org-wide-app-settings"></a>Administrar la configuración de la aplicación de toda la organización

Usar la configuración de la aplicación de toda la organización para controlar qué aplicaciones están disponibles en toda la organización. La configuración de aplicaciones de toda la organización determinan el comportamiento para todos los usuarios e invalidar cualquier otras aplicación las directivas de permisos asignadas a los usuarios. La configuración de aplicaciones de toda la organización surta efecto inmediatamente y se puede usar para controlar aplicaciones malintencionadas o problemáticas.

1. En la izquierda el centro de administración de Microsoft Teams, vaya a la **aplicación de los equipos** > **las directivas de permisos de aplicación**.
2. Seleccione **configuración de toda la organización**. A continuación, puede configurar la configuración que desee en el panel. 
![Captura de pantalla de la configuración de aplicaciones de toda la organización](media/app-permission-policies-org-wide-settings.png)
3. En las **aplicaciones de terceros**, desactivar o activar estas opciones para controlar el acceso a aplicaciones de terceros:

- **Permitir aplicaciones de terceros en los equipos**: esta opción controla si los usuarios pueden usar aplicaciones de terceros.
- **Permitir que cualquier nuevas aplicaciones de terceros publicadas en el almacén de forma predeterminada**: esta controla si almacenan nuevas aplicaciones de terceros que se publican en la aplicación de los equipos estarán disponibles automáticamente en los equipos. Sólo se puede establecer esta opción si permite que las aplicaciones de terceros. 
- **Permitir la interacción con aplicaciones personalizadas**: esta opción controla si los usuarios pueden interactuar con aplicaciones personalizadas (sideloaded). Tenga en cuenta que esto es diferente de lo que permite a los usuarios *cargar* aplicaciones de cliente. 

4. En las **aplicaciones bloqueado**, buscar y agregar las aplicaciones que desea bloquear en toda la organización. Puede elegir aplicaciones desde el catálogo de aplicaciones de inquilinos o la tienda de aplicaciones de los equipos.
5. Haga clic en **Guardar** para la configuración de aplicaciones de toda la organización para que surtan efecto.

## <a name="create-a-custom-app-permission-policy"></a>Crear una directiva de permisos de aplicación personalizada

Si desea controlar las aplicaciones que están disponibles para distintos grupos de usuarios de la organización, cree y asigne una o varias directivas personalizadas. Puede crear y asignar directivas personalizadas independientes en función de si se publican aplicaciones por Microsoft, terceros o la organización. Es importante saber que después de crear una directiva personalizada, no se puede cambiar si aplicaciones de terceros están deshabilitadas en la configuración de toda la organización. 

1. En la izquierda el centro de administración de Microsoft Teams, vaya a la **aplicación de los equipos** > **las directivas de permisos de aplicación**.
2. Seleccione **nueva directiva**.
    ![Captura de pantalla de la nueva directiva de permisos de aplicación](media/app-permission-policies-new-policy.png)
3. Escriba un nombre descriptivo para la directiva.
4. En **aplicaciones de Microsoft**, **aplicaciones de terceros**y **aplicaciones del inquilino**, seleccione una de las siguientes opciones:

- **Permitir que todas las aplicaciones**
- **Permitir aplicaciones específicas y bloquear todos los demás**
- **Bloquear aplicaciones específicas y permitir que todos los otros**
- **Bloquear todas las aplicaciones**

5. Si ha seleccionado **permitir aplicaciones específicas y bloquear otros usuarios**, agregue las aplicaciones que desea permitir:

    1. Seleccione **permitir aplicaciones**.
    1. Búsqueda de las aplicaciones que desee permitir y, a continuación, haga clic en **Agregar**. Los resultados de búsqueda se filtran para el publicador de la aplicación (**las aplicaciones de Microsoft**, **aplicaciones de terceros**o **aplicaciones de inquilino**).
    1. Cuando haya elegido la lista de aplicaciones, haga clic en **Permitir**.

6. De forma similar, si selecciona **bloquear aplicaciones específicas y permitir que todos los otros usuarios**, buscar y agregar las aplicaciones que desea bloquear.
7. Haga clic en **Guardar**.

## <a name="edit-an-app-permission-policy"></a>Editar una directiva de permisos de aplicación

Puede usar el centro de administración de Microsoft Teams o Windows PowerShell para modificar una directiva, incluida la directiva global de (valor predeterminado de toda la organización) y las directivas personalizadas que se crean. 

1. En la izquierda el centro de administración de Microsoft Teams, vaya a la **aplicación de los equipos** > **las directivas de permisos de aplicación**.
2. Seleccione la directiva que desee editar.
3. Desde aquí, realice los cambios que desee. Puede administrar la configuración según el publicador de la aplicación y agregar y quitar aplicaciones según la configuración de permitir o bloquear.
4. Haga clic en **Guardar**.

## <a name="assign-a-custom-app-permission-policy-to-users"></a>Asignar una directiva de permisos de aplicación personalizada a los usuarios

Puede usar el centro de administración de Microsoft Teams para asignar una directiva personalizada a usuarios individuales o el Skype para el módulo de PowerShell de negocio para asignar una directiva personalizada a varios usuarios, por ejemplo, todos los usuarios de un grupo de seguridad o un grupo de distribución.

### <a name="assign-a-custom-app-setup-policy-to-individual-users"></a>Asignar una directiva de aplicación personalizada del programa de instalación a usuarios individuales

1. En la izquierda el centro de administración de Microsoft Teams, vaya a **los usuarios**y, a continuación, haga clic en el usuario.
2. Junto a **las directivas asignadas**, elija **Editar**.
3. En la **Directiva de permisos de aplicación**, seleccione la directiva de permisos de aplicación que desea asignar y, a continuación, elija **Guardar**.

    ![aplicación del programa de instalación permiso asignar policy.png](media/app-permission-policies-assign-policy.png)

### <a name="assign-a-custom-app-permission-policy-to-users-in-a-group"></a>Asignar una directiva de permisos de aplicación personalizada a los usuarios en un grupo

Es posible que desee asignar una directiva de permisos de aplicación personalizadas a varios usuarios que ya ha identificado. Por ejemplo, es posible que desee asignar una directiva a todos los usuarios de un grupo de seguridad. Puede hacer esto conectándose a Azure Active Directory PowerShell para el módulo de gráfico y la Skype para el módulo de PowerShell de negocio. Para obtener más información acerca del uso de PowerShell para administrar los equipos, vea [Información general de los equipos de PowerShell](teams-powershell-overview.md).

En este ejemplo, se asigna una directiva de permisos de aplicación personalizada denominada directiva de permisos de aplicación de recursos humanos a todos los usuarios en el grupo de proyecto de recursos humanos de Contoso farmacéutico.  

> [!NOTE]
> Asegúrese de que primero se conecta a Azure Active Directory PowerShell para el módulo de gráfico y Skype para el módulo de PowerShell de negocio siguiendo los pasos descritos en [Conectar a todos los servicios de Office 365 en una sola ventana de Windows PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).

Obtener la GroupObjectId de un grupo en particular.
```
$group = Get-AzureADGroup -SearchString "Contoso Pharmaceuticals HR Project"
```
Obtener a los miembros del grupo especificado.
```
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
Asignar a todos los usuarios en el grupo a una directiva de permisos de aplicación determinado. En este ejemplo, es una directiva de permisos de aplicación de recursos humanos.
```
$members | ForEach-Object { Grant-CsTeamsAppPermissionPolicy -PolicyName "HR App Permission Policy" -Identity $_.EmailAddress}
``` 
Según la cantidad de los miembros del grupo, este comando puede tardar varios minutos en ejecutarse.

## <a name="faq"></a>Preguntas más frecuentes

### <a name="working-with-app-permission-policies"></a>Trabajar con directivas de permisos de aplicación

#### <a name="can-i-control-line-of-business-lob-apps"></a>¿Se puede controlar la línea de aplicaciones de negocio (LOB)?

Sí, puede usar las directivas de permisos de aplicación para controlar la implantación y la distribución de aplicaciones personalizadas de (LOB).

#### <a name="how-do-app-permission-policies-relate-to-pinned-apps-and-app-setup-policies"></a>¿Cómo las directivas de permisos de aplicación se relacionan con aplicaciones ancladas y las directivas de aplicación del programa de instalación?

Puede usar directivas de configuración de la aplicación junto con las directivas de permisos de aplicación. Aplicaciones previamente fijadas están seleccionadas en el conjunto de aplicaciones habilitadas para un usuario. Además, si un usuario tiene una directiva de permisos de aplicación que se bloquea una aplicación en su directiva del programa de instalación de la aplicación, esa aplicación no aparecerá en los equipos.

#### <a name="how-long-does-it-take-for-policy-changes-to-take-effect"></a>¿Cuánto tiempo tarda para que surtan efecto los cambios de directiva?

Después de editar la directiva global o asignar una directiva a los usuarios, puede tardar hasta 24 horas para que los cambios surtan efecto. La configuración de aplicaciones de toda la organización surta efecto inmediatamente.

#### <a name="does-blocking-an-app-apply-to-teams-mobile-clients"></a>¿Bloqueo de una aplicación se aplica a los clientes móviles de los equipos?

Sí, cuando se bloquea una aplicación, se bloquea en todos los clientes de los equipos de esa aplicación.  

### <a name="user-experience"></a>Experiencia de usuario

#### <a name="what-does-a-user-experience-when-an-app-is-blocked"></a>¿Qué un experiencia del usuario cuando se bloquea una aplicación?

Los usuarios no pueden interactuar con una aplicación bloqueada o sus capacidades, tales bots, las fichas y las extensiones de mensajería. En un contexto compartido, como un equipo o grupo de chat, bots puede seguir enviando mensajes a todos los participantes de ese contexto. Los equipos se indica al usuario cuando se bloquea una aplicación. 

Por ejemplo, si se bloquea una aplicación, los usuarios no cualquiera de las siguientes opciones:

- Agregar la aplicación personalmente o a una conversación o de equipo
- Enviar mensajes a bot de la aplicación
- Realizar acciones de botón que envían información a la aplicación, como los mensajes que se pueden procesar  
- Ver la ficha de la aplicación
- Configurar conectores para recibir notificaciones
- Use la extensión de mensajería de la aplicación

 ## <a name="related-topics"></a>Temas relacionados
- [Administrar directivas de configuración de aplicación en Microsoft Teams](teams-app-setup-policies.md)
