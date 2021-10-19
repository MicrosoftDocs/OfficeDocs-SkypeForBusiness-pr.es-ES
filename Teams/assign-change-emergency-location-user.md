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
description: En este artículo, aprenderá a asignar o cambiar una ubicación de emergencia para los usuarios de su organización.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5395c74bfab124cb1036d696dd3613c920bed1e9
ms.sourcegitcommit: 5a28d052379aef67531d3023cbe4dff30dba1136
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2021
ms.locfileid: "60465796"
---
# <a name="assign-or-change-an-emergency-location-for-a-user"></a>Asignar o cambiar la ubicación de emergencia de un usuario

**¿SE APLICA LO SIGUIENTE A TODOS LOS 3?**

**Es necesario asignar una ubicación de emergencia a cada número de teléfono o usuario. Para obtener más información sobre las direcciones y ubicaciones de emergencia, vea ¿Qué son las ubicaciones de emergencia, los lugares [y el enrutamiento de llamadas?](./what-are-emergency-locations-addresses-and-call-routing.md).**

**Para los planes de llamadas de Microsoft, en los países europeos, la ubicación de emergencia está asociada con el número de teléfono al obtenerlo de Microsoft 365 o al transferir un número de teléfono a Microsoft 365. En Estados Unidos, la ubicación de emergencia está asociada con el número de teléfono cuando se asigna al usuario. La dirección de emergencia se puede cambiar si el usuario al que está asignada se mueve a una nueva ubicación.**

**Para Operador Conectar, ...**

**Para enrutamiento directo,...**
  
Puede asignar o cambiar una ubicación de emergencia para un usuario en el centro de Microsoft Teams o mediante PowerShell.

## <a name="using-the-microsoft-teams-admin-center"></a>Usar el Centro de administración de Microsoft Teams

1. En el panel de navegación izquierdo del centro Microsoft Teams de administración, haga **clic**  >  **en Teléfono números.**

2. En la **Teléfono números,** haga  clic en la pestaña Números, seleccione un número de usuario en la lista y, a continuación, haga clic en **Editar.**

3. En el **panel Editar,** en **Ubicación de emergencia**, realice una de las siguientes acciones:

   - Para asignar una ubicación de emergencia, busque y seleccione una ubicación de emergencia.

   - Para cambiar la ubicación de emergencia que ya está asignada al usuario, haga clic en **X** para quitar la ubicación existente y, después, busque y seleccione la ubicación que desea asignar.

4. Dependiendo de si desea enviar un correo electrónico al usuario con su información de número de teléfono, desactive o active Usuario de correo electrónico con información **de número de teléfono.** De forma predeterminada, está en.

5. Haga clic en **Aplicar**.

## <a name="using-powershell"></a>Con PowerShell

Vea [Set-CsOnlineVoiceUser](/powershell/module/skype/set-csonlinevoiceuser). 

    
## <a name="related-topics"></a>Temas relacionados

- [Administrar llamadas de emergencia](what-are-emergency-locations-addresses-and-call-routing.md)
- [Agregar, cambiar o quitar una ubicación de emergencia para su organización](add-change-remove-emergency-location-organization.md)
- [Agregar, cambiar o quitar una ubicación de emergencia para su organización](add-change-remove-emergency-place-organization.md)
- [Asignar o cambiar la ubicación de emergencia de un usuario](assign-change-emergency-place-user.md)
- [Administrar los números de teléfono para su organización](/microsoftteams/manage-phone-numbers-for-your-organization)
- [Términos y condiciones de las llamadas de emergencia](./emergency-calling-terms-and-conditions.md)
- [Descripción de PowerShell para Teams](teams-powershell-overview.md)