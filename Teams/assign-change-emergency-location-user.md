---
title: Asignar o cambiar la ubicación de emergencia de un usuario
author: lanachin
ms.author: v-lanac
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
description: En este artículo, obtendrá información sobre cómo asignar o cambiar una ubicación de emergencia para los usuarios de su organización.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0f2e927e90a7ac6b79d6eb63c807e063ca7d78c7
ms.sourcegitcommit: d1e4e1105d86745009cf0fdf42d1fc5ad545a952
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/18/2020
ms.locfileid: "46788664"
---
# <a name="assign-or-change-an-emergency-location-for-a-user"></a>Asignar o cambiar la ubicación de emergencia de un usuario

Cuando configuras planes de llamadas, deberás asignar una ubicación de emergencia a cada número de teléfono o usuario. En los países de Europa, la ubicación de emergencia está asociada al número de teléfono cuando se obtiene de Microsoft 365 u Office 365 o cuando se transfiere un número de teléfono a Microsoft 365 u Office 365. En los Estados Unidos, la ubicación de emergencia está asociada al número de teléfono cuando se le asigna al usuario. La dirección de emergencia se puede cambiar si el usuario al que está asignada se mueve a una nueva ubicación. Para obtener más información sobre las direcciones y ubicaciones de emergencia, vea [¿Qué son las ubicaciones de emergencia, los lugares y el enrutamiento de llamadas?](/microsoftteams/what-are-emergency-locations-addresses-and-call-routing).
  
Para obtener información sobre cómo obtener un plan de llamadas y cuánto cuestan, vea [licencias complementarias de Teams](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing).
  
Puede asignar o cambiar una ubicación de emergencia para un usuario en el centro de administración de Microsoft Teams o mediante PowerShell.

## <a name="using-the-microsoft-teams-admin-center"></a>Usar el centro de administración de Microsoft Teams

1. En el centro de navegación izquierdo del centro de administración de Microsoft Teams, haga clic en números de teléfono de **voz**  >  **Phone numbers**.

2. En la página **números de teléfono** , haga clic en la pestaña **números** , seleccione un número de usuario en la lista y, a continuación, haga clic en **Editar**.

3. En el panel de **edición** , en **Ubicación de emergencia**, realice una de las siguientes acciones:

   - Para asignar una ubicación de emergencia, busque y seleccione una ubicación de emergencia.

   - Para cambiar la ubicación de emergencia que ya está asignada al usuario, haga clic en **X** para quitar la ubicación existente y, a continuación, busque y seleccione la ubicación que desea asignar.

4. En función de si desea enviar un correo electrónico al usuario con la información de su número de teléfono, desactive o Active el **usuario de correo electrónico con información sobre el número de**teléfono. De forma predeterminada, esta opción está activada.

5. Haga clic en **Aplicar**.

## <a name="using-powershell"></a>Con PowerShell

Consulte [set-CsOnlineVoiceUser](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceuser). 

    
## <a name="related-topics"></a>Temas relacionados

- [Administrar las llamadas de emergencia](what-are-emergency-locations-addresses-and-call-routing.md)
- [Agregar, cambiar o quitar una ubicación de emergencia para su organización](add-change-remove-emergency-location-organization.md)
- [Agregar, cambiar o quitar una ubicación de emergencia para su organización](add-change-remove-emergency-place-organization.md)
- [Asignar o cambiar la ubicación de emergencia de un usuario](assign-change-emergency-place-user.md)
- [Administrar los números de teléfono para su organización](/microsoftteams/manage-phone-numbers-for-your-organization)
- [Términos y condiciones de las llamadas de emergencia](/microsoftteams/emergency-calling-terms-and-conditions)
- [Descripción de PowerShell para Teams](teams-powershell-overview.md)
