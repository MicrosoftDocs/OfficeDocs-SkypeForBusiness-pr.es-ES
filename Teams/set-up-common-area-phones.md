---
title: Configurar la licencia telefónica de área común
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
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
- seo-marvel-mar2020
description: 'Más información sobre cómo configurar teléfonos de área común para salas, áreas de recepción y salas de conferencias '
ms.openlocfilehash: da44a7d66cdc0810405711719f4545caf64007a7
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/03/2020
ms.locfileid: "43140873"
---
# <a name="set-up-the-common-area-phone-license-for-microsoft-teams"></a>Configuración de la licencia de teléfono de área común de Microsoft Teams
> [!NOTE]
> Los teléfonos de área común no admiten el buzón de voz.

Un teléfono de área común suele colocarse en un área como una sala de recepción u otra área que está disponible para muchas personas para hacer una llamada; por ejemplo, un área de recepción, una sala de recepción o un teléfono de conferencia. Los teléfonos de área común se configuran como dispositivos en lugar de usuarios y pueden iniciar sesión automáticamente en una red.

En los pasos siguientes, le ayudaremos a configurar una cuenta para el sistema telefónico para implementar teléfonos de área común para su organización. Para obtener una experiencia de sala de reuniones más completa, incluidas las conferencias de audio, considere la posibilidad de comprar la licencia de sala de reuniones dedicada con un dispositivo de sala de reuniones. 

En primer lugar, debe comprar una licencia de teléfono de área común (CAP) y asegurarse de que tiene un teléfono certificado. Para buscar y obtener más información sobre teléfonos certificados, vaya a [dispositivos de Microsoft Teams](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1). 

## <a name="step-1---buy-the-licenses"></a>Paso 1: comprar las licencias

1. En el centro de administración de Microsoft 365, vaya a**servicios de compra** de **facturación** > y, a continuación, expanda **otros planes**.

    ![Captura de pantalla que muestra el icono de teléfono de área común](media/set-up-common-area-phone-image1.png)

2. Seleccione el **teléfono** > de área común**comprar ahora**.

3. En la página Desproteger, haga clic en **comprar ahora**.

4. Expanda **suscripciones de complementos** y, a continuación, haga clic para comprar un plan de llamadas. Elige el **plan de llamadas nacionales** o el **plan de llamadas nacionales e internacionales**.

> [!NOTE]
> Si está usando el enrutamiento directo de Microsoft Phone System, no necesita una licencia de plan de llamadas.

> [!NOTE]
> No es necesario agregar una licencia de sistema telefónico. Está incluida en la licencia del teléfono de área común.

Para obtener más información sobre las licencias, vea [licencias complementarias de Microsoft Teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).

La licencia de telefonía por área común admite: 


|   |  Teléfono de área común  |
|---------|---------|
|Skype Empresarial |   &#x2714; |
|Microsoft Teams |   &#x2714; |
|Sistemas telefónicos |    &#x2714; |
|Audioconferencia |       &#x2718; &Sup1;  |
|Microsoft Intune |        &#x2718; &sup2; |
|Disponibilidad en todo el mundo |    &#x2714; |
|Disponibilidad del canal |    EA, EAS, CSP, GCC, EES, Web Direct  |
|      |         |

&Sup1; Los teléfonos de área común pueden unirse a conferencias de audio a través del número de acceso telefónico proporcionado por el organizador de la reunión

&sup2; No disponible en nubes soberanos  



## <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a>Paso 2: crear una nueva cuenta de usuario para el teléfono y asignar las licencias

1. En el centro de administración de Microsoft 365, **vaya a** > usuarios**activos** > ,**Agregar un usuario**.

2. Escriba un nombre de usuario como "Main" para el nombre y "recepción" para el segundo nombre.

3. Escriba un nombre para mostrar si no genera automáticamente una "recepción principal".

4. Escriba un nombre de usuario como "MainReception" o "Mainlobby".

5. Para teléfonos de área común, es posible que desee establecer una contraseña de forma manual o tener la misma contraseña para todos los teléfonos de área común. Además, es posible que piense desactivando la casilla de verificación **hacer que este usuario cambie la contraseña la primera vez que inicie sesión** .

6. Asigne las licencias al usuario. En la misma página, haga clic para expandir las **Licencias de producto**. Enciende el teléfono de área común y elige un plan de **llamadas nacionales** o un **plan de llamadas nacionales e internacionales**. 

    ![Captura de pantalla que muestra la asignación de licencias](media/set-up-common-area-phone-image2.png)

> [!NOTE]
> Si está usando el enrutamiento directo de Microsoft Phone System, no es necesario que asigne una licencia de plan de llamadas.

Para obtener más información, vea [Agregar un usuario](https://docs.microsoft.com/office365/admin/add-users/add-users?redirectSourcePath=%252farticle%252f1970f7d6-03b5-442f-b385-5880b9c256ec&view=o365-worldwide).

## <a name="step-3---assign-a-phone-number-to-the-common-area-phone-user-account"></a>Paso 3: asignar un número de teléfono a la cuenta de usuario del teléfono de área común

Use el centro de administración de Teams para asignar un número al usuario.

1. En el centro de administración de Teams, seleccione**números de teléfono**de **voz** > .

3.    Seleccione un número de la lista de números de teléfono y haga clic en **Asignar**.

4. En la página **asignar** , en el cuadro usuario de voz, escriba el nombre del usuario que va a usar el teléfono y, a continuación, seleccione el usuario en la lista desplegable **seleccionar un usuario de voz** .

5. A continuación, debe agregar una dirección de emergencia. Elija **Buscar por ciudad**, **Buscar por Descripción**o **Buscar por ubicación** en la lista desplegable y, a continuación, escriba la ciudad, la descripción o la ubicación en el cuadro de texto. Una vez que haya buscado, mire en **seleccionar dirección de emergencia** para elegir el adecuado para usted.

6. Haga clic en **Guardar** y el usuario debería tener este aspecto:

   ![Captura de pantalla que muestra la asignación de licencias](media/set-up-common-area-phone-image3.png)

> [!NOTE]
> Los usuarios solo aparecerán si tienen una licencia de sistema telefónico aplicada. Si acaba de aplicársela, el usuario a veces tarda un poco de tiempo en aparecer en la lista.

Para obtener más información, vea [obtener números de teléfono para los usuarios](getting-phone-numbers-for-your-users.md).

También puede tomar su número de teléfono con otro operador y "puerto" o transferirlo a Office 365. Consulte [transferir números de teléfono a teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).


