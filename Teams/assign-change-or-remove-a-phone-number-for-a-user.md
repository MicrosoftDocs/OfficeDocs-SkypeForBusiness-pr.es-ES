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
description: Obtenga información sobre cómo asignar, cambiar o quitar un número de teléfono del trabajo para Teams usuarios para que los clientes y empresas externas puedan llamar.
ms.openlocfilehash: 4f40049b3856f24d3ae5ddd3999be7213817bcdc
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120822"
---
# <a name="assign-change-or-remove-a-phone-number-for-a-user-calling-plans"></a>Asignar, cambiar o quitar un número de teléfono para un usuario (Planes de llamadas)

Al configurar planes de llamadas, asigna números de teléfono a los usuarios. En Microsoft Teams, el número de teléfono que asigna se muestra cuando un usuario hace clic en **Llamadas.** Para obtener instrucciones sobre cómo asignar, cambiar o quitar un número de teléfono de un usuario en un escenario de enrutamiento directo, vea Habilitar usuarios para enrutamiento directo, voz y correo [de voz.](./direct-routing-enable-users.md)

![El número de teléfono del usuario se muestra en Teams.](media/teams-phone-number.png)

Cuando configura usuarios para que puedan realizar y recibir llamadas telefónicas, primero debe usar el centro de administración de Microsoft Teams y asignar un número de teléfono. Puede cambiar o quitar el número de teléfono si es necesario.
  
Para obtener información sobre cómo obtener planes de llamadas en Teams y cuánto cuestan, vea Teams [licencias de complementos.](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
  
> [!NOTE]
> Una forma de ver si un usuario tiene una licencia asignada es yendo al centro de administración de Microsoft Teams de > **Usuarios.** Si se asigna una licencia, se indicará en la página.  También puede usar el centro Microsoft 365 administración.
  
## <a name="assign-a-phone-number-to-a-user"></a>Asignar un número de teléfono a un usuario
 
![Un icono que muestra el logotipo de Microsoft Teams](media/teams-logo-30x30.png) **Centro de administración de Microsoft Teams en uso**
    
1. En el panel de navegación izquierdo, haga clic  >  **en Teléfono números.**
2. En la **Teléfono números,** seleccione un número sinsignado en la lista y, a continuación, haga clic en **Editar.**  
3. En el **panel Editar,** en **Asignado a**, busque al usuario por nombre para mostrar o nombre de usuario y, a continuación, haga clic en **Asignar**.
4. Para asignar o cambiar la ubicación de emergencia asociada, en **Ubicación de emergencia,** busque y seleccione la ubicación.
5. Dependiendo de si desea enviar un correo electrónico al usuario con su información de número de teléfono, desactive o active Usuario de correo electrónico con información **de número de teléfono.** De forma predeterminada, está en. 
6. Haga clic en **Guardar**.

Para obtener un ejemplo de PowerShell, [vea Set-CsOnlineVoiceUser](/powershell/module/skype/set-csonlinevoiceuser?view=skype-ps).

    > [!NOTE]
    > Because of the latency between Microsoft 365 or Office 365 and Teams, it can take up to 24 hours for users to be enabled. If the phone number isn't assigned correctly after 24 hours, [contact support for business products - Admin Help](/microsoft-365/admin/contact-support-for-business-products). We're here to help!

  
## <a name="change-a-phone-number-for-a-user"></a>Cambiar un número de teléfono para un usuario
 
![Un icono que muestra el logotipo de Microsoft Teams](media/teams-logo-30x30.png) **Centro de administración de Microsoft Teams en uso**
    
1. En el panel de navegación izquierdo, haga clic en Usuarios **,** busque y haga doble clic en el usuario que desee, haga clic en Cuenta y, a continuación, en Información **general,** anote el número de teléfono asignado al usuario.
2. En el panel de navegación izquierdo, haga clic  >  **en Teléfono números.**
3. En la **página Teléfono números,** seleccione el número que identificó en el paso 1 y, a continuación, haga clic en **Editar.**  
4. En el **panel Editar,** en **Asignado a**, haga clic en la **X** para quitar al usuario.
5. Haga clic en **Guardar**.
6. En la **Teléfono números,** seleccione un número sinsignado en la lista y, a continuación, haga clic en **Editar.**  
7. En el **panel Editar,** en **Asignado a**, busque al usuario por nombre para mostrar o nombre de usuario y, a continuación, haga clic en **Asignar**.
8. Para asignar o cambiar la ubicación de emergencia asociada, en **Ubicación de emergencia,** busque y seleccione la ubicación.
9. Haga clic en **Guardar**.

Para obtener un ejemplo de PowerShell, vea [Set-CsOnlineVoiceUser](/powershell/module/skype/set-csonlinevoiceuser?view=skype-ps).

## <a name="remove-a-phone-number-from-a-user"></a>Quitar un número de teléfono de un usuario
 
![Un icono que muestra el logotipo de Microsoft Teams](media/teams-logo-30x30.png) **Centro de administración de Microsoft Teams en uso**

1. En el panel de navegación izquierdo, haga clic en Usuarios **,** busque y haga doble clic en el usuario que desee, haga clic en Cuenta y, a continuación, en Información **general,** anote el número de teléfono asignado al usuario.
2. En el panel de navegación izquierdo, haga clic  >  **en Teléfono números.**
3. En la **Teléfono números,** seleccione el número que identificó en el paso 2 y, a continuación, haga clic en **Editar.**  
4. En el **panel Editar,** en **Asignado a**, haga clic en la **X** para quitar al usuario.
5. Haga clic en **Guardar**.

Para obtener un ejemplo de PowerShell, vea [Set-CsOnlineVoiceUser](/powershell/module/skype/set-csonlinevoiceuser?view=skype-ps).

## <a name="related-topics"></a>Temas relacionados

[¿Qué es la validación de direcciones?](/skypeforbusiness/what-are-calling-plans-in-office-365/what-is-address-validation)

[Administrar los números de teléfono para su organización](/microsoftteams/manage-phone-numbers-for-your-organization)

[Términos y condiciones de las llamadas de emergencia](./emergency-calling-terms-and-conditions.md)

[Etiqueta de declinación de responsabilidades de llamadas de emergencia](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

[Set-CsOnlineVoiceUser](/powershell/module/skype/set-csonlinevoiceuser?view=skype-ps)

[Planes de llamadas para Microsoft 365](./calling-plans-for-office-365.md)