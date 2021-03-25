---
title: Crear o modificar una regla de traducción para la presentación del identificador de autor de la llamada en Skype Empresarial Server
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
description: 'Summary: Learn how to configure Caller ID by using the Skype for Business Server Control Panel.'
ms.openlocfilehash: 2ffe547927c9f4d6df16a06cc8c95dff9814fc7f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51113036"
---
# <a name="create-or-modify-a-translation-rule-for-caller-id-presentation-in-skype-for-business-server"></a>Crear o modificar una regla de traducción para la presentación del identificador de autor de la llamada en Skype Empresarial Server

**Resumen:** Obtenga información sobre cómo configurar el identificador de llamada mediante el Panel de control de Skype Empresarial Server.

Con Skype Empresarial Server, el número de teléfono de la parte llamada (es decir, el número de teléfono llamado) se puede traducir del formato E.164 al formato de marcado local que requiere el tronco del mismo nivel  _(es_ decir, la puerta de enlace asociada, la central de conmutación de sucursal privada (PBX) o el tronco SIP). Para ello, defina una o varias reglas de traslación para traducir la URI de la solicitud antes de redirigirla al tronco de mismo nivel.

Skype Empresarial Server también le ofrece la opción de traducir también el número de teléfono de la persona que realiza la llamada (es decir, el número de teléfono desde el que llama el autor de la llamada) del formato E.164 al formato de marcado local que requiere el mismo nivel de tronco. Por ejemplo, puede escribir una regla de conversión para quitar el prefijo +34 del principio de una cadena de llamada y sustituirlo por 0134.

### <a name="to-configure-caller-id-by-using-skype-for-business-server-control-panel"></a>Para configurar el identificador de llamada mediante el Panel de control de Skype Empresarial Server

1. Abra el Panel de control de Skype Empresarial Server.

2. En la barra de navegación izquierda, haga clic en **Enrutamiento de voz** y, después, en **Configuración de tronco**.

3. En la página **Configuración de tronco**, haga doble clic en el tronco existente (por ejemplo, **Global**) para abrir el cuadro de diálogo **Editar configuración de tronco**.

4. Para configurar la presentación del identificador de llamada:

   - Para elegir una o más reglas en una lista de reglas de conversión disponible en la implementación de Telefonía IP empresarial, haga clic en **Seleccionar**. En **Reglas de conversión del número que llama**, haga clic en las reglas que quiera asociar al tronco y, después, haga clic en **Aceptar**.

   - Para definir una regla de conversión nueva y asociarla al tronco, haga clic en **Nueva**. Para obtener más información sobre cómo definir una nueva regla, consulte  [Defining Translation Rules](/previous-versions/office/lync-server-2013/lync-server-2013-defining-translation-rules) en la documentación sobre implementación.

   - Para editar una regla de conversión que ya esté asociada al tronco, haga clic en el nombre de la regla y, a continuación, en **Mostrar detalles**. Para obtener más información, consulte [Defining Translation Rules](/previous-versions/office/lync-server-2013/lync-server-2013-defining-translation-rules) en la documentación referente a la implementación.

   - Para copiar una regla de conversión existente con el fin de utilizarla como punto de partida en la definición de una regla nueva, haga clic en el nombre de la regla, en **Copiar** y, a continuación, en **Pegar**. Para obtener más información, consulte [Defining Translation Rules](/previous-versions/office/lync-server-2013/lync-server-2013-defining-translation-rules).

   - Para quitar una regla de conversión de un tronco, resalte el nombre de la regla y en **Quitar**.

     > [!CAUTION]
     > No asocie reglas de conversión a un tronco si ha configurado reglas de conversión en la entidad del mismo nivel que el tronco asociado, porque es posible que ambas reglas puedan entrar en conflicto.