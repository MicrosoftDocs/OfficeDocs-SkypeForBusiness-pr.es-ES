---
title: Introducción a las plantillas de equipos de venta por menor
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/11/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: phecda louie
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
localization_priority: Normal
search.appverid: MET150
description: Obtenga información sobre cómo usar las plantillas de equipos para crear estructuras de equipo diseñadas para las necesidades de minorista.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4ee9ecf1a6db549a002c72f7eeea1e0a383ae966
ms.sourcegitcommit: 70d4d02a3cc894f2f197aeea459ac079cde63877
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/11/2019
ms.locfileid: "30543018"
---
# <a name="get-started-with-teams-templates-in-retail"></a>Introducción a las plantillas de equipos de venta por menor 

Las plantillas de equipos permiten rápidamente y creación fácilmente los equipos, ya que proporciona una plantilla predefinida de configuración, canales y aplicaciones instaladas previamente.

Las plantillas de equipos han predefinidos definiciones de estructuras de equipo diseñadas en torno a las necesidades de minorista. Puede usar las plantillas de equipos para crear rápidamente los tipos de los equipos que funcionan bien para los minoristas y los implementan en toda la organización. También puede extender las plantillas de equipos para crear grupos de usuarios que están adaptadas a las necesidades de su organización específicos.

En este artículo, se describe cada una de las plantillas de los equipos y cómo se recomienda el uso de las mismas.

En este artículo es para usted, si es responsable de la planeación, implementación y administración de varios equipos en toda la organización de venta por menor.

Para obtener más información acerca del equipo plantillas en general, consulte [Introducción a las plantillas de equipos](get-started-with-teams-templates.md).

## <a name="store-template"></a>Plantilla de almacén

La plantilla de almacenamiento es ideal para la creación de un equipo para representar una ubicación de almacenamiento de venta por menor individuales. Con la plantilla de almacenamiento, puede crear un equipo para cada ubicación de almacén de venta por menor en su organización.

| Tipo de plantilla de base | baseTemplateId | Propiedades que se incluyen con esta plantilla de base |
| ------------------ | -------------- | ----------------------------------------------------- |
| Venta por menor- <br>Almacén | `https://graph.microsoft.com/beta/teamsTemplates/`<br>`retailStore`| Canales <ul><li>Entrega de turnos\*</li><li>Recursos de aprendizaje\*</li></ul>\*Canales de automático favoritos<br><br>Propiedades de equipo <ul><li>Visibilidad de equipo establecida en público</li></ul> <br>Permisos de miembro <ul><li>No se puede crear, actualizar o eliminar canales </li><li>No se puede agregar o quitar el aplicaciones </li><li>No se puede crear/actualizar/quitar pestañas</li><li>No se puede crear/actualizar/quitar conectores</li><ul>|
||||

Se recomienda formas de personalizar la plantilla de almacenamiento para su organización:

- Si su organización tiene departamentos dentro de cada almacén, agregue un canal para cada departamento. Esto facilita la comunicación y la colaboración dentro del departamento.

- Si su organización tiene los sitios Web internos (por ejemplo, un sitio de SharePoint), considere la posibilidad de fijación de ellos como fichas en el canal de equipo relevante. Para obtener instrucciones, consulte [Introducción a las plantillas de equipos](get-started-with-teams-templates.md) .

## <a name="manager-collaboration-template"></a>Plantilla de colaboración de administrador

La plantilla de administrador colaboración es otro una de las plantillas de los equipos que se diseñó en torno a minorista necesita. La plantilla de administrador colaboración es ideal para la creación de un equipo para un conjunto de administradores para colaborar entre almacenes o regiones, etcetera. Por ejemplo, si su organización tiene regiones, es posible que crear un equipo de colaboración de administrador para la región de California e incluir todos los administradores de almacenamiento de esa región, así como el administrador regional de esa región.

| Tipo de plantilla de base | baseTemplateId | Propiedades que se incluyen con esta plantilla de base |
| ------------------ | -------------- | ----------------------------------------------------- |
| Venta por menor- <br>Almacén | `https://graph.microsoft.com/beta/teamsTemplates/`<br>`retailManagerCollaboration`| Canales <ul><li>Operaciones\*</li><li>Recursos de aprendizaje\*</li></ul>\*Canales de automático favoritos<br><br>Propiedades de equipo <ul><li>Visibilidad de equipo establecida en privado</li></ul> <br>Permisos de miembro <ul><li>Puede crear, actualizar o eliminar canales </li><li>Puede agregar o quitar el aplicaciones </li><li>Puede crear/actualizar/quitar pestañas</li><li>Puede crear/actualizar/quitar conectores</li><ul>|
||||

Se recomienda formas de personalizar la plantilla de colaboración de administrador para su organización:

- Si su organización tiene los sitios Web interna (por ejemplo, un sitio de SharePoint) que es relevantes para los administradores, considere la posibilidad de fijación de ellos como fichas en un canal de equipo relevante (consulte la documentación [aquí](get-started-with-teams-templates.md) para obtener instrucciones).