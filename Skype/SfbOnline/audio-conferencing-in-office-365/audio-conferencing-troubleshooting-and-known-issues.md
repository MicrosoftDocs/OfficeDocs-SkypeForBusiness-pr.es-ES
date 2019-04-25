---
title: Solución de problemas y problemas conocidos de Audioconferencia
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 72979911-5319-4de2-a275-4dd9a0f44fe6
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Obtener una lista de problemas conocidos al usar Microsoft como su proveedor de conferencia de acceso telefónico, el estado y algunas soluciones alternativas. '
ms.openlocfilehash: 997cc5007df35b307cb714b891bc60764bd4a645
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32229188"
---
# <a name="audio-conferencing-troubleshooting-and-known-issues"></a>Solución de problemas y problemas conocidos de Audioconferencia

 **En este artículo está dirigido Skype para los usuarios empresariales mediante Microsoft como su proveedor de conferencias de audio. No se aplica a los clientes que están usando un proveedor de servicios de audioconferencia (ACP).**
  
## <a name="troubleshooting-and-known-issues"></a>Solución de problemas y problemas conocidos

Conferencias de audio que usa Microsoft como el proveedor de conferencias de audio tiene problemas actuales que se realiza un seguimiento son activamente investigarse y se resolverán potencialmente cuando la característica se actualiza en futuras versiones de Office 365.
  
Por ahora, use esta clase como una referencia para solucionar posibles problemas con la introducción de conferencias de Audio configurado y trabajo para las personas con Skype para la empresa en su organización.

|**Problema**|**Comportamiento/síntomas**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Notificaciones de entrada y salida se activan cuando se inicia una reunión, pero están desactivados breve tras que comience la reunión.  <br/> |De forma predeterminada, las notificaciones de entrada y salida están deshabilitadas para las reuniones donde los participantes unirse desde ambos Skype para aplicaciones empresariales y cuando se conectan a. Puede habilitar los anuncios en las **Opciones de reunión de Skype** en el Skype para la aplicación empresarial. Para una reunión donde todos los participantes llaman y se unen a la reunión, las notificaciones de entrada y salida están habilitadas de forma predeterminada ya que el registro de participantes no está disponible para ninguno de ellos. Cuando se ha iniciado una reunión con sólo los participantes en la entrada de llamada y se activará las notificaciones de salir, pero cuando un participante combinaciones mediante el uso de un Skype para la aplicación empresarial, las notificaciones estará desactivada. Cuando se establecen en desactivado, se pueden habilitar las notificaciones mediante **Las opciones de reunión de Skype** en el Skype para la aplicación empresarial. <br/> |No hay ninguna solución.  <br/> |30/8/2017  <br/> |
|Si un usuario aprovisiona la primera vez que se asigna una licencia E5, es posible que para el correo electrónico de bienvenida conferencias de Audio no entregar al usuario si no está habilitado el buzón de correo.  <br/> |En este caso, siempre puede volver a enviar la información de conferencia de audio del usuario mediante la **conferencia de Audio** en el Skype para el centro de administración de negocio o uso de PowerShell. Vea [Habilitar o deshabilitar el envío por correo electrónico cuando cambie la configuración de conferencias de Audio](enable-or-disable-sending-emails-when-their-settings-change.md).  <br/> **Nota:** Con el fin de volver a enviar el PIN de conferencia de audio para el usuario, el PIN tiene que se restablezca. También puede realizarse mediante la **conferencia de Audio** en el Skype para el centro de administración de negocio o mediante el uso de PowerShell.          |No hay ninguna solución.  <br/> |30/8/2017  <br/> |
|Las llamadas de conferencia de audio podrían tardar hasta 24 horas para mostrar en los informes de uso.  <br/> |Ya estamos deseando para realizar mejoras en esta área en servicio futuras actualizaciones.  <br/> |No hay ninguna solución.  <br/> |30/8/2017  <br/> |
|Cuando un autor de la llamada se conecta a un puente de conferencia después de la reunión ha sido bloqueada por un Skype para usuarios de empresa, no hay una notificación en el Skype para la aplicación de negocio que dice que el usuario está esperando en la sala de espera.  <br/> |Esto se ha hecho deliberadamente, pero hemos recibido los comentarios para agregar esta función en actualizaciones futuras del servicio.  <br/> |No hay ninguna solución.  <br/> |30/8/2017  <br/> |
   
## <a name="related-topics"></a>Temas relacionados

[Probar o comprar Audioconferencia en Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
