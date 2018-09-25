---
title: Directivas de retención en Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/11/2018
ms.topic: article
ms.service: msteams
ms.reviewer: anach
description: Obtenga información sobre cómo las directivas de retención y cómo se administran en los equipos.
localization_priority: Normal
search.appverid: MET150
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 453e6f161b62846143493d7a444b364e27f3885e
ms.sourcegitcommit: 5e8d04bbc3eb1a57fed893e5ff929674b4297851
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2018
ms.locfileid: "25004597"
---
# <a name="retention-policies-in-microsoft-teams"></a>Directivas de retención en Microsoft Teams

Las conversaciones de los equipos son persistentes y retenidas para siempre de forma predeterminada. Con la introducción de las directivas de retención, los administradores pueden configurar las directivas de retención (conservación y eliminación) en el centro de cumplimiento y seguridad para mensajes de chat y canal de los equipos. Esto ayuda a las organizaciones retener datos para el cumplimiento (es decir, la directiva de conservación) durante un período específico o deshacerse de datos (es decir, la directiva de eliminación) si se considera una responsabilidad después de un período específico. Las directivas de retención de los equipos Asegúrese de que al eliminar datos, se elimina de todas las ubicaciones de almacenamiento de datos permanente en el servicio de los equipos. 

Para administrar las directivas de retención de los equipos, use los cmdlets en el centro de cumplimiento en **Datos de gobierno**y seguridad de Office 365 y configuración > **retención**.

Son compatibles con las directivas de retención de los equipos: 
    
- Conservación: Conservar los datos de los equipos por una duración especificada y, a continuación, no haga nada
- Conservación y, a continuación, eliminar: conservar los datos de los equipos por una duración especificada y, a continuación, eliminar
- Eliminación: Eliminar datos de los equipos tras una duración especificada

Aún no admiten las directivas de retención de los equipos:

- Las directivas de retención avanzadas no se aplican a conversaciones en los equipos y ubicaciones de mensajes de canal de los equipos
- Duración de menos de 30 días

Los administradores pueden configurar las directivas de retención independiente para chats privadas de los equipos (1:1 o 1: muchas chats) y los mensajes del canal de los equipos. En muchos casos, las organizaciones, tenga en cuenta los datos de chat privado como más de un pasivo que no son mensajes de canal, que suelen ser más conversaciones relacionados con el proyecto. Configurar estas directivas en la seguridad & el centro de cumplimiento, el **Gobierno de datos** > **retención**. Activar **los mensajes del canal de los equipos** y **los equipos de chat** y, a continuación, defina las directivas de retención para estas ubicaciones (también se muestra en el diagrama siguiente). 

Cuando se activa en **los equipos de los mensajes del canal**, puede especificar los equipos a los que se aplicará esta directiva. Por ejemplo, para equipos de X, Y y Z, el administrador puede establecer las directivas de eliminación para 1 año (seleccionando esos equipos de forma individual) y aplicar una directiva de eliminación de 3 años para el resto de los equipos. 

Puede hacer lo mismo para **los equipos de chat** mediante la selección de usuarios específicos y aplicar las directivas de retención único. 

![Diagrama del flujo de trabajo de los datos de Teams en Exchange y SharePoint.](media/Retention-Policies.png)


> [!IMPORTANT]
> Las ubicaciones de mensaje de canal de los equipos y ubicaciones de los equipos chats dirección sólo las conversaciones de los equipos almacenadas en los buzones de Exchange Online (buzones de usuario y de grupo). Los mensajes se eliminan de todas las ubicaciones de almacenamiento de información relevante, es decir, los buzones de correo, sustrato y servicio de chat. 
> 
> Para administrar las directivas de retención para los archivos de los equipos, que se almacenan en OneDrive para profesionales y SharePoint, use sus directivas de retención.

Por diseño, se configuran las directivas de eliminación para los archivos de los equipos a través de SharePoint Online y OneDrive para las ubicaciones de negocio. Como resultado, es posible que una directiva pudo eliminar un archivo al que hace referencia en un mensaje de chat o canal de los equipos antes de que se eliminan los mensajes. En este caso, el archivo aún se mostrará en el mensaje de los equipos, pero si hace clic en el archivo, obtendrá un error de "Archivo no encontrado" (también puede suceder en ausencia de una directiva, si alguien elimina manualmente un archivo de SharePoint Online o OneDrive para la empresa).

Para obtener información detallada acerca de cómo configurar las directivas de retención para Office 365, lea [información general de las directivas de retención](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423).
 
