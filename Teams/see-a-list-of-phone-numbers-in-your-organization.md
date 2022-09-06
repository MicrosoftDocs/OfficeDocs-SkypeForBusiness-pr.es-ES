---
title: Ver una lista de números de teléfono en su organización
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: davlick, roykuntz, jastark
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- seo-marvel-mar2020
description: Aprenda a usar el Centro de administración de Microsoft Teams para ver una lista de todos los números de teléfono de su organización y todos los números asignados a usuarios o no asignados.
ms.openlocfilehash: ac7c63515b34b8c199f8050933b6c3ccbc6f8d33
ms.sourcegitcommit: 75dfc3cd9b59282d68e35e4d7185da572eb3795c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2022
ms.locfileid: "67606079"
---
# <a name="see-a-list-of-telephone-numbers"></a>Ver una lista de números de teléfono 

Hay diferentes tipos de números de teléfono que puede asignar a usuarios o aplicaciones de voz, como [Audioconferencia](deploy-audio-conferencing-teams-landing-page.md) o [Colas de llamadas](plan-auto-attendant-call-queue.md). Para obtener más información, vea [Administrar números de teléfono para su organización](/microsoftteams/manage-phone-numbers-landing-page).

Este artículo se aplica a los planes de llamadas, a la conexión de operadores y a Operador de conexión móvil (versión preliminar pública). Para obtener información sobre el enrutamiento directo, consulte [Configurar el número de teléfono y habilitar la voz empresarial](direct-routing-enable-users.md#configure-the-phone-number-and-enable-enterprise-voice).
  
## <a name="to-see-all-telephone-numbers-in-your-organization"></a>Para ver todos los números de teléfono de su organización

Para ver una lista de todos los números de teléfono de su organización:

1. Vaya al **Centro de administración de Microsoft Teams**.

2. En el panel de navegación izquierdo, vaya a **Voz** > **Números de teléfono**.

3. Para ver los números de teléfono asignados, vea la columna Estado de la **asignación** , que también muestra el tipo de servicio al que está asignado el número.

4. Para filtrar la vista, haga clic en el icono de filtro. En el panel **Filtro** , puede usar la lista desplegable para filtrar la vista por:

   - **Intervalo de números** que establezca. Puede buscar por número más bajo o por número más alto.

   - Números que comienzan con un número que especifique.

   - Estado de **activación de número**.

   - Tipo de **número**.

   - Estado del número **de** teléfono.

## <a name="to-see-all-telephone-numbers-that-are-assigned-to-users"></a>Para ver todos los números de teléfono asignados a los usuarios

Al configurar los usuarios, es posible que solo quiera ver la lista de los números de teléfono que ya están asignados a los usuarios y qué números de teléfono están disponibles para asignarles.

1. Vaya al **Centro de administración de Microsoft Teams**.

2. En el panel de navegación izquierdo, vaya a **Voz** > **Números de teléfono**.

    > [!IMPORTANT]
    > Para ver la opción **Voz** en el panel de navegación izquierdo del Centro de administración de Microsoft Teams, primero debe comprar al menos una **licencia de Enterprise E5**, una licencia del complemento **Sistema telefónico** o una licencia de complemento **de Audioconferencia** .

3. Para ordenar rápidamente los números para que pueda ver cuáles están asignados, haga clic en el encabezado **de columna Estado de la tarea** . O bien, puede hacer clic en el icono de filtro y luego filtrar la vista para ver los números de teléfono que ya están asignados a usuarios o números no asignados que puede asignar a un usuario. Puede filtrar por:

   - **Asignado al usuario**
   - **Asignado al puente de conferencia** 
   - **Asignado a la aplicación de voz (operador automático/cola de llamadas)**
   - **Sin asignar**

## <a name="to-see-all-telephone-numbers-that-are-assigned-to-voice-users"></a>Para ver todos los números de teléfono asignados a usuarios de voz

Al configurar los usuarios de su organización para realizar y recibir llamadas telefónicas, primero debe obtener los números de teléfono y, después, asignarlos a los usuarios. Después de obtener los números de teléfono, es posible que quiera ver el estado de activación de las asignaciones de números.
  
1. Vaya al **Centro de administración de Microsoft Teams**.

2. En el panel de navegación izquierdo, vaya a **Voz** > **Números de teléfono**.

3. Haga clic en el icono de filtro para filtrar la vista por **estado de activación**. Puede filtrar por:

   - **Activado**
   - **Tarea pendiente**
   - **Error en la tarea**
   - **Actualización pendiente**
   - **Error de actualización**

## <a name="using-the-teams-powershell-module"></a>Usar el módulo de PowerShell de Teams

Puede usar el módulo PowerShell de Teams para obtener la misma información de las secciones anteriores, pero es necesaria la versión 1.1.6 o posterior, que incluye la integración del conector Skype Empresarial Online. Para obtener más información sobre el módulo, consulte [Introducción a Microsoft Teams PowerShell](teams-powershell-overview.md).

Para ver una lista de todos los números de teléfono que tiene para su organización, use el cmdlet [Get-CsPhoneNumberAssignment](/powershell/module/teams/get-csphonenumberassignment) . Por ejemplo, para ver cada número de teléfono, su tipo y su estado, ejecute el siguiente comando:

```PowerShell
Get-CsPhoneNumberAssignment | ft TelephoneNumber,ActivationState,NumberType
```

Para ver todos los números de teléfono asignados a los usuarios, use el cmdlet [Get-CsOnlineUser](/powershell/module/skype/get-csonlineuser) . Por ejemplo, para ver todos los usuarios con un número de teléfono asignado, ejecute el siguiente comando:

```PowerShell
Get-CsOnlineUser | Where-Object  { $_.LineURI -notlike $null } | ft DisplayName,UserPrincipalName,LineURI
```

## <a name="related-topics"></a>Temas relacionados

[Administrar los números de teléfono de su organización](manage-phone-numbers-landing-page.md)

[Términos y condiciones de las llamadas de emergencia](./emergency-calling-terms-and-conditions.md)

[Etiqueta de declinación de responsabilidades de llamadas de emergencia](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

[Get-CsPhoneNumberAssignment](/powershell/module/teams/get-csphonenumberassignment)
  
[Get-CsOnlineUser](/powershell/module/skype/get-csonlineuser)
