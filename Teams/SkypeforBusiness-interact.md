---
title: "Interacción entre Skype Empresarial y Microsoft Teams | Soporte técnico de Microsoft"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: overview
ms.service: msteams
description: "Conozca cómo interaccionan Skype Empresarial y Microsoft Teams, desde los chats hasta las llamadas."
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: 02d11632a0a6b8f78504ab20ae3415a942e6c91f
ms.sourcegitcommit: 9e217129451afae32eb3cd27fb3ee591874c29c9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
<a name="how-skype-for-business-and-microsoft-teams-interact"></a>Interacción entre Skype Empresarial y Microsoft Teams
===================================================

Si su organización usa actualmente Skype Empresarial, es importante que comprenda cómo interaccionarán Skype Empresarial y Microsoft Teams.

Cuando Microsoft Teams está disponible de manera general, la interoperabilidad básica entre Microsoft Teams y Skype Empresarial Online o Híbrido está disponible solo mediante mensajería instantánea de punto a punto (P2P).

El comportamiento predeterminado es que el cliente de Microsoft Teams iniciará sesión en los servicios back-end de Microsoft Teams y en los servicios de Skype Empresarial (enfoque de doble pila). El cliente de Microsoft Teams presentará solamente capacidades de MI para Skype Empresarial, así que al buscar un usuario de Microsoft Teams desde Skype Empresarial solo indicará el usuario como Solo MI. En el ejemplo de abajo, Alix Wilber ha iniciado sesión solamente en el cliente de Microsoft Teams.

![](media/Understand_how_Skype_for_Business_and_Microsoft_Teams_interact_image1.png)

En Microsoft Teams, los usuarios pueden buscar otros usuarios dentro de su organización que actualmente estén habilitados solo para Skype Empresarial y realizar sesiones de chat de mensajería instantánea.

Los usuarios de Skype Empresarial pueden responder los mensajes instantáneos, que se recibirán en la ventana de chat de Microsoft Teams.

![](media/Understand_how_Skype_for_Business_and_Microsoft_Teams_interact_image2.png)

Los usuarios de Microsoft Teams, si están habilitados también para Skype Empresarial, pueden iniciar sesión en Microsoft Teams y Skype Empresarial simultáneamente con sus propios clientes respectivos.

Se atenderá el último punto de conexión activo, de modo que si el usuario usa activamente Microsoft Teams, todos los mensajes instantáneos enviados desde un usuario de Skype Empresarial se recibirán en la ventana de chat de Microsoft Teams. Si el usuario está usando actualmente Skype Empresarial para recibir o realizar llamadas o acaba de terminar una llamada con Skype Empresarial y no ha vuelto al cliente de Microsoft Teams, los mensajes instantáneos entrantes enviados por un usuario de Skype Empresarial llegarán al cliente de Skype Empresarial, ya que este será el punto de conexión más activo.

Como Microsoft Teams solo admite actualmente interoperabilidad de mensajería instantánea de punto a punto (P2P) entre Skype Empresarial, cualquier llamada de audio o vídeo, o cualquier invitación para unirse a una reunión de Skype Empresarial (de cualquier tipo) desde otro usuario de Skype Empresarial llegará solo al cliente de Skype Empresarial. Esto ocurre también a la inversa: cualquier llamada de audio o vídeo, o cualquier invitación para unirse a una llamada en grupo (de cualquier tipo) desde el cliente de Microsoft Teams sólo llegará al cliente de Microsoft Teams.

Dado este comportamiento, los usuarios finales pueden usar cómodamente Microsoft Teams y Skype Empresarial a la vez, y controlar sus necesidades de comunicación específicas mediante la herramienta adecuada. Sin embargo, puede que sea necesario que el usuario final comprenda cómo funciona la interoperabilidad y cómo puede afectar a la experiencia del usuario final.


|  |  |
|---------|---------|
|![](media/Understand_how_Skype_for_Business_and_Microsoft_Teams_interact_image3.png)<br>Nota</br>      |Con la interoperabilidad de Skype Empresarial, los mensajes instantáneos que se reciben en Teams no se registrarán en el historial de conversaciones de Skype Empresarial.         |

Microsoft Teams ofrece a los usuarios la posibilidad de deshabilitar la interoperabilidad de Skype Empresarial desde la opción Notificaciones. Esta opción está controlada por el usuario, lo que permite a cada usuario decidir el comportamiento que prefiera.
