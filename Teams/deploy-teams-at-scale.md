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
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 655e79e70945419c446dab3d721334a1a70b0e9e
ms.sourcegitcommit: d54217d3c339fe02f83d86efe50dabe67528a14c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2022
ms.locfileid: "65947237"
---
# <a name="deploy-teams-at-scale-for-frontline-workers-in-microsoft-teams"></a>Implementar equipos a escala para los trabajadores de primera línea en Microsoft Teams

> [!NOTE]
> Esta característica se encuentra actualmente en vista previa privada. Si quieres participar en la versión preliminar privada, ponte en contacto con nosotros en [dscale@microsoft.com](mailto:dscale@microsoft.com).

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
- Mantente informado por correo electrónico, incluyendo la finalización, el estado y los errores (si los hubiera). Se notifica a los propietarios y miembros del equipo.

## <a name="how-to-deploy-teams-at-scale"></a>Cómo implementar equipos a escala

> [!NOTE]
> Antes de implementar los equipos, asegúrese de que todos los propietarios de equipos tienen una licencia de Teams.

Siga estos pasos para implementar un gran número de equipos a la vez.

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

1. Ejecute lo siguiente para implementar un lote de equipos. Puede introducir hasta cinco direcciones de correo electrónico en el parámetro **UsersToNotify** .

    ```powershell
    New-CsBatchTeamsDeployment -TeamsFilePath "*Your file path*" -UsersFilePath "*Your file path*" -UsersToNotify *Email addresses* 
    ```

1. Ejecute lo siguiente para comprobar el estado del lote que ha enviado.

    ```powershell
    Get-CsBatchTeamsDeploymentStatus -OrchestrationId "OrchestrationId"
    ```

## <a name="send-us-feedback"></a>Envíenos su opinión

Valoramos tus comentarios. Facilidad de uso, confiabilidad y rendimiento&mdash;lo damos la bienvenida a todo.

Envíe [dscale@microsoft.com](mailto:dscale@microsoft.com) e incluya el id. de orquestación y el archivo de error, si lo tiene.

## <a name="related-articles"></a>Artículos relacionados

- [Descripción de PowerShell para Teams](teams-powershell-overview.md)
