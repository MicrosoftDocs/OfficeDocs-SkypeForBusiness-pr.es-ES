---
title: Directivas de retención en Microsoft Teams
author: cabailey
ms.author: cabailey
ms.reviewer:
- anwara
- prvijay
manager: laurawi
ms.topic: conceptual
ms.service: msteams
audience: admin
description: Use las directivas de retención de Microsoft Teams para conservar los mensajes necesarios para cumplir con directivas internas, normativas del sector o necesidades legales, y para eliminar mensajes que se consideren una responsabilidad o que no tienen ningún valor empresarial legal.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: aba9858466b43693603aa4a1cd396748d2c83d6e
ms.sourcegitcommit: def4b475b785a7b963f499cf9a1044e842ff66a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2021
ms.locfileid: "49786832"
---
# <a name="retention-policies-in-microsoft-teams"></a>Directivas de retención en Microsoft Teams

Las directivas de retención y las etiquetas de retención de Microsoft 365 le ayudan a administrar la información de la organización de forma más eficaz. Puede configurar las opciones de retención para conservar los datos necesarios para cumplir con las directivas internas, normativas del sector o necesidades legales de su organización. También puede configurar opciones de retención para eliminar datos que se consideren una responsabilidad, que ya no tenga que conservar o que no tenga valor empresarial o legal.

Teams admite directivas de retención para mensajes de canal y chat para que, como administrador, pueda decidir proactivamente si desea conservar estos datos, eliminarlos o retenerlo durante un período de tiempo específico y, a continuación, eliminarlos. Puede aplicar una directiva de retención de Teams a toda la organización o a usuarios y equipos específicos. Las etiquetas de retención no son compatibles con Teams.

Para obtener más información sobre la retención y cómo puede aplicar la configuración de retención mediante directivas de retención o etiquetas de retención para otras cargas de trabajo en Microsoft 365, vea Información sobre directivas de retención y etiquetas de [retención.](https://docs.microsoft.com/microsoft-365/compliance/retention)

El requisito mínimo de licencias para las directivas de retención de Teams es Microsoft 365 E3. Para obtener más información sobre las licencias, consulte la [descripción del servicio Microsoft Teams.](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)

## <a name="how-teams-retention-policies-work"></a>Cómo funcionan las directivas de retención de Teams

Los mensajes de chat de Teams se almacenan en una carpeta oculta en el buzón de cada usuario incluido en el chat, y los mensajes del canal de Teams se almacenan en una carpeta oculta similar en el buzón de grupo del equipo. Para conservar los mensajes que están sujetos a una directiva de retención, se mantiene automáticamente una copia del contenido en una carpeta oculta denominada Desportada **como** una subcarpeta de la carpeta Elementos recuperables **de** Exchange. Hasta que estos mensajes se eliminen de forma permanente de la carpeta Desenladtables, seguirán estando disponibles en las búsquedas mediante herramientas de exhibición de documentos electrónicos.

Para obtener información detallada sobre lo que se incluye y se excluye para las directivas de retención de Teams, y cómo funcionan estas directivas en función de la configuración de la directiva, vea Más información sobre la retención [de Microsoft Teams.](https://docs.microsoft.com/microsoft-365/compliance/retention-policies-teams)

> [!NOTE]
> Esa página explica por qué es posible que a veces vea retrasos cuando las directivas de retención eliminan mensajes. Por ejemplo, los mensajes pueden verse hasta 7 días después del período de expiración que haya configurado en la directiva de retención.

Si configura varias directivas de retención de Teams con distintas opciones de retención, los principios de retención resuelven cualquier conflicto. Por ejemplo:
- Si hay un conflicto entre retener o eliminar el mismo contenido, el contenido siempre se conserva.
- Si hay un conflicto en cuánto tiempo se retiene el mismo contenido, se retiene durante el período de retención más largo.

Estos dos principios de retención abordan la mayoría de los conflictos que pueden surgir cuando tiene varias directivas de retención para Teams, pero para obtener más información, consulte los principios de retención o qué tiene [prioridad?](https://docs.microsoft.com/microsoft-365/compliance/retention#the-principles-of-retention-or-what-takes-precedence)

## <a name="when-to-use-retention-policies-for-teams"></a>Cuándo usar directivas de retención para Teams

En muchos casos, las organizaciones consideran que los datos de chat privados son más una responsabilidad que los mensajes de canal, que generalmente son conversaciones más relacionadas con el proyecto.

Puede establecer directivas de retención distintas para chats privados (1 a 1 o 1 a muchos chats) y mensajes de canal. También puede configurar directivas únicas para aplicarlas a determinados usuarios o equipos de la organización. En el caso de chats de Teams, puede seleccionar a qué usuarios aplicar la directiva. En el caso de los mensajes de canal de Teams, puede seleccionar a qué equipos aplicar la directiva.

Por ejemplo, en el caso de los mensajes del canal, puede aplicar una directiva de eliminación de un año a equipos específicos de su organización y aplicar una directiva de eliminación de tres años a todos los demás equipos.

## <a name="create-and-manage-retention-policies-for-teams"></a>Crear y administrar directivas de retención para Teams

Para crear una directiva de retención para los mensajes de canal y chat de Teams, use las instrucciones de la directiva de [retención para ubicaciones de Teams.](https://docs.microsoft.com/microsoft-365/compliance/create-retention-policies#retention-policy-for-teams-locations)

Esa página contiene información adicional sobre cómo crear y administrar directivas de retención para otras cargas de trabajo en Microsoft 365. Por ejemplo, es posible que también desee crear una directiva de retención para grupos de Microsoft 365 para conservar y eliminar los archivos a los que se tiene acceso en Teams y que se almacenan en OneDrive o SharePoint.  

## <a name="end-user-experience"></a>Experiencia del usuario final

En los chats privados o chats grupales, los usuarios finales verán que se eliminaron los chats anteriores a la configuración de la directiva de retención y un mensaje de control que indica "Hemos eliminado mensajes antiguos debido a la directiva de retención de su organización" se muestra encima de los mensajes que todavía no se han eliminado.

:::image type="content" source="media/retention-policies-image1.png" alt-text="Usuario informado en Teams que el mensaje de chat se elimina por una directiva de retención de Teams":::


:::image type="content" source="media/retention-policies-image2.png" alt-text="El usuario en Teams explicando los mensajes se eliminan como resultado de una directiva de retención de Teams":::

Para los mensajes del canal, los usuarios finales (miembros del canal) verán los mensajes eliminados desaparecerán de la vista cuando expiren los mensajes. Si el mensaje eliminado era un mensaje principal de una conversación en hilo, se mostrará, en lugar del mensaje principal, un mensaje que indica "Este mensaje se ha eliminado por una directiva de retención".

:::image type="content" source="media/retention-policies-image3.png" alt-text="Captura de pantalla del canal antes de la retención":::

:::image type="content" source="media/retention-policies-image4.png" alt-text="Captura de pantalla de canal después de la retención":::

> [!NOTE]
> Los mensajes mostrados que los usuarios finales ven como resultado de la mensajería eliminada no se pueden configurar en este momento.


## <a name="related-topics"></a>Temas relacionados

- [Introducción a las directivas de retención y etiquetas de retención](https://docs.microsoft.com/microsoft-365/compliance/get-started-with-retention)
- [Más información sobre la retención de Microsoft Teams](https://docs.microsoft.com/microsoft-365/compliance/retention-policies-teams)
- [Crear y configurar directivas de retención](https://docs.microsoft.com/microsoft-365/compliance/create-retention-policies)