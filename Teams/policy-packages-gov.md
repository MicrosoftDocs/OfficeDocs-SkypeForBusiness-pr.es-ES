---
title: Paquetes de directivas de Teams para administración pública
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
appliesto:
- Microsoft Teams
f1.keywords: ''
ms.custom: ''
localization_priority: Normal
search.appverid: MET150
description: Obtenga información sobre cómo usar y administrar paquetes de directivas de Teams para su organización gubernamental.
ms.openlocfilehash: 19e2c692f2b5109e3ef0915ced9fd2b68c56e482
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812890"
---
# <a name="teams-policy-packages-for-government"></a>Paquetes de directivas de Teams para administración pública

> [!NOTE]
> Los paquetes de directivas no están disponibles actualmente en las implementaciones de Microsoft 365 Government GCC High o DoD.

## <a name="overview"></a>Descripción general

Un [paquete de directivas](manage-policy-packages.md) en Microsoft Teams es una colección de directivas predefinidas y configuraciones de directiva que puede asignar a los usuarios que tienen roles similares en su organización. Los paquetes de directivas simplifican y ayudan a proporcionar consistencia al administrar directivas. Puede personalizar la configuración de las directivas del paquete para adaptarla a las necesidades de los usuarios. Al cambiar la configuración de directivas en un paquete de directivas, todos los usuarios asignados a ese paquete obtienen la configuración actualizada. Puede administrar paquetes de directivas mediante el Centro de administración de Microsoft Teams o PowerShell.

Los paquetes de directiva definen previamente directivas para las siguientes, dependiendo del paquete:

- Mensajería 
- Reuniones
- Llamadas
- Configuración de la aplicación
- Eventos en directo

Teams incluye actualmente los siguientes paquetes de directiva para administración pública.

|Nombre del paquete en el Centro de administración de Microsoft Teams|Recomendado para|Descripción |
|---------|---------|---------|
|Responsable de seguridad pública  |Responsables de seguridad pública de su organización gubernamental  |Crea un conjunto de directivas y configuraciones de directivas que se aplican a los responsables de seguridad pública de su organización. |
|Firstline Manager  |Jefes de primera línea de la organización gubernamental |Crea un conjunto de directivas y aplica esa configuración a los administradores de primera línea de su organización.|
|Trabajador de primera línea  |Firstline Workers in your government organization |Crea un conjunto de directivas y aplica esa configuración a los Firstline Workers de su organización.|

![Captura de pantalla de paquetes de directivas sanitarias](media/policy-packages-gov.png)

A cada directiva individual se le da el nombre del paquete de directiva para que pueda identificar fácilmente las directivas vinculadas a un paquete de directivas. Por ejemplo, al asignar el paquete de directiva de responsable de seguridad pública a los usuarios de la organización, se crea una directiva denominada PublicSafety_Officer para cada directiva del paquete.

![Captura de pantalla de las directivas del paquete de trabajadores sanitarios](media/policy-packages-public-safety-officer.png)

## <a name="manage-policy-packages"></a>Administrar los paquetes de directivas

### <a name="view"></a>Ver

Ver la configuración de cada directiva en un paquete de directivas antes de asignar un paquete. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, seleccione **Paquetes de directivas**, escoja el nombre del paquete y seleccione el nombre de la directiva.

Decida si los valores predefinidos son adecuados para su organización o si necesita personalizarlos para que sean más restrictivos o flexibles en función de las necesidades de su organización.

### <a name="customize"></a>Personalizar

Personalice la configuración de las directivas en el paquete de directivas, según sea necesario, para adecuarlas a las necesidades de su organización. Los cambios que realice en la configuración de directivas se aplican automáticamente a los usuarios a los que se les asigna el paquete. Para editar la configuración de una directiva en un paquete de directivas, seleccione el paquete de directivas en el Centro de administración de Microsoft Teams. Luego, seleccione el nombre de la directiva que quiera editar y, finalmente, seleccione **Editar**.

Tenga en cuenta que también puede cambiar la configuración de las directivas en un paquete después de asignar el paquete de directivas. Para obtener más información, consulte [Personalizar directivas en un paquete de directivas](manage-policy-packages.md#customize-policies-in-a-policy-package). 

### <a name="assign"></a>Asignar

Asigne el paquete de directivas a los usuarios. Si un usuario tiene una directiva asignada y posteriormente asigna otra directiva, la asignación más reciente tendrá prioridad.

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

Use la asignación de paquete de directiva por lotes para asignar un paquete de directivas a grandes grupos de usuarios de una sola vez. Use el cmdlet [New-CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) para enviar un lote de usuarios y el paquete de directivas que quiera asignar. Las asignaciones se procesan como una operación de segundo plano y se genera un identificador de operación para cada lote.

Un lote puede contener hasta 5000 usuarios. Puede especificar los usuarios por su identificador de objeto, UPN, dirección SIP o dirección de correo electrónico. Para obtener más información, consulte [Asignar un paquete de directivas a un lote de usuarios](assign-policies.md#assign-a-policy-package-to-a-batch-of-users).

## <a name="related-topics"></a>Temas relacionados

[Administrar los paquetes de directivas para Teams](manage-policy-packages.md)

[Asignar directivas a los usuarios en Teams](assign-policies.md) 
