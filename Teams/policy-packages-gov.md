---
title: Paquetes de directivas de Teams para administración pública
author: lanachin
ms.author: v-lanac
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
ms.openlocfilehash: 8ef632689cb52180e8fd18cf4047fb9a25150885
ms.sourcegitcommit: ee217e1d7188842c7becd19387fd421b485c3575
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2020
ms.locfileid: "48908599"
---
# <a name="teams-policy-packages-for-government"></a>Paquetes de directivas de Teams para administración pública

> [!NOTE]
> Los paquetes de directivas actualmente no están disponibles en las implementaciones de Microsoft 365 gubernamentales GCC High o DoD.

## <a name="overview"></a>Información general

Un [paquete de directivas](manage-policy-packages.md) de Microsoft Teams es una colección de directivas y opciones de directiva predefinidas que puede asignar a los usuarios que tienen roles similares en su organización. Los paquetes de directivas simplifican y ayudan a proporcionar consistencia al administrar directivas. Puede personalizar la configuración de las directivas en el paquete para satisfacer las necesidades de los usuarios. Al cambiar la configuración de las directivas en un paquete de directivas, todos los usuarios asignados a ese paquete obtienen la configuración actualizada. Puede administrar paquetes de directivas mediante el centro de administración de Microsoft Teams o PowerShell.

Los paquetes de directivas predefinen directivas para los siguientes elementos, según el paquete:

- Mensajería 
- Reuniones
- Llamadas
- Configuración de la aplicación
- Eventos en directo

Actualmente, Teams incluye los siguientes paquetes de directivas para administración pública.

|Nombre del paquete en el centro de administración de Microsoft Teams|Recomendado para|Descripción |
|---------|---------|---------|
|Funcionario de seguridad pública  |Funcionarios de seguridad pública de su organización gubernamental  |Crea un conjunto de directivas y parámetros de directivas que se aplican a los directores de seguridad pública de su organización. |
|Los Firstline Manager  |Los Firstline managers en su organización gubernamental |Crea un conjunto de directivas y aplica esta configuración a los administradores de los Firstline de su organización.|
|Trabajador de los Firstline  |Trabajadores de los Firstline en su organización gubernamental |Crea un conjunto de directivas y aplica esta configuración a los trabajadores de los Firstline de su organización.|

![Captura de pantalla de paquetes de política sanitaria](media/policy-packages-gov.png)

A cada directiva individual se le da el nombre del paquete de directivas para que pueda identificar fácilmente las directivas vinculadas a un paquete de directivas. Por ejemplo, cuando se asigna el paquete de directiva del oficial de seguridad pública a los usuarios de su organización, se crea una directiva denominada PublicSafety_Officer para cada Directiva del paquete.

![Captura de pantalla de directivas en el paquete de trabajadores clínico de cuidado de la salud](media/policy-packages-public-safety-officer.png)

## <a name="manage-policy-packages"></a>Administrar los paquetes de directivas 

### <a name="view"></a>Ver

Vea la configuración de cada directiva en un paquete de directivas antes de asignar un paquete. En el centro de navegación izquierdo del centro de administración de Microsoft Teams, seleccione **paquetes de directivas** , seleccione el nombre del paquete y, a continuación, seleccione el nombre de la Directiva.

Decida si los valores predefinidos son adecuados para su organización o si necesita personalizarlos para que sean más restrictivos o flexibles según las necesidades de su organización.

### <a name="customize"></a>Personalizar

Personalice la configuración de las directivas en el paquete de directivas según sea necesario para adaptarse a las necesidades de su organización. Los cambios que realice en la configuración de la Directiva se aplican automáticamente a los usuarios que tienen asignado el paquete. Para editar la configuración de una directiva en un paquete de directivas, en el centro de administración de Microsoft Teams, seleccione el paquete de directivas, seleccione el nombre de la Directiva que desea editar y, después, haga clic en **Editar**.

Tenga en cuenta que también puede cambiar la configuración de las directivas en un paquete después de asignar el paquete de directivas. Para obtener más información, consulte [personalizar directivas en un paquete de directivas](manage-policy-packages.md#customize-policies-in-a-policy-package). 

### <a name="assign"></a>Asignar

Asignar el paquete de directivas a los usuarios. Si un usuario tiene asignada una directiva y posteriormente asigna otra, la asignación más reciente tendrá prioridad.

#### <a name="assign-a-policy-package-to-one-or-several-users"></a>Asignar un paquete de directivas a uno o varios usuarios

Para asignar un paquete de directivas a uno o varios usuarios, en el navegación izquierdo del centro de administración de Microsoft Teams, vaya a **paquetes de directivas** y, después, seleccione **administrar usuarios**.  

![Captura de pantalla de cómo asignar un paquete de directivas en el centro de administración](media/policy-packages-healthcare-assign.png)

Para obtener más información, consulte [asignar un paquete de directivas](manage-policy-packages.md#assign-a-policy-package).

Si un usuario tiene asignada una directiva y posteriormente asigna otra, la asignación más reciente tendrá prioridad.

#### <a name="assign-a-policy-package-to-a-group"></a>Asignar un paquete de directivas a un grupo

**Esta característica está en versión preliminar privada**

La asignación de paquetes de directivas a grupos le permite asignar varias directivas a un grupo de usuarios, como un grupo de seguridad o una lista de distribución. La asignación de Directiva se propaga a los miembros del grupo según las reglas de prioridad. A medida que se agregan o quitan miembros de un grupo, sus asignaciones de directivas heredadas se actualizan según corresponda. Este método se recomienda para grupos de hasta 50.000 usuarios, pero también funciona con grupos más grandes.

Para obtener más información, consulte [asignar un paquete de directivas a un grupo](assign-policies.md#assign-a-policy-package-to-a-group).

#### <a name="assign-a-policy-package-to-a-large-set-batch-of-users"></a>Asignar un paquete de directivas a un conjunto grande (lote) de usuarios

Use la asignación de paquetes de directivas por lotes para asignar un paquete de directivas a grandes conjuntos de usuarios a la vez. Use el cmdlet [New-CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) para enviar un lote de usuarios y el paquete de directivas que desea asignar. Las asignaciones se procesan como una operación en segundo plano y se genera un identificador de operación para cada lote.

Un lote puede contener hasta 5.000 usuarios. Puede especificar los usuarios por su identificador de objeto, UPN, dirección SIP o dirección de correo electrónico. Para obtener más información, consulte [asignar un paquete de directivas a un lote de usuarios](assign-policies.md#assign-a-policy-package-to-a-batch-of-users).

## <a name="related-topics"></a>Temas relacionados

[Administrar los paquetes de directivas para Teams](manage-policy-packages.md)

[Asignar directivas a los usuarios de Teams](assign-policies.md) 
