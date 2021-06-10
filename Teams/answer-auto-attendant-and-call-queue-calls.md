---
title: Responder llamadas de operador automático y cola de llamadas
ms.reviewer: colongma
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.date: 09/20/2018
ms.topic: conceptual
ms.service: msteams
description: Describe los operadores automáticos de la nube y las colas de llamadas, y explica cómo puede responder a estas llamadas en Teams.
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 3e1656af8ee457cb4c112d229c2dee03d2590ece
ms.sourcegitcommit: 36bc47b2b9ee0e738fa814c31accacfe816da4a3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2021
ms.locfileid: "52856379"
---
# <a name="answer-auto-attendant-and-call-queue-calls-directly-from-teams"></a>Responder al operador automático y llamar a la cola de llamadas directamente desde Teams

Teams usuarios pueden recibir y responder llamadas de operadores automáticos de la nube y colas de llamadas directamente desde su Teams cliente.

## <a name="what-are-auto-attendants-and-call-queues"></a>¿Qué son los operadores automáticos y las colas de llamadas?

Los operadores automáticos en la nube proporcionan una serie de mensajes de voz o un archivo de audio que los autores de llamadas escuchan en lugar de un operador humano cuando llaman a una organización. Un operador automático permite que los autores de llamadas se muevan por el sistema de menús, llamen y localicen a usuarios utilizando el teclado del teléfono (DTMF) o su propia voz gracias al reconocimiento de voz.

Las colas de llamadas en la nube incluyen saludos que se usan cuando alguien llama a un número de teléfono de su organización, la capacidad de poner automáticamente las llamadas en espera y la capacidad de buscar el siguiente agente de llamada disponible para controlar la llamada mientras las personas que llaman escuchan música en espera. Puede crear una o varias colas de llamadas para su organización.

## <a name="handling-an-auto-attendant-or-call-queue-call"></a>Administrar un operador automático o una llamada de cola de llamadas

Los usuarios podrán diferenciar las llamadas entrantes de un operador automático o una cola de llamadas antes de responder a la llamada. Junto con el nombre o el número del autor de la llamada, cada llamada incluirá información sobre a quién estaba intentando contactar el autor de la llamada, lo que proporciona a los usuarios un contexto mejor para dirigirse al autor de la llamada.

En la ilustración siguiente se muestra cómo se mostrará a un usuario una llamada entrante desde un operador automático o una cola de llamadas.

![Captura de pantalla de una notificación de llamada entrante](media/answer-auto-attendant-and-call-queue-calls-image1.png)

Una vez que se responde a un operador automático o llamada de cola de llamadas, el usuario puede procesar la llamada como cualquier otra llamada &#x2014; puede agregar o conferenciar en otro usuario o transferir la llamada a otra parte. Además, las llamadas de operador automático se reenviarán en función de la configuración del usuario.

> [!NOTE] 
> Las llamadas de cola de llamadas no se reenvía en función de la configuración del usuario. Esto es para asegurarse de que los autores de llamadas permanezcan en la cola hasta que un agente pueda responder a la llamada y el autor de la llamada no se reenvía inesperadamente.

> Los agentes no son notificados de las llamadas perdidas o mensajes de voz para las llamadas en cola de llamadas.

## <a name="supported-clients"></a>Clientes compatibles

El soporte para llamadas automáticas y de cola de llamadas está disponible en los clientes siguientes:

-    Cliente de Microsoft Teams para Windows (versiones de 32 y 64 bits)
-    Cliente de Microsoft Teams para Mac
-    Aplicación Microsoft Teams para iPhone
-    Aplicación Microsoft Teams para Android

## <a name="configure-auto-attendant-and-call-queue-support-for-microsoft-teams"></a>Configurar el operador automático y la cola de llamadas para Microsoft Teams

Para recibir llamadas automáticas de operador y cola de llamadas Microsoft Teams, debe configurar la directiva de interoperabilidad y la directiva de actualización. Revise Migración [e interoperabilidad para las organizaciones](migration-interop-guidance-for-teams-with-skype.md)que usan Teams junto con Skype Empresarial . Si no tiene configurado el operador automático o la cola de [](create-a-phone-system-auto-attendant.md) llamadas y quiere hacerlo, vea Configurar un operador automático en la nube y Crear una cola de llamadas en la [nube.](create-a-phone-system-call-queue.md)

## <a name="known-issues"></a>Problemas conocidos

Cuando un agente de la cola de llamadas recibe una llamada en su dispositivo móvil, las llamadas pueden estar en espera si el dispositivo está bloqueado. El usuario debe desbloquear el dispositivo primero y, a continuación, responder a la llamada.


## <a name="related-topics"></a>Temas relacionados

-    [¿Qué Sistema telefónico en Microsoft 365 o Office 365](what-is-phone-system-in-office-365.md)
-    [Crear una cola de llamadas en la nube](create-a-phone-system-call-queue.md)
-    [¿Qué son los operadores automáticos en la nube?](what-are-phone-system-auto-attendants.md)
-    [Configurar un operador automático en la nube](create-a-phone-system-auto-attendant.md)

