---
title: Crear o modificar una regla de conversión para la presentación del identificador de llamada en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6a643961-a0a1-41d1-96ba-6c428a89d82e
description: 'Resumen: obtenga información sobre cómo configurar el identificador de llamada mediante el Panel de control de Skype Empresarial Server.'
ms.openlocfilehash: ca1451a051a1c9053b88861222d2c4d42c5d555b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804190"
---
# <a name="create-or-modify-a-translation-rule-for-caller-id-presentation-in-skype-for-business-server"></a>Crear o modificar una regla de conversión para la presentación del identificador de llamada en Skype Empresarial Server

**Resumen:** Obtenga información sobre cómo configurar el identificador de llamada mediante el Panel de control de Skype Empresarial Server.

Con Skype Empresarial Server, el número de teléfono de la parte a la que se llama (es decir, el número de teléfono al que se llama) se puede traducir del formato E.164 al formato de marcado local que requiere el tronco  _del_ mismo nivel (es decir, la puerta de enlace asociada, la central de conmutación (PBX) o el tronco SIP. Para ello, defina una o varias reglas de traslación para traducir la URI de la solicitud antes de redirigirla al tronco de mismo nivel.

Skype Empresarial Server también le ofrece la opción de traducir también el número de teléfono de la persona que llama (es decir, el número de teléfono desde el que llama el autor de la llamada) del formato E.164 al formato de marcado local que requiere el tronco del mismo nivel. Por ejemplo, puede escribir una regla de conversión para quitar el prefijo +34 del principio de una cadena de llamada y sustituirlo por 0134.

### <a name="to-configure-caller-id-by-using-skype-for-business-server-control-panel"></a>Para configurar el identificador de llamada mediante el Panel de control de Skype Empresarial Server

1. Abra el Panel de control de Skype Empresarial Server.

2. En la barra de navegación izquierda, haga clic en **Enrutamiento de voz** y, después, en **Configuración de tronco**.

3. En la página **Configuración de tronco**, haga doble clic en el tronco existente (por ejemplo, **Global**) para abrir el cuadro de diálogo **Editar configuración de tronco**.

4. Para configurar la presentación del identificador de llamada:

   - Para elegir una o más reglas en una lista de reglas de conversión disponible en la implementación de Telefonía IP empresarial, haga clic en **Seleccionar**. En **Reglas de conversión del número que llama**, haga clic en las reglas que quiera asociar al tronco y, después, haga clic en **Aceptar**.

   - Para definir una regla de conversión nueva y asociarla al tronco, haga clic en **Nueva**. Para obtener más información sobre cómo definir una regla nueva, consulte  [Defining Translation Rules](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx) en la documentación sobre implementación.

   - Para editar una regla de conversión que ya esté asociada al tronco, haga clic en el nombre de la regla y, a continuación, en **Mostrar detalles**. Para obtener más información, consulte [Defining Translation Rules](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx) en la documentación referente a la implementación.

   - Para copiar una regla de conversión existente con el fin de utilizarla como punto de partida en la definición de una regla nueva, haga clic en el nombre de la regla, en **Copiar** y, a continuación, en **Pegar**. Para obtener más información, consulte [Defining Translation Rules](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx).

   - Para quitar una regla de conversión de un tronco, resalte el nombre de la regla y en **Quitar**.

     > [!CAUTION]
     > No asocie reglas de conversión a un tronco si ha configurado reglas de conversión en la entidad del mismo nivel que el tronco asociado, porque es posible que ambas reglas puedan entrar en conflicto.


