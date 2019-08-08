---
title: Responder al operador automático y llamar a la cola de llamadas directamente desde Teams
ms.reviewer: waseemh
author: LolaJacobsen
ms.author: lolaj
manager: serdars
audience: ITPro
ms.date: 09/20/2018
ms.topic: conceptual
ms.service: msteams
description: Describe los operadores automáticos de la nube y las colas de llamadas, y explica cómo puede responder a estas llamadas en Teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5eb58a945f1a5ff06c9f92c9440e783e4df9cde0
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36241258"
---
<a name="answer-auto-attendant-and-call-queue-calls-directly-from-teams"></a>Responder al operador automático y llamar a la cola de llamadas directamente desde Teams
===========================================================

Los usuarios de Teams pueden recibir y responder llamadas de los operadores automáticos de la nube y de las colas de llamadas directamente desde el cliente de su equipo. Para los usuarios de Teams, la característica de operador automático ahora está disponible generalmente y la función cola de llamadas está en versión preliminar. 

## <a name="what-are-auto-attendants-and-call-queues"></a>¿Qué son los operadores automáticos y las colas de llamadas?

Los operadores automáticos de la nube proporcionan una serie de mensajes de voz o un archivo de audio que escuchan las personas que llaman en lugar de un operador humano cuando llaman a una organización. Un operador automático permite que los autores de llamadas se muevan por el sistema de menús, llamen y localicen a usuarios utilizando el teclado del teléfono (DTMF) o su propia voz gracias al reconocimiento de voz.

Las colas de llamadas en nube incluyen saludos que se usan cuando un usuario llama a un número de teléfono de su organización, la capacidad de poner automáticamente las llamadas en espera y la capacidad de buscar el siguiente agente de llamada disponible para controlar la llamada mientras las personas que llaman son escuchando música en espera. Puede crear una o varias colas de llamadas para su organización.

## <a name="handling-an-auto-attendant-or-call-queue-call"></a>Control de una llamada de cola de llamadas o de operador automático

Los usuarios podrán diferenciar las llamadas entrantes de un operador automático o de una cola de llamadas antes de responder a la llamada. Junto con el nombre o el número de la persona que llama, cada llamada incluirá información sobre la persona que llama intentando llegar, lo que proporciona a los usuarios un contexto mejor para dirigir la llamada.

La ilustración siguiente muestra cómo un usuario verá una llamada entrante de un operador automático o una cola de llamadas.

![Captura de pantalla de una notificación de llamada entrante](media/answer-auto-attendant-and-call-queue-calls-image1.png)

Una vez que se responde a un operador automático o a una llamada de cola de llamadas, el usuario puede procesar la llamada como cualquier otra llamada &#x2014; que pueden agregar o realizar una conferencia en otro usuario o transferir la llamada a otra persona. Además, las llamadas de operador automático se desviarán en función de la configuración del usuario.

> [!NOTE] 
> Las llamadas a la cola de llamadas no se desvían en función de la configuración del usuario. Esto garantiza que los autores de llamadas permanezcan en la cola hasta que un agente pueda contestar la llamada y que la persona que llama no se desvíe de forma inesperada.

## <a name="supported-clients"></a>Clientes compatibles

La compatibilidad con el operador automático y las llamadas a la cola de llamadas está disponible en los siguientes clientes:

-   Cliente de Microsoft Teams para Windows (versiones de 32 y 64 bits)
-   Cliente de Microsoft Teams para Mac
-   Aplicación Microsoft Teams para iPhone
-   Aplicación Microsoft Teams para Android

## <a name="configure-auto-attendant-and-call-queue-support-for-microsoft-teams"></a>Configurar el operador automático y la cola de llamadas para Microsoft Teams

Para recibir llamadas de operador automático y cola de llamadas en Microsoft Teams, necesita configurar la Directiva de interoperabilidad y la actualización de la Directiva. Revise la [migración y la interoperabilidad de las organizaciones que usan Teams conjuntamente con Skype empresarial](migration-interop-guidance-for-teams-with-skype.md). Si no tiene configurado el operador automático o la cola de llamadas y desea hacerlo, consulte [configurar un operador automático de la nube](create-a-phone-system-auto-attendant.md) y [crear una cola de llamadas en la nube](create-a-phone-system-call-queue.md).

## <a name="related-topics"></a>Temas relacionados

-   [Qué es el sistema telefónico en Office 365](what-is-phone-system-in-office-365.md)
-   [Crear una cola de llamadas en la nube](create-a-phone-system-call-queue.md)
-   [¿Qué son los operadores automáticos en la nube?](what-are-phone-system-auto-attendants.md)
-   [Configurar un operador automático en la nube](create-a-phone-system-auto-attendant.md)

