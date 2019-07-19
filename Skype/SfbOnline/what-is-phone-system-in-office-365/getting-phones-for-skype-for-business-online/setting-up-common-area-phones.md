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
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: Aprenda los pasos de implementación para obtener el firmware correcto, actualizarlo si es necesario, asignar licencias y configurar los valores de los teléfonos comunes de área.
ms.openlocfilehash: 9f84b8ebbdd9bfab6b146d3f748715a5e0602047
ms.sourcegitcommit: 4c041e8a7c39bd6517605ed7fc9aab18cf466596
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/18/2019
ms.locfileid: "35792459"
---
# <a name="set-up-common-area-phones"></a>Configurar teléfonos de área común
A common area phone (CAP) is typically placed in an area like a lobby or another area that is available to a lot of people. For example, a reception area phone, door phone or meeting room phone, CAPs are set up as devices rather than users and automatically sign into a network. In the steps below, we’ll help you set up an account for Phone System with Calling Plans so you can deploy these types of phones for your organization.

## <a name="prerequisites-for-common-area-phones"></a>Requisitos previos de los teléfonos de área común

Lo primero que debe hacer es confirmar que tiene lo siguiente:

- Adquiera una licencia de teléfono de área común y un plan de llamadas.
- Busque y compre teléfonos aprobados (vea la lista [aquí](deploying-skype-for-business-online-phones.md)).
- Update the firmware on your phones (See supported firmware [in this topic](getting-phones-for-skype-for-business-online.md)).  You can check the firmware on you phone by doing this:
  - **Teléfonos VVX de Polycom**: vaya **a configuración** > **Estado** > **plataforma** > **aplicación** > **principal**.
  - **Teléfonos Yealink**: Ve al **Estado** en la pantalla principal del teléfono.
  - **Teléfonos AudioCodes**: vaya a **menú menu** > **** > **versión de firmware** de estado de dispositivo desde la pantalla de inicio.
  - **Teléfonos Lync Phone Edition (LPE)**: vaya a **** > **información del sistema** de menús desde la pantalla Inicio.

    Firmware updates are managed by the Skype for Business Service. Every Skype for Business certified phone's firmware is uploaded to the Skype for Business Update server, and device update is enabled on all phones by default.

    Depending on the inactivity time on the phone and polling intervals, phones will automatically download and install the latest certified builds. You can disable the device update settings by using the  [Set-CsIPPhonePolicy](https://docs.microsoft.com/powershell/module/skype/set-csipphonepolicy) cmdlet and setting the *EnableDeviceUpdate* parameter to `false`.

## <a name="setting-up-a-common-area-phone"></a>Configurar un teléfono de área común
Tendrá que seguir estos pasos:

### <a name="step-1---buy-the-licenses"></a>Paso 1: comprar las licencias
1. En el centro de administración, vaya a**servicios de compra**de **facturación** > y agregue **otros planes**.

    ![CAP-license.png](../../images/cap-license.png)
2. Haga clic en **Teléfono de área común** > **Comprar ahora** > y en la página de **Pago** haga clic en **Compra ahora**.
3. Click on to expand **Add-on subscriptions** and then click on to buy a Calling Plan. Choose either the **Domestic Calling Plan** or **Domestic and International Calling Plan**.

> [!Note]
> You don't need a Phone System license. It's included with the **Common Area Phone** license.

Para obtener más información sobre las licencias, vea [licencias complementarias de Skype empresarial y Microsoft Teams](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).

### <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a>Paso 2: crear una nueva cuenta de usuario para el teléfono y asignar las licencias
1. En el centro de administración, vaya **** > a usuarios**activos usuarios** > ,**Agregar un usuario**.
2. Indique un **Nombre de usuario** del estilo de "Principal" para el primer nombre y "Recepción" para el segundo nombre.
3. Indique un **Nombre para mostrar** si no se autogenera uno del estilo de "Recepción principal".
4. Indique un **Nombre de usuario** del estilo de "RecepciónPrincipal" o "VestíbuloPrincipal".
5. For common area phones, you might want to set a password manually or have the same password for all of you common area phones. Also, you might think about unselecting **Make this user change their password when they first sign in**.
6. Estando aún allí, asigne las licencias a este usuario. En la misma página, haga clic para expandir las **Licencias de producto**. Active lo siguiente:
   - Teléfono de área común
   - Luego debe elegir un **Plan de llamadas nacionales** o un **Plan de llamadas internacionales** y nacionales.

     La asignación de licencias tendrá este aspecto:

     ![TurnOnCapLicense.png](../../images/cap-license-turn-on.png)

     > [!Note]
     > Para su interés, el Plan 2 de Skype for Business se incluye con la licencia del **teléfono de área común**.

Para más detalles, consulte [Agregar un usuario](https://support.office.com/article/1970f7d6-03b5-442f-b385-5880b9c256ec).

### <a name="step-3---assign-a-phone-number-to-the-common-area-phone-user-account"></a>Paso 3: asignar un número de teléfono a la cuenta de usuario del teléfono de área común

![Un icono que muestra el logotipo](../../images/sfb-logo-30x30.png) de Skype empresarial asignar un número de teléfono al usuario con el centro de **Administración de Skype empresarial**

1. En el centro de administración > **centros** > de administración**de Skype empresarial**.
2. En el **centro de administración de Skype for Business** >  **Voz** > **Números de teléfono**.
3. Seleccione un número de la lista de números de teléfono y haga clic en **Asignar**.
4. En la página **Asignar**, en el cuadro **Usuario de voz** indique el nombre del usuario que se utiliza para el teléfono y luego seleccione el usuario en el desplegable **Seleccionar un usuario de voz**.
5. Allí deberá agregar también una dirección de emergencia. Tras hacer la búsqueda, revise **Seleccionar dirección de emergencia** para elegir la correcta en su caso.
6. Haga clic en **Guardar** y el usuario debería tener este aspecto:

    ![cap-user-number.png](../../images/cap-user-number.png)

   > [!Note]
   > Los usuarios solo aparecerán si tienen aplicada una licencia de **sistema telefónico**. Si acaba de aplicársela, el usuario a veces tarda un poco de tiempo en aparecer en la lista.

Para más información, consulte [Obtener números de teléfono para los usuarios](/microsoftteams/getting-phone-numbers-for-your-users).

Por si se lo está preguntando, también puede coger el número de teléfono que tenga con otra compañía y "*pasarlo*" o transferirlo a Office 365. Consulte [transferir números de teléfono a Office 365](/microsoftteams/transfer-phone-numbers-to-office-365).

### <a name="step-4---setting-up-your-phone"></a>Paso 4: configurar el teléfono

**Configurar el modo en el teléfono**

El teléfono o teléfonos que posea deben tener activado el **Modo de teléfono de área común**. Quizá convenga verificarlo para asegurarse de que así es.

**Aquí tiene un ejemplo de cómo configurar un teléfono Polycom VVX**

- Habilite el modo de teléfono de área común en un Polycom VVX siguiendo estos pasos:
    1. En su explorador, conéctese a la interfaz web para poder habilitar el modo CAP.
    2. Luego entre en **Configuración** y, en la opción **Configuración de Skype for Business**, seleccione **Teléfono de área común**.
    3. Haga clic en **Sí** para guardar su configuración.

- Ahora que el modo CAP está habilitado, configure el teléfono usando la pantalla del mismo. La pantalla debería mostrar **CaAP está habilitado**. Luego haga esto:

    1. Haga clic en **Configuración**.
    2. Seleccione **avanzadas**.
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
> El sitio de aprovisionamiento de CAP indica que restablecerá la contraseña de la cuenta CAP a una contraseña aleatoria. Tenga en cuenta que la cuenta a la que hace referencia el CAP es la cuenta de Azure Active Directory (AAD). Solo si creó la cuenta en AAD el proceso es directo. Si sincronizó un Active Directory local con AAD y usa un IDP o ADFS de terceros, se producirá un error de aprovisionamiento CAP. En este caso, solo tiene que usar una cuenta de Office 365/Azure Active Directory (por ejemplo, una cuenta con dominio **onmicrosoft.com** ) para que funcione el aprovisionamiento Cap.


### <a name="related-topics"></a>Temas relacionados

- Obtenga más información sobre teléfonos disponibles en [Implementar teléfonos de Skype Empresarial Online](deploying-skype-for-business-online-phones.md).
- [Obtener teléfonos para Skype Empresarial Online](getting-phones-for-skype-for-business-online.md)


