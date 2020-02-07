---
title: Directivas de retención en Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: prvijay
description: Obtenga información sobre cómo usar las directivas de retención y cómo administrarlas en Teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6adaee32648a6ec522098d90fd3c90ff161ef00e
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41838200"
---
# <a name="retention-policies-in-microsoft-teams"></a>Directivas de retención en Microsoft Teams

Las conversaciones de Teams son persistentes y se conservan para siempre de forma predeterminada. Con la introducción de las directivas de retención, los administradores pueden configurar directivas de retención (tanto de conservación como de eliminación) en el centro de cumplimiento de seguridad & para los mensajes de chat y de canal de Teams. Esto ayuda a las organizaciones a retener datos de cumplimiento (concretamente, a la Directiva de conservación) durante un período específico o a deshacerse de los datos (es decir, la política de eliminación) si se considera un pasivo después de un período específico. Las directivas de retención de Teams garantizan que cuando se eliminan datos, se quitan de todas las ubicaciones de almacenamiento de datos permanentes en el servicio de Teams.

> [!NOTE]
> Aún no se admite la configuración de retención de mensajes de canal privado. La retención de archivos compartidos en canales privados es compatible.

Para administrar las directivas de retención de Teams, use la configuración y cmdlets del centro de cumplimiento de Office 365 Security & en**retención**de **gobierno** > de información.

Las directivas de retención de Teams sí son compatibles: 
    
- Preservación: mantener los datos de Teams por una duración determinada y no hacer nada
- Preservación y, a continuación, eliminar: mantener los datos de Teams durante un período específico y, a continuación, eliminar
- Eliminación: eliminar datos de Teams después de un período de tiempo especificado

Las directivas de retención de Teams aún no son compatibles:

- Las directivas de retención avanzadas no se aplican a los equipos chat y Teams canales de mensajes

Los administradores pueden configurar directivas de retención diferentes para los chats privados de los equipos (1:1 o 1: muchos chats) y los mensajes de canal de Teams. En muchos casos, las organizaciones consideran que los datos de los chats privados son más responsabilidad de los mensajes de canal, que suelen ser más conversaciones relacionadas con el proyecto. Configure estas directivas en el centro de cumplimiento de & de seguridad,**retención**del **gobierno** > de la información. Active **los mensajes de canal de Teams y los** **chats de equipos** y, a continuación, defina las directivas de retención para estas ubicaciones (también se muestra en el diagrama siguiente). 

Al activar **los mensajes de canal de Teams**, puede especificar los equipos a los que se aplicará esta Directiva. Por ejemplo, para Teams X, y y Z, el administrador puede establecer las directivas de eliminación para un año (seleccionando esos equipos individualmente) y aplicar una directiva de eliminación de 3 años al resto de los equipos. 

Puede hacer lo mismo para los **chats de Teams** seleccionando usuarios específicos y aplicando directivas de retención únicas. 

![Diagrama del flujo de trabajo de los datos de Teams en Exchange y SharePoint.](media/Retention-Policies.png)


> [!IMPORTANT]
> Las ubicaciones de los mensajes de canal y equipos de chat de equipos solo se redireccionan a las conversaciones de Teams almacenadas en buzones de Exchange Online (buzones de usuario y de grupo). Los mensajes se eliminan de todas las ubicaciones de almacenamiento relevantes, es decir, los buzones, el sustrato y el servicio de chat. 
> 
> Para administrar las directivas de retención de los archivos de Teams, que se almacenan en OneDrive para la empresa y SharePoint, use sus directivas de retención.

Por diseño, las directivas de eliminación de los archivos de Teams se configuran a través de SharePoint Online y OneDrive para la empresa. Como resultado, es posible que una directiva pueda eliminar un archivo al que se hace referencia en una conversación de equipos o un mensaje de canal antes de que esos mensajes se eliminen. En este caso, el archivo seguirá apareciendo en el mensaje de Teams, pero si hace clic en el archivo, aparecerá el error "no se encuentra el archivo" (esto también podría ocurrir si alguien elimina manualmente un archivo de SharePoint Online o OneDrive para la empresa).

Para obtener información detallada sobre cómo configurar directivas de retención para Office 365, consulte [información general sobre las directivas de retención](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423).
 
