---
title: Responder a llamadas del operador automático y de la cola de llamadas
ms.reviewer: waseemh
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
ms.openlocfilehash: 95719bc95cc752888964a5f404e6f8050ebf3fa4
ms.sourcegitcommit: 67c686810d37bffda72a6e92155d9c8ec86bfae6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "47766864"
---
<a name="answer-auto-attendant-and-call-queue-calls-directly-from-teams"></a>Responder al operador automático y llamar a la cola de llamadas directamente desde Teams
===========================================================

Los usuarios de Teams pueden recibir y responder llamadas de operadores automáticos en la nube y colas de llamadas directamente desde su cliente de Teams.

## <a name="what-are-auto-attendants-and-call-queues"></a>¿Qué son los operadores automáticos y las colas de llamadas?

Los operadores automáticos en la nube proporcionan una serie de mensajes de voz o un archivo de audio que los autores de las llamadas escuchan en lugar de un operador humano cuando llaman a una organización. Un operador automático permite que los autores de llamadas se muevan por el sistema de menús, llamen y localicen a usuarios utilizando el teclado del teléfono (DTMF) o su propia voz gracias al reconocimiento de voz.

Las colas de llamadas en la nube incluyen saludos que se usan cuando alguien llama a un número de teléfono de su organización, la capacidad para poner automáticamente las llamadas en espera y la capacidad de buscar el siguiente agente de llamada disponible para que se ocupará de la llamada mientras las personas que realiza la llamada escuchan música en espera. Puede crear una o varias colas de llamadas para su organización.

## <a name="handling-an-auto-attendant-or-call-queue-call"></a>Administración de un operador automático o una llamada en cola de llamadas

Los usuarios podrán diferenciar las llamadas entrantes de un operador automático o de la cola de llamadas antes de que respondan a la llamada. Junto con el nombre o número del autor de la llamada, cada llamada incluirá información sobre a quién se estaba intentando contactar con el autor de la llamada, lo que ofrece a los usuarios un contexto mejor para dirigirse al autor de la llamada.

En la ilustración siguiente se muestra cómo aparecerá una llamada entrante de un operador automático o una cola de llamadas a un usuario.

![Captura de pantalla de una notificación de llamada entrante](media/answer-auto-attendant-and-call-queue-calls-image1.png)

Una vez que se responde a un operador automático o a una llamada de la cola de llamadas, el usuario puede procesar la llamada como cualquier otra llamada &#x2014; puede agregar o realizar conferencias con otro usuario o transferir la llamada a otro usuario. Además, las llamadas del operador automático se desvía según la configuración del usuario.

> [!NOTE] 
> Las llamadas de la cola de llamadas no se desvía según la configuración del usuario. Así se garantiza que los autores de las llamadas permanezcan en la cola hasta que un agente pueda responder a la llamada y el autor de la llamada no se reenvía de forma inesperada.

## <a name="supported-clients"></a>Clientes compatibles

La compatibilidad con el operador automático y las llamadas de la cola de llamadas está disponible en los siguientes clientes:

-    Cliente de Microsoft Teams para Windows (versiones de 32 y 64 bits)
-    Cliente de Microsoft Teams para Mac
-    Aplicación Microsoft Teams para iPhone
-    Aplicación Microsoft Teams para Android

## <a name="configure-auto-attendant-and-call-queue-support-for-microsoft-teams"></a>Configurar el operador automático y la compatibilidad con la cola de llamadas para Microsoft Teams

Para recibir llamadas del operador automático y la cola de llamadas en Microsoft Teams, debe configurar la directiva de interoperabilidad y la directiva de actualización. Revise la [migración y la interoperabilidad para las organizaciones que usan Teams junto con Skype Empresarial.](migration-interop-guidance-for-teams-with-skype.md) Si no tiene configurado un operador automático o una cola de [](create-a-phone-system-auto-attendant.md) llamadas y le gustaría hacerlo, consulte Configurar un operador automático de la nube y Crear una cola de llamadas [en la nube.](create-a-phone-system-call-queue.md)

## <a name="known-issues"></a>Problemas conocidos

Cuando un agente de colas de llamadas recibe una llamada en su dispositivo móvil, las llamadas pueden entrar en espera si el dispositivo está bloqueado. El usuario debe desbloquear el dispositivo primero y luego responder a la llamada.


## <a name="related-topics"></a>Temas relacionados

-    [¿Qué es el sistema telefónico en Microsoft 365 u Office 365?](what-is-phone-system-in-office-365.md)
-    [Crear una cola de llamadas en la nube](create-a-phone-system-call-queue.md)
-    [¿Qué son los operadores automáticos en la nube?](what-are-phone-system-auto-attendants.md)
-    [Configurar un operador automático en la nube](create-a-phone-system-auto-attendant.md)

