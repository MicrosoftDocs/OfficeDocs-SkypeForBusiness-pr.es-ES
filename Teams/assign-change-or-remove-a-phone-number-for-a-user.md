---
title: Asignar, cambiar o quitar un teléfono móvil de un usuario
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: davelick, roykuntz, jastark
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Calling Plans
description: Obtenga información sobre cómo asignar, cambiar o quitar un número de teléfono del trabajo a los usuarios de Teams para que clientes y empresas externas puedan llamar.
ms.openlocfilehash: 0dd126f3aa19e0b65b7a0c789f769cef1803f8c8
ms.sourcegitcommit: 321de0e5d8846caaaab944826f6ca06394e707ef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/16/2022
ms.locfileid: "69414688"
---
# <a name="assign-change-or-remove-a-phone-number-for-a-user"></a>Asignar, cambiar o quitar un teléfono móvil de un usuario

Al configurar Planes de llamadas, Operador De conexión o Teléfono móvil de Teams, asigna números de teléfono a los usuarios. En Microsoft Teams, el número de teléfono que asigne aparece cuando un usuario hace clic en **Llamadas**.

Este artículo se aplica a los planes de llamadas, a la conexión de operadores y al teléfono móvil de Teams. Para obtener información sobre cómo asignar, cambiar o quitar un número de teléfono a un usuario en un escenario de enrutamiento directo, vea [Habilitar usuarios para enrutamiento directo, voz y correo de voz](./direct-routing-enable-users.md).

