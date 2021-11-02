---
title: Agregar, cambiar y quitar ubicaciones de emergencia
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
description: 'Obtenga información sobre cómo agregar, cambiar o quitar una ubicación de emergencia para su organización. '
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 4d9c7c56b4e2b2fd14f703d51b4c07cfc173dfa3
ms.sourcegitcommit: 197debacdcd1f7902f6e16940ef9bec8b07641af
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/02/2021
ms.locfileid: "60634859"
---
# <a name="add-change-or-remove-an-emergency-location-for-your-organization"></a>Agregar, cambiar o quitar una ubicación de emergencia para su organización

Independientemente de la opción de conectividad [RTC](pstn-connectivity.md) que elija Planes de llamadas de Microsoft, Operador Conectar o Ubicaciones de emergencia de enrutamiento directo se pueden asociar &mdash; con un número de &mdash; teléfono.

Sin embargo, dependiendo de la opción de conectividad RTC, la forma en que administra las ubicaciones de emergencia y los requisitos de ubicación pueden variar. Para obtener más información, vea [Administrar llamadas de emergencia.](what-are-emergency-locations-addresses-and-call-routing.md)

En este artículo se describe cómo agregar, cambiar o quitar una ubicación de emergencia para su organización. 

Este artículo se aplica a planes de llamadas de Microsoft, Conectar operador y enrutamiento directo.

Puede administrar las ubicaciones de emergencia de su organización en el Microsoft Teams de administración o mediante PowerShell.

Para asignar una ubicación de emergencia, los usuarios, los números de teléfono y las ubicaciones de emergencia deben estar en el mismo país. Para obtener más información, vea [Asignar o cambiar una ubicación de emergencia para un usuario.](assign-change-emergency-location-user.md)
  
## <a name="add-an-emergency-location"></a>Agregar una ubicación de emergencia

### <a name="using-the-microsoft-teams-admin-center"></a>Usar el Centro de administración de Microsoft Teams

1. En el panel de navegación izquierdo del Microsoft Teams de administración, haga clic en **Ubicaciones**  >  **Direcciones de emergencia.**
2. Haga clic en **Agregar**.
3. Escriba un nombre y una descripción para la ubicación.
4. Seleccione el país o la región y, a continuación, escriba la dirección.

   > [!NOTE]
   > En Bélgica, Francia, Alemania, Irlanda, Países Bajos y España, es importante comprender que para activar correctamente un número de teléfono en Microsoft 365, la dirección configurada en la ubicación de emergencia, que se usa para adquirir el número, debe coincidir con el código de área del número de teléfono.

5. Si la dirección no se encuentra y desea editarla manualmente, active **Editar la dirección manualmente.**
6. Haga clic en **Guardar**.

### <a name="using-powershell"></a>Con PowerShell

Vea [New-CsOnlineLisCivicAddress](/powershell/module/skype/new-csonlineliscivicaddress).
    
## <a name="change-an-emergency-location"></a>Cambiar una ubicación de emergencia

### <a name="using-the-microsoft-teams-admin-center"></a>Usar el Centro de administración de Microsoft Teams

1. En el panel de navegación izquierdo del Microsoft Teams de administración, haga clic en **Ubicaciones**  >  **Direcciones de emergencia.**
2. En la lista, seleccione la ubicación que desea cambiar y, a continuación, haga clic en **Editar.**
3. Realice los cambios que desee.
4. Haga clic en **Guardar**.

> [!NOTE]
> Solo puede cambiar la información de dirección de una ubicación si la dirección no está validada. Si la dirección ya está validada y necesita cambiar la dirección, elimine la ubicación y, después, cree una nueva ubicación con la dirección correcta.

### <a name="using-powershell"></a>Con PowerShell

Vea [Set-CsOnlineLisCivicAddress](/powershell/module/skype/set-csonlineliscivicaddress).
    
## <a name="remove-an-emergency-location"></a>Quitar una ubicación de emergencia

### <a name="using-the-microsoft-teams-admin-center"></a>Usar el Centro de administración de Microsoft Teams

1. En el panel de navegación izquierdo del Microsoft Teams de administración, haga clic en **Ubicaciones**  >  **Direcciones de emergencia.**
2. En la lista, seleccione la ubicación que desea quitar y, a continuación, haga clic en **Eliminar.**

### <a name="using-powershell"></a>Con PowerShell

Vea [Remove-CsOnlineLisCivicAddress](/powershell/module/skype/remove-csonlineliscivicaddress).

## <a name="related-topics"></a>Temas relacionados

- [Administrar llamadas de emergencia](what-are-emergency-locations-addresses-and-call-routing.md)
- [Agregar, cambiar o quitar una ubicación de emergencia para su organización](add-change-remove-emergency-place-organization.md)
- [Administrar los números de teléfono para su organización](/microsoftteams/manage-phone-numbers-for-your-organization)
- [Términos y condiciones de las llamadas de emergencia](./emergency-calling-terms-and-conditions.md)