---
title: Configuración de la licencia de teléfono de área común de Microsoft Teams
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.date: 12/13/2018
ms.reviewer: kponnus
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- M365-voice
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: 'Obtenga información sobre cómo configurar los teléfonos de área común para salas de espera, áreas de recepción y salas de conferencias '
ms.openlocfilehash: 9e68d5bc4ef0355e80e1fe6359385c10a339c0fe
ms.sourcegitcommit: cf2cb5b7e03385b33e34a5ff89719adb882525b1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2019
ms.locfileid: "33632380"
---
# <a name="set-up-the-common-area-phone-license-for-microsoft-teams"></a>Configuración de la licencia de teléfono de área común de Microsoft Teams

Un teléfono de área común normalmente se coloca en un área como una sala de espera o a otra área que se encuentra disponible a varias personas para realizar una llamada; Por ejemplo, una recepción área, sala de espera o conferencia telefónica. Teléfonos de área común se configuran como dispositivos en lugar de los usuarios y pueden iniciar sesión automáticamente en una red.

En los pasos siguientes, le ayudaremos a configurar una cuenta para el sistema telefónico implementar teléfonos de área común para su organización. Para una sala de reuniones más completa experiencia, incluyendo conferencias de audio, considere la posibilidad de adquirir la licencia de sala de reuniones dedicada con una reunión de dispositivo de sala. 

Las primeras cosas que debe hacer son compra una licencia de teléfono de área común (CAP) y asegúrese de que tiene un teléfono certificado. Para buscar y obtener más información sobre certificados teléfonos, vaya a [los dispositivos de los equipos de Microsoft](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1). 

## <a name="step-1---buy-the-licenses"></a>Paso 1: comprar las licencias

1. En el centro de administración de Microsoft 365, vaya a **facturación** > **Servicios de compra** y, a continuación, expanda **otros planes**.

    ![Captura de pantalla que muestra el icono de teléfono de área común](media/set-up-common-area-phone-image1.png)

2. Seleccione **teléfono de área común** > **comprar ahora**.

3. En la página de **finalización de compra** , haga clic en **comprar ahora**.

4. Expanda **las suscripciones del complemento** y, a continuación, haga clic en para adquirir un Plan de llamada. Elija la **nacionales llamar al Plan** o la **planeación de la llamada nacional e internacional**.

> [!NOTE]
> No necesita una licencia de sistema telefónico. Está incluida en la licencia del teléfono de área común.

Para obtener más información sobre las licencias, vea [licencias de complemento de equipos de Microsoft](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).

## <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a>Paso 2: crear una nueva cuenta de usuario para el teléfono y asignar las licencias

1. En el centro de administración de Microsoft 365, vaya a **los usuarios** > **usuarios activos** > **Agregar un usuario**.

2. Escriba un nombre de usuario como "Main" para el nombre y el "Recepción" para el segundo nombre.

3. Escriba un nombre para mostrar si no es así generar automáticamente como "Main recepción".

4. Escriba un nombre de usuario, como "MainReception" o "Mainlobby".

5. Para teléfonos de área común, es posible que desee establecer una contraseña manualmente o tener la misma contraseña para todos los teléfonos de área común. Además, es posible que piense desactivando la casilla de verificación **hacer que este usuario cambiar su contraseña cuando inician sesión por primera vez en** .

6. Asignar las licencias al usuario. En la misma página, haga clic para expandir las **Licencias de producto**. Encienda el teléfono de área común y seleccionar un **Llamar a planear nacionales** o un **nacionales y llamar a planear internacional**. 

    ![Asignación de licencias de captura de pantalla que muestra](media/set-up-common-area-phone-image2.png)

Para obtener más información, vea [Agregar un usuario](https://docs.microsoft.com/office365/admin/add-users/add-users?redirectSourcePath=%252farticle%252f1970f7d6-03b5-442f-b385-5880b9c256ec&view=o365-worldwide).

## <a name="step-3---assign-a-phone-number-to-the-common-area-phone-user-account"></a>Paso 3: asignar un número de teléfono a la cuenta de usuario del teléfono de área común

Use el Skype para el centro de administración de negocio para asignar a un número al usuario.

1. En el centro de administración de Microsoft 365, seleccione **centros de administración** > **& equipos Skype** > **portal heredado**.

2. En Skype para el centro de administración de negocio, seleccione **voz** > **los números de teléfono**.

3.  Seleccione un número de la lista de números de teléfono y haga clic en **Asignar**.

4. En la página **asignar** , en el cuadro de usuario de voz, escriba el nombre del usuario que va a utilizar el teléfono y, a continuación, seleccione el usuario en la lista desplegable **Seleccione un usuario de voz** .

5. Allí deberá agregar también una dirección de emergencia. Elija **Buscar por ciudad**, **Buscar por descripción**o **Buscar por ubicación** de la lista desplegable y, a continuación, escriba la ciudad, la descripción o la ubicación en el cuadro de texto. Una vez que buscar, mire en **Seleccione emergencia dirección** para elegir el adecuado para usted.

6. Haga clic en **Guardar** y el usuario debería tener este aspecto:

   ![Asignación de licencias de captura de pantalla que muestra](media/set-up-common-area-phone-image3.png)

> [!NOTE]
> Los usuarios sólo aparecerá si cuentan con una licencia de sistema telefónico aplicada. Si acaba de aplicársela, el usuario a veces tarda un poco de tiempo en aparecer en la lista.

Para obtener más información, vea la [Introducción de los números de teléfono para los usuarios](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/getting-phone-numbers-for-your-users).

También puede tomarse su número de teléfono que tiene con otro operador y "puerto" o transferir a través de Office 365. Consulte [transferir los números de teléfono para Office 365](transfer-phone-numbers-to-office-365.md).


