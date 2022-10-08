---
title: Configurar Teléfono Microsoft Teams sistema con números de teléfono del plan de llamadas
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
description: Obtenga información sobre cómo configurar Teléfono Microsoft Teams Sistema con números de teléfono de plan de llamadas para los usuarios y servicios de su organización.
appliesto:
- Microsoft Teams
ms.collection:
- M365-voice
- M365initiative-voice
ms.openlocfilehash: 9052fc0902c069e1ef097810a58f4adcbbae6174
ms.sourcegitcommit: fc87f4300f53abf7a049936944abb21d0cade0d9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/06/2022
ms.locfileid: "68480870"
---
# <a name="step-2-set-up-teams-phone-system-phone-numbers"></a>Paso 2: Configurar los números de teléfono del sistema telefónico de Teams

Para poder configurar usuarios o operadores automáticos en su organización, debe obtener números de teléfono para ellos. Hay varios tipos diferentes de números de teléfono, pero los siguientes son los dos tipos de números que debe agregar en este paso:

- **Números de servicio** Estos números se usan para operadores automáticos, audioconferencias y colas de llamadas. Pueden ser números de pago o gratuitos y administrar grandes cantidades de llamadas al mismo tiempo. El número de teléfono de su empresa debe ser un número de servicio, ya que se asignará a un operador automático en un paso posterior.
- **Números de suscriptor** Estos números se usan para los usuarios habituales para que puedan realizar y recibir llamadas telefónicas.

> [!IMPORTANT]
> Incluso si desea usar los números de teléfono existentes, debe crear y asignar números de teléfono temporales a la línea telefónica principal de su empresa y a los usuarios. Podrá reemplazar estos números temporales por los números de teléfono existentes en un paso posterior.

> [!NOTE]
> Los números de teléfono nuevos pueden tardar varias horas en estar disponibles en Teams.

## <a name="set-up-a-service-number"></a>Configurar un número de servicio

El número de servicio que configure ahora se usará en un paso posterior para el número de teléfono principal de su empresa.

1. Abra el Centro de administración de Microsoft Teams e inicie sesión con un usuario que sea administrador global (suele ser la cuenta que usó para registrarse en Microsoft 365).
2. En el panel de navegación izquierdo, vaya a <a href="https://admin.teams.microsoft.com/phone-numbers" target="_blank">**Números de teléfono** **de voz** > </a> y haga clic en **Agregar**.
3. Escriba un nombre para el pedido y agregue una descripción.
4. En la página Ubicación y cantidad, haga lo siguiente:
    1. En **País o región**, selecciona un país o región.
    2. En **Tipo de número**, seleccione una de las siguientes opciones:

        - **Operador automático (pago)** Número de teléfono normal, no gratuito. El autor de la llamada cobra tarifas de larga distancia.
        - **Operador automático (gratuito)** Número de teléfono gratuito (EE. UU. y Canadá) o teléfono gratuito (Reino Unido). Los gastos de larga distancia se cobran a su empresa. Antes de poder seleccionar esta opción, debes comprar créditos de comunicación. Para obtener más información, consulte [¿Qué necesito comprar para obtener capacidades de voz para mi pequeña o mediana empresa?](whats-business-voice.md).

    3. En **Cantidad**, selecciona **1**.
        > [!NOTE]
        > Si recibe el mensaje **No tiene suficientes licencias para solicitar más números de este tipo**, asegúrese de que ha comprado Teams Phone con licencias de paquetes del plan de llamadas. Para obtener más información, consulte [¿Qué necesito comprar para obtener capacidades de voz para mi pequeña o mediana empresa?](whats-business-voice.md).
    4. Elija **Ubicación** o **Código de área**, dependiendo de si desea buscar números de teléfono con la ciudad de una ubicación o si desea buscar números en un código de área específico.
    5. Si selecciona **Ubicación**:

        1. Escriba la ciudad en la que se encuentra la dirección de emergencia en el paso [Configurar ubicaciones de emergencia](set-up-emergency-locations.md) o, si necesita crear una nueva ubicación para otra oficina u oficina doméstica, haga clic en **Agregar una ubicación**.
        2. En **Código de área**, selecciona un código de área y, a continuación, selecciona **Siguiente** para reservar tu número.

    6. Si selecciona **Código de área**, escriba el código de área que desea buscar y, a continuación, seleccione **Siguiente** para reservar su número.

5. Seleccione el número que desee. Tienes 10 minutos para seleccionar tu número de teléfono y realizar el pedido. Si tarda más de 10 minutos, el número de teléfono se devolverá al grupo de números.
6. Cuando estés listo para realizar el pedido, haz clic en **Realizar pedido** y, a continuación, **en Finalizar**

## <a name="set-up-phone-numbers-for-your-users"></a>Configurar números de teléfono para los usuarios

1. Abra el Centro de administración de Microsoft Teams e inicie sesión con un usuario que sea administrador global. Esta suele ser la cuenta que usaste para registrarte en Microsoft 365.
2. En el panel de navegación izquierdo, vaya a <a href="https://admin.teams.microsoft.com/phone-numbers" target="_blank">**Números de teléfono** **de voz** > </a> y haga clic en **Agregar**.
3. Escriba un nombre para el pedido y agregue una descripción.
4. En la página Ubicación y cantidad, haga lo siguiente:

    1. En **País o región**, selecciona un país o región.
    2. En **Tipo de número**, seleccione **Usuario (suscriptor).**.
    3. En **Cantidad**, escriba el número de números que desea para su organización.
    4. Elija **Ubicación** o **Código de área**, dependiendo de si desea buscar números de teléfono con la ciudad de una ubicación o si desea buscar números en un código de área específico.
    5. Si selecciona **Ubicación**:

        1. Escriba la ciudad en la que se encuentra la dirección de emergencia en el paso [Configurar ubicaciones de emergencia](set-up-emergency-locations.md) o, si necesita crear una nueva ubicación para otra oficina u oficina doméstica, haga clic en **Agregar una ubicación**.
        2. En **Código de área**, selecciona un código de área y, a continuación, selecciona **Siguiente** para reservar tu número.

    6. Si selecciona **Código de área**, escriba el código de área que desea buscar y, a continuación, seleccione **Siguiente** para reservar su número.
5. Seleccione los números que desee. Tienes 10 minutos para seleccionar tus números de teléfono y realizar el pedido. Si tarda más de 10 minutos, los números de teléfono se devolverán al grupo de números.
6. Cuando esté listo para realizar el pedido, haga clic en **Realizar pedido** y, a continuación, **en Finalizar**.

> [!div class="nextstepaction"]
> [Siguiente paso: Asignar licencias a usuarios de Teams](set-up-licenses.md)
