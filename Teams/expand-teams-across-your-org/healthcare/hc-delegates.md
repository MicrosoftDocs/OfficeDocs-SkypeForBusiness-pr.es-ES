---
title: Delegación de mensajes
author: jambirk
ms.author: jambirk
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
MS.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.reviewer: acolonna
description: Un usuario puede establecer explícitamente otro usuario como delegado en su mensaje de estado.
ms.openlocfilehash: be7092d2a68010d00a2d214f12bfe9011d44bbc5
ms.sourcegitcommit: 1786d4beccc8749e20709d2360d90e2bf7634925
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/20/2019
ms.locfileid: "35119487"
---
# <a name="set-a-delegate-in-a-status-message"></a>Establecer un delegado en un mensaje de estado

Un usuario ya puede definir de forma explícita su estado como ausente o no molestar, y proporcionar texto personalizado. La característica de delegación les permite @username mencionar a otro usuario en un mensaje de estado de texto y sugerir que, aunque no estén disponibles, los usuarios que deseen comunicarse con ellos se pongan en contacto con el @username Usuario mencionado. Alguien que intente ponerse en contacto con ellos puede mantener el mouse sobre el delegado nominado y enviarle un mensaje fácilmente.  La persona a la que se le ha asignado como delegado recibe la notificación de que se ha designado como delegado.

Este es un proceso iniciado por el usuario en el cliente, y no es necesario que intervenga el administrador.

## <a name="delegation-use-scenario-in-healthcare"></a>Escenario de uso de delegación en el cuidado de la salud

*Ejemplo de uso sin establecer delegados:*  Dr. Franco Piccio es una llamada en el Departamento de radiología. Recibe una llamada personal urgente y tiene que desplazarse por las próximas horas. Usted pide a uno de sus colegas en el Departamento de radiología, Dr. Lena Ehrle, que lo cubre mientras está fuera. Informando a su buscapersonas a Dr. Ehrle, que está escuchando mensajes urgentes y pings en el buscapersonas y responde a ellos en nombre de Dr. Piccio además de sus responsabilidades actuales. Es posible que otros miembros del equipo no se den cuenta de que la delegación informal se produjo, y confusiones se comparan con el cuidado de un paciente.

*Ejemplo de uso con la configuración de delegados:* Dr. Franco Piccio es una llamada en el Departamento de radiología. Recibe una llamada personal urgente y tiene que desplazarse por las próximas horas. Usted pide a uno de sus colegas en el Departamento de radiología, Dr. Lena Ehrle que lo cubra mientras está fuera. Cambia su mensaje de estado personalizado para que diga algo similar a "no estoy disponible durante las próximas horas. Comunícate @DrEhrle cualquier emergencia.  Otros miembros del equipo se dan cuenta de que la delegación se produjo porque está intentando ponerse en contacto con Dr. Piccio, por lo que ahora saben comunicarse con Dr. Ehrle mientras tanto. El cuidado de un paciente tiene poca o ninguna confusión.

## <a name="impact-of-co-existence-modes-on-user-status-in-the-teams-client"></a>Impacto de los modos de coexistencia en el estado del usuario en el cliente de Teams

Los administradores deben ser conscientes de que las menciones de las notas de estado y la delegación dependerán en parte del modo de coexistencia del usuario. Esta matriz muestra las posibilidades:

|Modo de coexistencia | Comportamiento esperado|
|---|---|
|TeamsOnly |Los usuarios solo pueden establecer una nota desde Teams. <br> La nota de Teams del usuario está visible en Teams & SfB. |
|Logra | La nota del usuario se establece en Teams visible solo en Teams. <br> La nota del usuario se establece en SfB visible solo en SfB |
|Modos SfB * | Los usuarios solo pueden establecer una nota desde SfB. <br> La nota de SfB del usuario está visible en los equipos de SfB &.  |
|||

Un usuario solo puede establecer una nota en Teams si su modo es TeamsOnly o islas.  

### <a name="displaying-notes-set-in-skype-for-business"></a>Mostrar notas establecidas en Skype empresarial
  
No hay ninguna indicación visual de que una nota se haya establecido desde Skype empresarial.

Skype empresarial no impone un límite de caracteres en las notas de estado. Microsoft Teams solo mostrará los primeros 280 caracteres de una nota establecida desde Skype empresarial. Una elipse (...) al final indica truncar.
  
Skype empresarial no admite tiempos de caducidad para las notas.

La migración de notas de Skype empresarial a teams no es compatible cuando un usuario se actualiza al modo TeamsOnly.

## <a name="configure-allowing-clients-to-use-delegates"></a>Configurar la posibilidad de que los clientes usen delegados

Esta característica no requiere configuración en el centro de administración de Microsoft Teams ni mediante PowerShell. En los espacios empresariales que lo admiten, está disponible de forma predeterminada en el cliente de Teams.

## <a name="related-topics"></a>Temas relacionados

[Coexistencia con Skype Empresarial](../../coexistence-chat-calls-presence.md)
