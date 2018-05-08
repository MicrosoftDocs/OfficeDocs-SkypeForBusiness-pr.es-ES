---
title: Problemas conocidos y solución de problemas de conferencia audio
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 72979911-5319-4de2-a275-4dd9a0f44fe6
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Obtener una lista de problemas conocidos al usar Microsoft como su proveedor de conferencia de acceso telefónico, el estado y algunas soluciones alternativas. '
ms.openlocfilehash: fb22149d2aca537f491c0c8d475059ec9f6bc506
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="audio-conferencing-troubleshooting-and-known-issues"></a>Problemas conocidos y solución de problemas de conferencia audio

 **Este artículo está dirigido Skype para los usuarios profesionales y Microsoft Teams utilizando Microsoft como su proveedor de conferencias de audio. No se aplica a los clientes que están usando un proveedor de servicios de audioconferencia (ACP).**
  
## <a name="troubleshooting-and-known-issues"></a>Solución de problemas y problemas conocidos

Conferencias de audio que usa Microsoft como el proveedor de conferencias de audio tiene problemas actuales que se realiza un seguimiento son activamente investigarse y se resolverán potencialmente cuando la característica se actualiza en futuras versiones de Office 365.
  
Por ahora, use esta clase como una referencia para solucionar posibles problemas con la introducción de conferencias de Audio configurado y trabajo para las personas que usan el Skype para las aplicaciones de negocio o Teams de Microsoft en su organización.
  
### <a name="microsoft-teams-app"></a>Aplicación de los equipos de Microsoft

|**Problema**|**Comportamiento/síntomas**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Los autores de llamadas de RTC con el mismo "número de de" se muestran con el mismo usuario en la lista de participantes de la reunión.  <br/> |Cuando varios autores de llamadas de RTC unirse a una reunión, y sus identificadores de autor de la llamada se enmascaran como un solo número, se mostrará como un único autor de la llamada en la lista de reuniones.  <br/> |No hay ninguna solución.  <br/> |25/9/2017  <br/> |
|Panel de información de la reunión no está visible forma intermitente.  <br/> |Panel de información de la reunión no se puede mostrar en el cliente de los equipos cuando los usuarios están intentando buscar para números de teléfono de puente de conferencia o identificador de conferencia.  <br/> |Examine los detalles de la reunión o el calendario de Outlook para ver los números de teléfono de puente de conferencia o identificador de conferencia.  <br/> |25/9/2017  <br/> |
|Invitaciones de reunión de Outlook, complemento mostrar caracteres de elementos no utilizados en las coordenadas de RTC para configuraciones regionales de EE.  <br/> |Al programar reuniones privadas mediante Outlook, complemento para Microsoft Teams en un equipo con configuraciones regionales que no sean-US, las coordenadas de RTC pueden contener caracteres de elementos no utilizados.  <br/> |No hay ninguna solución.  <br/> |25/9/2017  <br/> |
|En el marcado de las necesidades de uso de 5 dígitos o más.  <br/> |Los usuarios que intentan marcar un número de una reunión necesitan escribir 5 o más dígitos, aunque la regla de normalización del plan de marcado está disponible para normalizar el marcado de dígitos breve al formato E.164.  <br/> |Marcar un número, escriba el número DID completo o el formato de número local en lugar de número de extensión interna.  <br/> |25/9/2017  <br/> |
|Salida control no está visible forma intermitente.  <br/> |Salida control no estén visible en el panel de información de reunión.  <br/> |No hay ninguna solución.  <br/> |25/9/2017  <br/> |
|Identificador de conferencia estática no se admite para las reuniones de Microsoft Teams.  <br/> |Si el administrador reemplaza la configuración predeterminada de identificador de conferencia dinámico al identificador de conferencia estática, esta configuración no surtirán efecto para las reuniones de Microsoft Teams. Vea [uso de conferencias de Audio identificadores dinámicos en su organización](using-audio-conferencing-dynamic-ids-in-your-organization.md).  <br/> |No hay ninguna solución.  <br/> |25/9/2017  <br/> |
|Las coordenadas de la reunión de RTC no están disponibles para Skype local para usuarios de empresas  <br/> |Si el usuario es un Skype para usuarios de empresa local, asignado con Skype para profesionales en línea, conferencias de Audio y las licencias de los equipos, todas las reuniones programadas con los equipos no incluirá las coordenadas de la reunión de RTC. <br/> |No hay ninguna solución.  <br/> |1/2/2018  <br/> |
   
### <a name="skype-for-business-app"></a>Skype para la aplicación empresarial

|**Problema**|**Comportamiento/síntomas**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Notificaciones de entrada y salida se activan cuando se inicia una reunión, pero están desactivados breve tras que comience la reunión.  <br/> |De forma predeterminada, las notificaciones de entrada y salida están deshabilitadas para las reuniones donde los participantes unirse desde ambos Skype para aplicaciones empresariales y cuando se conectan a. Puede habilitar los anuncios en las **Opciones de reunión de Skype** en el Skype para la aplicación empresarial. Para una reunión donde todos los participantes llaman y se unen a la reunión, las notificaciones de entrada y salida están habilitadas de forma predeterminada ya que el registro de participantes no está disponible para ninguno de ellos. Cuando se ha iniciado una reunión con sólo los participantes en la entrada de llamada y se activará las notificaciones de salir, pero cuando un participante combinaciones mediante el uso de un Skype para la aplicación empresarial, las notificaciones estará desactivada. Cuando se establecen en desactivado, se pueden habilitar las notificaciones mediante **Las opciones de reunión de Skype** en el Skype para la aplicación empresarial. <br/> |No hay ninguna solución.  <br/> |30/8/2017  <br/> |
|Si un usuario aprovisiona la primera vez que se asigna una licencia E5, es posible que para el correo electrónico de bienvenida conferencias de Audio no entregar al usuario si no está habilitado el buzón de correo.  <br/> |En este caso, siempre puede volver a enviar la información de conferencia de audio del usuario mediante la **conferencia de Audio** en el Skype para el centro de administración de negocio o uso de PowerShell. Vea [Habilitar o deshabilitar el envío por correo electrónico cuando cambie la configuración de conferencias de Audio](enable-or-disable-sending-emails-when-their-settings-change.md).  <br/> **Nota:** Con el fin de volver a enviar el PIN de conferencia de audio para el usuario, el PIN tiene que se restablezca. También puede realizarse mediante la **conferencia de Audio** en el Skype para el centro de administración de negocio o mediante el uso de PowerShell.          |No hay ninguna solución.  <br/> |30/8/2017  <br/> |
|Las llamadas de conferencia de audio podrían tardar hasta 24 horas para mostrar en los informes de uso.  <br/> |Ya estamos deseando para realizar mejoras en esta área en servicio futuras actualizaciones.  <br/> |No hay ninguna solución.  <br/> |30/8/2017  <br/> |
|Cuando un autor de la llamada se conecta a un puente de conferencia después de la reunión ha sido bloqueada por un Skype para usuarios de empresa, no hay una notificación en el Skype para la aplicación de negocio que dice que el usuario está esperando en la sala de espera.  <br/> |Esto se ha hecho deliberadamente, pero hemos recibido los comentarios para agregar esta función en actualizaciones futuras del servicio.  <br/> |No hay ninguna solución.  <br/> |30/8/2017  <br/> |
   
## <a name="related-topics"></a>See also

[Probar o comprar Audioconferencia en Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
