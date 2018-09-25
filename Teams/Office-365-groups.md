---
title: Office 365 grupos y equipos de Microsoft
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 08/29/2018
ms.topic: article
ms.service: msteams
description: Aprenda cómo funcionan los grupos y las pertenencias a grupos de Office 365 con Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: d7ce73b84dd45ebe85c82a207fdd1062703a0ffe
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2018
ms.locfileid: "25012948"
---
<a name="office-365-groups-and-microsoft-teams"></a>Office 365 grupos y equipos de Microsoft
=====================================

> [!Tip]
> Vea la sesión siguiente para obtener información sobre cómo los equipos interactúa con Azure Active Directory (AAD), grupos de Office 365, Exchange, SharePoint y OneDrive para la empresa: [Fundamentos de los equipos de Microsoft](https://aka.ms/teams-foundations)

Grupos de Office 365 es el servicio de pertenencia entre aplicaciones de Office 365. En el nivel básico, un grupo de Office 365 es un objeto de Azure Active Directory con una lista de miembros y un acoplamiento flexible para cargas de trabajo relacionados, incluidos un sitio de grupo de SharePoint, el grupo de Yammer, comparte recursos de buzón de correo de Exchange, organizador, PowerBI y OneNote. Puede agregar o quitar personas al grupo como lo haría con cualquier otro objeto de seguridad basadas en grupos de Active Directory.

Un administrador de Office 365 puede definir un grupo de Office 365, agregar a miembros y beneficiarse de las características, como un intercambio shared buzón de correo, biblioteca de documentos de SharePoint, grupo de Yammer y así sucesivamente. Para obtener más información acerca de los grupos de Office 365, visite: [Obtenga información acerca de los grupos de Office 365](https://support.office.com/article/Learn-about-Office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2).

<a name="how-office-365-groups-work"></a>Cómo funcionan los grupos de Office 365
--------------------------

Cuando se crea un Team Microsoft, en el back-end, está creando un grupo de Office 365 y la biblioteca de documentos de SharePoint asociado y el Bloc de notas de OneNote, junto con vínculos a otras aplicaciones de nube de Office 365. Si la persona que crea el equipo es un propietario de una existente Office 365 público o privado grupo, pueden agregar funcionalidad de los equipos al grupo. Esto crea un canal **General** de forma predeterminada en qué chat residen los mensajes, documentos, OneNote y otros objetos. Visualización de la biblioteca de documentos para el canal mostrará la carpeta **General** que representa el canal en el equipo. Lo más importante, si crear su propia estructura de carpetas dentro de un documento biblioteca **no se propaga** a los equipos como un canal; por ahora, sólo fluya de los equipos en SharePoint.

> [!NOTE]
> Eliminación de un grupo de Office 365 se remove que invita el buzón de alias de las conversaciones de Outlook/OWA persistentes y la reunión de los equipos y marca de SharePoint del sitio para su eliminación. Se tardan aproximadamente 20 minutos entre la eliminación de un equipo y su efecto en Outlook. Eliminación de un equipo desde el cliente de los equipos, se quitará inmediatamente la vista a todos los que son miembros del equipo. Quitar a miembros de un grupo de Office 365 que se haya habilitado en él la funcionalidad de los equipos, puede haber un retraso de aproximadamente dos horas antes de que el equipo se ha quitado de la vista en el cliente de los equipos para las personas afectados que se han eliminado.
>
>Lea [este](https://support.office.com/article/Restore-a-deleted-Office-365-Group-b7c66b59-657a-4e1a-8aa0-8163b1f4eb54) para obtener información acerca de la restauración de un grupo de Office 365 que eliminó.

<a name="group-membership"></a>Pertenencia a grupos
----------------

Grupo características y funciones para los usuarios dependen de donde unidad pertenencia al grupo desde. Por ejemplo, si quita a un miembro de un equipo, se quitan del grupo así como Office 365. Eliminación del grupo inmediatamente quita el equipo y canales desde el cliente de los equipos. Si quita a una persona de un grupo mediante el portal de administración de Office 365, ya no tendrán acceso a los otros aspectos de colaboración como biblioteca de documentos SharePoint Online, grupo de Yammer o compartida OneNote. Sin embargo, aún tendrán acceso a la funcionalidad de chat del grupo para aproximadamente dos horas.

Práctica recomendada para la administración de los miembros de los equipos: agregar y quitar miembros desde el cliente de los equipos para asegurarse de que se aplica el control de acceso en cascada correcta a otras aplicaciones dependientes en la nube. Además, evitará un personas salir disjuntos experiencia con la impresión aún tienen acceso a los recursos que se solía (hasta que el próximo ciclo de sincronización agrega o revoca el acceso a un componente concreto del servicio). Si agrega o quita los integrantes del grupo fuera el cliente de los equipos (mediante el centro de administración de Office 365, Azure AD o Exchange Online PowerShell), puede tardar hasta dos horas para que los cambios se reflejan en los equipos.
