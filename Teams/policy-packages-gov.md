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
ms.openlocfilehash: 738197a82303c1149ebc89a8e3ad7c6b37df90eb
ms.sourcegitcommit: bd13aecbb25c14e17d1b64343df6d80c90b2aa45
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/19/2020
ms.locfileid: "46804048"
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

Vea la configuración de cada directiva en un paquete de directivas antes de asignar un paquete. En el centro de navegación izquierdo del centro de administración de Microsoft Teams, seleccione **paquetes de directivas**, seleccione el nombre del paquete y, a continuación, seleccione el nombre de la Directiva.

Decida si los valores predefinidos son adecuados para su organización o si necesita personalizarlos para que sean más restrictivos o flexibles según las necesidades de su organización.

### <a name="customize"></a>Personalizar

Personalice la configuración de las directivas en el paquete de directivas según sea necesario para adaptarse a las necesidades de su organización. Los cambios que realice en la configuración de la Directiva se aplican automáticamente a los usuarios que tienen asignado el paquete. Para editar la configuración de una directiva en un paquete de directivas, en el centro de administración de Microsoft Teams, seleccione el paquete de directivas, seleccione el nombre de la Directiva que desea editar y, después, haga clic en **Editar**.

Tenga en cuenta que también puede cambiar la configuración de las directivas en un paquete después de asignar el paquete de directivas. Para obtener más información, consulte [personalizar directivas en un paquete de directivas](manage-policy-packages.md#customize-policies-in-a-policy-package). 

### <a name="assign"></a>Asignar

Asignar el paquete de directivas a los usuarios. Para asignar un paquete de directivas a uno o varios usuarios, haga clic en **administrar usuarios**. También puede [usar PowerShell](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) para asignar un paquete de directivas a lotes grandes de usuarios. 

Para conocer los pasos sobre cómo asignar un paquete de directivas mediante el centro de administración de Microsoft Teams o PowerShell, consulte [asignar un paquete de directivas](manage-policy-packages.md#assign-a-policy-package).

![Captura de pantalla de cómo asignar un paquete de directivas en el centro de administración](media/policy-packages-gov-assign.png)

Si un usuario tiene asignada una directiva y posteriormente asigna otra, la asignación más reciente tendrá prioridad.

## <a name="related-topics"></a>Temas relacionados

[Administrar los paquetes de directivas para Teams](manage-policy-packages.md)

[Asignar directivas a los usuarios de Teams](assign-policies.md) 
