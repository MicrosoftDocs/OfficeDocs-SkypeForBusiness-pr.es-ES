---
title: Asignar o cambiar lugares para ubicaciones de emergencia para los usuarios
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- NOCSH
description: En este artículo, aprenderá a asignar o cambiar el lugar de una ubicación de emergencia para los usuarios de su organización.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9bd69356be22954ee1b1b44b2dcc1a52c1e72507
ms.sourcegitcommit: 197debacdcd1f7902f6e16940ef9bec8b07641af
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/02/2021
ms.locfileid: "60634889"
---
# <a name="assign-or-change-the-place-for-an-emergency-location-for-a-user"></a>Asignar o cambiar el lugar de una ubicación de emergencia para un usuario

Independientemente de la opción de conectividad [RTC](pstn-connectivity.md) que elija Planes de llamadas de Microsoft, Operador Conectar o Enrutamiento directo, es necesario asignar una ubicación de emergencia a cada número de teléfono &mdash; o &mdash; usuario.

Sin embargo, según la opción de conectividad RTC, la forma en que administra y asigna ubicaciones de emergencia para un usuario puede variar. Para obtener más información, vea [Administrar llamadas de emergencia.](what-are-emergency-locations-addresses-and-call-routing.md)

En este artículo se describe  cómo asignar o cambiar el lugar de una ubicación de emergencia para un usuario en el centro de administración de Microsoft Teams o mediante PowerShell.

Este artículo se aplica a planes de llamadas y Conectar.

## <a name="using-the-microsoft-teams-admin-center"></a>Usar el Centro de administración de Microsoft Teams

1. En el panel de navegación izquierdo del centro Microsoft Teams de administración, haga **clic**  >  **en Teléfono números.**

2. En la **Teléfono números,** haga  clic en la pestaña Números, seleccione un número de usuario en la lista y, a continuación, haga clic en **Editar.**

3. En el **panel Editar,** en **Ubicación de emergencia**, realice una de las siguientes acciones:

    - Para asignar un lugar, busque la ubicación o el lugar y, a continuación, seleccione el lugar en los resultados de la búsqueda.

    - Para cambiar el lugar que ya está asignado al usuario, haga clic en **X** para quitar la ubicación y el lugar existentes, busque y seleccione el lugar que desea asignar.

4. Dependiendo de si desea enviar un correo electrónico al usuario con su información de número de teléfono, desactive o active Usuario de correo electrónico con información **de número de teléfono.** De forma predeterminada, está en.

5. Haga clic en **Aplicar**.

## <a name="using-powershell"></a>Con PowerShell

Vea [Set-CsOnlineLisLocation](/powershell/module/skype/set-csonlinelislocation).
    
## <a name="related-topics"></a>Temas relacionados

- [Administrar llamadas de emergencia](what-are-emergency-locations-addresses-and-call-routing.md)
- [Asignar o cambiar la ubicación de emergencia de un usuario](assign-change-emergency-location-user.md)
- [Agregar, cambiar o quitar una ubicación de emergencia para su organización](add-change-remove-emergency-location-organization.md)
- [Agregar, cambiar o quitar una ubicación de emergencia para su organización](add-change-remove-emergency-place-organization.md)
- [Administrar los números de teléfono para su organización](/microsoftteams/manage-phone-numbers-for-your-organization)
- [Términos y condiciones de las llamadas de emergencia](./emergency-calling-terms-and-conditions.md)