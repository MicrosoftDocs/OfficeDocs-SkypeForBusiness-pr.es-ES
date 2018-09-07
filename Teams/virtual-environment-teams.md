---
title: Ejecute Microsoft Teams en un entorno virtual
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 08/28/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: jaym
description: Obtenga información sobre cómo ejecutar Microsoft Teams en un entorno virtualizado.
localization_priority: Normal
search.appverid: MET150
ms.custom:
- Devices
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5a55dba95ee57738a708db1167288cc6bd210fc6
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "23858468"
---
<a name="run-microsoft-teams-in-a-virtual-environment"></a>Ejecute Microsoft Teams en un entorno virtual
============================================

En este artículo se describe los requisitos y limitaciones para el uso de los equipos en un entorno virtualizado.

El entorno de Infraestructura de escritorio virtual (VDI) se utiliza en algunas organizaciones donde los problemas de seguridad y cumplimiento son especialmente delicados. Los usuarios realizan su trabajo en un escritorio virtual que contiene todas sus aplicaciones de escritorio y los archivos que usan los servicios de escritorio remoto o una conexión remota similar. Dado que los equipos en el escritorio virtual no se ha optimizado para obtener acceso o utilizar los dispositivos de audio o vídeos en el dispositivo del usuario local (sin software adicional), trabajar en un entorno VDI tendrá normalmente desafíos relacionados con escenarios de multimedios como la llamada, llamada de vídeo, uso compartido de la pantalla, uso compartido de aplicaciones, co-autoría y mucho más. 

> [!NOTE]
> Las organizaciones pueden elegir ejecutar los equipos totalmente en VDI (mediante la aplicación Web o el cliente de escritorio), pero se recomienda que las siguientes directivas se establecen en desactivado, por lo que los usuarios no tienen una mala experiencia en un entorno virtualizado. Tenga en cuenta que puede tardar cierto tiempo propagar estos cambios de la directiva. Si no ve inmediatamente los cambios para una cuenta determinada, vuelva a intentarlo después unas cuantas horas. 

## <a name="calling"></a>Llamadas

Los cmdlets *CsTeamsCallingPolicy* permiten a los administradores control si al llamar a y las opciones de llamada en privado y charlas de grupo están habilitadas o no. 


|Nombre de la directiva |Descripción  |Valor recomendado  |
|---------|---------|---------|
|AllowPrivateCalling   |Controla si la aplicación de llamada está disponible en la columna izquierda del cliente para los equipos o no. También controla si los usuarios ven las opciones de llamadas y llamada de vídeo de chat privado. |Debe establecer en **False** para quitar la aplicación de llamada desde la columna izquierda y para quitar las opciones de llamadas y llamada de vídeo de chat privado. |

### <a name="powershell-instructions"></a>Instrucciones de PowerShell

1.  Inicie PowerShell como administrador.
2.  Conectarse al conector de Skype en línea:<br>
\>> *# Establecer el nombre de usuario de Office 365 y la contraseña*<br>
\>> *$username = "dirección de correo electrónico de admin"*<br>
\>> *$password = ConvertTo-SecureString "contraseña" - AsPlainText-Force*<br>
\>> *$LiveCred = nuevo objeto - typename System.Management.Automation.PSCredential - argumentlist $username, $password*<br><br>
\>> *# Conectarse a Skype en línea*<br>
\>> *Import-Module SkypeOnlineConnector*<br>
\>> *$sfboSession = New-CsOnlineSession-$LiveCred credenciales*<br>
\>> *Import-PSSession $sfboSession*<br>
3.  Ver la lista de opciones de directiva de llamada:<br>
\>> *Get-CsTeamsCallingPolicy*
4.  Busque la opción preestablecida donde se deshabilitan todas las directivas de llamada:<br>
![Captura de pantalla de opción de las reuniones con todas las directivas de reunión deshabilitado.](media/virtual-environment-image2.png)
5.  La opción de directiva preestablecido "DisallowCalling" se aplican a todos los usuarios que van a usar los equipos en un entorno virtualizado:<br>
\>> *GRANT-CsTeamsCallingPolicy - PolicyName DisallowCalling-Identity "user id de correo electrónico"*

## <a name="meetings"></a>Reuniones.

Los cmdlets *CsTeamsMeetingPolicy* permiten a los administradores controlar el tipo de las reuniones que los usuarios pueden crear o las características que puede tener acceso a mientras está en una reunión. También ayuda a determinar cómo abordar los problemas en las reuniones con usuarios anónimos o externos.

