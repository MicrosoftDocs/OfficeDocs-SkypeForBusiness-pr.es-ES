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
description: Obtenga información sobre cómo un usuario con el estado Ausente o No molestar puede establecer explícitamente a otro usuario como delegado en su mensaje de estado.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 967ed83f89d991ad001dbac9001d4d20b412efec80f0edb5bf4caca77e487a87
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54276535"
---
# <a name="message-delegation"></a>Delegación de mensajes

Un usuario ya puede establecer explícitamente su estado en "Ausente" o "No molestar" y proporcionar texto personalizado. La característica de delegación de mensajes funciona de la siguiente manera:

1. Un usuario @username menciona a otro usuario en parte de un mensaje de estado de texto, lo que indica que, aunque no estén disponibles, los usuarios que quieran ponerse en contacto con él, en su lugar se pondrán en contacto con el @username mencionado.
2. A la persona que ha sido designada como delegado será notificada de su nominación como delegado.
3. Alguien que intente ponerse en contacto con el primer usuario puede pasar el ratón por encima del delegado nominado y enviarle un mensaje fácilmente.  

Este es un proceso iniciado por el usuario en el cliente y no se requiere participación del administrador para habilitar la característica. 

## <a name="delegation-use-scenario-in-healthcare"></a>Escenario de uso de delegación en los cuidados de la salud

*Ejemplo de uso sin configurar delegados:*  el Dr. Franco Piccio está de llamadas en el departamento de rayos X. Recibe una llamada personal urgente y tiene que ausentarse durante las próximas dos horas. Le pide a uno de sus colegas del departamento de radioactividad, la Dra. Lena Ehrle, que lo cubra mientras está ausente. Le entrega de forma informal su localizador a la Dra. Ehrle, quien escucha mensajes urgentes y pings en el localizador y responde en nombre del Dr. Piccio, además cumplir con sus responsabilidades actuales. Es posible que otros miembros del equipo no se den cuenta de que ha sucedido una delegación informal y es seguro que habrá confusiones en el cuidado de un paciente,

*Ejemplo de uso con la configuración de delegados:* el Dr. Franco Piccio está de llamadas en el departamento de rayos X. Recibe una llamada personal urgente y tiene que ausentarse durante las próximas dos horas. Le pide a uno de sus compañeros del departamento de rayos X, la Dra. Lena Ehrle, que lo cubra mientras está ausente. Cambia su mensaje de estado personalizado para decir algo como: "No estoy disponible durante las próximas horas. Comuníquese con la @DrEhrle para cualquier emergencia".  Otros miembros del equipo se dan cuenta de que la delegación ocurrió cuando intentan ponerse en contacto con el Dr. Piccio, así que ahora saben que tienen que ponerse en contacto con la Dra. Ehrle durante este periodo. Prácticamente no hay confusiones en cuanto a cuidados del paciente.

## <a name="impact-of-co-existence-modes-on-user-status-in-the-teams-client"></a>Impacto de los modos de coexistencia en el estado del usuario en el cliente de Teams

Los administradores deben tener en cuenta que los comportamientos de las notas de estado y las menciones de delegación dependerán en parte del modo de coexistencia de un usuario. Esta matriz presenta las posibilidades siguientes:

|Modo de coexistencia | Comportamiento esperado|
|---|---|
|TeamsOnly |Los usuarios solo pueden establecer una nota desde Teams. <br> La nota de Equipos del usuario está visible en Teams y SfB. |
|Aplicaciones aisladas | Conjunto de notas del usuario establecido en Teams visible solo en Teams. <br> Conjunto de notas del usuario en SesB visible solo en Seb |
|Modos Sesb* | Los usuarios solo pueden establecer una nota desde SebaB. <br> La nota de SeB del usuario es visible en Sebab y Equipos.  |
|||

Un usuario solo puede establecer una nota en Teams si su modo es TeamsOnly o Aplicaciones aisladas.  

### <a name="displaying-notes-set-in-skype-for-business"></a>Mostrar notas establecidas en Skype Empresarial
  
No hay nada visual que indica que una nota se ha establecido desde Skype Empresarial.

Skype Empresarial no exige un límite de caracteres en las notas de estado. Microsoft Teams solo mostrará los primeros 280 caracteres de un conjunto de notas de Skype Empresarial. Unos puntos suspensivos (...) al final de una nota indican truncamiento.
  
Skype Empresarial no admite los tiempos de expiración para las notas.

La migración de notas de Skype Empresarial a Teams no se admite cuando un usuario se actualiza al modo TeamsOnly.

## <a name="related-topics"></a>Temas relacionados

[Coexistencia con Skype Empresarial](../../coexistence-chat-calls-presence.md)
