---
title: "Interacción de SharePoint Online y OneDrive para la Empresa con Microsoft Teams | Soporte técnico de Microsoft"
author: LolaJacobsen
ms.author: lolaj
manager: serdar
ms.date: 08/10/2017
ms.topic: overview
ms.prod: teams
description: "Conozca cómo SharePoint Online y OneDrive para la Empresa interaccionan con Microsoft Teams (por ejemplo, cómo se almacenan los chats privados) y la relación entre el equipo, el canal y la biblioteca de documentos."
ms.openlocfilehash: e43bd32cb7f999ff5de60b711f04a9eb079cd17c
ms.sourcegitcommit: 3b9b3f07f4f67cd5f43da68f48d62222d7e49167
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2017
---
<a name="how-sharepoint-online-and-onedrive-for-business-interact-with-microsoft-teams"></a>Interacción de SharePoint Online y OneDrive para la Empresa con Microsoft Teams
=============================================================================

Cada equipo de Microsoft Teams tiene un sitio de grupo en SharePoint Online y cada canal de un equipo tiene una carpeta dentro de la biblioteca de documentos del sitio de grupo predeterminado. Los archivos compartidos en un chat se agregan automáticamente a la biblioteca de documentos y los permisos y opciones de seguridad configurados en SharePonit se reflejan automáticamente en Microsoft Teams.

Los archivos de chats privados se almacenan en la carpeta de OneDrive para la Empresa del **remitente** y se conceden permisos automáticamente a todos los participantes como parte del proceso de compartir archivos.

Si no tiene habilitado SharePoint Online en su inquilino, los usuarios de Microsoft Teams no siempre podrán compartir archivos en los grupos. Los usuarios de chats privados no pueden compartir archivos porque se necesita OneDrive para la Empresa (que está ligado a la licencia de SharePoint) para esa funcionalidad. 

Al almacenar archivos en la biblioteca de documentos de SharePoint Online y OneDrive para la Empresa, se siguen todas las reglas de cumplimiento configuradas en el nivel de inquilino.

Este es un ejemplo de las relaciones entre el equipo, el canal y la biblioteca de documentos.

Se crea un sitio de SharePoint para cada equipo y la carpeta *Documentos compartidos* es la carpeta predeterminada que se crea para el equipo. Cada canal, incluido el canal **General**, que es canal predeterminado para cada equipo, tiene una carpeta dentro de la carpeta *Documentos compartidos*.

![](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image1.png)

Para cada usuario, la carpeta de OneDrive *Archivos de chat de Microsoft Teams* se usa para almacenar todos los archivos compartidos en los chat privados con otros usuarios (1:1 o 1:varios), y los permisos se configuran automáticamente para restringir el acceso sólo a usuarios autorizados.

![](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image2.png)
