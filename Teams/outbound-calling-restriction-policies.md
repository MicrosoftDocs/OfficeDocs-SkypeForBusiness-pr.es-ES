---
title: 'Restricciones de llamadas salientes: Audioconferencia & llamadas RTC'
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: Los administradores pueden controlar el tipo de audioconferencia y las llamadas RTC de usuario final que pueden realizar los usuarios.
ms.openlocfilehash: e085f996226a59d88339b20e64dd06f68ef566ce
ms.sourcegitcommit: ee217e1d7188842c7becd19387fd421b485c3575
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2020
ms.locfileid: "48908659"
---
# <a name="outbound-calling-restriction-policies-for-audio-conferencing-and-user-pstn-calls"></a>Políticas de restricción de llamadas salientes para Audioconferencia y las llamadas RTC de usuario

Como administrador, puede usar los controles de llamadas salientes para restringir el tipo de audioconferencias y llamadas RTC del usuario final que pueden realizar los usuarios de su organización. 

Los controles de llamada saliente se pueden aplicar por usuario y proporcionar los siguientes dos controles para restringir de forma independiente cada tipo de llamadas salientes. De forma predeterminada, ambos controles se establecen para permitir llamadas internacionales y nacionales salientes. 

|Control|Descripción|Opciones de control|
|:-----|:-----|:-----|
|Llamadas RTC de Audioconferencia|Restringe el tipo de salida </br>llamadas que se permiten desde dentro </br>reuniones organizadas por un usuario.|Cualquier destino (predeterminado)</br>En el mismo país o región que el organizador </br> [Solo países o regiones de la zona A](audio-conferencing-zones.md) </br>No permitir|
|Llamadas RTC de usuario final|Restringe el tipo de llamadas </br>que puede realizar un usuario.|Internacional y nacional (predeterminado)</br>Nacionales</br>Ninguna|

Para averiguar qué países y regiones se consideran zona A, vea zonas de país y [región para Audioconferencia.](audio-conferencing-zones.md)

   > [!NOTE]
   > Una llamada se considera nacional si el número marcado se encuentra en el mismo país donde se ha configurado Microsoft 365 u Office 365 para el organizador de la reunión (en el caso de las audioconferencias) o el usuario final (en el caso de las llamadas RTC del usuario final). 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="restrict-audio-conferencing-outbound-calls"></a>Restringir las llamadas salientes de audioconferencia

![Un icono que muestra el logotipo de Microsoft Teams](media/teams-logo-30x30.png) **Usando el centro de administración de Microsoft Teams**

1. En el panel de navegación izquierdo, **haga** clic en Usuarios y, a continuación, haga clic en el nombre para mostrar del usuario en la lista de usuarios disponibles.

3. Junto a **Audioconferencia,** haga clic en **Editar.**

4. En **Llamar desde las reuniones,** seleccione la opción de restricción de acceso telefónico que desee.

5. Haga clic en **Guardar**. 

![Icono que muestra el logotipo de Skype Empresarial](media/sfb-logo-30x30.png) **Usar el Centro de administración de Skype Empresarial**

1. En el **Centro de administración** de Skype Empresarial, en el panel de navegación izquierdo, vaya a Usuarios de **Audioconferencia** y, a continuación, seleccione el usuario en la lista  >  de usuarios disponibles.

2. En el panel de acciones, haga clic en **Editar**.

3.  En **Restricciones a las llamadas desde las reuniones** de este usuario, seleccione la opción de restricción de acceso telefónico que desee.

      ![Las restricciones a las opciones de acceso telefónico](media/restrictions-to-dial-outs.png)
      

4. Haga clic en **Guardar**.

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

**Con PowerShell**

Las restricciones de llamada saliente se controlan mediante una sola directiva denominada OnlineDialOutPolicy, que tiene un atributo de restricción para cada uno. La directiva no se puede personalizar, sino que hay instancias de directiva predefinidas para cada combinación de la configuración. 

Puede usar el cmdlet Get-CSOnlineDialOutPolicy para ver las directivas de llamadas salientes y asignarlas a los usuarios mediante el cmdlet Grant-CSDialOutPolicy cmdlet. (Tenga en cuenta que el cmdlet Grant no contiene la palabra "En línea" como lo hace el cmdlet Get). 

En la tabla siguiente se proporciona información general de cada directiva.

|||
|:-----|:-----|
|Identity='tag:DialoutCPCandPSTNInternational'    |    Los usuarios de la conferencia pueden llamar a números nacionales e internacionales, y este usuario también puede realizar llamadas a números nacionales e internacionales.    |
|Identity='tag:DialoutCPCDomesticPSTNInternational'  |    Los usuarios de la conferencia solo pueden llamar a números nacionales y este usuario puede realizar llamadas a números nacionales e internacionales.    |
|    Identity='tag:DialoutCPCDisabledPSTNInternational'    |    El usuario de la conferencia no puede realizar ninguna llamada. Este usuario puede realizar llamadas a números nacionales e internacionales.    |
|    Identity='tag:DialoutCPCInternationalPSTNDomestic'    |    El usuario de la conferencia puede llamar a números nacionales e internacionales, y este usuario solo puede realizar llamadas salientes a números RTC nacionales.    |
|    Identity='tag:DialoutCPCInternationalPSTNDisabled'    |    El usuario de la conferencia puede llamar a números nacionales e internacionales, y este usuario no puede realizar llamadas a números RTC además de números de emergencia.    |
|    Identity='tag:DialoutCPCandPSTNDomestic'    |    Los usuarios de la conferencia solo pueden llamar a números nacionales y este usuario solo puede realizar llamadas a números RTC nacionales.    |
|    Identity='tag:DialoutCPCDomesticPSTNDisabled'    |    Los usuarios de la conferencia solo pueden llamar a números nacionales y este usuario no puede realizar llamadas a números RTC además de números de emergencia.    |
|    Identity='tag:DialoutCPCDisabledPSTNDomestic'    |    El usuario de la conferencia no puede realizar ninguna llamada, y este usuario solo puede realizar una llamada saliente a números RTC nacionales.    |
|    Identity='tag:DialoutCPCandPSTNDisabled'    |    El usuario de la conferencia no puede realizar ninguna llamada y este usuario no puede realizar llamadas salientes a un número RTC además de a los números de emergencia.    |
|    Identity='tag:DialoutCPCZoneAPSTNInternational'    |    El usuario de la conferencia solo puede llamar a países y regiones de la zona A, y este usuario puede realizar llamadas [salientes](audio-conferencing-zones.md)a números nacionales e internacionales.    |
|    Identity='tag:DialoutCPCZoneAPSTNDomestic'    |    El usuario de la conferencia solo puede llamar a países y regiones de la zona A, y este usuario solo puede realizar llamadas [salientes](audio-conferencing-zones.md)a un número RTC nacional.    |
|    Identity='tag:DialoutCPCZoneAPSTNDisabled'    |    El usuario de la conferencia solo puede llamar a países y regiones de la zona A, y este usuario no puede realizar llamadas [salientes](audio-conferencing-zones.md)a números de RTC además de números de emergencia.    |
