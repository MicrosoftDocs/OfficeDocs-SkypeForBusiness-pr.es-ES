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
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'Obtenga una lista de problemas conocidos al usar Microsoft como su proveedor de conferencias de acceso telefónico local, su estado y algunas soluciones alternativas. '
ms.openlocfilehash: 13c493e16e5a6fef8b93b80d2a0e706f8f222ffa
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51111966"
---
# <a name="audio-conferencing-troubleshooting-and-known-issues"></a>Solución de problemas y problemas conocidos de Audioconferencia

 **Este artículo es para usuarios de Skype Empresarial que usan Microsoft como su proveedor de audioconferencias. No se aplica a los clientes que usan un proveedor de servicios de audioconferencia (ACP) de terceros.**
  
## <a name="troubleshooting-and-known-issues"></a>Solución de problemas y problemas conocidos

Las audioconferencias que usan Microsoft como proveedor de servicios de audioconferencia tienen problemas actuales que se están investigando y que se están investigando activamente y que se resolverán potencialmente cuando la característica se actualice en futuras versiones de Microsoft 365.
  
Por ahora, use esto como referencia cuando esté solucionando posibles problemas con la configuración de audioconferencias y trabajando para las personas que usan Skype Empresarial en su organización.

|**Problema**|**Comportamiento/síntomas**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Las notificaciones de entrada y salida están activadas cuando se inicia una reunión, pero se desactivarán poco después de que se inicie la reunión.  <br/> |De forma predeterminada, las notificaciones de entrada y salida están deshabilitadas para las reuniones en las que los participantes se unen desde las aplicaciones de Skype Empresarial y cuando llamen. Puede habilitar los anuncios en las Opciones de reunión **de Skype** en la aplicación de Skype Empresarial. Para una reunión donde todos los participantes llaman y se unen a la reunión, las notificaciones de entrada y salida están habilitadas de forma predeterminada ya que el registro de participantes no está disponible para ninguno de ellos. Cuando una reunión ha comenzado con solo los participantes que llaman, las notificaciones de entrada y salida se desactivarán, pero cuando un participante se una con una aplicación de Skype Empresarial, las notificaciones se desactivarán. Cuando está desactivada, las notificaciones se pueden habilitar de nuevo con Las opciones de reunión **de Skype** en la aplicación Skype Empresarial. <br/> |No hay ninguna solución.  <br/> |8/30/2017  <br/> |
|Si a un usuario se le aprovisiona la primera vez que se le asigna una licencia E5, es posible que el correo electrónico de bienvenida de audioconferencia no se entregue al usuario si el buzón no está habilitado.  <br/> |Si esto ocurre, siempre puede reenviar la información de audioconferencia del usuario mediante audioconferencias en el Centro de administración de Skype Empresarial o con PowerShell.  Vea Habilitar o deshabilitar el envío de correos electrónicos cuando cambie la [configuración de conferencias de audio.](enable-or-disable-sending-emails-when-their-settings-change.md)  <br/> **Nota:** Para volver a enviar el PIN de audioconferencia al usuario, el PIN debe restablecerse. Esto también se puede hacer mediante **audioconferencias** en el Centro de administración de Skype Empresarial o mediante PowerShell.          |No hay ninguna solución.  <br/> |8/30/2017  <br/> |
|Las llamadas de audioconferencia pueden tardar hasta 24 horas en mostrarse en los informes de uso.  <br/> |Estamos deseando realizar mejoras en esta área en futuras actualizaciones del servicio.  <br/> |No hay ninguna solución.  <br/> |8/30/2017  <br/> |
|Cuando un autor de la llamada llama a un puente de conferencia después de que un usuario de Skype Empresarial haya bloqueado la reunión, no hay una notificación en la aplicación de Skype Empresarial que indique que el usuario está esperando en la sala de espera.  <br/> |Esto se ha hecho deliberadamente, pero hemos recibido los comentarios para agregar esta función en actualizaciones futuras del servicio.  <br/> |No hay ninguna solución.  <br/> |8/30/2017  <br/> |
|Un usuario de Skype Empresarial Server (local) asignó la licencia de Audioconferencia antes del 1 de marzo de 2019, es posible que no vea las coordenadas de marcado en sus invitaciones a reuniones.  <br/> |El aprovisionamiento de usuarios de Skype Empresarial Server para las audioconferencias de Teams no se admite hasta esa fecha. Ahora es compatible y es un componente de [Reuniones Primero.](/microsoftteams/meetings-first) El usuario debe tener una licencia de Teams.  <br/> |Es necesario reactivar la canalización de aprovisionamiento. Quite la licencia de audioconferencia del usuario, espere un par de horas y vuelva a asignar la licencia.  <br/> |1/3/2019  <br/> |
   
## <a name="related-topics"></a>Temas relacionados

[Probar o comprar audioconferencias en Microsoft 365 u Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)