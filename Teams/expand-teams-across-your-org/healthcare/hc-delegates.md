---
title: Delegación de mensajes
author: dstrome
ms.author: dstrome
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: acolonna
description: Obtenga información sobre cómo un usuario con el estado ausente o no molestar puede establecer explícitamente otro usuario como delegado en su mensaje de estado.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 5fea05e8f316117ae711cc9f00da752c45959f2e
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2020
ms.locfileid: "43904742"
---
# <a name="message-delegation"></a>Delegación de mensajes

Un usuario ya puede definir de forma explícita su estado como ausente o no molestar, y proporcionar texto personalizado. La característica de delegación de mensajes funciona de la siguiente manera:

1. Un usuario @username mencione a otro usuario en un mensaje de estado de texto, lo que sugiere que no se les puede comunicar con ellos en su lugar, póngase en contacto con el @username Usuario mencionado.
2. La persona a la que se le ha asignado como delegado recibe la notificación de que se ha designado como delegado.
3. Alguien que está intentando ponerse en contacto con el primer usuario puede desplazar el puntero sobre el delegado nominado y enviarle fácilmente un mensaje al delegado.  

Este es un proceso iniciado por el usuario en el cliente, y no es necesario que intervenga el administrador para habilitar la característica. 

## <a name="delegation-use-scenario-in-healthcare"></a>Escenario de uso de delegación en el cuidado de la salud

*Ejemplo de uso sin establecer delegados:*  Dr. Franco Piccio es una llamada en el Departamento de radiología. Recibe una llamada personal urgente y tiene que desplazarse por las próximas horas. Usted pide a uno de sus colegas en el Departamento de radiología, Dr. Lena Ehrle, que lo cubre mientras está fuera. Informando a su buscapersonas a Dr. Ehrle, que está escuchando mensajes urgentes y pings en el buscapersonas y responde a ellos en nombre de Dr. Piccio además de sus responsabilidades actuales. Es posible que otros miembros del equipo no se den cuenta de que la delegación informal se produjo, y confusiones se comparan con el cuidado de un paciente.

*Ejemplo de uso con la configuración de delegados:* Dr. Franco Piccio es una llamada en el Departamento de radiología. Recibe una llamada personal urgente y tiene que desplazarse por las próximas horas. Usted pide a uno de sus colegas en el Departamento de radiología, Dr. Lena Ehrle que lo cubra mientras está fuera. Cambia su mensaje de estado personalizado para que diga algo similar a "no estoy disponible durante las próximas horas. Comunícate @DrEhrle cualquier emergencia.  Otros miembros del equipo se dan cuenta de que la delegación se produjo porque está intentando ponerse en contacto con Dr. Piccio, por lo que ahora saben comunicarse con Dr. Ehrle mientras tanto. El cuidado de un paciente tiene poca o ninguna confusión.

## <a name="impact-of-co-existence-modes-on-user-status-in-the-teams-client"></a>Impacto de los modos de coexistencia en el estado del usuario en el cliente de Teams

Los administradores deben tener en cuenta que los comportamientos de notas de estado y de la delegación dependen en parte del modo de coexistencia del usuario. Esta matriz muestra las posibilidades:

|Modo de coexistencia | Comportamiento esperado|
|---|---|
|TeamsOnly |Los usuarios solo pueden establecer una nota desde Teams. <br> La nota de Teams del usuario está visible en Teams & SfB. |
|Aplicaciones aisladas | La nota del usuario se establece en Teams visible solo en Teams. <br> La nota del usuario se establece en SfB visible solo en SfB |
|Modos SfB * | Los usuarios solo pueden establecer una nota desde SfB. <br> La nota de SfB del usuario está visible en los equipos de SfB &.  |
|||

Un usuario solo puede establecer una nota en Teams si su modo es TeamsOnly o islas.  

### <a name="displaying-notes-set-in-skype-for-business"></a>Mostrar notas establecidas en Skype empresarial
  
No hay ninguna indicación visual de que una nota se haya establecido desde Skype empresarial.

Skype empresarial no impone un límite de caracteres en las notas de estado. Microsoft Teams solo mostrará los primeros 280 caracteres de una nota establecida desde Skype empresarial. Una elipse (...) al final de una nota indica que se ha truncado.
  
Skype empresarial no admite tiempos de caducidad para las notas.

La migración de notas de Skype empresarial a teams no es compatible cuando un usuario se actualiza al modo TeamsOnly.

## <a name="related-topics"></a>Temas relacionados

[Coexistencia con Skype Empresarial](../../coexistence-chat-calls-presence.md)
