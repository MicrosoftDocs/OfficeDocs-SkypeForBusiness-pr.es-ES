---
title: Característica de expiración de la grabación de reunión
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
ms.openlocfilehash: cfbbc8602044c0429de414b94b88d0e0e5aa8b19
ms.sourcegitcommit: 11a803d569a57410e7e648f53b28df80a53337b6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/10/2021
ms.locfileid: "60889534"
---
# <a name="meeting-recording-expiration-feature---frequently-asked-questions"></a>Característica de expiración de la grabación de reunión: preguntas más frecuentes

**¿Cuál es el cambio?**

Estamos introduciendo una configuración de expiración predeterminada  de 60 días para todas las grabaciones de reuniones Teams (TMR) creadas recientemente. Esta opción está activa de forma predeterminada para todos los inquilinos y debe desactivarla si no desea esta característica. El OneDrive y SharePoint supervisará la fecha de expiración establecida en todos los TMR y moverá automáticamente los TMR a la papelera de reciclaje en su fecha de expiración.

**¿Por qué presentamos este cambio?**

Hemos respondido a sus solicitudes para la característica de expiración de la grabación de la reunión. Este es un mecanismo de limpieza ligero para reducir el desorden de almacenamiento creado a partir de TMR frío. En promedio, el 99 % de los TMR nunca se vuelve a observar después de 60 días.

**¿Por qué está activado de forma predeterminada?**

Creemos que casi todos los clientes se beneficiarán de la carga de almacenamiento reducida en su espacio empresarial mediante la eliminación de grabaciones que probablemente nunca se volverán a ver después de 60 días. Nuestro objetivo es proporcionar una experiencia lo más limpia posible para todos los clientes de forma predeterminada.

**Cómo se calcula la fecha de expiración?**

La fecha de expiración se calcula como el día en que se creó más el número predeterminado de días establecido en la directiva de Teams por el administrador.

**¿Cómo puede un administrador cambiar la fecha de expiración?**

Los administradores pueden editar la configuración de expiración predeterminada en su Teams de directivas. Ese cambio afectará solo a los TMR recién creados a partir de ese momento. No afectará a las grabaciones anteriores a esa fecha.

Los administradores no pueden cambiar la fecha de expiración de los TMR existentes. Esto se hace para proteger la decisión del usuario propietario del TMR.

**¿A quién afecta esto?**

Cualquier persona que almacene TMR en OneDrive o SharePoint.

**¿Por qué debo usar esta característica?**

Esta característica está activada de forma predeterminada. Para deshabilitarla, cambie la configuración de expiración predeterminada en la Teams directiva a **Sin expiración.**
Debe usar esta opción para limitar el OneDrive o Sharepoint para el consumo de almacenamiento en la nube impulsado por Teams de reunión. Una grabación de reunión típica consume unos 400 MB por hora de grabación.

**¿Debo confiar en esta característica para una estricta seguridad y cumplimiento normativo?**

No, no debe confiar en esto para la protección legal, ya que los usuarios finales pueden modificar la fecha de expiración de las grabaciones que controlan.

**¿Una directiva de retención o eliminación que he establecido en el Centro de cumplimiento de seguridad & invalidará la configuración de expiración de la grabación Teams reunión?**

Sí, todas las directivas que haya establecido en el centro de cumplimiento tendrán prioridad completa.

Por ejemplo:

- Si tiene una directiva que indica que todos los archivos de un sitio deben conservarse durante 100 días y la configuración de expiración para una grabación de reunión de Teams es de 30 días, la grabación se conservará durante los 100 días completos.
- Si tiene una directiva de eliminación que indica que todas las grabaciones de reunión de Teams se eliminarán después de cinco días y tiene una configuración de expiración para una grabación de reunión de Teams de 30 días, la grabación se eliminará después de cinco días.

**¿Qué sucede cuando expira un TMR?**

En la fecha de expiración, la grabación se mueve a la papelera de reciclaje y se borra el campo de fecha de expiración. Si recupera la grabación de la papelera de reciclaje, esta característica no la eliminará de nuevo porque se ha desactivado la fecha de expiración.

**¿Cómo se me notificará la expiración de un archivo?**

- Todos los usuarios verán una notificación sobre la fecha de expiración en la lista de comprobación de grabación en Teams de chat.
- Todos los usuarios con acceso de vista verán un icono rojo junto al archivo en su carpeta de OneDrive o SharePoint 14 días antes de que expire el archivo.
- El propietario del archivo recibirá una notificación por correo electrónico cuando expire la grabación y se le dirigirá a la papelera de reciclaje para recuperar la grabación.

**¿Qué SKU se requieren para esta función?**

- Todas las SKU tendrán esta característica de forma predeterminada.

- Todos los usuarios tendrán un período de expiración predeterminado de 30 días y no podrán modificar la fecha de expiración.

**Es la expiración del archivo un evento auditado y podré verlo en mis registros de auditoría?**

Sí, se mostrarán como eventos de eliminación del sistema en el registro de auditoría.

**¿Qué sucede si quiero que el administrador tenga control total sobre el ciclo de vida de las grabaciones de reuniones y no quiera dar a los usuarios finales la capacidad de invalidar la fecha de expiración?**

Se recomienda usar las directivas de retención y cumplimiento de seguridad y/o eliminación disponibles como parte de la SKU de cumplimiento de E5. Esta oferta está destinada a resolver problemas administrativos complejos basados en políticas y acuerdos de nivel de servicio.

Esta característica está pensada únicamente como un mecanismo de limpieza ligero para reducir el desorden de almacenamiento creado a partir de Teams grabaciones de reuniones.

**¿Cuándo se eliminará el archivo?**

El archivo se eliminará dentro de los cinco días siguientes a la fecha de expiración, aunque esto no es una garantía estricta.
