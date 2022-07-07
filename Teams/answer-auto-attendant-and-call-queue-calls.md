---
title: Responder a llamadas del operador automático y de la cola de llamadas
ms.reviewer: colongma
author: CarolynRowe
ms.author: crowe
manager: serdars
audience: ITPro
ms.date: 09/20/2018
ms.topic: conceptual
ms.service: msteams
description: Describe operadores automáticos en la nube y colas de llamadas, y explica cómo puede responder estas llamadas en Teams.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 1a9058dbd583c9d795d04f27b43995c75095e80d
ms.sourcegitcommit: 90f03a841f8ca33092dce65c543357c7c2f7b82a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2022
ms.locfileid: "66647672"
---
# <a name="answer-auto-attendant-and-call-queue-calls-directly-from-teams"></a>Responder al operador automático y llamar a la cola de llamadas directamente desde Teams

Los usuarios de Teams pueden recibir y responder llamadas de operadores automáticos en la nube y colas de llamadas directamente desde su cliente de Teams.

## <a name="what-are-auto-attendants-and-call-queues"></a>¿Qué son los operadores automáticos y las colas de llamadas?

Los operadores automáticos en la nube proporcionan una serie de mensajes de voz o un archivo de audio que los autores de llamadas escuchan en lugar de un operador humano cuando llaman a una organización. Un operador automático permite que los autores de llamadas se muevan por el sistema de menús, llamen y localicen a usuarios utilizando el teclado del teléfono (DTMF) o su propia voz gracias al reconocimiento de voz.

Las colas de llamadas en la nube incluyen saludos que se usan cuando alguien llama a un número de teléfono de su organización, la capacidad de poner automáticamente las llamadas en espera y la posibilidad de buscar el siguiente agente de llamadas disponible para administrar la llamada mientras las personas que llaman escuchan música en espera. Puede crear una o varias colas de llamadas para su organización.

## <a name="handling-an-auto-attendant-or-call-queue-call"></a>Administrar un operador automático o una llamada en cola de llamadas

Los usuarios podrán diferenciar las llamadas entrantes de un operador automático o de una cola de llamadas antes de responder a la llamada. Junto con el nombre o el número del autor de la llamada, cada llamada incluirá información sobre a quién estaba intentando ponerse en contacto el autor de la llamada, lo que proporciona a los usuarios un mejor contexto para dirigirse al autor de la llamada.

En la ilustración siguiente se muestra cómo se mostrará una llamada entrante de un operador automático o una cola de llamadas a un usuario.

![Captura de pantalla de una notificación de llamada entrante.](media/answer-auto-attendant-and-call-queue-calls-image1.png)

Una vez que se responde a un operador automático o a una llamada en cola de llamadas, el usuario puede procesar la llamada como cualquier otra llamada &#x2014; puede agregar o conferencia en otro usuario o transferir la llamada a otra parte. Además, las llamadas del operador automático se desviarán en función de la configuración del usuario.

> [!NOTE] 
> Las llamadas de la cola de llamadas no se desvía según la configuración de las reglas de respuesta de llamadas del usuario. Esto garantiza que los autores de llamadas permanezcan en la cola hasta que un agente pueda responder a la llamada y que el autor de la llamada no se reenvíe inesperadamente.
>
> Los usuarios que reciban llamadas de operadores automáticos y colas de llamadas solo se mostrarán con el nombre del autor de la llamada si se proporciona desde la RTC o si el número del autor de la llamada coincide con los contactos de cliente del equipo local del usuario de destino.
>
> No se notifica a los agentes las llamadas perdidas ni los correos de voz de las llamadas de la cola de llamadas.

## <a name="supported-clients"></a>Clientes compatibles

La compatibilidad con las llamadas de operador automático y cola de llamadas está disponible en los siguientes clientes:

-    Cliente de Microsoft Teams para Windows (versiones de 32 y 64 bits)
-    Cliente de Microsoft Teams para Mac
-    Aplicación Microsoft Teams para iPhone
-    Aplicación Microsoft Teams para Android

El cliente de Teams solo es compatible con un [modo de existencia única de Teams](/microsoftteams/setting-your-coexistence-and-upgrade-settings).

## <a name="configure-auto-attendant-and-call-queue-support-for-microsoft-teams"></a>Configurar la compatibilidad del operador automático y la cola de llamadas para Microsoft Teams

Para recibir llamadas del operador automático y de la cola de llamadas en Microsoft Teams, debe configurar la directiva de interoperabilidad y la directiva de actualización. Revise [migración e interoperabilidad para organizaciones que usan Teams junto con Skype Empresarial](migration-interop-guidance-for-teams-with-skype.md). Si no tiene un operador automático o una cola de llamadas configurados y le gustaría hacerlo, consulte [Configurar un operador automático](create-a-phone-system-auto-attendant.md) de nube y [Crear una cola de llamadas](create-a-phone-system-call-queue.md) en la nube.

## <a name="known-issues"></a>Problemas conocidos

Cuando un agente de cola de llamadas recibe una llamada en su dispositivo móvil, la llamada puede ponerse en espera si el dispositivo está bloqueado. Los usuarios deben desbloquear primero el dispositivo y, a continuación, responder a la llamada.


## <a name="related-topics"></a>Temas relacionados

[Crear una cola de llamadas en la nube](create-a-phone-system-call-queue.md)

[¿Qué son los operadores automáticos en la nube?](what-are-phone-system-auto-attendants.md)

[Configurar un operador automático en la nube](create-a-phone-system-auto-attendant.md)

