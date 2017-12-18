---
title: "Problemas conocidos y solución de problemas de conferencias audio"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/9/2017
ms.audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- DianeF_Adm_Simplified
ms.assetid: 72979911-5319-4de2-a275-4dd9a0f44fe6

description: "Get a list of known isses when using Microsoft as their dial-in conference provider, status, and some work arounds. "
---

# Problemas conocidos y solución de problemas de conferencias audio

> [!IMPORTANT]
> Este artículo se ha traducido con traducción automática; vea la declinación de responsabilidades.  
  
 **Este artículo es para Skype para usuarios de empresa y Microsoft Teams usando Microsoft como su proveedor de servicios de audioconferencia. No se aplica a los clientes que usan un proveedor de servicios de audioconferencia de terceros (ACP).**
  
## Problemas conocidos y solución de problemas

Conferencias de audio que usa Microsoft como el proveedor de servicios de audioconferencia tiene problemas actuales que se controlan son conocidas investigar y se potencialmente resolverá cuando la característica se actualiza en futuras versiones de Office 365.
  
Por ahora, use esto como una referencia al solucionar posibles problemas con la configuración de conferencias de Audio, configurar y su funcionamiento para las personas que usan el Skype para empresas o Microsoft Teams aplicaciones de su organización.
  
### Aplicación de equipos de Microsoft

|**Problema**|**Comportamiento/síntomas**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Las personas que llaman de RTC con el mismo "número de" se muestran como el mismo usuario en la lista de la reunión.  <br/> |Cuando varios autores de llamadas de RTC unirse a una reunión y sus identificadores de llamada se enmascaran como un único número, se muestran como un único llamador en la lista de reuniones.  <br/> |No hay ninguna solución.  <br/> |25/9/2017  <br/> |
|Panel de información de la reunión no se muestra forma intermitente.  <br/> |Panel de información de la reunión puede no mostrar en el cliente de equipos cuando los usuarios intentan buscar números de teléfono del puente de conferencia o el identificador de conferencia.  <br/> |Ver los detalles de la reunión o el calendario de Outlook para ver los números de teléfono del puente de conferencia o el identificador de conferencia.  <br/> |25/9/2017  <br/> |
|Invitaciones a reuniones de complemento de Outlook, muestran caracteres extraños en coordenadas de RTC para las configuraciones regionales de EE.  <br/> |Durante la programación de reuniones privadas con complemento de Outlook para Microsoft Teams en un equipo con configuraciones regionales EE, RTC coordenadas podrán contienen caracteres incorrectos.  <br/> |No hay ninguna solución.  <br/> |25/9/2017  <br/> |
|Marcar debe utilizar 5 dígitos o más.  <br/> |Intenta marcar desde una reunión de usuarios necesitan escribir en dígitos de 5 o más, aunque también está disponible para normalizar dígitos breve a E.164 regla de normalización del plan de marcado.  <br/> |Marcar escribiendo el número DID completo o el formato de número local en lugar del número de extensión internos.  <br/> |25/9/2017  <br/> |
|Acceso telefónico control no se muestra forma intermitente.  <br/> |Acceso telefónico control no podrán ver desde el panel de información de la reunión.  <br/> |No hay ninguna solución.  <br/> |25/9/2017  <br/> |
|Identificador de conferencia estático no compatible para las reuniones de Microsoft Teams.  <br/> |Si el administrador reemplaza la configuración predeterminada de Id. de conferencia dinámico identificador de conferencia estática, esta configuración no entra en vigor para las reuniones de Microsoft Teams. Vea [Uso de los identificadores dinámicos de conferencias de Audio de su organización](using-audio-conferencing-dynamic-ids-in-your-organization.md).  <br/> |No hay ninguna solución.  <br/> |25/9/2017  <br/> |
   
### Skype empresarial

|**Problema**|**Comportamiento/síntomas**|**Solución conocida**|**Fecha de descubrimiento**|
|:-----|:-----|:-----|:-----|
|Notificaciones de entrada y salida están activadas cuando se inicia una reunión, pero están desactivados breve tras el inicio de la reunión.  <br/> |De forma predeterminada, las notificaciones de entrada y salida están deshabilitadas para las reuniones en unirse los participantes de ambas Skype para empresas y cuándo llamar en. Puede habilitar los anuncios de las **Opciones de reunión de Skype** en la Skype empresarial. Para una reunión, donde todos los participantes acceso telefónico y unirse a una reunión, notificaciones de entrada y salida están habilitadas de forma predeterminada como la lista de participantes no está disponible para cualquier participante. Cuando haya empezado una reunión con solo los participantes de una llamada, la entrada y salida notificaciones se activará, pero cuando un participante combinaciones utilizando un Skype empresarial, las notificaciones estará desactivado. Cuando se desactiva, se pueden habilitar las notificaciones mediante **Opciones de reunión de Skype** en la Skype empresarial. <br/> |No hay ninguna solución.  <br/> |30/8/2017  <br/> |
|Si un usuario aprovisiona la primera vez que se asigna una licencia E5, es posible que el mensaje de bienvenida de conferencias de Audio no se ha entregado al usuario si no se ha habilitado el buzón.  <br/> |Si esto sucede, siempre puede volver a enviar la información de conferencias de audio del usuario usando las **conferencias de Audio** en la Skype centro de administración de la empresa o con PowerShell. Vea[Habilitar o deshabilitar el envío de correos electrónicos cuando cambie la configuración de conferencias de Audio](enable-or-disable-sending-emails-when-audio-conferencing-settings-change.md).  <br/> > [!NOTE]> Para volver a enviar el PIN de conferencia de audio para el usuario, el PIN debe restablecer. También puede hacerse mediante **conferencias de Audio** en la Skype centro de administración de la empresa o con PowerShell.          |No hay ninguna solución.  <br/> |30/8/2017  <br/> |
|Llamadas de conferencia de audio podrían tardar hasta 24 horas para mostrar en los informes de uso.  <br/> |Esperamos realizar mejoras en esta área de servicio futuras actualizaciones.  <br/> |No hay ninguna solución.  <br/> |30/8/2017  <br/> |
|Cuando una persona llama a un puente de conferencia después de la reunión se ha bloqueado por un usuario Skype Empresarial, no hay una notificación en la aplicación de Skype Empresarial que indica que el usuario está en espera en la sala de espera.  <br/> |Esto se ha hecho deliberadamente, pero hemos recibido los comentarios para agregar esta función en actualizaciones futuras del servicio.  <br/> |No hay ninguna solución.  <br/> |30/8/2017  <br/> |
   
## Temas relacionados

[Configurar conferencias de Audio de Skype para la empresa y Teams de Microsoft](set-up-audio-conferencing-for-skype-for-business-and-microsoft-teams.md)
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Declinación de responsabilidades de traducción automática**: Este artículo se ha traducido con un sistema informático sin intervención humana. Microsoft ofrece estas traducciones automáticas para que los hablantes de otros idiomas distintos del inglés puedan disfrutar del contenido sobre los productos, los servicios y las tecnologías de Microsoft. Puesto que este artículo se ha traducido con traducción automática, es posible que contenga errores de vocabulario, sintaxis o gramática. 
  

