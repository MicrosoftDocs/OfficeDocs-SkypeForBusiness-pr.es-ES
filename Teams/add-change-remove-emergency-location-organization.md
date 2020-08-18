---
title: Agregar, cambiar o quitar ubicaciones de emergencia
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
description: 'Obtenga información sobre cómo agregar, cambiar o quitar una ubicación de emergencia para su organización en el centro de administración de Microsoft Teams. '
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 762246630d245acf92c16aff8df2c9392a307b07
ms.sourcegitcommit: d1e4e1105d86745009cf0fdf42d1fc5ad545a952
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/18/2020
ms.locfileid: "46788574"
---
# <a name="add-change-or-remove-an-emergency-location-for-your-organization"></a>Agregar, cambiar o quitar una ubicación de emergencia para su organización

Una ubicación de emergencia debe estar asociada a un número de teléfono, pero cuando esto sucede puede variar entre países y regiones. Por ejemplo, en los Estados Unidos, debe asociar una ubicación de emergencia cuando asigne el número de teléfono al usuario. En el Reino Unido, debe asociar una ubicación de emergencia con el número de teléfono al obtener los números de teléfono de Microsoft 365 u Office 365 o transferir números de teléfono de su proveedor de servicios actual.

No importa en qué país o región se encuentre, puede Agregar un lugar o lugares a una ubicación de emergencia y quitar una ubicación de emergencia. Según el número de ubicaciones físicas de su organización, puede crear lugares para edificios, plantas y oficinas. Consulte [Manage Emergency Call](what-are-emergency-locations-addresses-and-call-routing.md).
  
Para obtener información sobre cómo obtener un plan de llamadas y cuánto cuestan, vea [licencias complementarias de Teams](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing).

Administre las ubicaciones de emergencia de su organización en el centro de administración de Microsoft Teams o mediante PowerShell.
  
## <a name="add-an-emergency-location"></a>Agregar una ubicación de emergencia

### <a name="using-the-microsoft-teams-admin-center"></a>Usar el centro de administración de Microsoft Teams

1. En el centro de navegación izquierdo del centro de administración de Microsoft Teams, haga clic en **ubicaciones**de  >  **emergencia**.
2. Haga clic en **Agregar**.
3. Escriba un nombre y una descripción para la ubicación.
4. Seleccione el país o la región y, a continuación, escriba la dirección.

   > [!NOTE]
   > En Bélgica, Francia, Alemania, Irlanda, Países Bajos y España, es importante comprender que para activar correctamente un número de teléfono en Microsoft 365 u Office 365, la dirección establecida en la ubicación de emergencia, que se usa para adquirir el número, debe coincidir con el código de área del número de teléfono.

5. Si la dirección no se encuentra y desea editarla manualmente, Active **editar la dirección de forma manual**.
6. Haga clic en **Guardar **.

### <a name="using-powershell"></a>Con PowerShell

Vea [New-CsOnlineLisCivicAddress](https://docs.microsoft.com/powershell/module/skype/new-csonlineliscivicaddress).
    
## <a name="change-an-emergency-location"></a>Cambiar una ubicación de emergencia

### <a name="using-the-microsoft-teams-admin-center"></a>Usar el centro de administración de Microsoft Teams

1. En el centro de navegación izquierdo del centro de administración de Microsoft Teams, haga clic en **ubicaciones**de  >  **emergencia**.
2. En la lista, seleccione la ubicación que desee cambiar y, a continuación, haga clic en **Editar**.
3. Realice los cambios que desee.
4. Haga clic en **Guardar **.

> [!NOTE]
> Puede cambiar la información de dirección de una ubicación solo si no se ha validado la dirección. Si la dirección ya se ha validado y necesita cambiar la dirección, elimine la ubicación y, a continuación, cree una nueva ubicación con la dirección correcta.

### <a name="using-powershell"></a>Con PowerShell

Consulte [set-CsOnlineLisCivicAddress](https://docs.microsoft.com/powershell/module/skype/set-csonlineliscivicaddress).
    
## <a name="remove-an-emergency-location"></a>Quitar una ubicación de emergencia

### <a name="using-the-microsoft-teams-admin-center"></a>Usar el centro de administración de Microsoft Teams

1. En el centro de navegación izquierdo del centro de administración de Microsoft Teams, haga clic en **ubicaciones**de  >  **emergencia**.
2. En la lista, seleccione la ubicación que desea quitar y, a continuación, haga clic en **eliminar**.

### <a name="using-powershell"></a>Con PowerShell

Consulte [Remove-CsOnlineLisCivicAddress](https://docs.microsoft.com/powershell/module/skype/remove-csonlineliscivicaddress).

## <a name="related-topics"></a>Temas relacionados

- [Administrar las llamadas de emergencia](what-are-emergency-locations-addresses-and-call-routing.md)
- [Agregar, cambiar o quitar una ubicación de emergencia para su organización](add-change-remove-emergency-place-organization.md)
- [Administrar los números de teléfono para su organización](/microsoftteams/manage-phone-numbers-for-your-organization)
- [Términos y condiciones de las llamadas de emergencia](/microsoftteams/emergency-calling-terms-and-conditions)
