---
title: Restablecer un Id. de conferencia para un usuario en Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 6e12242c-55f7-4bf4-90d7-0f36c0326b8e
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: Obtenga información sobre los pasos para restablecer el id. de conferencia de reunión de un usuario en Microsoft Teams y obtener vínculos a herramientas de actualización y migración de reuniones.
ms.openlocfilehash: edccab5da883c1707ade75519e96615ed3524bf3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117648"
---
# <a name="reset-a-conference-id-for-a-user-in-microsoft-teams"></a>Restablecer un Id. de conferencia para un usuario en Microsoft Teams

Se incluye un id. de conferencia dinámico en la parte inferior de las invitaciones de reunión junto con los números de teléfono de acceso telefónico que pueden usar las personas que llaman para llamar a una reunión. Cuando el usuario marca el número de teléfono, el operador automático de la reunión le pedirá al autor de la llamada que escriba este id. de conferencia para que pueda asistir a la reunión.
  
> [!NOTE]
> Los id. de conferencia se generan automáticamente, estarán entre 7 y 9 dígitos y se establecerán al habilitar audioconferencias para un usuario. **Los IDs de conferencia estáticos no son compatibles.** 

## <a name="resetting-the-conference-id-for-a-user"></a>Restablecer el id. de conferencia de un usuario

![Un icono que muestra el logotipo de Microsoft Teams](media/teams-logo-30x30.png) **Centro de administración de Microsoft Teams en uso**

1. En el panel de navegación izquierdo, haga clic **en Usuarios** y, a continuación, seleccione el usuario de la lista de usuarios disponibles.

2. Haga clic **en Editar.**

3. En **Audioconferencia, haga** clic **en Restablecer id. de conferencia.**

2. En la ventana **Restablecer id. de** conferencia, haga clic en **Restablecer.** Se creará automáticamente un id. de conferencia y se enviará un correo electrónico al usuario con el nuevo id. de conferencia. De forma predeterminada, los correos electrónicos se envían a los usuarios, pero esto se puede desactivar.   

    
> [!NOTE]
> Después de restablecer el id. de conferencia, se enviará al usuario un correo electrónico con el nuevo id. de conferencia. Este correo electrónico se enviará a la dirección de correo electrónico principal, en muchos casos, su Microsoft 365 o Office 365 buzón. El correo electrónico contiene el nuevo id. de conferencia, los números de teléfono de acceso telefónico locales predeterminados e instrucciones para actualizar las reuniones existentes. 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a>¿Qué más debo saber?

- Puede enviar toda la información de conferencia al usuario en un correo electrónico que incluya  el id. de conferencia y los números de teléfono de acceso telefónico local haciendo clic en Enviar información de conferencia por correo electrónico para el usuario en la sección **Audioconferencia.** No envía el PIN.
    
- El servicio de conferencia de 7 a 9 dígitos se crea Teams conferencia. No puede cambiar su longitud.
    
- Una vez que se ha restablecido el nuevo id. de conferencia, podrá verlo en **Id. de conferencia**.
    
- After a new conference ID is created, the old conference ID can't be used by callers. You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations. 

## <a name="want-to-know-more-about-windows-powershell"></a>¿Quiere saber más sobre Windows PowerShell?

Windows PowerShell se centra en la administración de usuarios y en las acciones que se les está permitido o no realizar. Con Windows PowerShell, puede administrar Microsoft 365 o Office 365 un único punto de administración que puede simplificar su trabajo diario cuando tiene varias tareas que hacer. To get started with Windows PowerShell, see these topics:
    
  - [Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [Las mejores formas de administrar Microsoft 365 o Office 365 con Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
Para obtener más información sobre Windows PowerShell, consulte la [referencia de PowerShell para Microsoft Teams](/powershell/module/teams/?view=teams-ps).
    
## <a name="related-topics"></a>Temas relacionados

[Restablecer el PIN de Audioconferencia](reset-the-audio-conferencing-pin-in-teams.md)