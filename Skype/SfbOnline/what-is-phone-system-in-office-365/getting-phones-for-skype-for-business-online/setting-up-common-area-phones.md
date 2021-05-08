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
f1.keywords:
- NOCSH
ms.custom:
- Phone System
description: Obtenga información sobre los pasos de implementación para obtener el firmware correcto, actualizarlo si es necesario, asignar licencias y configurar la configuración para teléfonos de área común.
ms.openlocfilehash: 4fd45f446d71e581305f7e596c7eacc62f54f8ca
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237356"
---
# <a name="set-up-common-area-phones"></a>Configurar teléfonos de área común

[!INCLUDE [sfbo-retirement](../../../Hub/includes/sfbo-retirement.md)]
Por lo general, un teléfono de área común (CAP) se coloca en un área como un vestíbulo u otra área que está disponible para muchas personas. Por ejemplo, un teléfono del área de recepción, un teléfono de la puerta o un teléfono de la sala de reuniones; los CAP se configuran como dispositivos en lugar de como usuarios y se conectan automáticamente a una red. En los pasos a continuación, le ayudaremos a configurar una cuenta para un sistema telefónico con planes de llamadas, de modo que pueda implementar este tipo de teléfonos en su organización.

## <a name="prerequisites-for-common-area-phones"></a>Requisitos previos de los teléfonos de área común

Lo primero que debe hacer es confirmar que tiene lo siguiente:

- Adquiera una licencia de teléfono de área común y un plan de llamadas.
- Busque y compre teléfonos aprobados (vea la lista [aquí](deploying-skype-for-business-online-phones.md)).
- Actualice el firmware de sus teléfonos (consulte el firmware compatible [en este tema](getting-phones-for-skype-for-business-online.md)).  Puede verificar el firmware en su teléfono haciendo esto:
  - **Teléfonos Polycom VVX:** Vaya **a Configuración** principal de la aplicación  >    >  **plataforma de**  >    >  **estado.**
  - **Teléfonos Yealink:** Ve a **Estado en** la pantalla principal del teléfono.
  - **AudioCodes teléfonos:** Vaya **a** La versión del firmware del estado del dispositivo  >    >  **del menú** desde la pantalla de inicio.
  - **Lync Teléfono Edition (LPE):** Vaya a **Menú**  >  **Información del sistema** desde la pantalla de inicio.

    Las actualizaciones de firmware las administra el servicio de Skype for Business. Todos los firmware de teléfono certificados para Skype for Business se cargan en el servidor de actualización de Skype for Business, y la actualización del dispositivo está habilitada en todos los teléfonos de forma predeterminada.

    En función del tiempo de inactividad del teléfono y de los intervalos de sondeo, los teléfonos descargarán e instalarán automáticamente las últimas compilaciones certificadas. Puede deshabilitar la configuración de actualización del dispositivo usando el cmdlet [Set-CsIPPhonePolicy](/powershell/module/skype/set-csipphonepolicy) y configurando el parámetro *EnableDeviceUpdate* como `false`.

## <a name="setting-up-a-common-area-phone"></a>Configurar un teléfono de área común
Tendrá que seguir estos pasos:

### <a name="step-1---buy-the-licenses"></a>Paso 1: comprar las licencias
1. En el centro de administración, vaya a **Servicios de** compra  >  **de facturación** y agregue Otros **planes.**

    ![Captura de pantalla del área común Teléfono licencia](../../images/cap-license.png)
2. Haga clic en **Teléfono de área común** > **Comprar ahora** > y en la página de **Pago** haga clic en **Compra ahora**.
3. Haga clic para expandir las **Suscripciones de complementos** y luego haga clic para comprar un plan de llamadas. Elija el Plan **de llamadas nacionales** o el Plan **de llamadas nacionales e internacionales.**

> [!Note]
> No necesita una licencia de sistema telefónico. Está incluida en la licencia del **teléfono de área común**.

Para obtener más información sobre licencias, [vea Skype Empresarial y Microsoft Teams de complementos.](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)

