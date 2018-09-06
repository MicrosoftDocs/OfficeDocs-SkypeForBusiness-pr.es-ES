---
title: Interacción de SharePoint Online y OneDrive para la Empresa con Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 07/31/2018
ms.topic: article
ms.service: msteams
ms.reviewer: snigdhav
description: Conozca cómo SharePoint Online y OneDrive para la Empresa interaccionan con Microsoft Teams (por ejemplo, cómo se almacenan los chats privados) y la relación entre el equipo, el canal y la biblioteca de documentos.
localization_priority: Priority
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 19d5be5ebab02b839354a79af6a75e3ade9f3000
ms.sourcegitcommit: dbef8028cb7f8c6366e0fdb34f5f2e2a30d8c32a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2018
ms.locfileid: "23797326"
---
<a name="how-sharepoint-online-and-onedrive-for-business-interact-with-microsoft-teams"></a>Interacción de SharePoint Online y OneDrive para la Empresa con Microsoft Teams
=============================================================================

Cada equipo de Microsoft Teams tiene un sitio de grupo en SharePoint Online y cada canal de un equipo tiene una carpeta dentro de la biblioteca de documentos del sitio de grupo predeterminado. Los archivos compartidos en un chat se agregan automáticamente a la biblioteca de documentos y los permisos y opciones de seguridad configurados en SharePonit se reflejan automáticamente en Microsoft Teams.

Los archivos de chats privados se almacenan en la carpeta de OneDrive para la Empresa del remitente y se conceden permisos automáticamente a todos los participantes como parte del proceso de compartir archivos.

Si los usuarios no están asignados y habilitados con licencias de SharePoint Online, no tienen OneDrive para el almacenamiento de negocio en Office 365. Uso compartido de archivos seguirán funcionando en canales, pero los usuarios no podrán compartir archivos en chats sin OneDrive para el almacenamiento de negocio en Office 365.

Al almacenar archivos en la biblioteca de documentos de SharePoint Online y OneDrive para la Empresa, se siguen todas las reglas de cumplimiento configuradas en el nivel de inquilino. 

> [!NOTE]
> No se admite la integración con Sharepoint local para Microsoft Teams en este momento.

Este es un ejemplo de las relaciones entre el equipo, el canal y la biblioteca de documentos.

Se crea un sitio de SharePoint para cada equipo y la carpeta **Documentos compartidos** es la carpeta predeterminada que se crea para el equipo. Cada canal, incluido el canal **General** (que es un canal predeterminado para cada equipo) tiene una carpeta en **Documentos compartidos**.

![Diagrama de las carpetas Documentos compartidos de SharePoint Online para un equipo y sus canales de Microsoft Teams.](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image1.png)

> [!NOTE]
> En este momento no es posible reemplazar el sitio de SharePoint predeterminado y la biblioteca de documentos con otro. Nos han comentado que les gustaría, por lo que estamos pensando en esa posibilidad. Revise el [mapa de ruta de Teams](https://aka.ms/teamsroadmap) o [Teams UserVoice](https://aka.ms/TeamsUserVoice) para estar al tanto de las próximas características.

> [!TIP]
> Para agregar una ficha a su equipo que vínculos a una existente de SharePoint del sitio o biblioteca de documentos a la base de SharePoint existente:
> 1. Seleccione el signo más junto a las fichas.
> 2. Seleccione el **sitio Web**.
> 3. Escriba un nombre y escriba la dirección URL de la biblioteca de documentos o sitio de SharePoint.

Para cada usuario, la carpeta de OneDrive **Archivos de chat de Microsoft Teams** se usa para almacenar todos los archivos compartidos en los chat privados con otros usuarios (1:1 o 1:varios), y los permisos se configuran automáticamente para restringir el acceso sólo a usuarios autorizados.

![Diagrama de la carpeta de OneDrive denominada Archivos de chat de Microsoft Teams de los chats de cada usuario.](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image2.png)