Antes de asignar un número para un plan de llamadas, una conexión de operadores o un usuario de Teams Phone Mobile, debe obtener los números de los usuarios. Para obtener más información, vea [Obtener números para los usuarios del plan de llamadas](getting-phone-numbers-for-your-users.md), [Configurar números para los usuarios de Operator Connect](operator-connect-configure.md#set-up-phone-numbers) o [Configurar números para los usuarios de Teams Phone Mobile](operator-connect-mobile-configure.md).

> [!NOTE]
> Una forma de ver si un usuario tiene asignada una licencia es ir al Centro de administración de Microsoft Teams > **Usuarios**. Si se asigna una licencia, se indicará en la página.  También puede usar el Centro de administración de Microsoft 365.

> [!NOTE]
> Esta nota se aplica a los clientes que tienen una implementación híbrida con una Active Directory local. Si desea asignar un plan de llamadas o un número de teléfono Operador Conectar a una cuenta de usuario o recurso, debe asegurarse de que se ha quitado cualquier número de teléfono almacenado en el atributo msRTCSIP-Line en el objeto de cuenta de usuario o recurso de la Active Directory local y que el cambio se ha sincronizado con Microsoft 365.

## <a name="assign-a-phone-number-to-a-user"></a>Asignar un número de teléfono a un usuario

Al asignar un número de teléfono a un usuario, asegúrese de que el número de teléfono y la ubicación de uso del usuario son del mismo país.

Para asignar un número mediante el Centro de administración de Teams:

[!INCLUDE [assign-phone-numbers-to-users-steps](./includes/assign-phone-numbers-to-users-steps.md)]


Para asignar números mediante PowerShell, use el cmdlet [Set-CsPhoneNumberAssignment de](/powershell/module/teams/set-csphonenumberassignment) la siguiente manera:

Para los números del plan de llamadas:

```PowerShell
Set-CsPhoneNumberAssignment -Identity <user> -PhoneNumber <phone number> -PhoneNumberType CallingPlan
```

Para los números de Operador Conectar:

```PowerShell
Set-CsPhoneNumberAssignment -Identity <user> -PhoneNumber <phone number> -PhoneNumberType OperatorConnect
```

Para los números de teléfono móvil de Teams:

```PowerShell
Set-CsPhoneNumberAssignment -Identity <user> -PhoneNumber <phone number> -PhoneNumberType OCMobile
```

Por ejemplo:

```PowerShell
Set-CsPhoneNumberAssignment -Identity john@contoso.com -PhoneNumber "+14255550101" -PhoneNumberType CallingPlan
Set-CsPhoneNumberAssignment -Identity jack@contoso.com -PhoneNumber "+14255550102" -PhoneNumberType OperatorConnect
Set-CsPhoneNumberAssignment -Identity jack@contoso.com -PhoneNumber "+14255550103" -PhoneNumberType OCMobile
```

> [!NOTE]
> Debido a la latencia entre Microsoft 365 y Teams, los usuarios pueden tardar hasta 24 horas en habilitarse. Si el número de teléfono no se asigna correctamente después de 24 horas, consulte [Centro de servicio de números de teléfono](https://pstnsd.powerappsportals.com/).

> [!NOTE]
> Al asignar un número de teléfono, la marca EnterpriseVoiceEnabled se establece automáticamente en True.

## <a name="change-a-phone-number-for-a-user"></a>Cambiar un número de teléfono de un usuario

Para cambiar un número de teléfono de un usuario mediante el Centro de administración de Teams:

1. En el panel de navegación izquierdo, haga clic en **Usuarios**, busque y haga doble clic en el usuario que desee, haga clic en **Cuenta** y, a continuación, en **Información general**, anote el número de teléfono asignado al usuario.

2. En el panel de navegación izquierdo, haga clic en **Números de teléfono** **de voz**\>.

3. En la página **Números de teléfono** , seleccione el número que identificó en el paso 1 y, a continuación, haga clic en **Editar**.

4. En el panel **Editar** , en **Asignado a**, haga clic en la **X** para quitar el usuario.

5. Haga clic en **Guardar**.

6. En la página **Números de teléfono** , seleccione un número sin asignar en la lista y, a continuación, haga clic en **Editar**.

7. En el panel **Editar** , en **Asignado a**, busque el usuario por nombre para mostrar o nombre de usuario y, a continuación, haga clic en **Asignar**.

8. Para asignar o cambiar la ubicación de emergencia asociada, en **Ubicación de emergencia**, busque y seleccione la ubicación.

      > [!NOTE]
      > Si va a cambiar los números de los usuarios de Operator Connect o Teams Phone Mobile, es posible que pueda asignar o cambiar la ubicación de emergencia asociada. Esta funcionalidad dependerá de tu operador. Ponte en contacto con tu operador para obtener más información.

9. Haga clic en **Guardar**.

Para obtener un ejemplo de PowerShell, vea [Set-CsPhoneNumberAssignment](/powershell/module/teams/set-csphonenumberassignment).

## <a name="remove-a-phone-number-from-a-user"></a>Quitar un número de teléfono de un usuario

Para quitar un número de teléfono mediante el Centro de administración de Teams:

1. En el panel de navegación izquierdo, haga clic en **Usuarios**, busque y haga doble clic en el usuario que desee, haga clic en **Cuenta** y, a continuación, en **Información general**, anote el número de teléfono asignado al usuario.

2. En el panel de navegación izquierdo, haga clic en **Números de teléfono** **de voz**\>.

3. En la página **Números de teléfono** , seleccione el número que identificó en el paso 2 y, a continuación, haga clic en **Editar**.

4. En el panel **Editar** , en **Asignado a**, haga clic en la **X** para quitar el usuario.

5. Haga clic en **Guardar**.

Para obtener un ejemplo de PowerShell, vea [Remove-CsPhoneNumberAssignment](/powershell/module/teams/remove-csphonenumberassignment).

## <a name="related-topics"></a>Temas relacionados

[¿Qué es la validación de direcciones?](/skypeforbusiness/what-are-calling-plans-in-office-365/what-is-address-validation)

[Administrar los números de teléfono para su organización](/microsoftteams/manage-phone-numbers-for-your-organization)

[Términos y condiciones de las llamadas de emergencia](./emergency-calling-terms-and-conditions.md)

[Etiqueta de declinación de responsabilidades de llamadas de emergencia](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

[Set-CsPhoneNumberAssignment](/powershell/module/teams/set-csphonenumberassignment)

[Remove-CsPhoneNumberAssignment](/powershell/module/teams/remove-csphonenumberassignment)
