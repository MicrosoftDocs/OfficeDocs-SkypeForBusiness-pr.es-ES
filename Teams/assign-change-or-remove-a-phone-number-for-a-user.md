---
title: Asignar, cambiar o quitar un teléfono móvil de un usuario
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 91089761-cb87-4119-885b-3713840dd9f7
ms.tgt.pltfrm: cloud
audience: admin
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
description: Obtenga información sobre cómo asignar, cambiar o quitar un número de teléfono de trabajo para los usuarios de Teams para que los clientes y empresas externas puedan llamar.
ms.openlocfilehash: e606885aee1e87dfdfc9b36a5247eedba225a185
ms.sourcegitcommit: 91fbc7c9cd43c2a5b7e6dfedf2388939f2f77d57
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2021
ms.locfileid: "50589624"
---
# <a name="assign-change-or-remove-a-phone-number-for-a-user-calling-plans"></a>Asignar, cambiar o quitar un número de teléfono para un usuario (Planes de llamadas)

Al configurar planes de llamadas, asigna números de teléfono a los usuarios. En Microsoft Teams, el número de teléfono que asigna se muestra cuando un usuario hace clic en **Llamadas.** Para obtener instrucciones sobre cómo asignar, cambiar o quitar un número de teléfono de un usuario en un escenario de enrutamiento directo, vea Habilitar usuarios para enrutamiento directo, voz y correo [de voz.](https://docs.microsoft.com/microsoftteams/direct-routing-enable-users)

![Número de teléfono del usuario que se muestra en Teams.](media/teams-phone-number.png)

Cuando configura usuarios para que puedan realizar y recibir llamadas telefónicas, primero debe usar el Centro de administración de Microsoft Teams y asignar un número de teléfono. Puede cambiar o quitar el número de teléfono si es necesario.
  
Para obtener información sobre cómo obtener planes de llamadas en Teams y cuánto cuestan, vea [Licencias de complemento de Teams.](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing)
  
> [!NOTE]
> Una forma de ver si un usuario tiene una licencia asignada es yendo al Centro de administración de Microsoft Teams > **Usuarios.** Si se asigna una licencia, se indicará en la página.  También puede usar el Centro de administración de Microsoft 365.
  
## <a name="assign-a-phone-number-to-a-user"></a>Asignar un número de teléfono a un usuario
 
![Un icono que muestra el logotipo de Microsoft Teams](media/teams-logo-30x30.png) **Usando el centro de administración de Microsoft Teams**
    
1. En el panel de navegación izquierdo, haga clic en **Números de teléfono** de  >  **voz.**
2. En la **página Números de** teléfono, seleccione un número sinsignado en la lista y, a continuación, haga clic en **Editar.**  
3. En el **panel Editar,** en **Asignado a**, busque al usuario por nombre para mostrar o nombre de usuario y, a continuación, haga clic en **Asignar**.
4. Para asignar o cambiar la ubicación de emergencia asociada, en **Ubicación de emergencia,** busque y seleccione la ubicación.
5. Dependiendo de si desea enviar un correo electrónico al usuario con su información de número de teléfono, desactive o active Usuario de correo electrónico con información **de número de teléfono.** De forma predeterminada, está en. 
6. Haga clic en **Guardar**.

Para obtener un ejemplo de PowerShell, [vea Set-CsOnlineVoiceUser](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceuser?view=skype-ps).

    > [!NOTE]
    > Because of the latency between Microsoft 365 or Office 365 and Teams, it can take up to 24 hours for users to be enabled. If the phone number isn't assigned correctly after 24 hours, [contact support for business products - Admin Help](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products). We're here to help!

  
## <a name="change-a-phone-number-for-a-user"></a>Cambiar un número de teléfono para un usuario
 
![Un icono que muestra el logotipo de Microsoft Teams](media/teams-logo-30x30.png) **Usando el centro de administración de Microsoft Teams**
    
1. En el panel de navegación izquierdo, haga clic en Usuarios **,** busque y haga doble clic en el usuario que desee, haga clic en Cuenta y, a continuación, en Información **general,** anote el número de teléfono asignado al usuario.
2. En el panel de navegación izquierdo, haga clic en **Números de teléfono** de  >  **voz.**
3. En la **página Números de** teléfono, seleccione el número que identificó en el paso 1 y, a continuación, haga clic en **Editar.**  
4. En el **panel Editar,** en **Asignado a**, haga clic en la **X** para quitar al usuario.
5. Haga clic en **Guardar**.
6. En la **página Números de** teléfono, seleccione un número sinsignado en la lista y, a continuación, haga clic en **Editar.**  
7. En el **panel Editar,** en **Asignado a**, busque al usuario por nombre para mostrar o nombre de usuario y, a continuación, haga clic en **Asignar**.
8. Para asignar o cambiar la ubicación de emergencia asociada, en **Ubicación de emergencia,** busque y seleccione la ubicación.
9. Haga clic en **Guardar**.

Para obtener un ejemplo de PowerShell, vea [Set-CsOnlineVoiceUser](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceuser?view=skype-ps).

## <a name="remove-a-phone-number-from-a-user"></a>Quitar un número de teléfono de un usuario
 
![Un icono que muestra el logotipo de Microsoft Teams](media/teams-logo-30x30.png) **Usando el centro de administración de Microsoft Teams**

1. En el panel de navegación izquierdo, haga clic en Usuarios **,** busque y haga doble clic en el usuario que desee, haga clic en Cuenta y, a continuación, en Información **general,** anote el número de teléfono asignado al usuario.
2. En el panel de navegación izquierdo, haga clic en **Números de teléfono** de  >  **voz.**
3. En la **página Números de** teléfono, seleccione el número que identificó en el paso 2 y, a continuación, haga clic en **Editar.**  
4. En el **panel Editar,** en **Asignado a**, haga clic en la **X** para quitar al usuario.
5. Haga clic en **Guardar**.

Para obtener un ejemplo de PowerShell, vea [Set-CsOnlineVoiceUser](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceuser?view=skype-ps).

## <a name="related-topics"></a>Temas relacionados

[¿Qué es la validación de direcciones?](/skypeforbusiness/what-are-calling-plans-in-office-365/what-is-address-validation)

[Administrar los números de teléfono para su organización](/microsoftteams/manage-phone-numbers-for-your-organization)

[Términos y condiciones de las llamadas de emergencia](/microsoftteams/emergency-calling-terms-and-conditions)

[Etiqueta de declinación de responsabilidades de llamadas de emergencia](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

[Set-CsOnlineVoiceUser](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceuser?view=skype-ps)

[Planes de llamadas para Microsoft 365](https://docs.microsoft.com/MicrosoftTeams/calling-plans-for-office-365)
