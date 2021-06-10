---
title: Configurar el área común Teléfono licencia
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

Un teléfono de área común normalmente se coloca en un área como una sala de espera u otra área que está disponible para muchas personas para realizar una llamada; por ejemplo, un área de recepción, una sala de espera o un teléfono de conferencia. Los teléfonos de área común han iniciado sesión con cuentas vinculadas a una licencia de Teléfono común. La directiva teamsIPPhone también debe establecerse correctamente para que el teléfono tenga una experiencia de usuario de área común.

En los pasos siguientes, le ayudaremos a configurar una cuenta para Sistema telefónico para implementar teléfonos de área comunes para su organización. Para una experiencia de sala de reuniones más completa, incluida la audioconferencia, considere la posibilidad de comprar la licencia de Sala de reuniones dedicada con un dispositivo de sala de reuniones. 

En primer lugar, debe comprar una licencia de área Teléfono común (CAP) y asegurarse de que tiene un teléfono certificado. Para buscar y obtener más información sobre teléfonos certificados, ve a [Microsoft Teams dispositivos](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1). 

## <a name="step-1---buy-the-licenses"></a>Paso 1: comprar las licencias

1. En el Microsoft 365 de administración, vaya a Servicios **de**  >  **compra de facturación** y, a continuación, expanda **Otros planes.**

    ![Captura de pantalla que muestra el icono Teléfono área común](media/set-up-common-area-phone-image1.png)

2. Selecciona **Área común Teléfono** Comprar  >  **ahora.**

3. En la página Desprotección, haga clic **en Comprar ahora.**

4. Expanda **Suscripciones de complementos y,** a continuación, haga clic para comprar un plan de llamadas. Elija el Plan **de llamadas nacionales** o el Plan **de llamadas nacionales e internacionales.**

> [!NOTE]
> Si usa Teléfono Microsoft System Direct Routing, no necesita una licencia del Plan de llamadas.

> [!NOTE]
> No es necesario agregar una licencia Sistema telefónico usuario. Está incluida en la licencia del teléfono de área común.

Para obtener más información sobre licencias, [vea Microsoft Teams de complementos.](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)

La licencia de Teléfono común es compatible con: 


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

1. En el Microsoft 365 de administración, vaya a **Usuarios**  >  **usuarios activos** agregar un  >  **usuario.**

2. Escriba un nombre de usuario como "Principal" para el nombre y "Recepción" para el segundo nombre.

3. Escriba un nombre para mostrar si no genera automáticamente uno como "Recepción principal".

4. Escriba un nombre de usuario como "MainReception" o "Mainlobby".

5. Para teléfonos de área común, es posible que desee establecer una contraseña manualmente o tener la misma contraseña para todos los teléfonos de área comunes. Además, es posible que piense en desactivar la casilla Hacer que este **usuario cambie su contraseña** al iniciar sesión por primera vez.

6. Asigne las licencias al usuario. En la misma página, haga clic para expandir las **Licencias de producto**. Active el área común Teléfono y elija un plan de llamadas nacionales o un **plan** de llamadas nacionales **e internacionales.** 

    ![Captura de pantalla que muestra la asignación de licencias](media/set-up-common-area-phone-image2.png)

> [!NOTE]
> Si usa Teléfono Microsoft system direct routing, no es necesario asignar una licencia del Plan de llamadas.

Para obtener más información, vea [Asignar licencias a usuarios.](/microsoft-365/admin/manage/assign-licenses-to-users)

## <a name="step-3---assign-a-phone-number-to-the-common-area-phone-user-account"></a>Paso 3: asignar un número de teléfono a la cuenta de usuario del teléfono de área común

Use el Teams de administración para asignar un número al usuario.

1. En el Teams de administración, seleccione **Números**  >  **de Teléfono voz.**

3.    Seleccione un número de la lista de números de teléfono y haga clic en **Asignar**.

4. En **la** página Asignar, en el cuadro Usuario de voz, escriba el nombre del usuario que va a usar el teléfono y, a continuación, seleccione el usuario en la lista desplegable Seleccionar **un** usuario de voz.

5. A continuación, debe agregar una dirección de emergencia. Elija **Buscar por ciudad,** Buscar  por **descripción** o Buscar por ubicación en la lista desplegable y, a continuación, escriba la ciudad, descripción o ubicación en el cuadro de texto. Una vez que busque, busque en Seleccionar dirección **de emergencia** para elegir la correcta para usted.

6. Haga clic en **Guardar** y el usuario debería tener este aspecto:

   ![Captura de pantalla que muestra la asignación de licencias](media/set-up-common-area-phone-image3.png)

> [!NOTE]
> Los usuarios solo se mostrarán si tienen una licencia Sistema telefónico aplicación. Si acaba de aplicársela, el usuario a veces tarda un poco de tiempo en aparecer en la lista.

Para obtener más información, vea [Obtener números de teléfono para los usuarios.](getting-phone-numbers-for-your-users.md)

También puede tomar el número de teléfono que tiene con otro operador y "portabilidad" o transferirlo a Microsoft 365 o Office 365. Vea [Transferir números de teléfono a Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).