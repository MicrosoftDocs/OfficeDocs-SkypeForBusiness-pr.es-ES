---
title: Administrar directivas de retención de Microsoft Teams
author: cabailey
ms.author: cabailey
ms.reviewer:
- anwara
- prvijay
manager: laurawi
ms.topic: conceptual
ms.service: msteams
audience: admin
description: Use las directivas de retención de Microsoft Teams para mantener los mensajes que su organización necesita para cumplir con las directivas internas, los reglamentos del sector o los requisitos legales, y para eliminar mensajes que se consideran una responsabilidad o que no tienen ningún valor empresarial legal.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c99fc4bfb185ec291a98a96572167b389b3e6252
ms.sourcegitcommit: 28b83243411b54760875e7fd137549d5d2182c7a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2021
ms.locfileid: "53252655"
---
# <a name="manage-retention-policies-for-microsoft-teams"></a>Administrar directivas de retención de Microsoft Teams

> [!NOTE]
> Si ve un mensaje en Teams que indica que los chats y los mensajes se han eliminado debido a una directiva de retención, consulte [Mensajes de Teams sobre directivas de retención](https://support.microsoft.com/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b).
> 
> La información de esta página es para los administradores de TI que administran estas directivas de retención.

Las directivas de retención y las etiquetas de retención de Microsoft 365 permiten administrar de manera más efectiva la información en su organización. Puede configurar las opciones de retención para mantener los datos necesarios para cumplir con las directivas internas, las regulaciones del sector o los requisitos legales. También puede configurar las opciones de retención para eliminar los datos que se consideran una responsabilidad, que ya no es necesario conservar o que no tienen ningún valor legal o empresarial.

Teams admite directivas de retención para mensajes de chat y canal para que, como administrador, pueda decidir de forma proactiva si desea conservar estos datos, eliminarlos o conservarlos durante un período de tiempo específico y, a continuación, eliminarlos. El inicio del período de retención de estas acciones siempre se basa en el momento en que se crea un mensaje. Puede aplicar una directiva de retención de Teams a toda la organización o a usuarios y equipos específicos. Las etiquetas de retención no se admiten en Teams.

Para obtener más información sobre las soluciones de retención en Microsoft 365 consulte [Obtener información sobre las directivas de retención y las etiquetas de retención](/microsoft-365/compliance/retention).

Los usuarios que están sujetos a una directiva de retención para Teams deben tener una licencia adecuada, como Office 365 E3 u Office 365 A3. Para ver otras opciones de licencia para estas directivas de retención consulte la sección [Gobierno de información](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-governance) de la [Guía de licencias de Microsoft 365 para seguridad y cumplimiento](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-governance). Para obtener más información sobre las licencias de Teams consulte [Descripción del servicio Microsoft Teams](/office365/servicedescriptions/teams-service-description).

## <a name="how-teams-retention-policies-support-retain-and-delete-actions"></a>Compatibilidad de las directivas de retención de Teams con las acciones de retención y eliminación

Si configura una directiva de retención de Teams para conservar chats o mensajes de canal, los usuarios aún podrá editar y eliminar sus mensajes en su aplicación de Teams. Aunque los usuarios ya no ven sus mensajes editados o eliminados previamente en Teams, los datos de estos mensajes se almacenan en una ubicación segura diseñada para búsquedas de eDiscovery por parte de los administradores de cumplimiento. La eliminación permanente de estos datos no se produce antes del final del período de retención configurado, o si otra directiva de retención está configurada para conservar estos datos o si los datos están bajo [retención de exhibición de documentos electrónicos](/microsoft-365/compliance/retention#when-to-use-retention-policies-and-retention-labels-or-ediscovery-holds).

Cuando se configura una directiva de retención para eliminar chats y mensajes de canal, estos mensajes se convierten en aptos para la eliminación automática. Si los mensajes se siguen mostrando en la aplicación de Teams, desaparecerán de allí y [se informará a los usuarios de que una directiva de retención ha eliminado estos mensajes](#end-user-experience). Si los mensajes estaban sujetos previamente a una acción de retención y los usuarios los han editado o eliminado, estos mensajes se eliminarán ahora de la ubicación segura y ya no se devolverán en las búsquedas de eDiscovery.

Para obtener información detallada sobre cómo funcionan estas directivas en función de la configuración de directivas y las acciones del usuario, y qué datos de mensajes se incluyen y excluyen para las directivas de retención de Teams, consulte [Obtener información sobre la retención de Microsoft Teams](/microsoft-365/compliance/retention-policies-teams). En esa página también se explica por qué a veces puede experimentar retrasos cuando las directivas de retención eliminan mensajes. Por ejemplo, los mensajes pueden ser visibles para los usuarios en la aplicación Teams hasta 7 días después del período de expiración configurado en la directiva de retención.

Si configura varias directivas de retención en Teams con diferentes configuraciones de retención, los principios de retención resuelven los conflictos. Por ejemplo:

- Si hay un conflicto entre conservar o eliminar el mismo contenido, el contenido se conservará en la ubicación protegida para que siga siendo utilizable en búsquedas con eDiscovery para los administradores de cumplimiento.
    
    Este principio también se aplica a los mensajes con retención de exhibición de documentos electrónicos por motivos legales o de investigación.

- Si hay un conflicto en el tiempo que se conserva el mismo contenido, se conservará en la ubicación protegida durante el período de retención más largo.

Estos dos principios de retención abordan la mayoría de los conflictos que pueden surgir cuando tiene varias directivas de retención para Teams, pero para obtener más información consulte [Los principios de retención o ¿qué tiene prioridad?](/microsoft-365/compliance/retention#the-principles-of-retention-or-what-takes-precedence)

## <a name="when-to-use-retention-policies-for-teams"></a>Cuándo usar directivas de retención para Teams

En muchos casos, las organizaciones consideran que los datos de chat privados son más una responsabilidad que los mensajes de canal, que generalmente son conversaciones más relacionadas con el proyecto.

Puede configurar de forma muy eficaz una única directiva de retención para todos los Teams mensajes. O bien, para obtener un control más preciso, puede:

- Tenga directivas de retención independientes para chats privados (chats 1:1 o 1:many), mensajes de canales estándar o mensajes de canales privados.

- Aplique las directivas solo a usuarios o equipos específicos de su organización. Para Teams chats y canales privados, puede seleccionar a qué usuarios se aplica la directiva. En el caso de los mensajes de canal de Teams, puede seleccionar a qué equipos aplicar la directiva.

Por ejemplo, para los mensajes de canal estándar: Cree una directiva de retención para equipos específicos de su organización y configure esa directiva con una acción de eliminación después de 1 año. A continuación, cree otra directiva de retención para los mensajes de canal estándar para todos los demás equipos y configure esa directiva con una acción de eliminación después de 3 años.

## <a name="create-and-manage-retention-policies-for-teams"></a>Crear y administrar directivas de retención en Teams

Para crear o editar una directiva de retención para Teams mensajes, use las instrucciones de la directiva de retención [para Teams ubicación.](/microsoft-365/compliance/create-retention-policies#retention-policy-for-teams-locations)

Esa página contiene información adicional sobre cómo crear y administrar directivas de retención para otras cargas de trabajo en Microsoft 365. Por ejemplo, es posible que también desee crear una directiva de retención para Grupos de Microsoft 365 para conservar y eliminar archivos a los que se accede en Teams y que se almacenan en OneDrive o SharePoint.  

## <a name="end-user-experience"></a>Experiencia del usuario final

En el caso de los chats privados (chats 1:1) o de grupo los usuarios verán que los chats anteriores a la configuración de la directiva de retención se eliminan y que se muestra un mensaje generado automáticamente que indica que «Hemos eliminado mensajes más antiguos debido a la directiva de retención de su organización» encima de los mensajes que aún no se han eliminado. Por ejemplo:

:::image type="content" source="media/retention-policies-image1.png" alt-text="El usuario informó en Teams de que los mensajes de chat se eliminan debido a una directiva de retención de Teams":::


:::image type="content" source="media/retention-policies-image2.png" alt-text="El usuario de Teams explica que los mensajes se eliminan como resultado de una directiva de retención de Teams":::

En el caso de los mensajes de canal, los usuarios (miembros del canal) verán que los mensajes eliminados desaparecen de la vista después de expirar. Si el mensaje eliminado era un mensaje primario de una conversación encadenada, en lugar del mensaje primario se mostrará un mensaje que indica «Este mensaje se ha eliminado debido a una directiva de retención». Por ejemplo:

:::image type="content" source="media/retention-policies-image3.png" alt-text="Captura de pantalla del canal antes de la retención":::

:::image type="content" source="media/retention-policies-image4.png" alt-text="Captura de pantalla del canal después de la retención":::

> [!NOTE]
> Los mensajes que se muestran a los usuarios como resultado de los mensajes eliminados no se pueden configurar en este momento.

Los vínculos de estos mensajes que se muestran llevan a [Mensajes de Teams sobre directivas de retención](https://support.microsoft.com/en-us/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b). Esta documentación para los usuarios finales ayuda a responder a preguntas básicas sobre por qué se han eliminado sus mensajes. Sin embargo, como parte de la implementación de la directiva de retención, asegúrese de comunicar a los usuarios y al departamento de soporte técnico el impacto de las opciones configuradas.

## <a name="related-topics"></a>Temas relacionados

- [Introducción a las directivas y etiquetas de retención](/microsoft-365/compliance/get-started-with-retention)
- [Más información sobre las directivas de retención para Microsoft Teams](/microsoft-365/compliance/retention-policies-teams)
- [Crear y configurar directivas de retención](/microsoft-365/compliance/create-retention-policies)
