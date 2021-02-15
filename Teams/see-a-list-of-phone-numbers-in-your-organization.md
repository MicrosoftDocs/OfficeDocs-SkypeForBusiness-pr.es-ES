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
description: Aprenda a usar el Centro de administración de Microsoft Teams para ver una lista de todos los números de teléfono de su organización y todos los números asignados a usuarios o sin asignar.
ms.openlocfilehash: 61e1fb59ba5b68aeb2ab2af51b2ef91202e43678
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/21/2021
ms.locfileid: "49918906"
---
# <a name="see-a-list-of-phone-numbers-in-your-organization"></a>Ver una lista de números de teléfono de su organización

Existen diferentes tipos de números de teléfono que puede asignar a los usuarios u otros servicios (números de servicio), como para Audioconferencia en Microsoft 365 u Office 365.
  
## <a name="to-see-a-list-of-all-phone-numbers-that-you-have-for-your-organization"></a>Para ver una lista de todos los números de teléfono de los que dispone para su organización

![Icono que muestra el logotipo de Teams ](media/teams-logo-30x30.png) **con el Centro de administración de Microsoft Teams**

1. Vaya al Centro **de administración de Microsoft Teams.**

2. En el panel de navegación izquierdo, vaya a **Voz** > **Números de teléfono**.

    > [!IMPORTANT]
    > Para que vea  la opción Voz en el panel de navegación izquierdo del Centro de administración  de Skype Empresarial, primero debe comprar al menos una licencia **de Enterprise E5,** una licencia del complemento Sistema telefónico o una licencia del complemento **Audioconferencia.**

3. Para ver los números de teléfono asignados, vea la **columna** Estado.

4. Para filtrar la vista, haga clic en el icono de filtro. En el **panel** Filtro, puede usar la lista desplegable para filtrar la vista por:

   - **Rango de** números que establezca. Puede buscar por el número más bajo o el número más alto.

   - Números que comienzan con un número que especifique.

   - Estado **de activación del número.**

   - Tipo **de número.**

   - Estado del número **de teléfono.**

## <a name="to-see-all-of-the-phone-numbers-that-are-assigned-to-users"></a>Para ver todos los números de teléfono asignados a los usuarios

Al configurar usuarios, es posible que desee ver la lista de los números de teléfono que ya están asignados a los usuarios y los números de teléfono que se les asignarán.
  
![Icono que muestra el logotipo de Teams ](media/teams-logo-30x30.png) **con el Centro de administración de Microsoft Teams**

1. Vaya al Centro **de administración de Microsoft Teams.**

2. En el panel de navegación izquierdo, vaya a **Voz** > **Números de teléfono**.

    > [!IMPORTANT]
    > Para que vea  la opción Voz en el panel de navegación izquierdo del Centro de administración  de Microsoft Teams, primero debe comprar al menos una licencia **de Enterprise E5,** una licencia del complemento Sistema telefónico o una licencia del complemento **Audioconferencia.**

3. Para ordenar rápidamente los números de modo que pueda ver cuáles están asignados, haga clic en el encabezado **de** la columna Estado. O bien, puede hacer clic en el icono de filtro y luego filtrar la vista para ver los números de teléfono que ya están asignados a usuarios o números sin asignar que puede asignar a un usuario. Puede filtrar por:

   - **Asignado a un usuario**

   - **Asignado al puente de conferencia** 

   - **Sinsignado**

## <a name="to-see-the-phone-numbers-that-are-assigned-to-voice-users"></a>Para ver los números de teléfono asignados a los usuarios de voz

Al configurar los usuarios de su organización para realizar y recibir llamadas telefónicas, deberá obtener primero los números de teléfono y después asignarlos a los usuarios. Después de obtener los números de teléfono, es posible que solo quiera ver el estado de activación de las asignaciones de números.

![Un icono que muestra el logotipo de Teams ](media/teams-logo-30x30.png) **con el Centro de administración de Microsoft Teams.**
  
1. Vaya al Centro **de administración de Microsoft Teams.**

2. En el panel de navegación izquierdo, vaya a **Voz** > **Números de teléfono**.

    > [!IMPORTANT]
    > Para que vea  la opción Voz en el panel de navegación izquierdo del Centro de administración  de Microsoft Teams, primero debe comprar al menos una licencia **de Enterprise E5,** una licencia de complemento de Sistema telefónico o una licencia del complemento **Audioconferencia.**

3. Haga clic en el icono de filtro para filtrar la vista por estado **de activación** Por el que puede filtrar:

   - **Activado**

   - **Tarea pendiente**

   - **Error en la asignación**

   - **Actualización pendiente**

   - **Error en la actualización**

## <a name="using-the-teams-powershell-module"></a>Usar el módulo PowerShell de Teams

Puede usar el módulo PowerShell de Teams para obtener la misma información de las secciones anteriores, pero se requiere la versión 1.1.6 o posterior, que incluye la integración del conector de Skype Empresarial Online. Para obtener más información sobre el módulo, consulte [Información general sobre PowerShell de Microsoft Teams.](teams-powershell-overview.md)

Puede ver una lista de todos los números de teléfono que tiene para su organización mediante el cmdlet [Get-CsOnlineTelephoneNumber.](https://docs.microsoft.com/powershell/module/skype/get-csonlinetelephonenumber) Por ejemplo, puede ejecutar el siguiente comando para ver cada número de teléfono y su estado:

```PowerShell
Get-CsOnlineTelephoneNumber | ft Id,ActivationState
```

Puede ver todos los números de teléfono asignados a los usuarios mediante el cmdlet [Get-CsOnlineUser.](https://docs.microsoft.com/powershell/module/skype/get-csonlineuser) Por ejemplo, puede ejecutar el siguiente comando para ver todos los usuarios con un número de teléfono asignado:

```PowerShell
Get-CsOnlineUser | Where-Object  { $_.LineURI -notlike $null } | ft DisplayName,UserPrincipalName,LineURI
```

## <a name="related-topics"></a>Temas relacionados
[Preguntas comunes sobre la transferencia de números de teléfono](/microsoftteams/transferring-phone-numbers-common-questions)

[Diferentes tipos de números de teléfono que se usan para Planes de llamada](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[Administrar los números de teléfono para su organización](/microsoftteams/manage-phone-numbers-for-your-organization)

[Términos y condiciones de las llamadas de emergencia](/microsoftteams/emergency-calling-terms-and-conditions)

[Etiqueta de declinación de responsabilidades en llamadas de emergencia](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

[Get-CsOnlineTelephoneNumber](https://docs.microsoft.com/powershell/module/skype/get-csonlinetelephonenumber)
  
[Get-CsOnlineUser](https://docs.microsoft.com/powershell/module/skype/get-csonlineuser)
