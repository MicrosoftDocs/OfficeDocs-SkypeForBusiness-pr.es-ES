---
title: Implementar equipos a escala para los trabajadores de primera línea en Microsoft Teams
author: LanaChin
ms.author: v-lanachin
ms.reviewer: rahuldey
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Obtenga información sobre cómo implementar equipos a escala para los trabajadores de primera línea de su organización.
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: feffd8e6f651b4592e789cd24243f01417f1b966
ms.sourcegitcommit: f2253162a23d0683e7424211da1a0a8760c8a91b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/29/2022
ms.locfileid: "66240739"
---
# <a name="deploy-teams-at-scale-for-frontline-workers-in-microsoft-teams"></a>Implementar equipos a escala para los trabajadores de primera línea en Microsoft Teams

> [!NOTE]
> Esta característica se encuentra actualmente en versión preliminar pública. Si desea participar, póngase en contacto con nosotros en [dscale@microsoft.com](mailto:dscale@microsoft.com).


## <a name="overview"></a>Información general
 
Su organización puede tener una gran cantidad de equipos que use para impulsar la comunicación y la colaboración entre los empleados de primera línea, que están repartidos por diferentes tiendas, ubicaciones y roles. Actualmente, no hay una solución fácil para implementar, configurar y administrar estos equipos y usuarios a escala.

Estamos creando una solución para permitir que los administradores implementen y administren equipos a escala.

Esta es una descripción general de las capacidades disponibles actualmente para crear y administrar grandes cantidades de equipos a la vez y lo que estamos planeando para el futuro próximo.

||Disponible hoy |Más adelante en 2022  |
|---------|---------|---------|
|**Número de equipos que puede crear por lote**|Hasta 100 |Hasta 500|
|**Número de usuarios que puede agregar por equipo**|Hasta 25|Hasta 25|

Implementar equipos a escala le permite:

- Cree equipos con plantillas predefinidas o sus propias plantillas personalizadas.
- Agregue usuarios a los equipos como propietarios o miembros.
- Administre equipos a escala agregando o quitando usuarios de equipos existentes.
- Mantente informado por correo electrónico, incluyendo la finalización, el estado y los errores (si los hubiera). Puede notificar hasta a cinco personas sobre el estado de cada lote de equipos que implemente. Los propietarios y miembros del equipo reciben automáticamente una notificación cuando se agregan a un equipo.

## <a name="how-to-deploy-teams-at-scale"></a>Cómo implementar equipos a escala

> [!NOTE]
> Antes de implementar los equipos, asegúrese de que todos los propietarios de equipos tienen una licencia de Teams.

Siga estos pasos para implementar un gran número de equipos a la vez.

### <a name="step-1-prepare-your-csv-files"></a>Paso 1: Preparar los archivos CSV

Tendrá que crear dos archivos CSV para cada lote de equipos que implemente:

- **Un archivo CSV que define los equipos que está creando**. Este archivo debe contener estas columnas necesarias, en el siguiente orden, empezando por la primera columna:

    |Nombre de columna  |Descripción  |
    |---------|---------|
    |**Nombre del equipo**|El nombre del equipo.|
    |**Id. de equipo existente**|Si va a agregar o quitar usuarios de un equipo existente, especifique el id. de equipo del equipo.|
    |**Visibilidad**|Tanto si el equipo es público (cualquier persona de su organización puede unirse) como privado (los usuarios necesitan la aprobación de los propietarios del equipo para unirse). Las opciones son **Pública** y **Privada**.|
    |**Id. de plantilla de equipo**|Si va a crear un equipo a partir de una plantilla predefinida o personalizada, especifique el id. de plantilla de equipo. Consulte [Introducción a las plantillas de equipo en el Centro de administración de Teams](get-started-with-teams-templates-in-the-admin-console.md) para obtener una lista de identificadores y plantillas de equipo predefinidas. Si desea usar la plantilla de equipo predeterminada estándar, déjela en blanco.|

- **Un archivo CSV que asigna los usuarios que va a agregar a cada equipo**. Este archivo debe contener estas columnas necesarias, en el siguiente orden, empezando por la primera columna:

    |Nombre de columna  |Descripción  |
    |---------|---------|
    |**Nombre completo de usuario**|El nombre para mostrar del usuario.|
    |**UPN o ID de usuario**|El nombre principal de usuario (UPN) o el id. del usuario. Por ejemplo, averyh@contoso.com.|
    |**Nombre del equipo**|El nombre del equipo.|
    |**Tipo de acción**|Tanto si va a agregar o quitar el usuario del equipo. Las opciones son **AddMember** y **RemoveMember**.|
    |**Propietario o miembro**|Si el usuario es propietario del equipo o miembro del equipo. Las opciones son **Propietario** y **Miembro**.|

#### <a name="examples"></a>Ejemplos

Use los ejemplos siguientes para ayudarle a crear sus archivos CSV. Aquí, hemos denominado los archivos, Teams.csv y Users.csv.

**Teams.csv**

