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
description: Obtenga información sobre cómo asignar, cambiar o quitar un número de teléfono del trabajo para Teams usuarios para que los clientes y empresas externas puedan llamar.
ms.openlocfilehash: 6341b6c3242eafad7039b210995ee7c56613442e
ms.sourcegitcommit: 39378888464ade3cb45879a449143f40f202f3e9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2022
ms.locfileid: "64456913"
---
# <a name="assign-change-or-remove-a-phone-number-for-a-user"></a>Asignar, cambiar o quitar un teléfono móvil de un usuario

Al configurar planes de llamadas u Conectar operador, se asignan números de teléfono a los usuarios. En Microsoft Teams, el número de teléfono que asigna se muestra cuando un usuario hace clic en **Llamadas**. 

Este artículo se aplica a planes de llamadas y Conectar. Para obtener información sobre cómo asignar, cambiar o quitar un número de teléfono de un usuario en un escenario de enrutamiento directo, vea Habilitar usuarios para enrutamiento directo, voz y correo [de voz](./direct-routing-enable-users.md).

Antes de asignar un número para un plan de llamadas u operador Conectar usuario, debe obtener números para los usuarios. Para obtener más información, vea [Obtener números para usuarios del plan de](getting-phone-numbers-for-your-users.md) llamadas o Configurar números para usuarios Conectar [operadores](operator-connect-configure.md#set-up-phone-numbers).

  
> [!NOTE]
> Una forma de ver si un usuario tiene una licencia asignada es yendo al centro de administración de Microsoft Teams de > **usuarios**. Si se asigna una licencia, se indicará en la página.  También puede usar el Centro de administración de Microsoft 365.

> [!NOTE]
> Esta nota se aplica a los clientes que tienen una implementación híbrida con un Active Directory local. Si desea asignar un plan de llamadas u operador Conectar un número de teléfono Conectar un usuario o cuenta de recursos, debe asegurarse de que se ha quitado cualquier número de teléfono almacenado en el atributo msRTCSIP-Line en el objeto de cuenta de usuario o recurso en el Active Directory local y que el cambio se haya sincronizado a Microsoft 365.
  
## <a name="assign-a-phone-number-to-a-user"></a>Asignar un número de teléfono a un usuario

Al asignar un número de teléfono a un usuario, asegúrese de que el número de teléfono y la ubicación de uso del usuario son del mismo país.

Para asignar un número mediante el centro Teams administración:
    
1. En el panel de navegación izquierdo, haga **clic en Teléfono** >  números.

2. En la **Teléfono números**, seleccione un número sinsignado en la lista y, a continuación, haga clic en **Editar**.  

3. En el **panel Editar** , en **Asignado** a, busque al usuario por nombre para mostrar o nombre de usuario y, a continuación, haga clic en **Asignar**.

4. Para asignar o cambiar la ubicación de emergencia asociada, en **Ubicación de emergencia**, busque y seleccione la ubicación.

   > [!NOTE]
   > Si va a asignar números al operador Conectar usuarios, es posible que no pueda asignar o cambiar la ubicación de emergencia asociada. Esta funcionalidad dependerá del operador. Póngase en contacto con su operador para obtener más información.

5. Según si desea enviar un correo electrónico al usuario con su información de número de teléfono, desactive o active Usuario de correo electrónico **con información de número de teléfono**. De forma predeterminada, está en. 

6. Haga clic en **Guardar**.

Para asignar números mediante PowerShell, use el cmdlet [Set-CsPhoneNumberAssignment](/powershell/module/teams/set-csphonenumberassignment) de la siguiente manera:

Para números de plan de llamadas
```PowerShell
Set-CsPhoneNumberAssignment -Identity <user>  -PhoneNumber <phone number> -PhoneNumberType CallingPlan
```

Para Números de Conectar operadores
```PowerShell
Set-CsPhoneNumberAssignment -Identity <user>  -PhoneNumber <phone number> -PhoneNumberType OperatorConnect
```

Por ejemplo:

```PowerShell
Set-CsPhoneNumberAssignment -Identity john@contoso.com -PhoneNumber "+14255550101" -PhoneNumberType CallingPlan
Set-CsPhoneNumberAssignment -Identity jack@contoso.com -PhoneNumber "+14255550102" -PhoneNumberType OperatorConnect
```

> [!NOTE]
> Debido a la latencia entre Microsoft 365 y Teams, los usuarios pueden tardar hasta 24 horas en habilitarse. Si el número de teléfono no se asigna correctamente después de 24 horas, vea [Teléfono Centro de servicio de números](https://pstnsd.powerappsportals.com/). 

  
## <a name="change-a-phone-number-for-a-user"></a>Cambiar un número de teléfono para un usuario

Para cambiar un número de teléfono para un usuario mediante el centro Teams administración:
    
1. En el panel de navegación izquierdo, haga clic en **Usuarios, busque** y haga doble clic en el usuario que desee, haga clic en Cuenta **y, a** continuación, en Información **general**, anote el número de teléfono asignado al usuario.

2. En el panel de navegación izquierdo, haga **clic en Teléfono** >  números.

3. En la **Teléfono números**, seleccione el número que identificó en el paso 1 y, a continuación, haga clic en **Editar**.  

4. En el **panel Editar** , en **Asignado a**, haga clic en la **X** para quitar al usuario.

5. Haga clic en **Guardar**.

6. En la **Teléfono números**, seleccione un número sinsignado en la lista y, a continuación, haga clic en **Editar**.  

7. En el **panel Editar** , en **Asignado** a, busque al usuario por nombre para mostrar o nombre de usuario y, a continuación, haga clic en **Asignar**.

8. Para asignar o cambiar la ubicación de emergencia asociada, en **Ubicación de emergencia**, busque y seleccione la ubicación.

      > [!NOTE]
      > Si va a cambiar los números de operador Conectar usuarios, es posible que no pueda asignar o cambiar la ubicación de emergencia asociada. Esta funcionalidad dependerá del operador. Póngase en contacto con su operador para obtener más información.

9. Haga clic en **Guardar**.

Para obtener un ejemplo de PowerShell, vea [Set-CsPhoneNumberAssignment](/powershell/module/teams/set-csphonenumberassignment).

## <a name="remove-a-phone-number-from-a-user"></a>Quitar un número de teléfono de un usuario

Para quitar un número de teléfono mediante el centro Teams administración:

1. En el panel de navegación izquierdo, haga clic en **Usuarios, busque** y haga doble clic en el usuario que desee, haga clic en Cuenta **y, a** continuación, en Información **general**, anote el número de teléfono asignado al usuario.

2. En el panel de navegación izquierdo, haga **clic en Teléfono** >  números.

3. En la **Teléfono números**, seleccione el número que identificó en el paso 2 y, a continuación, haga clic en **Editar**.  

4. En el **panel Editar** , en **Asignado a**, haga clic en la **X** para quitar al usuario.

5. Haga clic en **Guardar**.

Para obtener un ejemplo de PowerShell, vea [Quitar-CsPhoneNumberAssignment](/powershell/module/teams/remove-csphonenumberassignment).

## <a name="related-topics"></a>Temas relacionados

[¿Qué es la validación de direcciones?](/skypeforbusiness/what-are-calling-plans-in-office-365/what-is-address-validation)

[Administrar los números de teléfono para su organización](/microsoftteams/manage-phone-numbers-for-your-organization)

[Términos y condiciones de las llamadas de emergencia](./emergency-calling-terms-and-conditions.md)

[Etiqueta de declinación de responsabilidades de llamadas de emergencia](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

[Set-CsPhoneNumberAssignment](/powershell/module/teams/set-csphonenumberassignment)

[Remove-CsPhoneNumberAssignment](/powershell/module/teams/remove-csphonenumberassignment)

