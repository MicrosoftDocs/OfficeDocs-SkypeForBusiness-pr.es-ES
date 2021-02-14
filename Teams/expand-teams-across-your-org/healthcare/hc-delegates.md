---
title: Delegación de mensajes
author: dstrome
ms.author: dstrome
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.reviewer: acolonna
description: Obtenga información sobre cómo un usuario con el estado No molestar o con el estado No molestar puede establecer explícitamente a otro usuario como delegado en su mensaje de estado.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: ac23afbea7f452967718a8c2d86fd4d36584492d
ms.sourcegitcommit: 62d5ccf10202a50755166e3b8de0bd31d1f94fef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/28/2020
ms.locfileid: "48790472"
---
# <a name="message-delegation"></a>Delegación de mensajes

Un usuario ya puede establecer explícitamente su estado en "No molestar" o "No molestar" y proporcionar texto personalizado. La característica de delegación de mensajes funciona de la siguiente manera:

1. Un usuario @username menciona a otro usuario en parte de un mensaje de estado de texto, lo que sugiere que, aunque no estén disponibles, los usuarios que deban ponerse en contacto con él en su lugar se pondrán en contacto con el @username mencionado.
2. A la persona que se le ha asignado como delegado se le notifica que se le ha nominado para ser delegado.
3. Alguien que está intentando ponerse en contacto con el primer usuario puede mantener el puntero sobre el delegado nominado y, en su lugar, enviar mensajes fácilmente al delegado.  

Se trata de un proceso iniciado por el usuario en el cliente y no es necesaria la participación del administrador para habilitar la característica. 

## <a name="delegation-use-scenario-in-healthcare"></a>Escenario de uso de la delegación en el sector sanitario

*Ejemplo de uso sin configurar delegados:*  El Dr. Franco Piccio está en llamada en el departamento de radioactividad. Recibe una llamada personal urgente y debe alejerse durante las próximas horas. Le pide a uno de sus compañeros del departamento de radiología, el Dr. Lena Ehrle, que lo cubra mientras está desaparecido. Informalmente, entrega su página al Dr. Ehrle, que escucha mensajes urgentes y hace ping al pager y los responde en nombre del Dr. Piccio, además de sus responsabilidades actuales. Es posible que otros miembros del equipo no se percatan de que ha sucedido una delegación informal y se está confusión en la atención de un paciente.

*Ejemplo de uso con la configuración de delegados:* El Dr. Franco Piccio está en llamada en el departamento de radioactividad. Recibe una llamada personal urgente y debe alejerse durante las próximas horas. Le pide a uno de sus compañeros del departamento de radiología, el Dr. Lena Ehrle que lo cubra mientras está desaparecido. Cambia su mensaje de estado personalizado para decir algo similar a "No estoy disponible para las próximas horas. Póngase en contacto @DrEhrle emergencia".  Los demás miembros del equipo se percatan de que la delegación se ha producido al intentar ponerse en contacto con el Dr. Piccio, para que ahora sepan que se debe comunicar con el Dr. Ehrle mientras tanto. Poco o ninguna confusión se ve con la atención de un paciente.

## <a name="impact-of-co-existence-modes-on-user-status-in-the-teams-client"></a>Impacto de los modos de coexistencia en el estado del usuario en el cliente de Teams

Los administradores deben tener en cuenta que las notas de estado y los comportamientos de las menciones de delegación dependerán en parte del modo coexistencia de un usuario. Esta matriz le muestra las posibilidades:

|Co-Existence privado | Comportamiento esperado|
|---|---|
|TeamsOnly |Los usuarios solo pueden establecer una nota desde Teams. <br> La nota de Teams del usuario está visible en Teams & SfB. |
|Aplicaciones aisladas | El conjunto de notas del usuario en Teams solo se puede ver en Teams. <br> El conjunto de notas del usuario en SfB solo visible en SfB |
|Modos sfB* | Los usuarios pueden establecer una nota solo desde SfB. <br> La nota de SfB del usuario está visible en SfB & Teams.  |
|||

Un usuario solo puede establecer una nota en Teams si su modo es TeamsOnly o Islas.  

### <a name="displaying-notes-set-in-skype-for-business"></a>Mostrar notas configuradas en Skype Empresarial
  
No hay ninguna indicación visual de que skype empresarial haya establecido una nota.

Skype Empresarial no aplica un límite de caracteres a las notas de estado. Microsoft Teams solo mostrará los primeros 280 caracteres de un conjunto de notas de Skype Empresarial. Los puntos suspensivos (...) al final de una nota indican truncamiento.
  
Skype Empresarial no admite la caducidad de las notas.

La migración de notas de Skype Empresarial a Teams no se admite cuando un usuario se actualiza al modo TeamsOnly.

## <a name="related-topics"></a>Temas relacionados

[Coexistencia con Skype Empresarial](../../coexistence-chat-calls-presence.md)
