---
title: Directivas de restricción de llamada saliente para conferencias de Audio y usuario llamadas PSTN
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 2/12/2018
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: Los administradores pueden controlar el tipo de audio llamadas PSTN conferencias y el usuario final que se pueden realizar los usuarios.
ms.openlocfilehash: ab6f34e46ceb6a9811830ba1444278db667de73c
ms.sourcegitcommit: ffca287cf70db2cab14cc1a6cb7cea68317bedd1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/05/2018
---
# <a name="outbound-calling-restriction-policies-for-audio-conferencing-and-user-pstn-calls"></a>Directivas de restricción de llamada saliente para conferencias de Audio y usuario llamadas PSTN

Como administrador, puede utilizar controles de llamada saliente para restringir el tipo de usuario final y conferencias PSTN llamadas de audio de que se pueden realizar los usuarios de su organización. 

Controles de llamada saliente pueden aplicarse a cada usuario y proporcionan los siguientes dos controles para restringir de forma independiente cada tipo de llamadas salientes. De forma predeterminada, ambos controles están configurados para permitir llamadas salientes nacionales e internacionales. 

|Control|Descripción|Opciones de control|
|:-----|:-----|:-----|
|Llamadas de audio de conferencias PSTN|Restringe el tipo de salida </br>llamadas que se permiten desde dentro </br>reuniones organizadas por un usuario.|Internacional y nacional (predeterminado)</br>Nacionales</br>Ninguna|
|Usuario final las llamadas PSTN|Restringe el tipo de llamadas </br>que puede ser realizado por un usuario.|Internacional y nacional (predeterminado)</br>Nacionales</br>Ninguna|

   > [!NOTE]
   > Una llamada se determina como doméstica Si el número de teléfono al que llame se encuentra en el mismo país como el país en el que se ha establecido en Office 365 para el organizador de la reunión (en el caso de conferencias de audio) o el usuario final (en el caso de las llamadas PSTN usuario final). 


## <a name="restrict-audio-conferencing-outbound-calls"></a>Restringir las llamadas salientes de conferencia de audio 

**Utilizando los equipos de Microsoft y Skype para el centro de administración de negocios**

1. En la exploración de la izquierda, haga clic en **usuarios**y, a continuación, seleccione el usuario de la lista de usuarios disponibles.

2. En la parte superior de la página, haga clic en **Editar**.

3. Haga clic en el menú situado junto a **Los puentes de conferencia**y, a continuación, haga clic en **Editar** en la lista desplegable.

4. En el panel de **proveedor de puente de conferencia** , en **restricciones de marcado de salida de las reuniones de este usuario**, seleccione la opción de restricción de acceso telefónico de salida que desee.

5. Haga clic en **Aplicar**. 

Puede usar el Centro de administración de Skype Empresarial o Windows PowerShell para habilitar o deshabilitar el envío de correos electrónicos a los usuarios.

1.  En el **Skype para el centro de administración de negocios**, en la exploración de la izquierda, vaya a las **conferencias de Audio** > **usuarios**y, a continuación, seleccione el usuario de la lista de usuarios disponibles.

2.  En el panel de acciones, haga clic en **Editar**.

3.  En **restricciones de marcado de salida de las reuniones de este usuario**, seleccione la opción de restricción de acceso telefónico de salida que desee.

    ![Las restricciones a las opciones de acceso telefónico de salida](../images/restrictions-to-dial-outs.png)

5. Haga clic en **Guardar**.

**Uso de PowerShell**

Restricciones de llamadas salientes están controladas por una directiva única denominada OnlineDialOutPolicy que tiene un atributo de restricción para cada uno. No se puede personalizar la directiva, en su lugar, existen instancias de directivas predefinidas para cada combinación de la configuración. 

Puede utilizar el cmdlet Get-CSOnlineDialOutPolicy para ver las directivas llamadas salientes y asignarlos a los usuarios mediante el cmdlet de concesión CSDialOutPolicy. (Tenga en cuenta que el cmdlet de concesión no contiene la palabra "En línea" igual que el cmdlet Get.) 

En la siguiente tabla proporciona una visión general de cada directiva.

|||
|:-----|:-----|
|Identidad = 'etiqueta: DialoutCPCandPSTNInternational'    |    Usuario en la conferencia puede marcar a números nacionales e internacionales, y este usuario puede realizar también llamadas salientes a números nacionales e internacionales.    |
|Identidad = 'etiqueta: DialoutCPCDomesticPSTNInternational'  |    Sólo puede marcar el usuario en la conferencia a números nacionales, y este usuario puede realizar llamadas salientes a números nacionales e internacionales.    |
|    Identidad = 'etiqueta: DialoutCPCDisabledPSTNInternational'    |    Usuario de la conferencia no puede divisar cualquier marcado. Este usuario puede realizar llamadas salientes a números nacionales e internacionales.    |
|    Identidad = 'etiqueta: DialoutCPCInternationalPSTNDomestic'    |    Usuario en la conferencia puede marcar a números nacionales e internacionales, y este usuario sólo puede realizar llamadas salientes a número nacional de RTC.    |
|    Identidad = 'etiqueta: DialoutCPCInternationalPSTNDisabled'    |    Usuario en la conferencia puede marcar a números nacionales e internacionales, y este usuario no puede realizar llamadas salientes a número de RTC además de números de emergencia.    |
|    Identidad = 'etiqueta: DialoutCPCandPSTNDomestic'    |    Sólo puede marcar el usuario en la conferencia a números nacionales, y este usuario sólo puede realizar llamadas salientes a números nacionales de RTC.    |
|    Identidad = 'etiqueta: DialoutCPCDomesticPSTNDisabled'    |    Sólo puede marcar el usuario en la conferencia a números nacionales, y este usuario no puede realizar llamadas salientes a número de RTC además de números de emergencia.    |
|    Identidad = 'etiqueta: DialoutCPCDisabledPSTNDomestic'    |    Usuario en la conferencia no puede realizar ninguna llamada de salida, y este usuario sólo puede realizar llamadas salientes a números nacionales de RTC.    |
|    Identidad = 'etiqueta: DialoutCPCandPSTNDisabled'    |    Usuario en la conferencia no puede realizar ninguna llamada de salida, y este usuario no puede realizar llamadas salientes a número de RTC además de números de emergencia.    |
