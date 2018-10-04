---
title: Configurar teléfonos de área común
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: wasseemh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: Obtenga información sobre los pasos de implementación para obtener el firmware correcto, actualizarlo si es necesario, asignar licencias y configurar las opciones de teléfonos de área común.
ms.openlocfilehash: 3faa66235f3c3364a0da6560a6dc52daa252915b
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "25370679"
---
# <a name="set-up-common-area-phones"></a>Configurar teléfonos de área común
A common area phone (CAP) is typically placed in an area like a lobby or another area that is available to a lot of people. For example, a reception area phone, door phone or meeting room phone, CAPs are set up as devices rather than users and automatically sign into a network. In the steps below, we’ll help you set up an account for Phone System with Calling Plans so you can deploy these types of phones for your organization.

## <a name="prerequisites-for-common-area-phones"></a>Requisitos previos de los teléfonos de área común

Lo primero que debe hacer es confirmar que tiene lo siguiente:

- Adquiera una licencia de teléfono de área común y un plan de llamadas.
- Busque y compre teléfonos aprobados (vea la lista [aquí](deploying-skype-for-business-online-phones.md)).
- Update the firmware on your phones (See supported firmware [in this topic](getting-phones-for-skype-for-business-online.md)).  You can check the firmware on you phone by doing this:
  - **Los teléfonos Polycom VVX**: Ir a la **configuración de** > **estado** > **plataforma** > **aplicación** > **principal**.
  - **Teléfonos Yealink**: vaya al **estado** de la pantalla del teléfono principal.
  - **Teléfonos AudioCodes**: vaya al **menú** > **Estado del dispositivo** > **versión de Firmware** desde la pantalla de inicio.
  - **Teléfonos de Lync Phone Edition (LPE)**: vaya al **menú** > **Información del sistema** desde la pantalla de inicio.

    Firmware updates are managed by the Skype for Business Service. Every Skype for Business certified phone's firmware is uploaded to the Skype for Business Update server, and device update is enabled on all phones by default.

    Depending on the inactivity time on the phone and polling intervals, phones will automatically download and install the latest certified builds. You can disable the device update settings by using the  [Set-CsIPPhonePolicy](https://docs.microsoft.com/powershell/module/skype/set-csipphonepolicy) cmdlet and setting the *EnableDeviceUpdate* parameter to `false`.

## <a name="setting-up-a-common-area-phone"></a>Configurar un teléfono de área común
Tendrá que seguir estos pasos:

### <a name="step-1---buy-the-licenses"></a>Paso 1: comprar las licencias
1. En el centro de administración de Office 365, entre en **Facturación** > **Servicios de compra**, y agregue **Otros planes**.

    ![CAP-license.png](../../images/cap-license.png)
2. Haga clic en **Teléfono de área común** > **Comprar ahora** > y en la página de **Pago** haga clic en **Compra ahora**.
3. Click on to expand **Add-on subscriptions** and then click on to buy a Calling Plan. Choose either the **Domestic Calling Plan** or **Domestic and International Calling Plan**.

> [!Note]
> You don't need a Phone System license. It's included with the **Common Area Phone** license.

Para obtener más información sobre las licencias, vea [Skype para profesionales y los equipos de Microsoft complemento licencias](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).

### <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a>Paso 2: crear una nueva cuenta de usuario para el teléfono y asignar las licencias
1. En el centro de administración de Office 365, entre en **Usuarios** > **Usuarios activos** > **Agregar un usuario**.
2. Indique un **Nombre de usuario** del estilo de "Principal" para el primer nombre y "Recepción" para el segundo nombre.
3. Indique un **Nombre para mostrar** si no se autogenera uno del estilo de "Recepción principal".
4. Indique un **Nombre de usuario** del estilo de "RecepciónPrincipal" o "VestíbuloPrincipal".
5. For common area phones, you might want to set a password manually or have the same password for all of you common area phones. Also, you might think about unselecting **Make this user change their password when they first sign in**.

    > [!Tip]
    > WAIT!! Don't click **Add**!! Ugh, if you did click **Add** the do this: Office 365 admin center > **Users** > **Active users** and then find the user. Then on the user's properties page, click **Product licenses** and then click **Edit**. On the **Product licenses** page, turn on **Common Area Phone** and pick either a **Domestic Calling Plan** or a Domestic and **International Calling Plan**.

6. If you are still there, assign the licenses to this user. On the same page, click to expand **Product licenses**. Turn on the following:
   - Teléfono de área común
   - Luego debe elegir un **Plan de llamadas nacionales** o un **Plan de llamadas internacionales** y nacionales.

     La asignación de licencias tendrá este aspecto:

     ![TurnOnCapLicense.png](../../images/cap-license-turn-on.png)

     > [!Note]
     > Para su interés, el Plan 2 de Skype for Business se incluye con la licencia del **teléfono de área común**.

Para más detalles, consulte [Agregar un usuario](https://support.office.com/article/1970f7d6-03b5-442f-b385-5880b9c256ec).

### <a name="step-3---assign-a-phone-number-to-the-common-area-phone-user-account"></a>Paso 3: asignar un número de teléfono a la cuenta de usuario del teléfono de área común

![sfb-logo-30x30.png](../../images/sfb-logo-30x30.png) Asignar un número de teléfono al usuario mediante el **centro de administración de Skype for Business**

1. En el centro de administración de Office 365 > **centros de administración** > **Skype para la empresa**.
2. En el **centro de administración de Skype for Business** >  **Voz** > **Números de teléfono**.
3. Seleccione un número de la lista de números de teléfono y haga clic en **Asignar**.
4. En la página **Asignar**, en el cuadro **Usuario de voz** indique el nombre del usuario que se utiliza para el teléfono y luego seleccione el usuario en el desplegable **Seleccionar un usuario de voz**.
5. While you're there you will need to add an emergency address. Once you search, look under the **Select emergency address** to pick the right one for you.
6. Haga clic en **Guardar** y el usuario debería tener este aspecto:

    ![cap-user-number.png](../../images/cap-user-number.png)

   > [!Note]
   > Users will only show up if they have a **Phone System** licence applied. If you just did this, then sometimes it takes a bit for the user to show up in the list.

Para más información, consulte [Obtener números de teléfono para los usuarios](../../what-are-calling-plans-in-office-365/getting-phone-numbers-for-your-users.md).

If you're wondering, you can also take your phone number that you have with another carrier and "*port*" or transfer them over to Office 365. See, [Transfer phone numbers to Office 365](/microsoftteams/transfer-phone-numbers-to-office-365).

### <a name="step-4---setting-up-your-phone"></a>Paso 4: configurar el teléfono

**Configurar el modo en el teléfono**

The phone or phones you have must have the **Common Area Phone mode** turned on. You might want to check on that to make sure they do.

**Aquí tiene un ejemplo de cómo configurar un teléfono Polycom VVX**

- Habilite el modo de teléfono de área común en un Polycom VVX siguiendo estos pasos:
    1. En su explorador, conéctese a la interfaz web para poder habilitar el modo CAP.
    2. Luego entre en **Configuración** y, en la opción **Configuración de Skype for Business**, seleccione **Teléfono de área común**.
    3. Haga clic en **Sí** para guardar su configuración.

- Now that CAP mode is enabled, set up the phone using the phone's display. The display should show **CaAP is enabled**. Then do the following:

    1. Haga clic en **Configuración**.
    2. Seleccione **avanzada**.
    3. Escriba la contraseña.
    4. En **Configuración de administración**, seleccione **Configuración del teléfono de área común**.
    5. Habilite **CAP** y **Modo de administración CAP**.
    6. Haga clic en **Guardar configuración**.

- Bien, ahora su teléfono está listo para que pueda conectarse en la pantalla de inicio.

    1. Conéctese seleccionando **Configuración** > **Características** > **Skype for Business.**
    2. Seleccione **Credenciales de usuario** y luego **conexión web (CAP)** para generar un código.
    3. Entre en el [portal de aprovisionamiento](https://aka.ms/skypecap) y conéctese como **administrador**.
    4. Escriba el nombre para mostrar (por ejemplo, Recepción principal).

       > [!Note]
       > Si está marcado **Buscar solo teléfonos de área común**, desactive la casilla de verificación y busque de nuevo.

    5. En la ventana del código de vinculación, escriba el código que se muestra en el teléfono y haga clic en **Aprovisionar**.

        Tras este último paso, el teléfono debería conectarse automáticamente.


> [!NOTE]
> The CAP provisioning site states it will reset the CAP account's password to a random password. Take note that the account the CAP is referring is the Azure Active Directory (AAD) account. If you created the account in AAD only then the process is straightforward. If you have synced an on premises Active Directory to AAD make sure to take note of the credentials you are using that will be changed by CAP provisioning.


### <a name="related-topics"></a>Temas relacionados

- Obtenga más información sobre teléfonos disponibles en [Implementar teléfonos de Skype Empresarial Online](deploying-skype-for-business-online-phones.md).
- [Obtener teléfonos con Skype Empresarial Online](getting-phones-for-skype-for-business-online.md)


