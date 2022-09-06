---
title: Asignar o cambiar la ubicación de emergencia de un usuario
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
description: En este artículo, obtendrá información sobre cómo asignar o cambiar una ubicación de emergencia para los usuarios de su organización.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 2562661a08c98c15a24a5e7db6a0f31dee864573
ms.sourcegitcommit: 75dfc3cd9b59282d68e35e4d7185da572eb3795c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2022
ms.locfileid: "67606609"
---
# <a name="assign-or-change-an-emergency-location-for-a-user"></a>Asignar o cambiar la ubicación de emergencia de un usuario

Independientemente de la [opción de conectividad con RTC](pstn-connectivity.md), elija&mdash;Planes de llamadas de Microsoft, Conexión de operadores, Operador de conexión móvil (versión preliminar pública) o Enrutamiento&mdash;directo, debe asignar una ubicación de emergencia a cada número de teléfono o usuario.

Sin embargo, en función de la opción de conectividad con RTC, la forma de administrar y asignar ubicaciones de emergencia a un usuario puede variar. Para obtener más información, consulte [Administrar llamadas de emergencia](what-are-emergency-locations-addresses-and-call-routing.md).

En este artículo se describe cómo asignar o cambiar una ubicación de emergencia a un usuario. 

Este artículo se aplica a los planes de llamadas, a la conexión de operadores y a Operador de conexión móvil (versión preliminar pública).
  
Puede asignar o cambiar una ubicación de emergencia para un usuario en el Centro de administración de Microsoft Teams o mediante PowerShell.

## <a name="using-the-microsoft-teams-admin-center"></a>Usar el Centro de administración de Microsoft Teams

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, haga clic en **Números de teléfono** **de voz** > .

2. En la página **Números de teléfono** , haga clic en la pestaña **Números** , seleccione un número de usuario en la lista y, a continuación, haga clic en **Editar**.

3. En el panel **Editar** , en **Ubicación de emergencia**, siga uno de estos procedimientos:

   - Para asignar una ubicación de emergencia, busque y seleccione una ubicación de emergencia.

   - Para cambiar la ubicación de emergencia que ya está asignada al usuario, haga clic en **X** para quitar la ubicación existente y, a continuación, busque y seleccione la ubicación que desea asignar.

4. Dependiendo de si desea enviar un correo electrónico al usuario con su información de número de teléfono, desactive o active **Email usuario con información de número de teléfono**. De forma predeterminada, esta opción está activada.

5. Haga clic en **Aplicar**.

## <a name="using-powershell"></a>Con PowerShell

Vea [Set-CsPhoneNumberAssignment](/powershell/module/teams/set-csphonenumberassignment). 

    
## <a name="related-topics"></a>Temas relacionados

- [Administrar las llamadas de emergencia](what-are-emergency-locations-addresses-and-call-routing.md)
- [Agregar, cambiar o quitar una ubicación de emergencia para su organización](add-change-remove-emergency-location-organization.md)
- [Asignar o cambiar la ubicación de emergencia de un usuario](assign-change-emergency-place-user.md)
- [Agregar, cambiar o quitar una ubicación de emergencia para su organización](add-change-remove-emergency-place-organization.md)
- [Administrar los números de teléfono para su organización](/microsoftteams/manage-phone-numbers-for-your-organization)
- [Términos y condiciones de las llamadas de emergencia](./emergency-calling-terms-and-conditions.md)
