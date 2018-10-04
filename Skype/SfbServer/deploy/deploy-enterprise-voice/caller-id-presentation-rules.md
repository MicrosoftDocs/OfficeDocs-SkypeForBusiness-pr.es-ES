---
title: Crear o modificar una regla de conversión para la presentación del identificador de autor de la llamada de Skype para Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6a643961-a0a1-41d1-96ba-6c428a89d82e
description: 'Resumen: Obtenga información sobre cómo configurar el identificador de autor de la llamada mediante el Skype para el Panel de Control de servidor empresarial.'
ms.openlocfilehash: 69d5a1d8f04900933b5de4ebd795961d8b450ca7
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "25373590"
---
# <a name="create-or-modify-a-translation-rule-for-caller-id-presentation-in-skype-for-business-server"></a>Crear o modificar una regla de conversión para la presentación del identificador de autor de la llamada de Skype para Business Server

**Resumen:** Obtenga información sobre cómo configurar el identificador de autor de la llamada mediante el Skype para el Panel de Control de servidor empresarial.

Con Skype para Business Server, número de teléfono del receptor (es decir, el número de teléfono denominado) se puede traducir del formato E.164 al formato de marcado local que requiera el _mismo nivel del tronco_ (es decir, la puerta de enlace asociada, (exchange) central de conmutación PBX), o un tronco SIP). Para ello, defina una o varias reglas de traslación para traducir la URI de la solicitud antes de redirigirla al tronco de mismo nivel.

Skype para Business Server también proporciona la opción de traducir también el número de teléfono de la persona que llama (es decir, el número de teléfono que el autor de la llamada está llamando desde) del formato E.164 a formato de marcado local requerido por el par de tronco. Por ejemplo, puede escribir una regla de conversión para quitar el prefijo +34 del principio de una cadena de llamada y sustituirlo por 0134.

### <a name="to-configure-caller-id-by-using-skype-for-business-server-control-panel"></a>Para configurar el identificador de autor de la llamada mediante Skype para el Panel de Control de servidor empresarial

1. Abra Skype para el Panel de Control de servidor empresarial.

2. En la barra de navegación izquierda, haga clic en **Enrutamiento de voz** y, a continuación, en **Configuración del tronco**.

3. En la página **Configuración de tronco**, haga doble clic en el tronco existente (por ejemplo, **Global**) para abrir el cuadro de diálogo **Editar configuración de tronco**.

4. Para configurar la presentación del identificador de llamada:

   - Para elegir una o varias reglas de una lista de todas las reglas de conversión disponibles en su implementación de Enterprise Voice, haga clic en **Seleccionar**. En **Reglas de traducción de números de llamada**, haga clic en las reglas que quiera asociar al tronco y, después, haga clic en **Aceptar**.

   - Para definir una regla de conversión nueva y asociarla con el tronco, haga clic en **Nueva**. Para obtener información detallada sobre cómo definir una nueva regla, consulte [Definición de reglas de conversión](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx) en la documentación de implementación.

   - Para editar una regla de conversión que ya esté asociada al tronco, haga clic en el nombre de la regla y, a continuación, haga clic en  **Mostrar detalles**. Para obtener más información, consulte [Definición de reglas de conversión](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx) en la documentación de implementación.

   - Para copiar una regla de conversión existente con el fin de usarla como punto de partida en la definición de una regla nueva, haga clic en el nombre de la regla, en **Copiar** y, a continuación, en  **Pegar**. Para obtener información detallada, consulte [Defining Translation Rules](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx).

   - Para quitar una regla de conversión del plan de marcado, resalte el nombre de la regla y haga clic en **Quitar**.

     > [!CAUTION]
     > No asocie reglas de conversión a un tronco si ha configurado reglas de conversión en la entidad del mismo nivel que el tronco asociado, ya que es posible que ambas reglas puedan entrar en conflicto.


