---
title: Crear o modificar una regla de conversión para presentación del identificador de llamada en Skype Empresarial Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 6a643961-a0a1-41d1-96ba-6c428a89d82e
description: 'Resumen: Conozca cómo configurar identificador utilizando el Skype para el Panel de Control de servidor empresarial.'
ms.openlocfilehash: b5460558d621b04ca041bd540f9aba9d3a19bd45
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="create-or-modify-a-translation-rule-for-caller-id-presentation-in-skype-for-business-server-2015"></a>Crear o modificar una regla de conversión para presentación del identificador de llamada en Skype Empresarial Server 2015
 
**Resumen:** Aprenda a configurar identificador mediante el Skype para el Panel de Control de servidor empresarial.
  
Con Skype para Business Server, número de teléfono del receptor (es decir, el número de teléfono llamado) se pueden traducir en formato E.164 en el formato de marcado local requerido por el _interlocutor de tronco_ (es decir, la puerta de enlace asociada, private branch exchange ( PBX), o troncal SIP). Para ello, defina una o varias reglas de traslación para traducir la URI de la solicitud antes de redirigirla al tronco de mismo nivel.
  
Skype para Business Server también tendrá la opción también traducir el número de teléfono de la persona que llama (es decir, el número de teléfono que el llamador está llamando desde) de formato E.164 para el formato de marcado local requerido por el interlocutor de tronco. Por ejemplo, puede escribir una regla de conversión para quitar el prefijo +34 del principio de una cadena de llamada y sustituirlo por 0134.
  
### <a name="to-configure-caller-id-by-using-skype-for-business-server-control-panel"></a>Para configurar el identificador de llamadas mediante Skype para Panel de Control de servidor de Business

1. Abre Skype para Panel de Control del servidor de empresa.
    
2. En la barra de navegación izquierda, haga clic en **Enrutamiento de voz** y, a continuación, en **Configuración del tronco**.
    
3. En la página **Configuración de tronco**, haga doble clic en el tronco existente (por ejemplo, **Global**) para abrir el cuadro de diálogo **Editar configuración de tronco**.
    
4. Para configurar la presentación del identificador de llamada:
    
   - Para elegir una o más reglas en una lista de todas las reglas de traducción disponibles en la implementación de Telefonía IP empresarial, haga clic en **Seleccionar**. En **Reglas de traducción de números de llamada**, haga clic en las reglas que quiera asociar al tronco y, después, haga clic en **Aceptar**.
    
   - Para definir una regla de conversión nueva y asociarla con el tronco, haga clic en **Nueva**. Para obtener más información acerca de la definición de una nueva regla, consulte [Definición de las reglas de conversión](http://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx) en la documentación de implementación.
    
   - Para editar una regla de conversión que ya esté asociada al tronco, haga clic en el nombre de la regla y, a continuación, haga clic en  **Mostrar detalles**. Para obtener más información, consulte [Definición de las reglas de conversión](http://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx) en la documentación de implementación.
    
   - Para copiar una regla de conversión existente con el fin de usarla como punto de partida en la definición de una regla nueva, haga clic en el nombre de la regla, en **Copiar** y, a continuación, en  **Pegar**. Para obtener más información, consulte [Definición de las reglas de conversión](http://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx). 
    
   - Para quitar una regla de conversión del plan de marcado, resalte el nombre de la regla y haga clic en **Quitar**.
    
    > [!CAUTION]
    > No asocie reglas de conversión a un tronco si ha configurado reglas de conversión en la entidad del mismo nivel que el tronco asociado, ya que es posible que ambas reglas puedan entrar en conflicto. 
  

