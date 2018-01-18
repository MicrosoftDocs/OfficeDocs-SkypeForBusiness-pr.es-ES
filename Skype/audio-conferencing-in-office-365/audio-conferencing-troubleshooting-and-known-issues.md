---
title: "Problemas conocidos y solución de conferencia de audio"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 72979911-5319-4de2-a275-4dd9a0f44fe6
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: "Obtener una lista de problemas conocidos al utilizar Microsoft como su proveedor de conferencia de acceso telefónico, el estado y algunas soluciones. "
ms.openlocfilehash: 2ceeb81de346b15ea606d1c343e34aa300b2cf59
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/15/2017
---
# <a name="audio-conferencing-troubleshooting-and-known-issues"></a>Problemas conocidos y solución de conferencia de audio

 **Este artículo es para Skype para usuarios de negocios y Teams de Microsoft mediante Microsoft como su proveedor de conferencia de audio. No se aplica a los clientes que utilizan un proveedor de conferencia de audio de terceros (ACP).**
  
## <a name="troubleshooting-and-known-issues"></a>Solución de problemas y problemas conocidos

Conferencias de audio que utiliza Microsoft como el proveedor de conferencia de audio tiene problemas actuales que se realiza un seguimiento son activamente investigado y potencialmente resolverán cuando la característica se ha actualizado en el futuro se libera de Office 365.
  
Por ahora, utilícelo como referencia cuando esté solucionando problemas potenciales con la obtención de conferencias de Audio, configurar y trabajar para las personas que usan el Skype para aplicaciones empresariales o Teams de Microsoft en su organización.
  
### <a name="microsoft-teams-app"></a>Aplicación de equipos de Microsoft

|**Problema**|**Comportamiento y los síntomas**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Los llamadores de RTC con el mismo "número desde" aparecen como el mismo usuario en la lista de reuniones.  <br/> |Cuando varios llamadores PSTN unirse a una reunión y sus identificadores de llamador se enmascaran como un solo número, se mostrará como un llamador única en la lista de reuniones.  <br/> |No hay ninguna solución.  <br/> |25/9/2017  <br/> |
|Panel de información de la reunión no aparece intermitentemente.  <br/> |Panel de información de la reunión no se puede mostrar en cliente de los equipos cuando los usuarios están intentando buscar para números de teléfono de puente de conferencia o el Id. de conferencia  <br/> |Ver detalles de la reunión o el calendario de Outlook para ver los números de teléfono de puente de conferencia o el Id. de conferencia  <br/> |25/9/2017  <br/> |
|Invitaciones a reuniones desde Outlook Add-in muestran caracteres ilegibles en coordenadas PSTN para configuraciones regionales fuera de Estados Unidos.  <br/> |Cuando se programan reuniones privadas utilizando Outlook Add-in para Microsoft Teams en un equipo con configuraciones regionales fuera de Estados Unidos, coordenadas PSTN pueden contener caracteres ilegibles.  <br/> |No hay ninguna solución.  <br/> |25/9/2017  <br/> |
|Marcar las necesidades para utilizar 5 dígitos o más.  <br/> |Los usuarios que intentan marcar desde una reunión necesitan escribir en 5 o más dígitos, aunque esté disponible para normalizar dígitos corto a E.164, regla de normalización de plan de marcado.  <br/> |Marcar escribiendo el número DID completo o el formato de número local en lugar del número de extensión interna.  <br/> |25/9/2017  <br/> |
|Dial de control no aparece intermitentemente.  <br/> |Dial de control puede no ser visible desde el panel de información de la reunión.  <br/> |No hay ninguna solución.  <br/> |25/9/2017  <br/> |
|Id. de conferencia estático no compatible para reuniones de Microsoft Teams.  <br/> |Si el admin reemplaza el valor predeterminado de Id. de conferencia dinámico al ID de conferencia estática, este valor no tiene efecto para las reuniones de Microsoft Teams. Vea [conferencias de Audio utilizando identificadores dinámicos en su organización](using-audio-conferencing-dynamic-ids-in-your-organization.md).  <br/> |No hay ninguna solución.  <br/> |25/9/2017  <br/> |
   
### <a name="skype-for-business-app"></a>Skype para el negocio de la aplicación

|**Problema**|**Comportamiento y los síntomas**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Notificaciones de entrada y salida se activan cuando se inicia una reunión, pero están desactivados breve tras la reunión comienza.  <br/> |De forma predeterminada, entrada y salida se deshabilitan para las reuniones donde los participantes unirse a desde ambos Skype para aplicaciones empresariales y cuando se conectan. Puede habilitar los anuncios en las **Opciones de la reunión de Skype** en el Skype para el negocio de la aplicación. Para una reunión, donde todos los participantes conectan y unirse a una reunión, notificaciones de entrada y salida están habilitadas de forma predeterminada como la lista de participantes no está disponible para cualquier participante. Cuando inició una reunión con sólo los participantes llamar en la entrada y salida notificaciones se activará, pero cuando un participante combinaciones utilizando un Skype para el negocio de la aplicación, las notificaciones será desactivada. Cuando se desactiva, se pueden habilitar las notificaciones mediante **Opciones de la reunión de Skype** en el Skype para el negocio de la aplicación. <br/> |No hay ninguna solución.  <br/> |8/30/2017  <br/> |
|Si un usuario que proveen la primera vez que se asigna una licencia E5, es posible que el correo de bienvenida de conferencia de Audio no entregará al usuario si el buzón no está habilitado.  <br/> |Si esto sucede, siempre puede reenviar la información de conferencia de audio del usuario utilizando **conferencias de Audio** en el Skype para el centro de administración de negocios o PowerShell. Consulte [Activar o desactivar el envío correos electrónicos cuando cambie la configuración de conferencia de Audio](enable-or-disable-sending-emails-when-their-settings-change.md).  <br/> **Nota:** Para reenviar la audioconferencia PIN al usuario, el PIN debe restablecerse. También puede hacerse mediante **conferencias de Audio** en el Skype para el centro de administración de negocios o mediante el uso de PowerShell.          |No hay ninguna solución.  <br/> |8/30/2017  <br/> |
|Llamadas de conferencia de audio pueden tardar hasta 24 horas para mostrar en los informes de uso.  <br/> |Esperamos hacer mejoras en esta área de servicio futuras actualizaciones.  <br/> |No hay ninguna solución.  <br/> |8/30/2017  <br/> |
|Cuando un llamador llama a un puente de conferencia después de la reunión ha sido bloqueada por un Skype para usuarios de empresa, no hay una notificación en el Skype para el negocio de la aplicación que se indica que el usuario está esperando en la sala.  <br/> |Esto es así por diseño actualmente, pero hemos tomado la retroalimentación con respecto a la compatibilidad con esta capacidad en las actualizaciones futuras del servicio.  <br/> |No hay ninguna solución.  <br/> |8/30/2017  <br/> |
   
## <a name="related-topics"></a>Temas relacionados

[Configurar Audioconferencia para Skype Empresarial y Microsoft Teams](set-up-audio-conferencing.md)
  

