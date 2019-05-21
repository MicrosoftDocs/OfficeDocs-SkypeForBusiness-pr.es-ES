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
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Obtenga una lista de los problemas conocidos al usar Microsoft como su proveedor de conferencias de acceso telefónico local, su estado y algunas soluciones alternativas. '
ms.openlocfilehash: 9b70cfcdeeb80be43cd0ecc99ca7eced71bb9319
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34289587"
---
# <a name="audio-conferencing-troubleshooting-and-known-issues"></a>Solución de problemas y problemas conocidos de Audioconferencia

 **Este artículo está destinado a usuarios de Skype empresarial que usan Microsoft como proveedor de servicios de audioconferencia. No se aplica a los clientes que usan un proveedor de servicios de audioconferencia (ACP) de terceros.**
  
## <a name="troubleshooting-and-known-issues"></a>Solución de problemas y problemas conocidos

Las conferencias de audio que usan Microsoft como el proveedor de servicios de audioconferencia tiene problemas actuales que se están rastreando e investigan activamente y se pueden resolver cuando la característica se actualiza en versiones futuras de Office 365.
  
Por ahora, use esto como una referencia al solucionar posibles problemas con la configuración de las conferencias de audio y el trabajo para las personas que usan Skype empresarial en su organización.

|**Problema**|**Comportamiento/síntomas**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Las notificaciones de entrada y salida se activan cuando se inicia una reunión, pero se desactivan poco después de que se inicie la reunión.  <br/> |De forma predeterminada, las notificaciones de entrada y salida están deshabilitadas para las reuniones en las que los participantes se unen desde las aplicaciones de Skype empresarial y cuando llaman. Puede habilitar los anuncios en las opciones de **reunión de Skype** en la aplicación Skype empresarial. Para una reunión donde todos los participantes llaman y se unen a la reunión, las notificaciones de entrada y salida están habilitadas de forma predeterminada ya que el registro de participantes no está disponible para ninguno de ellos. Cuando se inicia una reunión y solo los participantes llaman, se activan las notificaciones de entrada y salida, pero cuando un participante se une mediante una aplicación de Skype empresarial, se desactivan las notificaciones. Cuando se desactivan, las notificaciones se pueden volver a habilitar con **las opciones de reunión de Skype** en la aplicación de Skype empresarial. <br/> |No hay ninguna solución.  <br/> |8/30/2017  <br/> |
|Si se aprovisiona un usuario la primera vez mediante la asignación de una licencia de E5, es posible que el correo electrónico de bienvenida a la audioconferencia no se entregue al usuario si el buzón no está habilitado.  <br/> |Si esto sucede, siempre puede volver a enviar la información de las conferencias de audio del usuario mediante **audioconferencia** en el centro de administración de Skype empresarial o mediante PowerShell. Consulte [habilitar o deshabilitar el envío de correos electrónicos cuando cambia la configuración de las conferencias de audio](enable-or-disable-sending-emails-when-their-settings-change.md).  <br/> **Nota:** Para volver a enviar el PIN de audioconferencia al usuario, debe restablecer el PIN. Esto también se puede realizar mediante **audioconferencia** en el centro de administración de Skype empresarial o mediante PowerShell.          |No hay ninguna solución.  <br/> |8/30/2017  <br/> |
|Las llamadas de audioconferencia pueden demorar hasta 24 horas en mostrar los informes de uso.  <br/> |Esperamos realizar mejoras en esta área en actualizaciones futuras del servicio.  <br/> |No hay ninguna solución.  <br/> |8/30/2017  <br/> |
|Cuando una persona llama a un puente de conferencia después de que un usuario de Skype empresarial haya bloqueado la reunión, no se produce una notificación en la aplicación de Skype empresarial que indica que el usuario está en la sala de espera.  <br/> |Esto se ha hecho deliberadamente, pero hemos recibido los comentarios para agregar esta función en actualizaciones futuras del servicio.  <br/> |No hay ninguna solución.  <br/> |8/30/2017  <br/> |
   
## <a name="related-topics"></a>Temas relacionados

[Probar o comprar Audioconferencia en Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
