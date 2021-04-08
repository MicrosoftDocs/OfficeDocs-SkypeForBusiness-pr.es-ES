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
description: Use directivas de retención para Microsoft Teams para mantener los mensajes que su organización necesita para cumplir con directivas internas, normativas del sector o requisitos legales, y para eliminar mensajes que se consideran una responsabilidad o no tienen ningún valor empresarial legal.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ec6b257f91c7e5003a4a69079e37b20b5f338528
ms.sourcegitcommit: b52b6aba289396c4fc10dd856817137eb1bc1f67
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/07/2021
ms.locfileid: "51617762"
---
# <a name="manage-retention-policies-for-microsoft-teams"></a>Administrar directivas de retención para Microsoft Teams

> [!NOTE]
> Si ve un mensaje en Teams en el que se indica que los chats o mensajes se han eliminado mediante una directiva de retención, vea Mensajes de [Teams sobre directivas de retención.](https://support.microsoft.com/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b)
> 
> La información de esta página es para los administradores de TI que administran estas directivas de retención.

Las directivas de retención y las etiquetas de retención de Microsoft 365 le ayudan a administrar de forma más eficaz la información de su organización. Puede configurar la configuración de retención para conservar los datos necesarios para cumplir con las directivas internas, las normativas del sector o los requisitos legales de su organización. También puede configurar la configuración de retención para eliminar datos que se consideran una responsabilidad, que ya no se le exige conservar o que no tienen ningún valor legal o empresarial.

Teams admite directivas de retención para mensajes de canal y chat para que, como administrador, pueda decidir de forma proactiva si desea conservar estos datos, eliminarlos o conservarlo durante un período de tiempo específico y, a continuación, eliminarlos. El inicio del período de retención de estas acciones siempre se basa en el momento en que se crea un mensaje. Puede aplicar una directiva de retención de Teams a toda la organización o a usuarios y equipos específicos. Las etiquetas de retención no son compatibles con Teams.

Para obtener más información sobre las soluciones de retención en Microsoft 365, vea Más información sobre directivas de retención [y etiquetas de retención.](/microsoft-365/compliance/retention)

Los usuarios sujetos a una directiva de retención para Teams deben tener una licencia adecuada, como Office 365 E3 u Office 365 A3. Para obtener otras opciones de licencia para estas directivas de retención, vea la sección [Gobierno](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-governance) de la información de las instrucciones de licencias de [Microsoft 365](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-governance)para el cumplimiento & seguridad. Para obtener más información sobre las licencias de Teams, vea [Descripción del servicio de Microsoft Teams.](/office365/servicedescriptions/teams-service-description)

## <a name="how-teams-retention-policies-support-retain-and-delete-actions"></a>Cómo las directivas de retención de Teams admiten las acciones de retención y eliminación

Si configura una directiva de retención de Teams para retener chats o mensajes de canal, los usuarios podrán editar y eliminar sus mensajes en su aplicación de Teams. Aunque los usuarios ya no ven sus mensajes preeditados o eliminados en Teams, los datos de estos mensajes se almacenan en una ubicación segura diseñada para las búsquedas de exhibición de documentos electrónicos por los administradores de cumplimiento. La eliminación permanente de estos datos no se hace antes del final del período de retención configurado, o si otra directiva de retención está configurada para conservar estos datos o está sujeta a una retención de [exhibición](/microsoft-365/compliance/retention#when-to-use-retention-policies-and-retention-labels-or-ediscovery-holds)de documentos electrónicos.

Cuando se configura una directiva de retención para eliminar chats y mensajes de canal, estos mensajes se convierten en aptos para la eliminación automática. Si los mensajes se siguen visualizando en la aplicación Teams, desaparecerán de allí y se informará a los usuarios de que una directiva de retención ha [eliminado estos mensajes.](#end-user-experience) Si los mensajes estaban previamente sujetos a una acción de retención y los usuarios los modificaron o eliminaron, estos mensajes ahora se eliminarán de la ubicación protegida y ya no se devolverán en las búsquedas de exhibición de documentos electrónicos.

Para obtener información detallada sobre cómo funcionan estas directivas en función de la configuración de directiva y las acciones de usuario, y qué datos de mensaje se incluyen y se excluyen para las directivas de retención de Teams, vea Obtener información sobre la retención de [Microsoft Teams.](/microsoft-365/compliance/retention-policies-teams) Esa página también explica por qué a veces puede experimentar retrasos cuando las directivas de retención eliminan mensajes. Por ejemplo, los mensajes pueden ser visibles para los usuarios de la aplicación Teams hasta 7 días después del período de expiración que haya configurado en la directiva de retención.

Si configura varias directivas de retención de Teams con diferentes configuraciones de retención, los principios de retención resuelven los conflictos. Por ejemplo:

- Si hay un conflicto entre conservar o eliminar el mismo contenido, el contenido siempre se conserva en la ubicación protegida para que se pueda buscar con eDiscovery para los administradores de cumplimiento.
    
    Este principio también se aplica a los mensajes que se encuentran en retenciones de exhibición de documentos electrónicos por motivos legales o de investigación.

- Si hay un conflicto en cuánto tiempo se conserva el mismo contenido, se conserva en la ubicación protegida durante el período de retención más largo.

Estos dos principios de retención abordan la mayoría de los conflictos que pueden surgir cuando tiene varias directivas de retención para Teams, pero para obtener más información, vea Los principios de retención o ¿qué tiene [prioridad?](/microsoft-365/compliance/retention#the-principles-of-retention-or-what-takes-precedence)

## <a name="when-to-use-retention-policies-for-teams"></a>Cuándo usar directivas de retención para Teams

En muchos casos, las organizaciones consideran que los datos de chat privados son más una responsabilidad que los mensajes de canal, que generalmente son conversaciones más relacionadas con el proyecto.

Puede establecer directivas de retención distintas para chats privados (1 a 1 o 1 a muchos chats) y mensajes de canal. También puede configurar directivas únicas para aplicarlas a determinados usuarios o equipos de la organización. En el caso de chats de Teams, puede seleccionar a qué usuarios aplicar la directiva. En el caso de los mensajes de canal de Teams, puede seleccionar a qué equipos aplicar la directiva.

Por ejemplo, para los mensajes de canal, puede aplicar una directiva de retención a equipos específicos de su organización y esa directiva se configura con una acción de eliminación después de 1 año. Después, aplique otra directiva de retención a todos los demás equipos y esa directiva se configura con una acción de eliminación después de 3 años.

## <a name="create-and-manage-retention-policies-for-teams"></a>Crear y administrar directivas de retención para Teams

Para crear o editar una directiva de retención para chats y mensajes de canal de Teams, use las instrucciones de directiva de retención para [ubicaciones de Teams.](/microsoft-365/compliance/create-retention-policies#retention-policy-for-teams-locations)

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
