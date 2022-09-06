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
- m365initiative-voice
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- NOCSH
description: Obtenga información sobre cómo agregar, cambiar o quitar una ubicación de emergencia de su organización.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: c0a195a221bff5b008f5754592450f4f2b1e42e6
ms.sourcegitcommit: 75dfc3cd9b59282d68e35e4d7185da572eb3795c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2022
ms.locfileid: "67606639"
---
# <a name="add-change-or-remove-an-emergency-location-for-your-organization"></a>Agregar, cambiar o quitar una ubicación de emergencia para su organización

Independientemente de la [opción de conectividad con RTC](pstn-connectivity.md), elija&mdash;Planes de llamadas de Microsoft, Conexión de operadores, Operador de conexión móvil (versión preliminar pública) o ubicaciones de emergencia de Enrutamiento&mdash;directo se pueden asociar a un número de teléfono.

Sin embargo, en función de la opción de conectividad con RTC, la forma de administrar las ubicaciones de emergencia y los requisitos de ubicación puede variar. Para obtener más información, consulte [Administrar llamadas de emergencia](what-are-emergency-locations-addresses-and-call-routing.md).

En este artículo se describe cómo agregar, cambiar o quitar una ubicación de emergencia para su organización. 

Este artículo se aplica a los planes de llamadas de Microsoft, a la conexión de operadores, a la Operador de conexión móvil (versión preliminar pública) y al enrutamiento directo.

Puede administrar las ubicaciones de emergencia de su organización en el Centro de administración de Microsoft Teams o mediante PowerShell.

Para asignar una ubicación de emergencia, los usuarios, los números de teléfono y las ubicaciones de emergencia deben estar en el mismo país. Para obtener más información, vea [Asignar o cambiar una ubicación de emergencia a un usuario](assign-change-emergency-location-user.md).
  
## <a name="add-an-emergency-location"></a>Agregar una ubicación de emergencia

### <a name="using-the-microsoft-teams-admin-center"></a>Usar el Centro de administración de Microsoft Teams

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, haga clic en **Ubicaciones** > **de las direcciones de emergencia**.
2. Haga clic en **Agregar**.
3. Escriba un nombre y una descripción para la ubicación.
4. Selecciona el país o la región y, a continuación, escribe la dirección.

   > [!NOTE]
   > En Bélgica, Francia, Alemania, Irlanda, Países Bajos y España, es importante comprender que, para activar correctamente un número de teléfono en Microsoft 365, la dirección configurada en la ubicación de emergencia, que se usa para adquirir el número, debe coincidir con el código de área del número de teléfono.

5. Si no se encuentra la dirección y quiere editarla manualmente, active **Editar la dirección manualmente**.
6. Haga clic en **Guardar**.

### <a name="using-powershell"></a>Con PowerShell

Vea [New-CsOnlineLisCivicAddress](/powershell/module/skype/new-csonlineliscivicaddress).
    
## <a name="change-an-emergency-location"></a>Cambiar una ubicación de emergencia

### <a name="using-the-microsoft-teams-admin-center"></a>Usar el Centro de administración de Microsoft Teams

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, haga clic en **Ubicaciones** > **de las direcciones de emergencia**.
2. En la lista, seleccione la ubicación que desea cambiar y, a continuación, haga clic en **Editar**.
3. Realice los cambios que desee.
4. Haga clic en **Guardar**.

> [!NOTE]
> Solo puede cambiar la información de dirección de una ubicación si la dirección no está validada. Si la dirección ya está validada y necesita cambiarla, elimine la ubicación y, después, cree una nueva ubicación con la dirección correcta.

### <a name="using-powershell"></a>Con PowerShell

Vea [Set-CsOnlineLisCivicAddress](/powershell/module/skype/set-csonlineliscivicaddress).
    
## <a name="remove-an-emergency-location"></a>Quitar una ubicación de emergencia

### <a name="using-the-microsoft-teams-admin-center"></a>Usar el Centro de administración de Microsoft Teams

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, haga clic en **Ubicaciones** > **de las direcciones de emergencia**.
2. En la lista, seleccione la ubicación que desea quitar y, a continuación, haga clic en **Eliminar**.

### <a name="using-powershell"></a>Con PowerShell

Vea [Remove-CsOnlineLisCivicAddress](/powershell/module/skype/remove-csonlineliscivicaddress).

## <a name="related-topics"></a>Temas relacionados

- [Administrar las llamadas de emergencia](what-are-emergency-locations-addresses-and-call-routing.md)
- [Agregar, cambiar o quitar una ubicación de emergencia para su organización](add-change-remove-emergency-place-organization.md)
- [Administrar los números de teléfono para su organización](/microsoftteams/manage-phone-numbers-for-your-organization)
- [Términos y condiciones de las llamadas de emergencia](./emergency-calling-terms-and-conditions.md)