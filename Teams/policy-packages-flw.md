---
title: Paquetes de directivas de Teams para los trabajadores de primera línea
ms.author: v-lanachin
author: LanaChin
manager: samanro
ms.reviewer: ''
ms.topic: article
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- m365-frontline
appliesto:
- Microsoft Teams
- Microsoft 365 for frontline workers
f1.keywords: ''
ms.custom: ''
ms.localizationpriority: high
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft 365 for frontline workers
description: Obtenga información sobre cómo usar y administrar paquetes de directivas de Teams para los trabajadores de primera línea de su organización.
ms.openlocfilehash: 20f0f926a50a56140bab8d20c9c663e0020ac3c0
ms.sourcegitcommit: c4ec82b7d8a820362b6b0276470b0dea95a628df
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/15/2022
ms.locfileid: "66819583"
---
# <a name="teams-policy-packages-for-frontline-workers"></a>Paquetes de directivas de Teams para los trabajadores de primera línea

## <a name="overview"></a>Información general

Un [paquete de directivas](manage-policy-packages.md) en Microsoft Teams es una colección de directivas y configuraciones de directiva predefinidas que puede asignar a los usuarios que tienen roles similares en la organización. Los paquetes de directivas simplifican y ayudan a proporcionar consistencia al administrar directivas.

Puede personalizar la configuración de las directivas del paquete para adaptarla a las necesidades de los usuarios. Al cambiar la configuración de las directivas de un paquete de directiva, todos los usuarios asignados a ese paquete obtienen la configuración actualizada. Puede administrar paquetes de directiva con el Centro de administración de Microsoft Teams o PowerShell.

Los paquetes de directiva pre define directivas para las siguientes directivas, dependiendo del paquete:

- Mensajería 
- Reuniones
- Llamadas
- Configuración de la aplicación
- Eventos en directo

Teams incluye el **administrador de primera línea** y los paquetes de directivas de **los trabajadores de primera línea**.

|Nombre del paquete en el Centro de administración de Microsoft Teams|Descripción |
|---------|---------|
|**Administrador de primera línea** |Crea un conjunto de directivas y aplica esa configuración a los administradores de primera línea de su organización. |
|**Trabajador de primera línea**  |Crea un conjunto de directivas y aplica esa configuración a los trabajadores de primera línea de la organización.|

:::image type="content" source="media/policy-packages-flw.png" alt-text="Captura de pantalla de los paquetes de directivas de primera línea." lightbox="media/policy-packages-flw.png":::

Cada directiva individual se indica con el nombre del paquete de directivas para que pueda identificar fácilmente las directivas vinculadas a un paquete de directivas. Por ejemplo, al asignar el paquete de directivas del administrador de primera línea a los administradores de almacenamiento de la organización, se crea una directiva denominada Frontline_Manager para cada directiva del paquete.

:::image type="content" source="media/policy-packages-flw-frontline-manager.png" alt-text="Captura de pantalla de directivas en el paquete de directivas del Administrador de primera línea." lightbox="media/policy-packages-flw-frontline-manager.png":::

## <a name="manage-policy-packages"></a>Administrar los paquetes de directivas

### <a name="view"></a>Ver

Ver la configuración de cada directiva en un paquete de directivas antes de asignar un paquete. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Paquetes de directivas**, escoja el nombre del paquete y seleccione el nombre de la directiva.

Decida si los valores predefinidos son adecuados para su organización o si necesita personalizarlos para que sean más restrictivos o flexibles en función de las necesidades de su organización.

### <a name="customize"></a>Personalizar

Personalice la configuración de las directivas en el paquete de directivas, según sea necesario, para adecuarlas a las necesidades de su organización. Los cambios que realice en la configuración de directivas se aplican automáticamente a los usuarios a los que se les asigna el paquete. Para editar la configuración de una directiva en un paquete de directivas, en la navegación izquierda del Centro de administración de Microsoft Teams vaya a **Paquetes de directivas**, seleccione el paquete de directivas, seleccione el nombre de la directiva que desee editar y seleccione **Editar**.

Tenga en cuenta que también puede cambiar la configuración de las directivas en un paquete después de asignar el paquete de directivas. Para obtener más información, consulte [Personalizar directivas en un paquete de directivas](manage-policy-packages.md#customize-policies-in-a-policy-package).

### <a name="assign"></a>Asignar

Asigne el paquete de directiva a los usuarios. Si un usuario tiene asignada una directiva y, después, asigna otra directiva, la asignación más reciente tendrá prioridad.

> [!NOTE]
> Cada usuario necesitará el complemento de Comunicaciones avanzadas para recibir una tarea de paquete personalizado de directiva. Para más información, consulte [Complemento de Comunicaciones avanzadas para Microsoft Teams](/microsoftteams/teams-add-on-licensing/advanced-communications).

#### <a name="assign-a-policy-package-to-one-or-several-users"></a>Asignar un paquete de directivas a uno o más usuarios

Para asignar un paquete de directivas a uno o más usuarios, vaya al panel de navegación izquierdo del Centro de administración de Microsoft Teams. Allí, seleccione **Paquetes de directivas** y, después, **Administrar usuarios**.  

:::image type="content" source="media/policy-packages-flw-frontline-manager-assign.png" alt-text="Captura de pantalla de cómo asignar un paquete de directivas a un usuario en el Centro de administración de Teams." lightbox="media/policy-packages-flw-frontline-manager-assign.png":::

Para obtener más información, consulte [Asignar un paquete de directivas a un lote de usuarios](assign-policy-packages.md#assign-a-policy-package-to-users).

#### <a name="assign-a-policy-package-to-a-group"></a>Asignar un paquete de directivas a un grupo

La opción de asignar un paquete de directiva a grupos le permite asignar múltiples directivas a un grupo de usuarios, como un grupo de seguridad o una lista de distribución. La asignación de directiva se extiende a los miembros del grupo en función de las reglas de prioridad. A medida que se agregan o se eliminan miembros de un grupo, sus asignaciones de directivas heredadas se actualizan correspondientemente. Este método es el recomendado para grupos de hasta 50 000 usuarios, pero también funciona con grupos más grandes.

Para obtener más información, consulte [Asignar un paquete de directivas a un grupo](assign-policy-packages.md#assign-a-policy-package-to-a-group).

#### <a name="assign-a-policy-package-to-a-large-set-batch-of-users"></a>Asignar un paquete de directivas a un conjunto amplio (un lote) de usuarios

Use la asignación de paquete de directiva por lotes para asignar un paquete de directivas a grandes grupos de usuarios de una sola vez. Use el cmdlet [New-CsBatchPolicyPackageAssignmentOperation](/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) para enviar un lote de usuarios y el paquete de directivas que quiera asignar. Las asignaciones se procesan como una operación de segundo plano y se genera un identificador de operación para cada lote.

Un lote puede contener hasta 5000 usuarios. Puede especificar usuarios por su id. de objeto o dirección del Protocolo de inicio de sesión (SIP). Para obtener más información, consulte [Asignar un paquete de directivas a un lote de usuarios](assign-policy-packages.md#assign-a-policy-package-to-a-batch-of-users).

## <a name="related-topics"></a>Temas relacionados

- [Administrar los paquetes de directivas para Teams](manage-policy-packages.md)
- [Asignar paquetes de directivas a usuarios y grupos](assign-policy-packages.md)
