---
title: Configurar teléfonos de área común
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: wasseemh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
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
description: Conozca los pasos de implementación para obtener el firmware correcto, actualizarlo si es necesario, asignar licencias y configurar ajustes para teléfonos de área común.
ms.openlocfilehash: 25605e7538792080213eebb898e612be6ce5bfab
ms.sourcegitcommit: bdf9946b7c65ef7985d6b03a1479ea3a5c17a304
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/23/2018
ms.locfileid: "19426805"
---
# <a name="set-up-common-area-phones"></a>Configurar teléfonos de área común
Por lo general, un teléfono de área común (CAP) se coloca en un área como un vestíbulo u otra área que está disponible para muchas personas. Por ejemplo, un teléfono del área de recepción, un teléfono de la puerta o un teléfono de la sala de reuniones; los CAP se configuran como dispositivos en lugar de como usuarios y se conectan automáticamente a una red. En los pasos a continuación, le ayudaremos a configurar una cuenta para un sistema telefónico con planes de llamadas, de modo que pueda implementar este tipo de teléfonos en su organización.

## <a name="prerequisites-for-common-area-phones"></a>Requisitos previos de los teléfonos de área común

Lo primero que debe hacer es confirmar que tiene lo siguiente:

 - Adquiera una licencia de teléfono de área común y un plan de llamadas.
 - Busque y compre teléfonos aprobados (vea la lista [aquí](deploying-skype-for-business-online-phones.md)).         
 - Actualice el firmware de sus teléfonos (consulte el firmware compatible [en este tema](getting-phones-for-skype-for-business-online.md)).  Puede verificar el firmware en su teléfono haciendo esto:       
    - **Teléfonos Polycom VVX**: entre en **Configuración** > **Estado** > **Plataforma** > **Aplicación** > **Principal**.
    - **Teléfonos Yealink**: entre en **Estado** en la pantalla principal del teléfono.
    - **Teléfonos AudioCodes**: estando en la pantalla de inicio, entre en **Menú** > **Estado del dispositivo** > **Versión de firmware**. 
    - **Teléfonos Lync Phone Edition (LPE)**: estando en la pantalla de inicio, entre en **Menú** > **Información del sistema**.

    Las actualizaciones de firmware las administra el servicio de Skype for Business. Todos los firmware de teléfono certificados para Skype for Business se cargan en el servidor de actualización de Skype for Business, y la actualización del dispositivo está habilitada en todos los teléfonos de forma predeterminada. 

    En función del tiempo de inactividad del teléfono y de los intervalos de sondeo, los teléfonos descargarán e instalarán automáticamente las últimas compilaciones certificadas. Puede deshabilitar la configuración de actualización del dispositivo usando el cmdlet [Set-CsIPPhonePolicy](https://docs.microsoft.com/powershell/module/skype/set-csipphonepolicy) y configurando el parámetro *EnableDeviceUpdate* como `false`.

## <a name="setting-up-a-common-area-phone"></a>Configurar un teléfono de área común
Tendrá que seguir estos pasos:

### <a name="step-1---buy-the-licenses"></a>Paso 1: comprar las licencias
1. En el centro de administración de Office 365, entre en **Facturación** > **Servicios de compra**, y agregue **Otros planes**.

    ![CAP-license.png](../../images/cap-license.png)
2. Haga clic en **Teléfono de área común** > **Comprar ahora** > y en la página de **Pago** haga clic en **Compra ahora**.
3. Haga clic para expandir las **Suscripciones de complementos** y luego haga clic para comprar un plan de llamadas. Elija el **Plan de llamadas nacionales** o el **Plan de llamadas nacionales e internacionales**.

> [!Note]
> No necesita una licencia de sistema telefónico. Está incluida en la licencia del **teléfono de área común**.

Para obtener más información sobre las licencias, consulte [Licencias de complementos de Skype for Business y Microsoft Teams](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).

### <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a>Paso 2: crear una nueva cuenta de usuario para el teléfono y asignar las licencias
1. En el centro de administración de Office 365, entre en **Usuarios** > **Usuarios activos** > **Agregar un usuario**.
2. Indique un **Nombre de usuario** del estilo de "Principal" para el primer nombre y "Recepción" para el segundo nombre.
3. Indique un **Nombre para mostrar** si no se autogenera uno del estilo de "Recepción principal".
4. Indique un **Nombre de usuario** del estilo de "RecepciónPrincipal" o "VestíbuloPrincipal".
5. Para teléfonos de área común, quizá desee establecer una contraseña manualmente o tener la misma para todos los teléfonos de ese tipo. Además, puede plantearse deseleccionar **Hacer que este usuario cambie su contraseña cuando se conecte por primera vez**.

    > [!Tip]
    > ¡ESPERE! ¡No haga clic en **Agregar**! Uf, si ya ha hecho clic en **Agregar** haga esto: entre en el centro de administración de Office 365> **Usuarios** > **Usuarios activos** y luego encuentre al usuario. Después, en la página de propiedades del usuario, haga clic en **Licencias de producto** y después haga clic en **Editar**. En la página de **Licencias de producto**, active **Teléfono de área común** y elija un **Plan de llamadas nacionales** o un **Plan de llamadas internacionales** y nacionales.

6. Estando aún allí, asigne las licencias a este usuario. En la misma página, haga clic para expandir las **Licencias de producto**. Active lo siguiente:
    - Teléfono de área común
    - Luego debe elegir un **Plan de llamadas nacionales** o un **Plan de llamadas internacionales** y nacionales.
     
    La asignación de licencias tendrá este aspecto:

    ![TurnOnCapLicense.png](../../images/cap-license-turn-on.png)

    > [!Note]
    > Para su interés, el Plan 2 de Skype for Business se incluye con la licencia del **teléfono de área común**.

Para más detalles, consulte [Agregar un usuario](https://support.office.com/article/1970f7d6-03b5-442f-b385-5880b9c256ec).

### <a name="step-3---assign-a-phone-number-to-the-common-area-phone-user-account"></a>Paso 3: asignar un número de teléfono a la cuenta de usuario del teléfono de área común

![sfb-logo-30x30.png](../../images/sfb-logo-30x30.png) Asignar un número de teléfono al usuario mediante el **centro de administración de Skype for Business**

1. En el centro de administración de Office 365, entre en > **Centros de administración** > **Skype for Business**.
2. En el **centro de administración de Skype for Business** >  **Voz** > **Números de teléfono**.
3. Seleccione un número de la lista de números de teléfono y haga clic en **Asignar**.
4. En la página **Asignar**, en el cuadro **Usuario de voz** indique el nombre del usuario que se utiliza para el teléfono y luego seleccione el usuario en el desplegable **Seleccionar un usuario de voz**. 
5. Allí deberá agregar también una dirección de emergencia. Tras hacer la búsqueda, revise **Seleccionar dirección de emergencia** para elegir la correcta en su caso.
6. Haga clic en **Guardar** y el usuario debería tener este aspecto:

    ![cap-user-number.png](../../images/cap-user-number.png)

   > [!Note]
   > Los usuarios solo aparecerán si tienen aplicada una licencia de **sistema telefónico**. Si acaba de aplicársela, el usuario a veces tarda un poco de tiempo en aparecer en la lista.

Para más información, consulte [Obtener números de teléfono para los usuarios](../../what-are-calling-plans-in-office-365/getting-phone-numbers-for-your-users.md).

Por si se lo está preguntando, también puede coger el número de teléfono que tenga con otra compañía y "*pasarlo*" o transferirlo a Office 365. Consulte, [Transferir números de teléfono a Office 365](../../what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md).

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
    2. Seleccione **Avanzado**.
    3. Escriba la contraseña.
    4. En **Configuración de administración**, seleccione **Configuración del teléfono de área común**.
    5. Habilite **CAP** y **Modo de administración CAP**.
    6. Haga clic en **Guardar configuración**.

- Bien, ahora su teléfono está listo para que pueda conectarse en la pantalla de inicio.

    1. Conéctese seleccionando **Configuración** > **Características** > **Skype for Business.**
    2. Seleccione **Credenciales de usuario** y luego **conexión web (CAP)** para generar un código.
    3. Entre en el [portal de aprovisionamiento](http://aka.ms/skypecap) y conéctese como **administrador**.
    4. Escriba el nombre para mostrar (por ejemplo, Recepción principal).

       > [!Note]
       > Si está marcado **Buscar solo teléfonos de área común**, desactive la casilla de verificación y busque de nuevo.

    5. En la ventana del código de vinculación, escriba el código que se muestra en el teléfono y haga clic en **Aprovisionar**.

        Tras este último paso, el teléfono debería conectarse automáticamente.

### <a name="related-topics"></a>Temas relacionados

- Vea más información sobre teléfonos disponibles en [Implementar teléfonos de Skype for Business Online](deploying-skype-for-business-online-phones.md).
- [Obtener teléfonos con Skype Empresarial Online](getting-phones-for-skype-for-business-online.md)


