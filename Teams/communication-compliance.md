---
title: Cumplimiento de las comunicaciones de Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: anwara
description: Aprender sobre el cumplimiento de las comunicaciones, parte de la solución de riesgos de Insider, desde la perspectiva de Microsoft Teams (esta es parte de la funcionalidad de cumplimiento de comunicaciones de M365).
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: bf97f4adc33b0855e986cf2baed54f69de91f4f0
ms.sourcegitcommit: c8b5d4dd70d183f7ca480fb735a19290a3457b30
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/08/2020
ms.locfileid: "45077702"
---
# <a name="communication-compliance-for-microsoft-teams"></a>Cumplimiento de las comunicaciones de Microsoft Teams

El cumplimiento de la comunicación forma parte de la nueva solución de riesgo de Insider de Microsoft 365 que ayuda a minimizar los riesgos de comunicación ayudándole a detectar, capturar y tomar medidas de corrección para los mensajes inapropiados de su organización. Ayuda a identificar el lenguaje ofensivo y el Antiacoso de los canales del equipo o 1:1 y los chats grupales. También puede configurar directivas para ver si hay información confidencial compartida como parte de los canales del equipo o 1:1 y chats grupales. Para obtener más información sobre los distintos tipos de directivas y sobre cómo configurar, consulte el [artículo M365](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance).

## <a name="how-to-use-communication-compliance-in-teams"></a>Cómo usar el cumplimiento de las comunicaciones en Teams

### <a name="identify-inappropriate-messages"></a>Identificar mensajes inapropiados

Si desea identificar los mensajes que se envían en Microsoft Teams (1:1, chats grupales o conversaciones de canales) contienen lenguaje ofensivo o Antiacoso, puede habilitar las directivas para identificar esta opción y el revisor puede consultar los mensajes y llevar a cabo los pasos necesarios, como enviar material de formación o escalar a las autoridades adecuadas.

### <a name="identify-sensitive-or-regulatory-information"></a>Identificar información confidencial o normativa

Si desea analizar los mensajes enviados en Microsoft Teams (1:1, chats grupales o conversaciones de canal) para obtener información confidencial o tipos normativos, puede elegir directivas que admitan tipos predefinidos para la normativa o sensible.

> [!NOTE]
> Los canales privados no son compatibles con el cumplimiento de la comunicación.

### <a name="custom-policy"></a>Directiva personalizada

Use esta plantilla para configurar canales de comunicación específicos, condiciones de detección individuales y la cantidad de contenido que se debe supervisar y revisar en la organización.

### <a name="custom-trainable-classifier"></a>Clasificador personalizado personalizado

Use clasificadores capacitables cuando uno de los clasificadores del cuadro no se ajuste a sus necesidades. Un clasificador de Microsoft 365 es una herramienta que se puede utilizar para reconocer diversos tipos de contenido, proporcionándoles ejemplos para verlos. La formación del clasificador implica que, en primer lugar, las muestras de los seres humanos se seleccionan y cumplen positivamente la categoría. Después, después de que haya procesado esos ejemplos, pruebe las predicciones asignándole una combinación de muestras positivas y negativas. Para obtener más información sobre este tema, consulta el [artículo M365](https://docs.microsoft.com/microsoft-365/compliance/classifier-creating-a-trainable-classifier) para obtener más información sobre este tema.

> [!NOTE]
> El cumplimiento de la comunicación ahora es compatible con las implementaciones híbridas de Exchange.

El cumplimiento de la comunicación admite el historial de conversaciones para todos los mensajes que coincidan con las directivas. Esto proporciona contexto al administrador instructora.

:::image type="content" source="media/communication-compliance-1.png" alt-text="Una pantalla para el cumplimiento de la comunicación en Microsoft Teams.":::

## <a name="where-communication-policies-can-be-applied-in-teams"></a>Dónde se pueden aplicar las directivas de comunicación en Teams

Las directivas de cumplimiento de comunicaciones se pueden configurar para los mensajes enviados en Teams en los siguientes niveles:

- Nivel de usuario: un administrador puede configurar directivas a un nivel de usuario individual o aplicarlas a todos los usuarios del espacio empresarial. Esto solo cubrirá los mensajes que un usuario envió en 1:1 o conversaciones grupales.
- Nivel de equipo: un administrador también puede configurar directivas en un equipo. Esto cubre todos los mensajes enviados en el canal de ese equipo (no se admiten mensajes de canal privado).
