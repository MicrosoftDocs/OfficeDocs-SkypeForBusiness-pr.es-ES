---
title: Característica de expiración de la grabación de la reunión
author: cichur
ms.author: v-cichur
ms.reviewer: ''
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
searchScope:
- Microsoft Teams
search.appverid: MET150
description: Obtenga información sobre la característica de expiración de la grabación de la reunión en Microsoft Teams.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 67cbef7e6fad2c9620de17f89b8b3a4fe641368e
ms.sourcegitcommit: 68162a8c9dee9a27af596353baabeda9b8fa64f3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/14/2022
ms.locfileid: "64853231"
---
# <a name="meeting-recording-expiration-feature---frequently-asked-questions"></a>Característica de expiración de la grabación de la reunión: preguntas más frecuentes

**¿Cuál es el cambio?**

Presentamos una configuración de expiración predeterminada de 120 días para *todas las* grabaciones de reuniones de Teams recién creadas (TMR). Esta opción está activada de forma predeterminada para todos los inquilinos y debe desactivarla si no desea esta característica. El sistema de OneDrive y SharePoint supervisará la fecha de expiración establecida en todas las TMR y moverá automáticamente las TMR a la papelera de reciclaje en su fecha de expiración.

**¿Por qué presentamos este cambio?**

Hemos respondido a sus solicitudes de la característica de expiración de la grabación de la reunión. Se trata de un mecanismo de limpieza ligero para reducir el desorden de almacenamiento creado a partir de la tmr fría. En promedio, el 99% de los TMRs nunca se vuelven a ver después de 120 días.

**¿Por qué está activado de forma predeterminada?**

Creemos que casi todos los clientes se beneficiarán de la menor carga de almacenamiento en su inquilino mediante la eliminación de grabaciones que probablemente nunca se volverán a ver después de 120 días. Nuestro objetivo es proporcionar una experiencia lo más limpia posible a todos los clientes de forma predeterminada.

**Cómo se calcula la fecha de expiración?**

La fecha de expiración se calcula como el día en que se crea, más el número predeterminado de días establecido en la directiva de Teams por el administrador.

**¿Cómo puede un Administrador cambiar la fecha de expiración?**

Los administradores pueden editar la configuración de expiración predeterminada en su consola de directivas de Teams. Ese cambio sólo afectará a los R TMR recién creados desde ese punto hacia adelante. Las grabaciones no se verán afectadas antes de esa fecha.

Los administradores no pueden cambiar la fecha de expiración en los TMR existentes. Esto se hace para proteger la decisión del usuario propietario de la TMR.

**¿A quién afecta esto?**

Cualquier persona que almacene los TMR en OneDrive o SharePoint.

**¿Por qué debo usar esta característica?**

Esta característica se está activando de forma predeterminada. Para deshabilitarla, cambia la configuración de expiración predeterminada en la consola de directivas de Teams a **Sin expiración**.
Use esta opción para limitar el consumo de almacenamiento de OneDrive o SharePoint para la nube impulsado por Teams registros de reunión. Una grabación de reunión típica consume alrededor de 400 MB por hora de grabación.

**¿Debo confiar en esta característica para una estricta conformidad y seguridad?**

No, no debe confiar en esto para la protección legal, ya que los usuarios finales pueden modificar la fecha de expiración de las grabaciones que controlan.

**¿Una directiva de retención o eliminación que he establecido en el Centro de cumplimiento de & de seguridad invalidará la configuración de expiración de la grabación de Teams reunión?**

Sí, todas las directivas que haya establecido en el Centro de cumplimiento tendrán prioridad completa.

Por ejemplo:

- Si tiene una directiva que indica que todos los archivos de un sitio deben conservarse durante 100 días y la configuración de expiración de una Teams grabación de una reunión es de 30 días, la grabación se conservará durante los 100 días completos.
- Si tiene una directiva de eliminación que indica que todas las grabaciones de Teams reunión se eliminarán después de cinco días y tiene una configuración de expiración para una Teams grabación de la reunión de 30 días, la grabación se eliminará después de cinco días.

**¿Qué sucede cuando una TMR expira?**

En la fecha de expiración, la grabación se mueve a la Papelera de reciclaje y se borra el campo de fecha de expiración. Si recupera la grabación de la Papelera de reciclaje, esta característica no la eliminará de nuevo porque se ha borrado la fecha de expiración.

**¿Cómo se me notificará la expiración de un archivo?**

- Todos los usuarios verán una notificación sobre la fecha de expiración en la lista de comprobación de grabación de la ventana de chat Teams.
- Todos los usuarios con acceso de vista verán un icono rojo junto al archivo en su carpeta de OneDrive o SharePoint 14 días antes de que expire el archivo.
- El propietario del archivo recibirá una notificación por correo electrónico cuando expire la grabación y se le dirigirá a la papelera de reciclaje para recuperar la grabación.

**¿Qué SKU se requieren para esta función?**

- Todas las SKU tendrán esta característica de forma predeterminada.

- De forma predeterminada, los usuarios de A1 tendrán un período de expiración de 30 días y no podrán modificar la fecha de expiración.

**Es la expiración del archivo un evento auditado y podré verlo en mis registros de auditoría?**

Sí, estos se mostrarán como eventos de eliminación del sistema en el registro de auditoría.

**¿Qué ocurre si deseo que el administrador tenga control total sobre el ciclo de vida de las grabaciones de las reuniones y no quiera ofrecer a los usuarios finales la posibilidad de invalidar la fecha de expiración?**

Se recomienda usar las directivas de conservación y eliminación de seguridad y cumplimiento disponibles como parte de la SKU de cumplimiento E5. Esta oferta está destinada a resolver problemas administrativos complejos basados en políticas y acuerdos de nivel de servicio.

Esta característica se ha diseñado únicamente como un mecanismo ligero de limpieza para reducir el desorden de almacenamiento creado a partir de grabaciones de reuniones Teams fríos.

**¿Cuándo se eliminará el archivo?**

El archivo se eliminará dentro de los cinco días posteriores a la fecha de expiración, aunque esto no es una garantía estricta.

**La expiración predeterminada es de 120 días, pero cuando revisé Teams centro de administración, es 60 días. ¿Por qué?**

La forma en que funcionan las directivas de Teams es si el administrador establece cualquier directiva del centro, se toma una instantánea almacenada en caché de todas las opciones de configuración. Si el administrador estableció algún atributo en la directiva cuando teníamos temporalmente un valor predeterminado de 60 días, tendrá que cambiarlo manualmente a 120 días. Si no tenían una configuración personalizada antes de establecer el valor predeterminado de 120 días, obtendrán los 120 días.
