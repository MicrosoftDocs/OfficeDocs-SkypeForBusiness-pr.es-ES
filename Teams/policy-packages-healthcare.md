---
title: Paquetes de directivas de Teams para sanidad
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: aaglick
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
f1.keywords: ''
ms.custom: ''
localization_priority: Normal
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
description: Obtenga información sobre cómo usar y administrar paquetes de directivas de Teams para su organización sanitaria.
ms.openlocfilehash: 19c0fee14138b248c4e25d88a9103df4a5618598
ms.sourcegitcommit: 8ad05b37c0b714adb069bc2503e88366ab75c57d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/07/2021
ms.locfileid: "52796814"
---
# <a name="teams-policy-packages-for-healthcare"></a>Paquetes de directivas de Teams para sanidad

## <a name="overview"></a>Información general

Un [paquete de directivas](manage-policy-packages.md) en Microsoft Teams es una colección de directivas y configuraciones de directiva predefinidas que puede asignar a los usuarios que tienen roles similares en la organización. Los paquetes de directivas simplifican y ayudan a proporcionar consistencia al administrar directivas. Puede personalizar la configuración de las directivas del paquete para adaptarla a las necesidades de los usuarios. Al cambiar la configuración de las directivas de un paquete de directiva, todos los usuarios asignados a ese paquete obtienen la configuración actualizada. Puede administrar paquetes de directiva con el Centro de administración de Microsoft Teams o PowerShell.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Ht2o]

Los paquetes de directiva pre define directivas para las siguientes directivas, dependiendo del paquete:

- Mensajería 
- Reuniones
- Llamadas
- Configuración de la aplicación
- Eventos en directo

Teams actualmente incluye los siguientes paquetes de directivas:

|Nombre del paquete en el Centro de administración de Microsoft Teams|Recomendado para|Descripción |
|---------|---------|---------|
|Trabajador clínico de la sanidad  |Trabajadores clínicos de una organización sanitaria  |Crea un conjunto de directivas y configuraciones de directivas que proporciona a los trabajadores clínicos como los profesionales clínicos registrados, las enfermeras de cargo, los médico y los trabajadores sociales acceso completo al chat, a las llamadas, a la administración de turnos y a las reuniones. |
|Trabajador de la información sanitaria  |Profesionales de la información de su organización sanitaria |Crea un conjunto de directivas y configuraciones de directivas que dan a los trabajadores de la información como el personal de TI, el personal informático, el personal del departamento financiero y los responsables de cumplimiento normativo, acceso completo a chat, llamadas y reuniones.|
|Sala de pacientes de cuidado de la salud  |Dispositivos de sala de pacientes|Crea un conjunto de directivas y configuraciones de directivas que se aplican a las salas de pacientes de su organización de cuidados de la salud.|

![Captura de pantalla de paquetes de directivas de cuidados de la salud](media/policy-packages-healthcare.png)

Cada directiva individual se indica con el nombre del paquete de directivas para que pueda identificar fácilmente las directivas vinculadas a un paquete de directivas. Por ejemplo, cuando asigna el paquete de directivas de trabajadores clínicos sanitarios a clínicas de su organización, se crea una directiva denominada Healthcare_ClinicalWorker para cada directiva del paquete.

![Captura de pantalla de las directivas del paquete de trabajadores clínicos sanitarios](media/policy-packages-healthcare-clinical-worker.png)

## <a name="get-started-with-policy-packages"></a>Introducción a los paquetes de directiva

Para empezar con los paquetes de directivas de cuidados de la salud, en el centro de integración del Centro de administración de Microsoft, seleccione **Cuidado de la salud** y, después, seleccione **Asignar configuración de directiva por rol**. Cuando esté listo para empezar, decida los paquetes de directiva a los que quiere asignar paquetes de directiva a los usuarios de su organización.

Seleccione **Ver detalles de directiva** obtener más información sobre las directivas específicas de un paquete y sus respectivas opciones de configuración. Estos [pueden personalizarse](manage-policy-packages.md#customize-policies-in-a-policy-package) después de su asignación en el Centro de administración de Teams.

Elija uno o varios paquetes para asignar y, a continuación, haga clic en **Siguiente**. Puede buscar y agregar personas al paquete de directivas más adecuado para su rol. No se puede asignar a una persona más de un paquete de directiva a la vez.

Una vez que haya agregado los usuarios al paquete de directiva correcto, **Terminar** finaliza las selecciones. Puede seguir personalizando y administrando paquetes de directiva en el Centro de administración de Microsoft Teams.

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
> Cada usuario necesitará el complemento Comunicaciones avanzadas para recibir una asignación de paquete de directiva personalizada. Para obtener más información, vea [Complemento comunicaciones avanzadas para Microsoft Teams](/microsoftteams/teams-add-on-licensing/advanced-communications).

#### <a name="assign-a-policy-package-to-one-or-several-users"></a>Asignar un paquete de directivas a uno o más usuarios

Para asignar un paquete de directivas a uno o más usuarios, vaya al panel de navegación izquierdo del Centro de administración de Microsoft Teams. Allí, seleccione **Paquetes de directivas** y, después, **Administrar usuarios**.  

![Captura de pantalla que muestra cómo asignar un paquete de directivas en el Centro de administración](media/policy-packages-healthcare-assign.png)

Para obtener más información, consulte [Asignar un paquete de directivas](manage-policy-packages.md#assign-a-policy-package).

Si un usuario tiene una directiva asignada y posteriormente asigna otra directiva, la asignación más reciente tendrá prioridad.

#### <a name="assign-a-policy-package-to-a-group"></a>Asignar un paquete de directivas a un grupo

**Esta característica está en versión preliminar privada**

La opción de asignar un paquete de directiva a grupos le permite asignar múltiples directivas a un grupo de usuarios, como un grupo de seguridad o una lista de distribución. La asignación de directiva se extiende a los miembros del grupo en función de las reglas de prioridad. A medida que se agregan o se eliminan miembros de un grupo, sus asignaciones de directivas heredadas se actualizan correspondientemente. Este método es el recomendado para grupos de hasta 50 000 usuarios, pero también funciona con grupos más grandes.

Para obtener más información, consulte [Asignar un paquete de directivas a un grupo](assign-policies.md#assign-a-policy-package-to-a-group).

#### <a name="assign-a-policy-package-to-a-large-set-batch-of-users"></a>Asignar un paquete de directivas a un conjunto amplio (un lote) de usuarios

Use la asignación de paquete de directiva por lotes para asignar un paquete de directivas a grandes grupos de usuarios de una sola vez. Use el cmdlet [New-CsBatchPolicyPackageAssignmentOperation](/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) para enviar un lote de usuarios y el paquete de directivas que quiera asignar. Las asignaciones se procesan como una operación de segundo plano y se genera un identificador de operación para cada lote.

Un lote puede contener hasta 5000 usuarios. Puede especificar los usuarios por su identificador de objeto, UPN, dirección SIP o dirección de correo electrónico. Para obtener más información, consulte [Asignar un paquete de directivas a un lote de usuarios](assign-policies.md#assign-a-policy-package-to-a-batch-of-users).

## <a name="related-topics"></a>Temas relacionados

[Administrar los paquetes de directivas para Teams](manage-policy-packages.md)

[Asignar paquetes de directiva a usuarios y grupos](assign-policy-packages.md)
