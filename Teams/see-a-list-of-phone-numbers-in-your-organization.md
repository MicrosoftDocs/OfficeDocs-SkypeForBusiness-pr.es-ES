---
title: Ver una lista de números de teléfono de su organización
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 93098bc5-df63-4a1f-8734-0b72a6280a69
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- seo-marvel-mar2020
description: Aprenda a usar el Microsoft Teams de administración para ver una lista de todos los números de teléfono de su organización y todos los números asignados a usuarios o no asignados.
ms.openlocfilehash: 41eceb3618fae61308b90a88165ce1935ad6b30b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117238"
---
# <a name="see-a-list-of-phone-numbers-in-your-organization"></a>Ver una lista de números de teléfono de su organización

Hay diferentes tipos de números de teléfono que puede asignar a usuarios u otros servicios (números de servicio), como por ejemplo, audioconferencias en Microsoft 365 o Office 365.
  
## <a name="to-see-a-list-of-all-phone-numbers-that-you-have-for-your-organization"></a>Para ver una lista de todos los números de teléfono de los que dispone para su organización

![Un icono que muestra el Teams ](media/teams-logo-30x30.png) **con el Microsoft Teams de administración**

1. Vaya al centro **Microsoft Teams de administración.**

2. En el panel de navegación izquierdo, vaya a **Voz** > **Números de teléfono**.

    > [!IMPORTANT]
    > Para que vea  la opción Voz en el panel de navegación izquierdo del Centro de administración de Skype Empresarial, primero debe comprar al  menos una licencia **de Enterprise E5,** una licencia de complemento de **Sistema telefónico** o una licencia de complemento de audioconferencia.

3. Para ver los números de teléfono asignados, vea la **columna** Estado.

4. Para filtrar la vista, haga clic en el icono de filtro. En el **panel** Filtro, puede usar la lista desplegable para filtrar la vista por:

   - **Rango de números** que establezca. Puede buscar por el número más bajo o el número más alto.

   - Números que comienzan con un número que especifique.

   - Estado **de activación de número**.

   - Tipo **de número**.

   - Teléfono de **número**.

## <a name="to-see-all-of-the-phone-numbers-that-are-assigned-to-users"></a>Para ver todos los números de teléfono asignados a los usuarios

Al configurar usuarios, es posible que solo desee ver la lista de los números de teléfono que ya están asignados a los usuarios y qué números de teléfono están disponibles para asignarlos.
  
![Un icono que muestra el Teams ](media/teams-logo-30x30.png) **con el Microsoft Teams de administración**

1. Vaya al centro **Microsoft Teams de administración.**

2. En el panel de navegación izquierdo, vaya a **Voz** > **Números de teléfono**.

    > [!IMPORTANT]
    > Para que vea  la opción Voz en el panel de navegación izquierdo del centro de administración de Microsoft Teams,  primero debe comprar al menos  una licencia **de Enterprise E5,** una licencia de complemento de Sistema telefónico o una licencia de complemento de audioconferencia.

3. Para ordenar rápidamente los números para que pueda ver cuáles están asignados, haga clic en el encabezado **de** columna Estado. O bien, puede hacer clic en el icono de filtro y filtrar la vista para ver números de teléfono que ya están asignados a usuarios o números sin asignar que puede asignar a un usuario. Puede filtrar por:

   - **Asignado al usuario**

   - **Asignado al puente de conferencia** 

   - **Sinsignado**

## <a name="to-see-the-phone-numbers-that-are-assigned-to-voice-users"></a>Para ver los números de teléfono asignados a los usuarios de voz

Al configurar los usuarios de su organización para realizar y recibir llamadas telefónicas, deberá obtener primero los números de teléfono y después asignarlos a los usuarios. Después de obtener los números de teléfono, es posible que desee ver el estado de activación de las asignaciones de números.

![Un icono que muestra el Teams ](media/teams-logo-30x30.png) **con el Microsoft Teams de administración.**
  
1. Vaya al centro **Microsoft Teams de administración.**

2. En el panel de navegación izquierdo, vaya a **Voz** > **Números de teléfono**.

    > [!IMPORTANT]
    > Para que vea  la opción Voz en el panel de navegación izquierdo del centro de administración de Microsoft Teams,  primero debe comprar al menos  una licencia **de Enterprise E5,** una licencia de complemento de Sistema telefónico o una licencia de complemento de audioconferencia.

3. Haga clic en el icono de filtro para filtrar la vista por **estado de activación** Puede filtrar por:

   - **Activado**

   - **Tarea pendiente**

   - **Error en la asignación**

   - **Actualización pendiente**

   - **Error en la actualización**

## <a name="using-the-teams-powershell-module"></a>Usar el Teams PowerShell

Puede usar el módulo Teams PowerShell para obtener la misma información de las secciones anteriores, pero se requiere la versión 1.1.6 o posterior, que incluye la integración del conector Skype Empresarial Online. Para obtener más información sobre el módulo, [vea Microsoft Teams información general de PowerShell.](teams-powershell-overview.md)

Puede ver una lista de todos los números de teléfono que tiene para su organización mediante el cmdlet [Get-CsOnlineTelephoneNumber.](/powershell/module/skype/get-csonlinetelephonenumber) Por ejemplo, puede ejecutar el siguiente comando para ver cada número de teléfono y su estado:

```PowerShell
Get-CsOnlineTelephoneNumber | ft Id,ActivationState
```

Puede ver todos los números de teléfono asignados a los usuarios mediante el cmdlet [Get-CsOnlineUser.](/powershell/module/skype/get-csonlineuser) Por ejemplo, puede ejecutar el siguiente comando para ver todos los usuarios con un número de teléfono asignado:

```PowerShell
Get-CsOnlineUser | Where-Object  { $_.LineURI -notlike $null } | ft DisplayName,UserPrincipalName,LineURI
```

## <a name="related-topics"></a>Temas relacionados
[Preguntas comunes sobre la transferencia de números de teléfono](./phone-number-calling-plans/port-order-overview.md)

[Diferentes tipos de números de teléfono que se usan para Planes de llamada](./different-kinds-of-phone-numbers-used-for-calling-plans.md)

[Administrar los números de teléfono para su organización](/microsoftteams/manage-phone-numbers-for-your-organization)

[Términos y condiciones de las llamadas de emergencia](./emergency-calling-terms-and-conditions.md)

[Etiqueta de declinación de responsabilidades de llamadas de emergencia](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

[Get-CsOnlineTelephoneNumber](/powershell/module/skype/get-csonlinetelephonenumber)
  
[Get-CsOnlineUser](/powershell/module/skype/get-csonlineuser)