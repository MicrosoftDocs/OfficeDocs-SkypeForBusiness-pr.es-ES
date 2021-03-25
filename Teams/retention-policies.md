---
title: Administrar directivas de retención para Microsoft Teams
author: cabailey
ms.author: cabailey
ms.reviewer:
- anwara
- prvijay
manager: laurawi
ms.topic: conceptual
ms.service: msteams
audience: admin
description: Use directivas de retención para Microsoft Teams para conservar los mensajes necesarios para cumplir con las directivas internas, las normativas del sector o las necesidades legales, y para eliminar mensajes que se consideren como responsabilidad o que no tienen ningún valor empresarial legal.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d7d998afb47480fa59ce936a93e20af9ac4b2a12
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117608"
---
# <a name="manage-retention-policies-for-microsoft-teams"></a>Administrar directivas de retención para Microsoft Teams

> [!NOTE]
> Si ve un mensaje en Teams en el que se indica que los chats o mensajes se han eliminado mediante una directiva de retención, vea Mensajes de [Teams sobre directivas de retención.](https://support.microsoft.com/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b)
> 
> La información de esta página es para los administradores de TI que administran estas directivas de retención.

Las directivas de retención y las etiquetas de retención de Microsoft 365 le ayudan a administrar de forma más eficaz la información de su organización. Puede configurar la configuración de retención para mantener los datos necesarios para cumplir con las directivas internas, las normativas del sector o las necesidades legales de su organización. También puede configurar la configuración de retención para eliminar datos que se consideran una responsabilidad, que ya no se le exige conservar o que no tienen ningún valor legal o empresarial.

Teams admite directivas de retención para mensajes de canal y chat para que, como administrador, pueda decidir de forma proactiva si desea conservar estos datos, eliminarlos o conservarlo durante un período de tiempo específico y, a continuación, eliminarlos. Puede aplicar una directiva de retención de Teams a toda la organización o a usuarios y equipos específicos. Las etiquetas de retención no son compatibles con Teams.

Para obtener más información sobre la retención y cómo puede aplicar la configuración de retención mediante directivas de retención o etiquetas de retención para otras cargas de trabajo en Microsoft 365, vea Más información sobre directivas de retención y etiquetas de [retención.](/microsoft-365/compliance/retention)

El requisito mínimo de licencia para directivas de retención para Teams es Microsoft 365 E3. Para obtener más información sobre las licencias, vea [Descripción del servicio de Microsoft Teams.](/office365/servicedescriptions/teams-service-description)

## <a name="how-teams-retentiondeletion-policies-work"></a>Cómo funcionan las directivas de retención y eliminación de Teams

Los mensajes de chat de Teams se almacenan en dos ubicaciones. La copia principal se almacena en Azure, una copia secundaria, que se usa para directivas de compilación, se almacena en una carpeta oculta en el buzón de Exchange Online de cada usuario incluido en el chat y los mensajes del canal de Teams se almacenan en una carpeta oculta similar en el buzón de grupo del equipo. Cuando se aplica una directiva de eliminación de mensajes de chat a un usuario o equipo, la copia secundaria se elimina primero, seguido de la copia principal. La búsqueda de eDiscovery o Teams se basa en los mensajes almacenados en copia secundaria y, por lo tanto, los mensajes no se pueden detectar cuando se elimina la copia secundaria. 

Cuando se aplica una poilcy de retención de mensajes de chat a un usuario o equipo, y si los mensajes se eliminan (ya sea debido a otra directiva de eliminación o por el propio usuario), la copia principal se elimina, por lo tanto, el cliente de **Teams** verá que el mensaje desaparece, pero la copia secundaria se mueve automáticamente a una carpeta oculta denominada **SubstrateHolds,** que es como subcarpeta en la carpeta Elementos recuperables de Exchange. Hasta que estos mensajes se eliminen permanentemente de la carpeta Desencuentables, seguirán siendo buscados por las herramientas de exhibición de documentos electrónicos.

Para obtener información detallada sobre lo que se incluye y se excluye para las directivas de retención de Teams y cómo funcionan estas directivas en función de la configuración de directiva, vea Obtener información sobre la retención [de Microsoft Teams.](/microsoft-365/compliance/retention-policies-teams)

> [!NOTE]
> En esa página se explica por qué a veces puede ver retrasos cuando las directivas de retención eliminan mensajes. Por ejemplo, los mensajes pueden verse hasta 7 días después del período de expiración que haya configurado en la directiva de retención.

Si configura varias directivas de retención de Teams con diferentes configuraciones de retención, los principios de retención resuelven los conflictos. Por ejemplo:
- Si hay un conflicto entre conservar o eliminar el mismo contenido, el contenido siempre se conserva.
- Si hay un conflicto en cuánto tiempo se conserva el mismo contenido, se conserva durante el período de retención más largo.

Estos dos principios de retención abordan la mayoría de los conflictos que pueden surgir cuando tiene varias directivas de retención para Teams, pero para obtener más información, vea Los principios de retención o ¿qué tiene [prioridad?](/microsoft-365/compliance/retention#the-principles-of-retention-or-what-takes-precedence)

## <a name="when-to-use-retention-policies-for-teams"></a>Cuándo usar directivas de retención para Teams

En muchos casos, las organizaciones consideran que los datos de chat privados son más una responsabilidad que los mensajes de canal, que generalmente son conversaciones más relacionadas con el proyecto.

Puede establecer directivas de retención distintas para chats privados (1 a 1 o 1 a muchos chats) y mensajes de canal. También puede configurar directivas únicas para aplicarlas a determinados usuarios o equipos de la organización. En el caso de chats de Teams, puede seleccionar a qué usuarios aplicar la directiva. En el caso de los mensajes de canal de Teams, puede seleccionar a qué equipos aplicar la directiva.

Por ejemplo, en el caso de los mensajes del canal, puede aplicar una directiva de eliminación de un año a equipos específicos de su organización y aplicar una directiva de eliminación de tres años a todos los demás equipos.

## <a name="create-and-manage-retention-policies-for-teams"></a>Crear y administrar directivas de retención para Teams

Para crear una directiva de retención para chats y mensajes de canal de Teams, use las instrucciones de directiva de retención para [ubicaciones de Teams.](/microsoft-365/compliance/create-retention-policies#retention-policy-for-teams-locations)

Esa página contiene información adicional sobre cómo crear y administrar directivas de retención para otras cargas de trabajo en Microsoft 365. Por ejemplo, es posible que también desee crear una directiva de retención para grupos de Microsoft 365 para conservar y eliminar archivos a los que se tiene acceso en Teams y almacenados en OneDrive o SharePoint.  

## <a name="end-user-experience"></a>Experiencia de usuario final

Para chats privados (chats de 1:1) o chats grupales, los usuarios verán que los chats anteriores a la configuración de directiva de retención se eliminan y se muestra un mensaje generado automáticamente que indica "Hemos eliminado mensajes antiguos debido a la directiva de retención de su organización" que se muestra encima de los mensajes que aún no se han eliminado. Por ejemplo:

:::image type="content" source="media/retention-policies-image1.png" alt-text="Usuario informado en Teams de que el mensaje de chat se elimina debido a una directiva de retención de Teams":::


:::image type="content" source="media/retention-policies-image2.png" alt-text="El usuario de Teams que explica los mensajes se elimina como resultado de una directiva de retención de Teams":::

En el caso de los mensajes del canal, los usuarios (miembros del canal) verán que los mensajes eliminados desaparecen de la vista después de que los mensajes expiren. Si el mensaje eliminado era un mensaje primario de una conversación en hilo, se mostrará, en lugar del mensaje principal, un mensaje que indique "Este mensaje se ha eliminado debido a una directiva de retención". Por ejemplo:

:::image type="content" source="media/retention-policies-image3.png" alt-text="Captura de pantalla del canal antes de la retención":::

:::image type="content" source="media/retention-policies-image4.png" alt-text="Captura de pantalla del canal después de la retención":::

> [!NOTE]
> Los mensajes mostrados que los usuarios ven como resultado de mensajes eliminados no se pueden configurar en este momento.

Los vínculos de estos mensajes mostrados van a Mensajes [de Teams sobre directivas de retención.](https://support.microsoft.com/en-us/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b) Esta documentación para usuarios finales ayuda a responder preguntas básicas sobre por qué se han eliminado sus mensajes. Sin embargo, como parte de la implementación de la directiva de retención, asegúrese de comunicar a los usuarios y al servicio de ayuda el impacto de la configuración configurada.

## <a name="related-topics"></a>Temas relacionados

- [Introducción a las directivas de retención y las etiquetas de retención](/microsoft-365/compliance/get-started-with-retention)
- [Más información sobre la retención de Microsoft Teams](/microsoft-365/compliance/retention-policies-teams)
- [Crear y configurar directivas de retención](/microsoft-365/compliance/create-retention-policies)