### <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a>Paso 2: crear una nueva cuenta de usuario para el teléfono y asignar las licencias
1. En el Centro de administración, vaya **a Usuarios**  >  **usuarios activos** Agregar un  >  **usuario.**
2. Indique un **Nombre de usuario** del estilo de "Principal" para el primer nombre y "Recepción" para el segundo nombre.
3. Indique un **Nombre para mostrar** si no se autogenera uno del estilo de "Recepción principal".
4. Indique un **Nombre de usuario** del estilo de "RecepciónPrincipal" o "VestíbuloPrincipal".
5. Para teléfonos de área común, quizá desee establecer una contraseña manualmente o tener la misma para todos los teléfonos de ese tipo. Además, puede plantearse deseleccionar **Hacer que este usuario cambie su contraseña cuando se conecte por primera vez**.
6. Estando aún allí, asigne las licencias a este usuario. En la misma página, haga clic para expandir las **Licencias de producto**. Active lo siguiente:
   - Teléfono de área común
   - Luego debe elegir un **Plan de llamadas nacionales** o un **Plan de llamadas internacionales** y nacionales.

     La asignación de licencias tendrá este aspecto:

     ![TurnOnCapLicense.png](../../images/cap-license-turn-on.png)

     > [!Note]
     > Para su interés, el Plan 2 de Skype for Business se incluye con la licencia del **teléfono de área común**.

Para más detalles, consulte [Agregar un usuario](https://support.office.com/article/1970f7d6-03b5-442f-b385-5880b9c256ec).

### <a name="step-3---assign-a-phone-number-to-the-common-area-phone-user-account"></a>Paso 3: asignar un número de teléfono a la cuenta de usuario del teléfono de área común

![Icono que muestra el logotipo Skype Empresarial asignar un número de teléfono al usuario con el ](../../images/sfb-logo-30x30.png) **centro Skype Empresarial administración**

1. En el centro de administración > **centros de administración**  >  **Skype Empresarial**.
2. En el **centro de administración de Skype for Business** >  **Voz** > **Números de teléfono**.
3. Seleccione un número de la lista de números de teléfono y haga clic en **Asignar**.
4. En la página **Asignar**, en el cuadro **Usuario de voz** indique el nombre del usuario que se utiliza para el teléfono y luego seleccione el usuario en el desplegable **Seleccionar un usuario de voz**.
5. Allí deberá agregar también una dirección de emergencia. Tras hacer la búsqueda, revise **Seleccionar dirección de emergencia** para elegir la correcta en su caso.
6. Haga clic en **Guardar** y el usuario debería tener este aspecto:

    ![Captura de pantalla del número de teléfono del usuario](../../images/cap-user-number.png)

   > [!Note]
   > Los usuarios solo aparecerán si tienen aplicada una licencia de **sistema telefónico**. Si acaba de aplicársela, el usuario a veces tarda un poco de tiempo en aparecer en la lista.

Para más información, consulte [Obtener números de teléfono para los usuarios](/microsoftteams/getting-phone-numbers-for-your-users).

Si se lo pregunta, también puede llevar el número deteléfono que tiene con otro operador y "portabilidad" o transferirlo a Microsoft 365 o Office 365. Vea Transferir [números de teléfono a Teams](/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams).

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
    2. Seleccione **Avanzadas**.
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
> El sitio de aprovisionamiento de CAP indica que restablecerá la contraseña de la cuenta CAP a una contraseña aleatoria. Tenga en cuenta que la cuenta a la que hace referencia el CAP es la cuenta de Azure Active Directory (AAD). Solo si creó la cuenta en AAD el proceso es directo. Si ha sincronizado un Active Directory local con AAD y usa un IDP o ADFS de terceros, se producirá un error en el aprovisionamiento de CAP. En este caso, debe usar una cuenta Microsoft 365 o Office 365/Azure Active Directory solo (por ejemplo, una cuenta con un dominio onmicrosoft.com) para que funcione el **aprovisionamiento** de CAP.


### <a name="related-topics"></a>Temas relacionados

- Obtenga más información sobre teléfonos disponibles en [Implementar teléfonos de Skype Empresarial Online](deploying-skype-for-business-online-phones.md).
- [Obtener teléfonos para Skype Empresarial Online](getting-phones-for-skype-for-business-online.md)
