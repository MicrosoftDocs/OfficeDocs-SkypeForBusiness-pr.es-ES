---
title: Crear o modificar una regla de traducción para la presentación de identificación de llamadas en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6a643961-a0a1-41d1-96ba-6c428a89d82e
description: 'Resumen: Aprenda a configurar la identificación de llamadas con el panel de control de Skype empresarial Server.'
ms.openlocfilehash: ca35b3398732296f435196ffeb38d915472b303d
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233770"
---
# <a name="create-or-modify-a-translation-rule-for-caller-id-presentation-in-skype-for-business-server"></a>Crear o modificar una regla de traducción para la presentación de identificación de llamadas en Skype empresarial Server

**Resumen:** Obtenga información sobre cómo configurar la identificación de llamadas con el panel de control de Skype empresarial Server.

Con Skype empresarial Server, el número de teléfono de la persona que llamó (es decir, el número de teléfono llamado) puede traducirse desde el formato E. 164 al formato de marcado local requerido por el _interlocutor troncal_ (es decir, la puerta de enlace asociada, la sucursal privada de intercambio ( PBX) o el tronco del SIP. Para ello, defina una o varias reglas de traslación para traducir la URI de la solicitud antes de redirigirla al tronco de mismo nivel.

Skype empresarial Server también le ofrece la opción de traducir el número de teléfono de la persona que llama (es decir, el número de teléfono desde el que llama el autor de la llamada) desde el formato E. 164 al formato de marcado local requerido por el interlocutor troncal. Por ejemplo, puede escribir una regla de conversión para quitar el prefijo +34 del principio de una cadena de llamada y sustituirlo por 0134.

### <a name="to-configure-caller-id-by-using-skype-for-business-server-control-panel"></a>Para configurar la identificación de llamadas con el panel de control de Skype empresarial Server

1. Abra el panel de control de Skype empresarial Server.

2. En la barra de navegación izquierda, haga clic en **Enrutamiento de voz** y, a continuación, en **Configuración del tronco**.

3. En la página **Configuración de tronco**, haga doble clic en el tronco existente (por ejemplo, **Global**) para abrir el cuadro de diálogo **Editar configuración de tronco**.

4. Para configurar la presentación del identificador de llamada:

   - Para elegir una o más reglas de una lista de todas las reglas de traducción disponibles en la implementación de telefonía IP empresarial, haga clic en **seleccionar**. En **Reglas de traducción de números de llamada**, haga clic en las reglas que quiera asociar al tronco y, después, haga clic en **Aceptar**.

   - Para definir una regla de conversión nueva y asociarla con el tronco, haga clic en **Nueva**. Para obtener más información sobre cómo definir una nueva regla, consulte [definición de reglas de traducción](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx) en la documentación de implementación.

   - Para editar una regla de conversión que ya esté asociada al tronco, haga clic en el nombre de la regla y, a continuación, haga clic en  **Mostrar detalles**. Para obtener más información, consulte  [Defining Translation Rules](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx) en la documentación sobre implementación.

   - Para copiar una regla de conversión existente con el fin de usarla como punto de partida en la definición de una regla nueva, haga clic en el nombre de la regla, en **Copiar** y, a continuación, en  **Pegar**. Para obtener más información, consulte [Defining Translation Rules](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx).

   - Para quitar una regla de conversión del plan de marcado, resalte el nombre de la regla y haga clic en **Eliminar**.

     > [!CAUTION]
     > No asocie reglas de conversión a un tronco si ha configurado reglas de conversión en la entidad del mismo nivel que el tronco asociado, ya que es posible que ambas reglas puedan entrar en conflicto.


