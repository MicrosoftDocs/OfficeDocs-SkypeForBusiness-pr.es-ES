---
title: Usar la funcionalidad de la unidad administrativa en Microsoft Teams
author: cichur
ms.author: v-cichur
ms.reviewer: prasad.ghlove
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Obtenga información sobre cómo usar la funcionalidad de la unidad administrativa en Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 556f220c9ca250f014ae604c96cabf9ef0b0ca0f
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "58636796"
---
# <a name="administrative-unit-functionality-for-device-management-in-teams"></a>Funcionalidad de unidad administrativa para la administración de dispositivos en Teams

Tenga acceso basado en roles más granular para la administración de dispositivos con el centro Microsoft Teams administración. Hemos implementado el concepto de unidad administrativa para la administración de dispositivos a través del centro Teams administración.

Con el concepto de unidad administrativa, garantizará el acceso a un conjunto específico de recursos a un administrador dedicado. La unidad administrativa limita el acceso a todos los recursos. Puede ampliar la misma funcionalidad para la administración Teams dispositivos.

> [!NOTE]
> El concepto de unidad administrativa solo está disponible para el Teams de administrador de dispositivos actualmente.

Como ejemplo, Contoso tiene operaciones en distintas geografías. Ana es administradora global de TI en Londres, mientras que Prashant es administradora de TI para India. Hoy, cuando Prashant inicia sesión en el centro de administración de Teams con el rol de administrador de dispositivos, pueden ver dispositivos en todo el mundo. Alicia quiere restringir el acceso de Prashant solo a los dispositivos que están presentes en la India. El concepto de unidades administrativas ayuda a resolver este problema. Más información sobre [el concepto de unidad administrativa.](/azure/active-directory/roles/administrative-units)

![un diagrama que muestra escenarios](media/au-diagram.png)

## <a name="creation-of-administrative-units"></a>Creación de unidades administrativas

Cree unidades administrativas en Azure Portal y asigne administradores para las unidades administrativas correspondientes. Obtenga más información sobre cómo asignar unidades administrativas en [administrar unidades de administración.](/azure/active-directory/roles/admin-units-manage)

![un ejemplo de unidades administrativas de la empresa](media/au-example.png)

Una vez creado, el administrador global de TI puede agregar usuarios de dispositivo que se correspondan con esa unidad administrativa.

![una empresa de ejemplo con vista previa de usuarios](media/au-example2.png)

La asignación del rol se puede realizar a través de PowerShell con el cmdlet [Add-AzureADMSScopedRoleMembership.](/powershell/module/azuread/add-azureadmsscopedrolemembership?view=azureadps-2.0)

Una vez que haya asignado roles a usuarios para unidades administrativas, los usuarios deben iniciar sesión en Teams de administración para empezar a administrar dispositivos de ámbito.

## <a name="experience-for-administrative-unit-admin"></a>Experiencia para administrador de unidades administrativas

Si a los mismos administradores se les asigna la responsabilidad de varias unidades administrativas, pueden cambiar entre unidades administrativas sin salir del portal. En la vista unidad administrativa cambiada, solo verán el conjunto de dispositivos asociados a la nueva unidad administrativa.
