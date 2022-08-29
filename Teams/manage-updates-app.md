---
title: Administrar la aplicación de Novedades para su organización
author: daisyfell
ms.author: daisyfeller
ms.reviewer: samanro
manager: pamgreen
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
description: Obtenga información sobre cómo administrar la aplicación Novedades en Teams para los usuarios de su organización.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- m365-frontline
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: 66ff8f642e3e006221507953a2fff1740237aea0
ms.sourcegitcommit: 46dbff43eec9631863b74b2b49c9a29c6497d8e8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/20/2022
ms.locfileid: "67397111"
---
# <a name="manage-the-updates-app-for-your-organization-in-microsoft-teams"></a>Administrar la aplicación de Novedades para su organización en Microsoft Teams

## <a name="what-is-the-updates-app"></a>¿Cuál es la aplicación Novedades

La Novedades en la aplicación Microsoft Teams proporciona un lugar centralizado para que los miembros de su organización creen, revisen y envíen actualizaciones. Al crear plantillas, puede usar la aplicación Novedades para realizar un seguimiento de todo lo que necesita su organización. Novedades está disponible tanto para equipos de escritorio como para móviles.

En Teams, los usuarios pueden obtener Novedades en la tienda de aplicaciones de Teams. Verán todas las actualizaciones que deben enviar en la página **Enviar** . Puede compartir el [artículo Introducción a Novedades](https://support.microsoft.com/office/get-started-in-updates-c03a079e-e660-42dc-817b-ca4cfd602e5a) con los usuarios para ayudarles a sentirse cómodos con Novedades.

[![Imagen de la página Enviar en Teams para escritorio.](media/updates-submit-small.png)](media/updates-submit.png#lightbox)

Los usuarios pueden ver las actualizaciones que han asignado en la página **Revisar** .

[![Imagen de la página Revisar en Teams para escritorio.](media/updates-home-small.png)](media/updates-home.png#lightbox)

Cuando se asigna una actualización a un usuario, se mostrará en su fuente de actividades de Teams. Los usuarios también pueden ver todas sus solicitudes de actualización actuales y envíos anteriores en la aplicación Novedades. Además, cualquier persona puede crear plantillas y enviar solicitudes de actualización.

Novedades incluye plantillas predefinidas para escenarios empresariales comunes y la opción de crear su propia plantilla. Cualquier persona puede crear una plantilla para nuevos tipos de actualizaciones.

## <a name="example-scenario"></a>Ejemplo ficticio

Los empleados de una tienda de ropa son responsables de abrir y cerrar la tienda todos los días. Todas las mañanas, el coordinador de turno rellena la actualización de apertura de store, que es una plantilla predefinida en la aplicación Novedades. En esta actualización, describen cualquier problema con el cierre de la noche anterior, responden preguntas sobre la limpieza de la tienda e informan de los suministros que necesitan reposición. Enviar una actualización les permite comunicar sus necesidades para store y cualquier problema de forma rápida y eficaz. Las actualizaciones diarias también ofrecen a los asociados de la tienda la oportunidad de resaltar lo que va bien.

En las instalaciones de fabricación de la tienda, los empleados realizan comprobaciones de seguridad con Novedades el uso de dispositivos móviles.

![Imagen de la plantilla tutorial de seguridad semanal en un dispositivo móvil.](media/updates-mobile.png)

Mientras tanto, un equipo de trabajadores remotos está actualizando el sitio web de la tienda. Están distribuidas en distintas zonas horarias, por lo que las reuniones de pie diarias no son prácticas. En su lugar, cada uno de los miembros del equipo envía informes diarios de Novedades sobre su progreso al jefe de equipo.

[Descarga el lookbook Novedades](https://go.microsoft.com/fwlink/?linkid=2197649&clcid=0x409) para ver más ejemplos de lo que puedes hacer con Novedades.

## <a name="required-permissions-and-licenses"></a>Permisos y licencias necesarios

Necesita permiso para que los siguientes elementos implementen Novedades:

- Permisos para crear una base de datos de Microsoft Dataverse.

- Una cuenta en [powerautomate.microsoft.com](https://powerautomate.microsoft.com/).

- Rol de administrador en el entorno de destino.

- Licencia de Power Automate, Office 365 o Dynamics 365.

- Se requiere licencia para Microsoft Forms para que los usuarios configuren nuevas plantillas.

## <a name="storage-with-microsoft-dataverse"></a>Almacenamiento con Microsoft Dataverse

El modelo de datos común (CDM) es el lenguaje de datos compartido que usan las aplicaciones empresariales y analíticas en Microsoft Dataverse. Se compone de un conjunto de esquemas de datos estandarizados y extensibles publicados por Microsoft y nuestros asociados que permite la coherencia de los datos y su significado en las aplicaciones y los procesos empresariales. Obtenga más información sobre el [modelo de datos común](/common-data-model/).

Novedades que se crean a partir de una plantilla siguen almacenando datos en Microsoft Dataverse, como su título, detalles, id. de plantilla y mucho más. Obtenga más información sobre  [Almacenamiento de datos para Microsoft Forms](https://support.microsoft.com/office/data-storage-for-microsoft-forms-97a34e2e-98e1-4dc2-b6b4-7a8444cb1dc3#:~:text=Where%20data%20is%20stored%20for%20Microsoft%20Forms.%20Microsoft,European-based%20tenants%20is%20stored%20on%20servers%20in%20Europe).

>[!Note]
>Si elimina la plantilla de formulario en el sitio de Microsoft Forms, se romperá el Novedades plantilla y los usuarios no podrán enviar la actualización. Los usuarios reciben el error "CDB TableNotFound" al intentar abrir una plantilla que se ha eliminado en Microsoft Forms.

## <a name="updates-teams-app-permissions"></a>Novedades permisos de aplicaciones de Teams

La aplicación Novedades Teams le permite acceder a las siguientes características:

- Recibir los mensajes y los datos que usted solicite.

- Envío de mensajes y notificaciones.

- Mostar cuadros de diálogo y aplicaciones personales sin un encabezado proporcionado por Teams.

- Obtenga acceso a la información del perfil, como su nombre, dirección de correo electrónico, nombre de la empresa e idioma de preferencia.

- Recibir mensajes y datos que los miembros del equipo le proporcionen en un canal.

- Enviar mensajes y notificaciones en un canal.

- Obtener acceso a la información del equipo:
  - nombre del equipo
  - lista de canales
  - lista (nombres y direcciones de correo electrónico de los miembros del equipo)

- Use la información del equipo para ponerse en contacto con ellos.

## <a name="disable-the-updates-app"></a>Deshabilitar la aplicación Novedades

La aplicación Novedades está disponible de forma predeterminada. Puede deshabilitar la aplicación en el Centro de administración de Microsoft Teams.

  1. Inicie la sesión en el Centro de administración de Teams

  2. Vaya a **Aplicaciones de Teams** > **Administrar aplicaciones**.

  3. Busca la aplicación Novedades.

     [![Captura de pantalla de la navegación del centro de Administración con las aplicaciones de Teams > Administrar aplicaciones resaltada.](media/manage-updates-small.png)](media/manage-updates.png#lightbox)

  4. Seleccione **Novedades**.

  5. Seleccione el botón de alternancia para deshabilitar la aplicación para su organización.
    ![Imagen del botón de alternancia para habilitar o deshabilitar Novedades.](media/toggle-updates.png)

## <a name="pin-updates-to-teams"></a>Anclar Novedades a Teams

Las directivas de configuración de aplicaciones le permiten personalizar Teams para anclar las aplicaciones que son más importantes para los usuarios de sus usuarios. Las aplicaciones se anclan en la barra de aplicaciones (la barra situada en el lateral del cliente de escritorio de Teams y en la parte inferior de los clientes móviles de Teams), donde los usuarios pueden acceder a ellas de forma rápida y sencilla.

Para anclar la aplicación Novedades para los usuarios, puede editar la directiva global (predeterminada para toda la organización) o crear y asignar una directiva de configuración de aplicación personalizada. Para obtener más información, consulte [Administrar las directivas de configuración de aplicaciones en Teams](teams-app-setup-policies.md).

## <a name="retention-policy"></a>Directiva de retención

Novedades creadas a partir de la aplicación Novedades se almacenan en el entorno predeterminado de Microsoft Dataverse, que no admite copias de seguridad en este momento. Obtenga más información sobre cómo [Respaldar y restaurar entornos - Power Platform \| Microsoft Docs](/power-platform/admin/backup-restore-environments).

Los datos almacenados en Forms no se eliminarán hasta que los creadores de la plantilla los limpien de la pestaña **formularios eliminados** de la aplicación web de Microsoft Forms.

## <a name="conditional-access-and-permission-policies"></a>Directivas de permisos y acceso condicional

La aplicación Novedades de Teams no es compatible actualmente con las directivas de acceso condicional establecidas para Microsoft Teams.

Puede usar [las directivas de permisos de la aplicación Teams](teams-app-permission-policies.md) para administrar Novedades.

## <a name="data-limitations"></a>Limitaciones de datos

Cada usuario puede crear como máximo 400 plantillas de Novedades, y cada plantilla puede recopilar un máximo de 50 000 solicitudes en función de la capacidad actual de Microsoft Forms.

## <a name="security"></a>Seguridad

Desde la aplicación de Teams Novedades, los usuarios tienen acceso para crear nuevas actualizaciones y ver las actualizaciones que han enviado y recibido. Los usuarios no tendrán acceso a Novedades creadas por otros usuarios a menos que sean lectores de la solicitud.

> [!Note]
> A un usuario se le asigna un rol de visor de una solicitud si forma parte del chat o canal en el que se creó el informe de actualización o si el creador de la plantilla los agrega manualmente como visor. No podrán tomar medidas en la solicitud si no se les proporcionó ese rol cuando se creó el informe.
