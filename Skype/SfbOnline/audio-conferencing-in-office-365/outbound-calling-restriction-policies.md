---
title: Políticas de restricción de llamadas salientes para Audioconferencia y las llamadas RTC de usuario
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
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
description: Los administradores pueden controlar el tipo de audioconferencias llamadas de RTC de conferencia y el usuario final que pueden realizar los usuarios.
ms.openlocfilehash: 6096816ef9fb98811ec3ebed5a56b90a90b58c29
ms.sourcegitcommit: 6207b98e8395f6c640b61cfb3f6c85d96520e33b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/20/2018
ms.locfileid: "22490579"
---
# <a name="outbound-calling-restriction-policies-for-audio-conferencing-and-user-pstn-calls"></a>Políticas de restricción de llamadas salientes para Audioconferencia y las llamadas RTC de usuario

Como administrador, puede usar los controles de llamada saliente para restringir el tipo de audioconferencias llamadas de RTC de conferencia y el usuario final que pueden realizar los usuarios de la organización. 

Controles de llamada saliente se pueden aplicar por usuario y proporcionan los siguientes dos controles para restringir cada tipo de llamadas salientes de forma independiente. De forma predeterminada, ambos controles están configurados para permitir llamadas salientes nacionales e internacionales. 

|Control|Descripción|Opciones de control|
|:-----|:-----|:-----|
|Llamadas de audio de conferencia RTC|Restringe el tipo de salida </br>llamadas que se permiten desde dentro </br>reuniones organizadas por un usuario.|Internacionales y nacionales (valor predeterminado)</br>Nacionales</br>Ninguna|
|Llamadas de RTC del usuario final|Restringe el tipo de llamadas </br>que puede ser realizados por un usuario.|Internacionales y nacionales (valor predeterminado)</br>Nacionales</br>Ninguna|

   > [!NOTE]
   > Una llamada se determina como nacionales si el número de teléfono llamada se encuentra en el mismo país como el país en el que se ha establecido en Office 365 para el organizador de la reunión (en el caso de conferencias de audio) o el usuario final (en el caso de las llamadas de RTC de usuario final). 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="restrict-audio-conferencing-outbound-calls"></a>Restringir las llamadas salientes de conferencias de audio 

![los equipos-logotipo-30x30.png](../images/teams-logo-30x30.png) **utilizando los equipos de Microsoft y Skype para el centro de administración de negocio**

1. En el panel de navegación izquierdo, haga clic en **usuarios**y, a continuación, seleccione el usuario de la lista de usuarios disponibles.

2. En la parte superior de la página, haga clic en **Editar**.

3. Junto a **Conferencias de Audio**, haga clic en **Editar**.

4. En **permisos de acceso telefónico de salida de las reuniones**, seleccione la opción de salida de la restricción que desee.

5. Haga clic en **Guardar**. 

![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **utilizando el Skype para el centro de administración de negocio**

1.  En el **Skype para el centro de administración de negocio**, en el panel de navegación izquierdo, vaya a la **conferencia de Audio** > **a los usuarios**y, a continuación, seleccione el usuario de la lista de usuarios disponibles.

2.  En el panel de acciones, haga clic en **Editar**.

3.  En **las restricciones de marcado-outs de reuniones de este usuario**, seleccione la opción de salida de la restricción que desee.

    ![Las restricciones a las opciones de marcado-outs](../images/restrictions-to-dial-outs.png)

5. Haga clic en **Guardar**.

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

**Uso de PowerShell**

Restricciones de llamadas salientes se controlan mediante una sola directiva denominada OnlineDialOutPolicy que tiene un atributo de restricción para cada uno. No se puede personalizar la directiva, en su lugar hay instancias de directiva predefinidas para cada combinación de la configuración. 

Puede usar el cmdlet Get-CSOnlineDialOutPolicy para ver las directivas llamadas salientes y asignar a los usuarios mediante el cmdlet Grant-CSDialOutPolicy. (Tenga en cuenta que el cmdlet Grant no contiene la palabra "En línea" al igual que el cmdlet Get.) 

En la siguiente tabla proporciona una visión general de cada directiva.

|||
|:-----|:-----|
|Identidad = 'etiqueta: DialoutCPCandPSTNInternational'    |    Números internacionales y nacionales puede marcar un usuario en la conferencia, y este usuario también puede efectuar llamadas salientes a números internacionales y nacionales.    |
|Identidad = 'etiqueta: DialoutCPCDomesticPSTNInternational'  |    Usuario en la conferencia puede marcar un sólo a los números nacionales, y este usuario puede realizar llamadas a números internacionales y nacionales.    |
|    Identidad = 'etiqueta: DialoutCPCDisabledPSTNInternational'    |    Usuario en la conferencia no puede realizar cualquier marcado. Este usuario puede realizar llamadas a números internacionales y nacionales.    |
|    Identidad = 'etiqueta: DialoutCPCInternationalPSTNDomestic'    |    Números internacionales y nacionales puede marcar un usuario en la conferencia, y este usuario solo puede realizar llamadas salientes a número nacional de RTC.    |
|    Identidad = 'etiqueta: DialoutCPCInternationalPSTNDisabled'    |    Números internacionales y nacionales puede marcar un usuario en la conferencia, y este usuario no puede realizar llamadas salientes al número de RTC además de los números de emergencias.    |
|    Identidad = 'etiqueta: DialoutCPCandPSTNDomestic'    |    Usuario en la conferencia puede marcar un sólo a los números nacionales, y este usuario solo puede realizar llamadas salientes a los números de RTC nacionales.    |
|    Identidad = 'etiqueta: DialoutCPCDomesticPSTNDisabled'    |    Usuario en la conferencia puede marcar un sólo a los números nacionales, y este usuario no puede realizar llamadas salientes al número de RTC además de los números de emergencias.    |
|    Identidad = 'etiqueta: DialoutCPCDisabledPSTNDomestic'    |    Usuario en la conferencia no puede realizar cualquier llamadas salientes, y este usuario solo puede realizar llamadas salientes a los números de RTC nacionales.    |
|    Identidad = 'etiqueta: DialoutCPCandPSTNDisabled'    |    Usuario en la conferencia no puede realizar cualquier llamadas salientes, y este usuario no puede realizar llamadas salientes al número de RTC además de los números de emergencias.    |
