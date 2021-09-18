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
description: Aprenda a usar el centro Microsoft Teams administración para ver una lista de todos los números de teléfono de su organización y todos los números asignados a usuarios o no asignados.
ms.openlocfilehash: 1473a87a190a671d537a958b34e839d53a668f3a
ms.sourcegitcommit: 9364f4fdf3dcd5ab6805360ff913d4e2e7ca9cfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2021
ms.locfileid: "59432492"
---
# <a name="see-a-list-of-telephone-numbers"></a>Ver una lista de números de teléfono 

Hay diferentes tipos de números de teléfono que puede asignar a usuarios o aplicaciones de voz como [Audioconferencias](deploy-audio-conferencing-teams-landing-page.md) o [Colas de llamadas.](plan-auto-attendant-call-queue.md) Para obtener más información, vea [Administrar números de teléfono para su organización.](/microsoftteams/manage-phone-numbers-landing-page)

Este artículo se aplica a planes de llamadas y Conectar. Para obtener información sobre enrutamiento directo, vea Configurar el número de teléfono y habilitar la voz y el correo de [voz empresariales.](direct-routing-enable-users.md#configure-the-phone-number-and-enable-enterprise-voice-and-voicemail-online)
  
## <a name="to-see-all-telephone-numbers-in-your-organization"></a>Para ver todos los números de teléfono de su organización

Para ver una lista de todos los números de teléfono de su organización:

1. Vaya al centro **Microsoft Teams de administración.**

2. En el panel de navegación izquierdo, vaya a **Voz** > **Números de teléfono**.

3. Para ver los números de teléfono  asignados, vea la columna Estado de asignación, que también muestra el tipo de servicio al que está asignado el número.

4. Para filtrar la vista, haga clic en el icono de filtro. En el **panel** Filtro, puede usar la lista desplegable para filtrar la vista por:

   - **Rango de números** que establezca. Puede buscar por el número más bajo o el número más alto.

   - Números que comienzan con un número que especifique.

   - Estado **de activación de número**.

   - Tipo **de número**.

   - Teléfono de **número**.

## <a name="to-see-all-telephone-numbers-that-are-assigned-to-users"></a>Para ver todos los números de teléfono asignados a los usuarios

Al configurar usuarios, es posible que solo desee ver la lista de los números de teléfono que ya están asignados a los usuarios y qué números de teléfono están disponibles para asignarlos.

1. Vaya al centro **Microsoft Teams de administración.**

2. En el panel de navegación izquierdo, vaya a **Voz** > **Números de teléfono**.

    > [!IMPORTANT]
    > Para que vea  la opción Voz en el panel de navegación izquierdo del centro de administración de Microsoft Teams,  primero debe comprar al menos  una licencia **de Enterprise E5,** una licencia de complemento de Sistema telefónico o una licencia de complemento de audioconferencia.

3. Para ordenar rápidamente los números para que pueda ver cuáles están asignados, haga clic en el encabezado de columna **Estado de asignación.** O bien, puede hacer clic en el icono de filtro y filtrar la vista para ver los números de teléfono que ya están asignados a usuarios o números sin asignar que puede asignar a un usuario. Puede filtrar por:

   - **Asignado al usuario**
   - **Asignado al puente de conferencia** 
   - **Asignado a la aplicación De voz (Operador automático/Cola de llamadas)**
   - **Sinsignado**

## <a name="to-see-all-telephone-numbers-that-are-assigned-to-voice-users"></a>Para ver todos los números de teléfono asignados a usuarios de voz

Cuando configura usuarios de su organización para realizar y recibir llamadas telefónicas, primero debe obtener los números de teléfono y, después, asignarlos a los usuarios. Después de obtener los números de teléfono, es posible que desee ver el estado de activación de las asignaciones de números.
  
1. Vaya al centro **Microsoft Teams de administración.**

2. En el panel de navegación izquierdo, vaya a **Voz** > **Números de teléfono**.

3. Haga clic en el icono de filtro para filtrar la vista por **estado de activación.** Puede filtrar por:

   - **Activado**
   - **Tarea pendiente**
   - **Error en la asignación**
   - **Actualización pendiente**
   - **Error en la actualización**

## <a name="using-the-teams-powershell-module"></a>Usar el Teams PowerShell

Puede usar el módulo Teams PowerShell para obtener la misma información de las secciones anteriores, pero se requiere la versión 1.1.6 o posterior, que incluye la integración del conector Skype Empresarial Online. Para obtener más información sobre el módulo, [vea Microsoft Teams información general de PowerShell.](teams-powershell-overview.md)

Para ver una lista de todos los números de teléfono que tiene para su organización, use el cmdlet [Get-CsOnlineTelephoneNumber.](/powershell/module/skype/get-csonlinetelephonenumber) Por ejemplo, para ver cada número de teléfono y su estado, ejecute el siguiente comando:

```PowerShell
Get-CsOnlineTelephoneNumber | ft Id,ActivationState
```

Para ver todos los números de teléfono asignados a los usuarios, use el cmdlet [Get-CsOnlineUser.](/powershell/module/skype/get-csonlineuser) Por ejemplo, para ver todos los usuarios con un número de teléfono asignado, ejecute el siguiente comando:

```PowerShell
Get-CsOnlineUser | Where-Object  { $_.LineURI -notlike $null } | ft DisplayName,UserPrincipalName,LineURI
```

## <a name="related-topics"></a>Temas relacionados

[Administrar números de teléfono para su organización](manage-phone-numbers-landing-page.md)

[Términos y condiciones de las llamadas de emergencia](./emergency-calling-terms-and-conditions.md)

[Etiqueta de declinación de responsabilidades de llamadas de emergencia](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

[Get-CsOnlineTelephoneNumber](/powershell/module/skype/get-csonlinetelephonenumber)
  
[Get-CsOnlineUser](/powershell/module/skype/get-csonlineuser)