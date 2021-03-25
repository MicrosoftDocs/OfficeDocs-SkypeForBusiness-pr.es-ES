---
title: Configurar la licencia de Teléfono de área común
ms.author: serdars
author: SerdarSoysal
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
description: 'Obtenga información sobre cómo configurar teléfonos de área común para lobbies, áreas de recepción y salas de conferencias '
ms.openlocfilehash: bb17b21eac262c160abc3e16a4b552fb32b97d00
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117118"
---
# <a name="set-up-the-common-area-phone-license-for-microsoft-teams"></a>Configuración de la licencia de teléfono de área común de Microsoft Teams
> [!NOTE]
> Los teléfonos de área común no admiten correo de voz.

Un teléfono de área común normalmente se coloca en un área como una sala de espera u otra área que está disponible para muchas personas para realizar una llamada; por ejemplo, un área de recepción, una sala de espera o un teléfono de conferencia. Los teléfonos de área común se han iniciado sesión con cuentas vinculadas a una licencia de teléfono de área común. La directiva teamsIPPhone también debe establecerse correctamente para que el teléfono tenga una experiencia de usuario de área común.

En los pasos siguientes, le ayudaremos a configurar una cuenta de Sistema telefónico para implementar teléfonos de área comunes para su organización. Para obtener una experiencia más completa de la sala de reuniones, incluidas las audioconferencias, considere la posibilidad de comprar la licencia dedicada de la sala de reuniones con un dispositivo de sala de reuniones. 

En primer lugar, debe comprar una licencia de Teléfono de área común (CAP) y asegurarse de que tiene un teléfono certificado. Para buscar y obtener más información sobre teléfonos certificados, vaya a [Dispositivos de Microsoft Teams.](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1) 

## <a name="step-1---buy-the-licenses"></a>Paso 1: comprar las licencias

1. En el Centro de administración de Microsoft 365, vaya a Servicios **de** compra de  >  **facturación** y, a continuación, expanda **Otros planes.**

    ![Captura de pantalla que muestra el icono Teléfono de área común](media/set-up-common-area-phone-image1.png)

2. Selecciona **Comprar teléfono de área** común  >  **ahora.**

3. En la página Desprotección, haga clic **en Comprar ahora.**

4. Expanda **Suscripciones de complementos y,** a continuación, haga clic para comprar un plan de llamadas. Elija el Plan **de llamadas nacionales** o el Plan **de llamadas nacionales e internacionales.**

> [!NOTE]
> Si usa Enrutamiento directo de Microsoft Phone System, no necesita una licencia del Plan de llamadas.

> [!NOTE]
> No es necesario agregar una licencia del sistema telefónico. Está incluida en la licencia del teléfono de área común.

Para obtener más información sobre licencias, vea [Licencias de complementos de Microsoft Teams.](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)

La licencia de Teléfono de área común es compatible con: 


|   |  Teléfono de área común  |
|---------|---------|
|Skype Empresarial |   &#x2714; |
|Microsoft Teams |   &#x2714; |
|Sistema telefónico |    &#x2714; |
|Audioconferencia |       &#x2718; &sup1;  |
|Microsoft Intune |    &#x2718; |
|Disponibilidad mundial |       &#x2718; &sup2;  |
|Disponibilidad del canal |    EA, EAS, CSP, GCC, EES, Web Direct  |
|      |         |

&sup1; Los teléfonos de área común pueden unirse a conferencias de audio a través del número de acceso telefónico proporcionado por el organizador de la reunión

&sup2; No disponible en nubes soberanas  



## <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a>Paso 2: crear una nueva cuenta de usuario para el teléfono y asignar las licencias

1. En el Centro de administración de Microsoft 365, vaya a **Usuarios**  >  **usuarios activos** agregar un  >  **usuario.**

2. Escriba un nombre de usuario como "Principal" para el nombre y "Recepción" para el segundo nombre.

3. Escriba un nombre para mostrar si no genera automáticamente uno como "Recepción principal".

4. Escriba un nombre de usuario como "MainReception" o "Mainlobby".

5. Para teléfonos de área común, es posible que desee establecer una contraseña manualmente o tener la misma contraseña para todos los teléfonos de área comunes. Además, es posible que piense en desactivar la casilla Hacer que este **usuario cambie su contraseña** al iniciar sesión por primera vez.

6. Asigne las licencias al usuario. En la misma página, haga clic para expandir las **Licencias de producto**. Activa el teléfono de área común y elige un **plan de llamadas** nacionales o un plan de llamadas **nacionales e internacionales.** 

    ![Captura de pantalla que muestra la asignación de licencias](media/set-up-common-area-phone-image2.png)

> [!NOTE]
> Si usa Enrutamiento directo de Microsoft Phone System, no es necesario asignar una licencia del Plan de llamadas.

Para obtener más información, vea [Asignar licencias a usuarios.](/microsoft-365/admin/manage/assign-licenses-to-users)

## <a name="step-3---assign-a-phone-number-to-the-common-area-phone-user-account"></a>Paso 3: asignar un número de teléfono a la cuenta de usuario del teléfono de área común

Use el Centro de administración de Teams para asignar un número al usuario.

1. En el Centro de administración de Teams, seleccione **Números de teléfono** de  >  **voz.**

3.    Seleccione un número de la lista de números de teléfono y haga clic en **Asignar**.

4. En **la** página Asignar, en el cuadro Usuario de voz, escriba el nombre del usuario que va a usar el teléfono y, a continuación, seleccione el usuario en la lista desplegable Seleccionar **un** usuario de voz.

5. A continuación, debe agregar una dirección de emergencia. Elija **Buscar por ciudad,** Buscar  por **descripción** o Buscar por ubicación en la lista desplegable y, a continuación, escriba la ciudad, descripción o ubicación en el cuadro de texto. Una vez que busque, busque en Seleccionar dirección **de emergencia** para elegir la correcta para usted.

6. Haga clic en **Guardar** y el usuario debería tener este aspecto:

   ![Captura de pantalla que muestra la asignación de licencias](media/set-up-common-area-phone-image3.png)

> [!NOTE]
> Los usuarios solo se mostrarán si tienen una licencia de Sistema telefónico aplicada. Si acaba de aplicársela, el usuario a veces tarda un poco de tiempo en aparecer en la lista.

Para obtener más información, vea [Obtener números de teléfono para los usuarios.](getting-phone-numbers-for-your-users.md)

También puede llevar el número de teléfono que tiene con otro operador y "portabilidad" o transferirlo a Microsoft 365 u Office 365. Vea [Transferir números de teléfono a Teams.](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)