|Nombre del equipo|Id. de equipo existente|Visibilidad|Id. de plantilla de equipo|
|---------|---------|---------|---------|
|Contoso Store 1||Público|com.microsoft.teams.template.retailStore|
|Contoso Store 2||Público|com.microsoft.teams.template.retailStore|
|Contoso Store 3||Público|com.microsoft.teams.template.retailStore|
|Contoso Store 4||Público|com.microsoft.teams.template.retailStore|
|Contoso Store 5||Público|com.microsoft.teams.template.ManageAProject|
|Contoso Store 6||Público|com.microsoft.teams.template.ManageAProject|
|Contoso Store 7||Público||
|Contoso Store 8||Privado|com.microsoft.teams.template.OnboardEmployees|
|Contoso Store 9||Privado|com.microsoft.teams.template.OnboardEmployees|
|Contoso Store 10||Privado|com.microsoft.teams.template.OnboardEmployees|

**Users.csv**

|Nombre completo de usuario |UPN o ID de usuario|Nombre del equipo|Tipo de acción|Propietario o miembro|
|---------|---------|---------|---------|---------|
|Avery Howard|averyh@contoso.com|Contoso Store 1|Agregar Miembro|Propietario|
|Casey Jensen|caseyj@contoso.com|Contoso Store 2|Agregar Miembro|Propietario|
|Jessie Irwin|jessiei@contoso.com|Contoso Store 3|Agregar Miembro|Propietario|
|Manjeet Bhatia|manjeetb@contoso.com|Contoso Store 4|Agregar Miembro|Propietario|
|Mikaela Lee|mikaelal@contoso.com|Contoso Store 5|Agregar Miembro|Propietario|
|Morgan Conners|morganc@contoso.com|Contoso Store 6|Agregar Miembro|Miembro|
|Oscar Ward|oscarw@contoso.com|Contoso Store 7|Agregar Miembro|Miembro|
|Rene Pelletier|renep@contoso.com|Contoso Store 8|Agregar Miembro|Miembro|
|Sydney Mattos|sydneym@contoso.com|Contoso Store 9|Agregar Miembro|Miembro|
|Violeta Martínez|violetm@contoso.com|Contoso Store 10|Agregar Miembro|Miembro|

### <a name="step-2-deploy-your-teams"></a>Paso 2: Implementar los equipos

Ahora que ha creado los archivos CSV, está listo para configurar su entorno e implementar sus equipos.

Use el ```New-CsBatchTeamsDeployment``` cmdlet para enviar un lote de equipos para crear. Se genera un id. de orquestación para cada lote. A continuación, puede usar el ```Get-CsBatchTeamsDeployment``` cmdlet para realizar un seguimiento del progreso y el estado de cada lote.

1. Instale PowerShell versión 7 o posterior. Para obtener instrucciones detalladas, vea [Instalar PowerShell en Windows](/powershell/scripting/install/installing-powershell-on-windows).
1. Ejecute PowerShell en modo de administrador.
1. Ejecute lo siguiente para desinstalar cualquier módulo de PowerShell de Teams instalado previamente.

    ```powershell
    Uninstall-module -Name MicrosoftTeams -Force -Allversions
    ```

    Si recibe un mensaje de error, significa que ya está listo. Vaya al paso siguiente.
1. Descargue e instale la [última versión del módulo de PowerShell de Teams](https://www.powershellgallery.com/packages/MicrosoftTeams).

1. Ejecute lo siguiente para conectarse a Teams.

    ```powershell
    Connect-MicrosoftTeams
    ```

    Cuando se le solicite, inicie sesión con sus credenciales de administrador.

1. Ejecute lo siguiente para obtener una lista de los comandos del módulo de PowerShell de Teams.

    ```powershell
    Get-Command -Module MicrosoftTeams
    ```

    Compruebe que ```New-CsBatchTeamsDeployment``` y ```Get-CsBatchTeamsDeployment``` se muestran.

1. Ejecute lo siguiente para implementar un lote de equipos. En este comando, especifique la ruta de acceso a los archivos CSV y las direcciones de correo electrónico de hasta cinco destinatarios para notificar sobre esta implementación.

    ```powershell
    New-CsBatchTeamsDeployment -TeamsFilePath "Your CSV file path" -UsersFilePath "Your CSV file path" -UsersToNotify "Email addresses" 
    ```

    Por ejemplo:

    ```powershell
    New-CsBatchTeamsDeployment -TeamsFilePath "C:\dscale\Teams.csv" -UsersFilePath "C:\dscale\Users.csv" -UsersToNotify "adminteams@contoso.com,adelev@contoso.com"
    ```

    Los destinatarios recibirán notificaciones por correo electrónico sobre el estado de la implementación. El correo electrónico contiene el id. de orquestación del lote que envió y los errores que se hayan podido producir.

1. Ejecute lo siguiente para comprobar el estado del lote que ha enviado.

    ```powershell
    Get-CsBatchTeamsDeploymentStatus -OrchestrationId "OrchestrationId"
    ```

## <a name="send-us-feedback"></a>Envíenos su opinión

Valoramos tus comentarios. Facilidad de uso, confiabilidad y rendimiento&mdash;lo damos la bienvenida a todo.

Envíe [dscale@microsoft.com](mailto:dscale@microsoft.com) e incluya el id. de orquestación y el archivo de error, si lo tiene.

## <a name="related-articles"></a>Artículos relacionados

- [Descripción de PowerShell para Teams](teams-powershell-overview.md)
