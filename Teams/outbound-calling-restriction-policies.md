---
title: Políticas de restricción de llamadas salientes para Audioconferencia y las llamadas RTC de usuario
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
description: Los administradores pueden controlar el tipo de conferencias de audio y llamadas RTC de usuarios finales que pueden realizar los usuarios.
ms.openlocfilehash: 830ab45178c10ab485d50aafd66a4bf5d4db9011
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41836890"
---
# <a name="outbound-calling-restriction-policies-for-audio-conferencing-and-user-pstn-calls"></a>Políticas de restricción de llamadas salientes para Audioconferencia y las llamadas RTC de usuario

Como administrador, puede usar los controles de llamadas salientes para restringir el tipo de audioconferencias y llamadas RTC del usuario final que pueden realizar los usuarios de su organización. 

Los controles de llamadas salientes se pueden aplicar en cada usuario y proporcionan los dos controles siguientes para restringir de forma independiente cada tipo de llamada saliente. De forma predeterminada, ambos controles se establecen para permitir llamadas salientes internacionales y nacionales. 

|Control|Descripción|Opciones de control|
|:-----|:-----|:-----|
|Llamadas RTC de audioconferencia|Restringe el tipo de salida </br>llamadas permitidas desde dentro de </br>reuniones organizadas por un usuario.|Internacional y nacional (predeterminado)</br>Nacionales</br>Ninguna|
|Llamadas RTC de usuarios finales|Restringe el tipo de llamadas </br>que puede realizar un usuario.|Internacional y nacional (predeterminado)</br>Nacionales</br>Ninguna|

   > [!NOTE]
   > Una llamada se considera nacional si el número marcado se encuentra en el mismo país en el que se ha configurado Office 365 para el organizador de la reunión (en el caso de las conferencias de audio) o el usuario final (en el caso de llamadas RTC de usuario final). 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="restrict-audio-conferencing-outbound-calls"></a>Restringir llamadas salientes de conferencias de audio 

![Un icono que muestra el logotipo](media/teams-logo-30x30.png) de Microsoft Teams **con el centro de administración de Microsoft Teams**

1. En el navegación de la izquierda, haga clic en **usuarios**y, a continuación, seleccione el usuario de la lista de usuarios disponibles.

2. En la parte superior de la página, haga clic en **Editar**.

3. Junto a **audioconferencia**, haga clic en **Editar**.

4. En **permisos de acceso telefónico de las reuniones**, seleccione la opción de restricción de llamada saliente que desee.

5. Haga clic en **Guardar **. 

![Un icono que muestra el logotipo](media/sfb-logo-30x30.png) de Skype empresarial **con el centro de administración de Skype empresarial**

1.  En el **centro de administración de Skype empresarial**, en el navegación de la izquierda, vaya a**usuarios**de **conferencias** > de audio y, a continuación, seleccione el usuario de la lista de usuarios disponibles.

2.  En el panel de acciones, haga clic en **Editar**.

3.  En **restricciones para las llamadas realizadas desde las reuniones de este usuario**, seleccione la opción de restricción de acceso telefónico que desee.

    ![Las restricciones de las opciones de marcado](media/restrictions-to-dial-outs.png)

5. Haga clic en **Guardar **.

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

**Usar PowerShell**

Las restricciones de llamadas salientes se controlan mediante una única directiva denominada OnlineDialOutPolicy que tiene un atributo de restricción para cada una de ellas. La Directiva no se puede personalizar, en lugar de que haya instancias de directiva predefinidas para cada combinación de configuración. 

Puede usar el cmdlet Get-CSOnlineDialOutPolicy para ver las directivas de llamadas salientes y asignarlas a los usuarios mediante el cmdlet Grant-CSDialOutPolicy. (Tenga en cuenta que el cmdlet Grant no contiene la palabra "conectado" como lo hace el cmdlet Get). 

En la tabla siguiente se proporciona una descripción general de cada Directiva.

|||
|:-----|:-----|
|Identity = ' etiqueta: DialoutCPCandPSTNInternational '    |    El usuario de la Conferencia puede llamar a números nacionales y internacionales, y este usuario también puede hacer llamadas salientes a números nacionales y internacionales.    |
|Identity = ' etiqueta: DialoutCPCDomesticPSTNInternational '  |    El usuario de la Conferencia solo puede llamar a números nacionales y este usuario puede hacer llamadas salientes a números nacionales e internacionales.    |
|    Identity = ' etiqueta: DialoutCPCDisabledPSTNInternational '    |    El usuario de la Conferencia no puede hacer llamadas. Este usuario puede hacer llamadas salientes a números internacionales y nacionales.    |
|    Identity = ' etiqueta: DialoutCPCInternationalPSTNDomestic '    |    El usuario de la Conferencia puede llamar a números nacionales y internacionales, y este usuario solo puede hacer llamadas salientes a un número de RTC nacional.    |
|    Identity = ' etiqueta: DialoutCPCInternationalPSTNDisabled '    |    El usuario de la Conferencia puede llamar a números nacionales y internacionales, y este usuario no puede hacer llamadas salientes a un número RTC además de números de emergencia.    |
|    Identity = ' etiqueta: DialoutCPCandPSTNDomestic '    |    El usuario de la Conferencia solo puede llamar a números nacionales y este usuario solo puede hacer llamadas salientes a números de RTC nacionales.    |
|    Identity = ' etiqueta: DialoutCPCDomesticPSTNDisabled '    |    El usuario de la Conferencia solo puede llamar a números nacionales y este usuario no puede realizar llamadas salientes a números de RTC además de números de emergencia.    |
|    Identity = ' etiqueta: DialoutCPCDisabledPSTNDomestic '    |    El usuario de la Conferencia no puede hacer llamadas, y este usuario solo puede hacer llamadas salientes a números RTC nacionales.    |
|    Identity = ' etiqueta: DialoutCPCandPSTNDisabled '    |    El usuario de la Conferencia no puede hacer llamadas, y este usuario no puede hacer llamadas salientes a un número de RTC además de números de emergencia.    |