|Nombre de la directiva |Descripción  |Valor recomendado  |
|---------|---------|---------|
|AllowPrivateMeetingScheduling    |Determina si un usuario podrán programar reuniones privadas.         |Debe establecer en **False** para prohibir al usuario la posibilidad de programar reuniones privadas.         |
|AllowChannelMeetingScheduling     |Determina si un usuario podrán programar reuniones de canal.         |Debe establecer en **False** para prohibir al usuario la posibilidad de programar reuniones de canal.         |
|AllowMeetNow     |Determina si un usuario podrán crear o iniciar reuniones ad hoc.         |Debe establecer en **False** para prohibir al usuario la posibilidad de iniciar reuniones ad hoc.         |
|ScreenSharingMode     |Determina el modo en que un usuario podrán compartir la pantalla en las llamadas o reuniones.         |Establecerlo en **deshabilitado** para prohibir el usuario de uso compartido de sus pantallas.         |
|AllowIPVideo     |Determina si el vídeo está habilitado en las reuniones o las llamadas de un usuario.         |Debe establecer en **False** para prohibir al usuario de uso compartido de su vídeo.         |
|AllowAnonymousUsersToDialOut     |Determina si los usuarios anónimos pueden marcar un número RTC.         |Debe establecer en **False** para prohibir a los usuarios anónimos llamadas de salida.         |
|AllowAnonymousUsersToStartMeeting     |Determina si los usuarios anónimos pueden iniciar una reunión.         |Debe establecer en **False** para prohibir a ellos desde el inicio de una reunión.         |
|AllowOutlookAddIn     |Determina si un usuario puede programar reuniones de los equipos en el cliente de escritorio de Outlook.         |Debe establecer en **False** para prohibir a un usuario Programar reunión de los equipos cliente de Outlook.         |
|AllowParticipantGiveRequestControl     |Determina si los participantes pueden solicitar o ceder el control de uso compartido de la pantalla.         |Debe establecer en **False** para prohibir al usuario proporcionar, solicitar el control en una reunión.         |
|AllowExternalParticipantGiveRequestControl     |Determina si los participantes externos pueden solicitar o ceder el control de uso compartido de la pantalla.         |Debe establecer en **False** para prohibir a un usuario externo que proporciona, solicitar el control en una reunión.         |
|AllowPowerPointSharing     |Determina si se permite el uso compartido de PowerPoint en las reuniones de un usuario.         |Debe establecer en **True** para permitir.<br>Debe establecer en **False** para prohibir al usuario de uso compartido de archivos de PowerPoint en una reunión.         |
|AllowWhiteboard     |Determina si se permite la Pizarra en las reuniones de un usuario.         |Debe establecer en **False** para prohibir aplicación de pizarra en una reunión.         |
|AllowTranscription     |Determina si se permiten los títulos en tiempo real o posteriores a la reunión y transcripciones en las reuniones de un usuario.         |Debe establecer en **False** para prohibir la transcripción y títulos en una reunión.         |

### <a name="powershell-instructions"></a>Instrucciones de PowerShell

1.  Inicie PowerShell como administrador.
2.  Conectarse al conector de Skype en línea:<br>
\>> *# Establecer el nombre de usuario de Office 365 y la contraseña*<br>
\>> *$username = "dirección de correo electrónico de admin"*<br>
\>> *$password = ConvertTo-SecureString "contraseña" - AsPlainText-Force*<br>
\>> *$LiveCred = nuevo objeto - typename System.Management.Automation.PSCredential - argumentlist $username, $password*<br><br>
\>> *# Conectarse a Skype en línea*<br>
\>> *Import-Module SkypeOnlineConnector*<br>
\>> *$sfboSession = New-CsOnlineSession-$LiveCred credenciales*<br>
\>> *Import-PSSession $sfboSession*
3.  Ver la lista de opciones de directiva de reunión:<br>
\>> *Get-CsTeamsMeetingPolicy*
4.  Busque la opción preestablecida donde se deshabilitan todas las directivas de reunión:<br>
![Captura de pantalla de la llamada a la opción con todas las directivas de reunión deshabilitadas.](media/virtual-environment-image1.png)
5.  La opción de directiva preestablecido "AllOff" se aplican a todos los usuarios que van a usar los equipos en un entorno virtualizado:<br>
\>> *GRANT-CsTeamsMeetingPolicy - PolicyName AllOff-Identity "user id de correo electrónico"*

##<a name="known-limitations"></a>Limitaciones conocidas

Además de previosly de limitaciones de audio y vídeo que se mencionan, existen algunas limitaciones adicionales, es posible que se enfrentan los usuarios en entornos virtualizados:

- **Unirse a las reuniones creadas por otros usuarios.** Aunque las directivas anteriores restringen a los usuarios de la creación de las reuniones, podrán unirse a reuniones enviadas por otros usuarios. Dentro de estas reuniones, su capacidad para compartir vídeo, utilizar la Pizarra y otras características dependen de si el administrador deshabilita o no.

- **Problemas relacionados con el contenido almacenado en caché.** Si no se conserva el entorno virtual que se está ejecutando en los equipos (datos se limpian al final de cada sesión de usuario), los usuarios podrían observar la degradación del rendimiento debido al cliente de tener que volver a descargar todo el contenido nuevo, independientemente de si el usuario determinado tener acceso al mismo contenido en una sesión anterior. Impacto en el rendimiento puede reducirse mediante soluciones móviles de memoria caché, como los proporcionados por FSLogix.

Una vez que los equipos se ha optimizado para su uso en entornos de Escritorio Virtual, los administradores pueden revertir estas directivas y permitir a los usuarios utilizar los equipos como de costumbre.

         
        
        
        
        
        
        
        
        
        
        


