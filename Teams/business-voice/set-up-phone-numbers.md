---
title: Configurar Microsoft 365 Business Voice de teléfono
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: Obtenga información sobre cómo configurar Microsoft 365 Business Voice de teléfono para los usuarios y servicios de su organización.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6cec0bc8e55ef6be169de1f48a375ab40ca8ccf7
ms.sourcegitcommit: 49cdcf344c63c805bcb6365804c6f5d1393e926a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2021
ms.locfileid: "52130120"
---
# <a name="step-2-set-up-business-voice-phone-numbers"></a>Paso 2: Configurar números de teléfono de Business Voice

Para poder configurar usuarios o operadores automáticos en su organización, debe obtener números de teléfono para ellos. Hay varios tipos diferentes de números de teléfono, pero los siguientes son los dos tipos de números que necesita agregar en este paso:

- **Números de servicio** Estos números se usan para operadores automáticos, audioconferencias y colas de llamadas. Pueden ser números gratuitos o de pago y pueden atender grandes cantidades de llamadas al mismo tiempo. El número de teléfono de su empresa debe ser un número de servicio porque se asignará a un operador automático en un paso posterior.
- **Números de suscriptor** Estos números se usan para los usuarios normales para que puedan realizar y recibir llamadas telefónicas.

> [!IMPORTANT]
> Incluso si desea usar los números de teléfono existentes, debe crear y asignar números de teléfono temporales a la línea telefónica principal de su empresa y a sus usuarios. Podrá reemplazar estos números temporales por los números de teléfono existentes en un paso posterior.

> [!NOTE]
> Los nuevos números de teléfono pueden tardar varias horas en estar disponibles en Teams.

## <a name="set-up-a-service-number"></a>Configurar un número de servicio

El número de servicio que configure ahora se usará en un paso posterior para el número de teléfono principal de su empresa.

1. Vaya al Centro Microsoft Teams administración.
2. En el panel de navegación izquierdo, vaya **a Números** de Teléfono  >  **y,** a continuación, haga clic en **Agregar**.
3. Escriba un nombre para el pedido y agregue una descripción.
4. En la página Ubicación y cantidad, haga lo siguiente:
    1. En **País o región,** seleccione un país o región.
    2. En **Tipo de número**, seleccione una de las siguientes opciones:

        - **Operador automático (pago)** Número de teléfono normal, no gratuito. Las tarifas de larga distancia se cobran al autor de la llamada.
        - **Operador automático (gratuito)** Número de teléfono gratuito (EE. UU. y Canadá) o gratuito (Reino Unido). Las tarifas de largas distancias se cobran a su empresa. Para poder seleccionar esta opción, debe comprar créditos de comunicación. Para obtener más información, vea [¿Qué necesito comprar para usar Microsoft 365 Business Voice?](what-to-buy.md).

    3. En **Cantidad**, seleccione **1**.
        > [!NOTE]
        > Si recibe el mensaje No tiene licencias **suficientes** para solicitar más números de este tipo, asegúrese de que ha comprado licencias de Business Voice. Para obtener más información, vea [¿Qué necesito comprar para usar Microsoft 365 Business Voice?](what-to-buy.md).
    4. En **Ubicación**, escriba el nombre de la ubicación que creó en el paso [Configurar ubicaciones de](set-up-emergency-locations.md) emergencia.
    5. En **Código de área**, seleccione un código de área y, a continuación, haga clic en **Siguiente** para seleccionar los números
5. Seleccione el número que desee. Tienes 10 minutos para seleccionar tu número de teléfono y realizar el pedido. Si lleva más de 10 minutos, el número de teléfono se devolverá al grupo de números.
6. Cuando esté listo para realizar el pedido, haga clic **en Realizar pedido** y, a continuación, en **Finalizar**

## <a name="set-up-phone-numbers-for-your-users"></a>Configurar números de teléfono para los usuarios

1. Vaya al Centro Microsoft Teams administración.
2. En el panel de navegación izquierdo, vaya **a Números** de Teléfono  >  **y,** a continuación, haga clic en **Agregar**.
3. Escriba un nombre para el pedido y agregue una descripción.
4. En la página Ubicación y cantidad, haga lo siguiente:

    1. En **País o región,** seleccione un país o región.
    2. En **Tipo de número,** seleccione **Usuario (suscriptor).**
    3. En **Cantidad**, escriba el número de números que desea para su organización.
    4. En **Ubicación**, seleccione una ubicación. Puede seleccionar la ubicación de emergencia [](set-up-emergency-locations.md) que agregó en el paso Configurar ubicaciones de emergencia, o si necesita crear una nueva ubicación para otra oficina o una oficina principal, haga clic en Agregar **una ubicación.**
    5. En **Código de área,** seleccione un código de área y, a continuación, haga clic **en Siguiente** para seleccionar los números.
5. Seleccione los números que desee. Tienes 10 minutos para seleccionar tus números de teléfono y realizar el pedido. Si lleva más de 10 minutos, los números de teléfono se devolverán al grupo de números.
6. Cuando esté listo para realizar el pedido, haga clic **en Realizar pedido** y, a continuación, en **Finalizar.**

> [!div class="nextstepaction"]
> [Paso siguiente: Asignar licencias a Teams usuarios](set-up-licenses.md)