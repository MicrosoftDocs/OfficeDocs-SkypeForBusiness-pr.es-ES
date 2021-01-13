---
title: Agregar, cambiar, quitar ubicaciones de emergencia
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
description: 'Obtenga información sobre cómo agregar, cambiar o quitar una ubicación de emergencia de su organización en el Centro de administración de Microsoft Teams. '
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: a470a75d367bc47d4063a2a99171a4a09e052fca
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49799950"
---
# <a name="add-change-or-remove-an-emergency-location-for-your-organization"></a>Agregar, cambiar o quitar una ubicación de emergencia para su organización

Una ubicación de emergencia debe estar asociada a un número de teléfono, pero cuando esto ocurre puede variar entre países y regiones. Por ejemplo, en Estados Unidos, debe asociar una ubicación de emergencia al asignar el número de teléfono al usuario. En el Reino Unido, debe asociar una ubicación de emergencia al número de teléfono cuando obtiene los números de teléfono de Microsoft 365 u Office 365 o los transfiere de su proveedor de servicios actual.

No importa en qué país o región se encuentra, puede agregar un lugar o lugares a una ubicación de emergencia y quitar una ubicación de emergencia. Según el número de ubicaciones físicas de su organización, puede crear lugares para edificios, pisos y oficinas. Vea [Administrar llamadas de emergencia.](what-are-emergency-locations-addresses-and-call-routing.md)
  
Para obtener información sobre cómo obtener un plan de llamadas y cuánto cuestan, consulte licencias [de complementos de Teams.](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing)

Puede administrar las ubicaciones de emergencia de su organización en el centro de administración de Microsoft Teams o mediante PowerShell.
  
## <a name="add-an-emergency-location"></a>Agregar una ubicación de emergencia

### <a name="using-the-microsoft-teams-admin-center"></a>Usar el Centro de administración de Microsoft Teams

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, haga clic en  >  **Ubicaciones, Direcciones de emergencia.**
2. Haga clic en **Agregar**.
3. Escriba un nombre y una descripción para la ubicación.
4. Selecciona el país o la región y, a continuación, escribe la dirección.

   > [!NOTE]
   > En Bélgica, Francia, Alemania, Irlanda, Países Bajos y España, es importante comprender que para activar correctamente un número de teléfono en Microsoft 365 u Office 365, la dirección configurada en la ubicación de emergencia, que se utiliza para adquirir el número, debe coincidir con el código de área del número de teléfono.

5. Si no encuentra la dirección y quiere editarla manualmente, active Editar manualmente la **dirección.**
6. Haga clic en **Guardar**.

### <a name="using-powershell"></a>Con PowerShell

Vea [New-CsOnlineLisCivicAddress.](https://docs.microsoft.com/powershell/module/skype/new-csonlineliscivicaddress)
    
## <a name="change-an-emergency-location"></a>Cambiar una ubicación de emergencia

### <a name="using-the-microsoft-teams-admin-center"></a>Usar el Centro de administración de Microsoft Teams

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, haga clic en  >  **Ubicaciones, Direcciones de emergencia.**
2. En la lista, seleccione la ubicación que desea cambiar y, a continuación, haga clic en **Editar.**
3. Realice los cambios que desee.
4. Haga clic en **Guardar**.

> [!NOTE]
> Solo puede cambiar la información de dirección de una ubicación si la dirección no está validada. Si la dirección ya está validada y necesita cambiarla, elimine la ubicación y, a continuación, cree una nueva ubicación con la dirección correcta.

### <a name="using-powershell"></a>Con PowerShell

Vea [Set-CsOnlineLisCivicAddress.](https://docs.microsoft.com/powershell/module/skype/set-csonlineliscivicaddress)
    
## <a name="remove-an-emergency-location"></a>Quitar una ubicación de emergencia

### <a name="using-the-microsoft-teams-admin-center"></a>Usar el Centro de administración de Microsoft Teams

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, haga clic en  >  **Ubicaciones, Direcciones de emergencia.**
2. En la lista, seleccione la ubicación que desea quitar y, a continuación, haga clic en **Eliminar.**

### <a name="using-powershell"></a>Con PowerShell

Vea [Remove-CsOnlineLisCivicAddress.](https://docs.microsoft.com/powershell/module/skype/remove-csonlineliscivicaddress)

## <a name="related-topics"></a>Temas relacionados

- [Administrar llamadas de emergencia](what-are-emergency-locations-addresses-and-call-routing.md)
- [Agregar, cambiar o quitar una ubicación de emergencia para su organización](add-change-remove-emergency-place-organization.md)
- [Administrar los números de teléfono para su organización](/microsoftteams/manage-phone-numbers-for-your-organization)
- [Términos y condiciones de las llamadas de emergencia](/microsoftteams/emergency-calling-terms-and-conditions)
