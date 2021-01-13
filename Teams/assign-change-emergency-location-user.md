---
title: Asignar o cambiar la ubicación de emergencia de un usuario
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
description: En este artículo, aprenderá a asignar o cambiar una ubicación de emergencia para los usuarios de su organización.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8352c702d2c6d32b6384599499aa326def49fa4e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809570"
---
# <a name="assign-or-change-an-emergency-location-for-a-user"></a>Asignar o cambiar la ubicación de emergencia de un usuario

Al configurar planes de llamadas, debe asignar una ubicación de emergencia a cada número de teléfono o usuario. En los países de Europa, la ubicación de emergencia se asocia con el número de teléfono cuando se obtiene de Microsoft 365 u Office 365 o al transferir un número de teléfono a Microsoft 365 u Office 365. En los Estados Unidos, la ubicación de emergencia está asociada al número de teléfono cuando se asigna al usuario. La dirección de emergencia se puede cambiar si el usuario al que está asignado se traslada a una nueva ubicación. Para obtener más información sobre las direcciones y ubicaciones de emergencia, consulte ¿Qué son las ubicaciones [de emergencia, los lugares y el enrutamiento de llamadas?](/microsoftteams/what-are-emergency-locations-addresses-and-call-routing)
  
Para obtener información sobre cómo obtener planes de llamadas y cuánto cuestan, consulte licencias [de complementos de Teams.](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing)
  
Puede asignar o cambiar una ubicación de emergencia para un usuario en el Centro de administración de Microsoft Teams o mediante PowerShell.

## <a name="using-the-microsoft-teams-admin-center"></a>Usar el Centro de administración de Microsoft Teams

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, haga clic en **Números de** teléfono  >  **de voz.**

2. En la **página Números de** teléfono, haga clic en la **pestaña** Números, seleccione un número de usuario de la lista y, a continuación, haga clic en **Editar.**

3. En el **panel de** edición, en **Ubicación de** emergencia, realice una de las siguientes acciones:

   - Para asignar una ubicación de emergencia, busque y seleccione una ubicación de emergencia.

   - Para cambiar la ubicación de emergencia que ya está asignada al usuario, haga clic en **X** para quitar la ubicación existente y, a continuación, busque y seleccione la ubicación que desea asignar.

4. En función de si desea enviar un correo electrónico al usuario con su información de número de teléfono, desactive o active El usuario de correo electrónico con la información del número **de teléfono.** Esta opción está predeterminada de forma predeterminada.

5. Haga clic en **Aplicar**.

## <a name="using-powershell"></a>Con PowerShell

Vea [Set-CsOnlineVoiceUser.](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceuser) 

    
## <a name="related-topics"></a>Temas relacionados

- [Administrar llamadas de emergencia](what-are-emergency-locations-addresses-and-call-routing.md)
- [Agregar, cambiar o quitar una ubicación de emergencia para su organización](add-change-remove-emergency-location-organization.md)
- [Agregar, cambiar o quitar una ubicación de emergencia para su organización](add-change-remove-emergency-place-organization.md)
- [Asignar o cambiar la ubicación de emergencia de un usuario](assign-change-emergency-place-user.md)
- [Administrar los números de teléfono para su organización](/microsoftteams/manage-phone-numbers-for-your-organization)
- [Términos y condiciones de las llamadas de emergencia](/microsoftteams/emergency-calling-terms-and-conditions)
- [Descripción de PowerShell para Teams](teams-powershell-overview.md)
