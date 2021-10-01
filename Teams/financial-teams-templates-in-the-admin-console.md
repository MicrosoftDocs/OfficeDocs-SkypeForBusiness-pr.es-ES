---
title: Usar plantillas de equipo financiero
author: lanachin
ms.author: v-lanachin
manager: samanro
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: yinchang
ms.collection:
- M365-collaboration
ms.localizationpriority: high
search.appverid: MET150
description: Obtenga información sobre cómo administrar y usar plantillas de equipo financiero en el Centro de administración de Teams y con Microsoft Graph para crear equipos de forma rápida y sencilla para su organización de servicios financieros.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 19c6676bb742deacf97afae54f29b369d551b9ae
ms.sourcegitcommit: 5eb5acd7910724f7f4a598ecc28b003e5bbe5ea5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2021
ms.locfileid: "60007770"
---
# <a name="use-financial-team-templates"></a>Usar plantillas de equipo financiero

Las plantillas de equipo de Microsoft Teams le permiten crear equipos de forma rápida y sencilla al proporcionar una estructura predefinida de equipos de configuración, canales y aplicaciones preinstaladas.

Para las organizaciones de servicios financieros, las plantillas de equipo pueden ser especialmente eficaces, ya que le ayudan a implementar rápidamente equipos coherentes en toda la organización. Las plantillas también ayudan al personal a orientarse con la forma de usar Teams de forma eficaz.

Teams incluye plantillas diseñadas para organizaciones de servicios financieros. Use estas plantillas predefinidas para crear de forma rápida equipos para que el personal pueda comunicarse y colaborar. En este artículo, le presentamos cada una de estas plantillas y le recomendamos que las use.

La forma de administrar y trabajar con plantillas de equipo depende de si es administrador o desarrollador.

|Si está: | A continuación, usted: |
| ---- | --------- |
| Un administrador o un profesional de TI |[Administrador de plantillas de equipo en el Centro de administración de Teams](#manage-team-templates-in-the-teams-admin-center). Vea las plantillas de equipo y aplique directivas de plantillas para controlar cuales puede usar su personal en Teams para crear equipos. |
| Un desarrollador | [Use Microsoft Graph](#use-team-templates-with-microsoft-graph) para crear equipos a partir de plantillas de equipo. |

## <a name="manage-team-templates-in-the-teams-admin-center"></a>Administrar plantillas de equipo en el Centro de administración de Teams

Como un administrador, puede administrar plantillas de equipo en el Centro de administración de Microsoft Teams. Aquí puede ver los detalles acerca de cada plantilla. También puede [crear y asignar directivas de plantillas](templates-policies.md) al personal para controlar qué plantillas ven en Teams para [crear equipos](https://support.microsoft.com/office/create-a-team-from-a-template-a90c30f3-9940-4897-ab5b-988e69e4cd9c).

Para obtener más información sobre las plantillas de equipo en general, vea [Introducción a las plantillas de Teams en el Centro de administración](get-started-with-teams-templates-in-the-admin-console.md).

Actualmente ofrecemos las siguientes plantillas de equipo predefinidas para organizaciones de servicios financieros. Para verlos, en el panel de navegación izquierdo del Centro de administración de Teams, vaya a **Teams** > **Plantillas de equipo**.

### <a name="collaborate-within-a-bank-branch"></a>Colaborar en una sucursal bancaria

Centralice la colaboración para los empleados de las sucursales bancarias en grupos, reuniones de clientes, procesos empresariales como la colaboración en cláusulas financieras y mantenga a todos al día con anuncios y elogios.

| Tipo de plantilla |TemplateId| Propiedades que vienen con esta plantilla |
| ------------------ |--|----------------------------------------------------- |
|Sucursal bancaria| `CollaborateWithinABankBranch`|Canales: <ul><li>General<li>Anuncios</li><li>Reuniones</li><li>Reuniones de clientes</li><li>Solicitud de aprobaciones </li><li>Asesoramiento</li><li>Desarrollo de aptitudes</li><li>Procesamiento de préstamos</li><li>Quejas de clientes</li><li>Elogios</li><li>Material divertido</li><li>Cumplimiento</li></ul>Aplicaciones:<ul><li>Elogiar </li><li>Informador del problema</li><li>Wiki</li><li>Calendario</li><li>Aprobaciones</li><li>Boletines</li><li>Ideas</li></ul>|
||||

## <a name="use-team-templates-with-microsoft-graph"></a>Uso de plantillas de equipo con Microsoft Graph

Los desarrolladores pueden usar Microsoft Graph para crear equipos a partir de plantillas de equipo predefinidas. Para obtener más información sobre el uso de plantillas de equipo con Microsoft Graph, vea[Introducción a las plantillas de equipo con Microsoft Graph](get-started-with-teams-templates.md), [información general de la API de Microsoft Teams](/graph/teams-concept-overview?view=graph-rest-1.0)y [tipo de recurso teamsTemplate](/graph/api/resources/teamstemplate?view=graph-rest-1.0).

### <a name="bank-branch"></a>Sucursal bancaria

Centralice la colaboración para los empleados de las sucursales bancarias en grupos, reuniones de clientes, procesos empresariales como la colaboración en cláusulas financieras y mantenga a todos al día con anuncios y elogios.

| Tipo de plantilla |TemplateId| Canales de plantilla |
| ------------------ |--|----------------------------------------------------- |
|Sucursal bancaria|`https://graph.microsoft.com/beta/teamsTemplates('CollaborateWithinABankBranch')`|General<br>Anuncios<br>Reuniones<br>Reuniones de clientes<br>Solicitud de aprobaciones<br>Asesoramiento<br>Desarrollo de aptitudes<br>Procesamiento de préstamos<br>Quejas de clientes<br>Elogios<br>Material divertido<br>Cumplimiento|
||||

> [!NOTE]
> Para obtener plantillas de equipo adicionales que se aplican a la organización de servicios financieros, vea [Plantillas de equipo integradas en Microsoft Graph para pequeñas y medianas empresas](smb-templates.md).