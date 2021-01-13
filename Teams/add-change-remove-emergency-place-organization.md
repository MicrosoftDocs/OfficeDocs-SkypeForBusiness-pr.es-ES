---
title: Agregar, cambiar o quitar lugares para ubicaciones de emergencia
author: cichur
ms.author: v-cichur
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
localization_priority: Normal
f1.keywords:
- NOCSH
description: Obtenga información sobre cómo agregar, cambiar o quitar un lugar para una ubicación de emergencia de su organización en el Centro de administración de Microsoft Teams.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: d390113b30558b94fadab695731b8c08b4c01ace
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806280"
---
# <a name="add-change-or-remove-a-place-for-an-emergency-location-in-your-organization"></a>Agregar, cambiar o quitar una ubicación de emergencia para su organización

Según el número de ubicaciones físicas de su organización, puede agregar lugares para edificios, pisos y oficinas con el objetivo de crear una ubicación de emergencia más específica. Vea [Administrar llamadas de emergencia](what-are-emergency-locations-addresses-and-call-routing.md) para obtener más información.
  
Para obtener información sobre cómo obtener un plan de llamadas y cuánto cuestan, consulte licencias [de complementos de Teams.](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)

Puede administrar las ubicaciones de emergencia de su organización en el centro de administración de Microsoft Teams o mediante PowerShell.
  
## <a name="add-a-place-to-an-emergency-location"></a>Agregar un lugar a una ubicación de emergencia

### <a name="using-the-microsoft-teams-admin-center"></a>Usar el Centro de administración de Microsoft Teams

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, haga clic en  >  **Ubicaciones, Direcciones de emergencia.**
2. En la lista, haga clic en el nombre de la ubicación a la que desea agregar un lugar.
3. En la **pestaña Lugares,** haga clic en **Agregar.**
4. Escriba un nombre de lugar y, a continuación, haga clic en **Aplicar.**

### <a name="using-powershell"></a>Con PowerShell

Vea [New-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/new-csonlinelislocation).
    
## <a name="change-a-place-for-an-emergency-location"></a>Cambiar un lugar para una ubicación de emergencia

### <a name="using-the-microsoft-teams-admin-center"></a>Usar el Centro de administración de Microsoft Teams

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, haga clic en  >  **Ubicaciones, Direcciones de emergencia.**
2. En la lista, haga clic en el nombre de la ubicación para la que desea cambiar un lugar.
3. En la **pestaña** Lugares, seleccione el lugar que desea cambiar y, a continuación, haga clic en **Editar.**
4. Actualice la información del lugar y, a continuación, haga clic en **Aplicar.**

### <a name="using-powershell"></a>Con PowerShell

Vea [Set-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/set-csonlinelislocation).
    
## <a name="remove-a-place-from-an-emergency-location"></a>Quitar un lugar de una ubicación de emergencia

### <a name="using-the-microsoft-teams-admin-center"></a>Usar el Centro de administración de Microsoft Teams

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, haga clic en  >  **Ubicaciones, Direcciones de emergencia.**
2. En la lista, haga clic en el nombre de la ubicación para la que desea quitar un lugar.
3. En la **pestaña** Lugares, seleccione el lugar que desea quitar y, a continuación, haga clic en **Eliminar.**

### <a name="using-powershell"></a>Con PowerShell

Vea [Remove-CsOnlineLisLocation.](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelislocation)
    
## <a name="related-topics"></a>Temas relacionados

- [Agregar, cambiar o quitar una ubicación de emergencia para su organización](add-change-remove-emergency-place-organization.md)
- [Administrar los números de teléfono para su organización](/microsoftteams/manage-phone-numbers-for-your-organization)
- [Términos y condiciones de las llamadas de emergencia](/microsoftteams/emergency-calling-terms-and-conditions)
