---
title: Aprobaciones de disponibilidad de aplicaciones en Teams
author: cichur
ms.author: v-cichur
ms.reviewer: aravin
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
searchScope:
- Microsoft Teams
search.appverid: MET150
description: Más información sobre la disponibilidad de la aplicación de aprobaciones en Microsoft Teams.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f916b4e794c862a05a42f075ca2f210a079ff42a
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909524"
---
# <a name="teams-approvals-app-availability"></a>Disponibilidad de la aplicación Aprobaciones de Teams

La aplicación Aprobaciones está disponible como una aplicación personal para todos los usuarios de Microsoft Teams.
La aplicación Aprobaciones ofrece una forma sencilla de ejercer las auditorías, el cumplimiento, la responsabilidad y los flujos de trabajo tanto a Aprobaciones estructuradas y no estructuradas en Teams.

 ![muestra la aplicación de aprobaciones](media/approvals-selection.png)

Los usuarios pueden anclar la aplicación Aprobaciones para guardarla en la barra de menús.

 ![muestra la aplicación de aprobaciones con la opción de ancla](media/approvalApp-pin.png)

La primera aprobación creada a partir de la aplicación Aprobaciones desencadenará el aprovisionamiento de la solución de aprobación en el entorno predeterminado del Servicio de datos comunes (CDS). Las aprobaciones creadas a partir de la aplicación Aprobaciones se almacenarán en el entorno de CDS predeterminado.

En este artículo se describen los roles y requisitos de la aplicación Aprobaciones.

## <a name="required-permissions-and-licenses"></a>Permisos y licencias necesarios

Para usar la aplicación Aprobaciones, necesita permisos para los elementos siguientes:

- Permisos para crear una base de datos de CDS de Microsoft.

- Una cuenta en [flow.microsoft.com](https://flow.microsoft.com/)

- Rol de administrador en el entorno de destino.

- Licencia para un [Power Automate](https://docs.microsoft.com/power-automate/get-started-approvals), un Office 365 o una Dynamics 365.

## <a name="storage-with-cds"></a>Almacenamiento con CDS

El modelo de datos común (CDM) es el lenguaje de datos compartido que usan las aplicaciones empresariales y de análisis en el CDS. Consiste en un conjunto de esquemas de datos estandarizados y extensibles publicados por Microsoft y nuestros asociados, que permiten la coherencia de los datos y su significado en aplicaciones y procesos empresariales. Obtenga más información sobre los [Modelos de datos común de la plataforma de Microsoft Power](https://docs.microsoft.com/power-automate/get-started-approvals).

Obtenga más información sobre el [flujo de trabajo de Aprobación](https://docs.microsoft.com/power-automate/modern-approvals).

## <a name="approvals-teams-app-permissions"></a>Permisos de aplicación de Approvals Teams

La aplicación Approvals Teams le permite acceder a las características siguientes:

- Recibir los mensajes y los datos que usted solicite.

- Envío de mensajes y notificaciones.

- Mostar cuadros de diálogo y aplicaciones personales sin un encabezado proporcionado por Teams.

- Obtenga acceso a la información del perfil, como su nombre, dirección de correo electrónico, nombre de la empresa e idioma de preferencia.

- Recibir mensajes y datos que los miembros del equipo le proporcionen en un canal.

- Enviar mensajes y notificaciones en un canal.

- Obtener acceso a la información del equipo:
  - nombre del equipo
  - lista de canales
  - lista (nombres y direcciones de correo electrónico de los miembros del equipo).

- Use la información del equipo para ponerse en contacto con ellos.

## <a name="disable-the-approvals-app"></a>Administrar la aplicación Aprobaciones

La aplicación Aprobaciones está disponible de forma predeterminada. Puede deshabilitar la aplicación en el Centro de administración de Microsoft Teams.

  1. Inicie la sesión en el Centro de administración de Teams

  2. Expanda **aplicación de Teams** y seleccione **Administrar aplicaciones**.

  3. Busque la aplicación Aprobaciones.

![muestra la navegación del Centro de administración donde se muestra Aplicaciones de Microsoft Teams > Administrar aplicaciones de forma resaltada](media/manage-approval-apps.png)

  4. Seleccione Aprobaciones.

  5. Seleccione el botón de alternancia para deshabilitar la aplicación para su organización.

![muestra los detalles de la aplicación Aprobaciones](media/approvals-details.png)

## <a name="retention-policy"></a>Directiva de retención

Las aprobaciones creadas a partir de la aplicación de Aprobaciones se almacenan en el entorno de CDS predeterminado, que no admite copias de seguridad en este momento. Obtenga más información sobre cómo [Respaldar y restaurar entornos - Power Platform \| Microsoft Docs](https://docs.microsoft.com/power-platform/admin/backup-restore-environments).

## <a name="auditing"></a>Auditoría

La aplicación Aprobaciones registra eventos de auditoría del Centro de seguridad y cumplimiento de Microsoft 365. Puede ver el registro de auditoría.

1. Vaya al sitio de cumplimiento de Microsoft 365.

2. Seleccione la sección **Auditoría**.

3. Buscar actividades en las actividades **Aprobación de Microsoft Teams**.

Puede buscar las actividades siguientes:

- Crear una nueva solicitud de aprobación

- Ver detalles de la solicitud de aprobación

- Solicitud de aprobación aprobada

- Solicitud de aprobación rechazada

- Solicitud de aprobación cancelada

- Solicitud de aprobación compartida

- Archivo adjunto a solicitud de aprobación

- Solicitud de aprobación reasignada

- Firma electrónica agregada a la solicitud de aprobación

Para tener acceso a más aprobaciones de auditoría en Flujo, habilite y configure la auditoría en el entorno predeterminado para las entidades de aprobación primaria Aprobación, solicitud de aprobación y respuesta de aprobación. Las operaciones de creación, actualización y eliminación son eventos auditables para los registros de Aprobación. Obtenga más información sobre [Datos de Auditoría y la actividad de usuario para la seguridad y el cumplimiento: Power Platform \| Microsoft Docs](https://docs.microsoft.com/power-platform/admin/audit-data-user-activity).

Las auditorías se pueden personalizar aún más en el [Centro de seguridad y cumplimiento de Microsoft 365](https://support.office.com/article/go-to-the-office-365-security-compliance-center-7e696a40-b86b-4a20-afcc-559218b7b1b8?ui=en-US&rs=en-US&ad=US).

1. Para usar los informes preconfigurados, inicie sesión en Seguridad y cumplimiento de Microsoft 365.

2. Seleccione **Búsqueda e investigación**.

3. Busque en el registro de Auditoría y seleccione la pestaña **Actividades de Dynamics 365**.

Obtenga más información sobre el [Registro de actividad de aplicaciones basadas en modelos y Microsoft Dataverse: Power Platform](https://docs.microsoft.com/power-platform/admin/enable-use-comprehensive-auditing).

## <a name="security"></a>Seguridad

Desde la aplicación Aprobaciones de Teams, los usuarios tienen acceso para crear nuevas aprobaciones y ver las aprobaciones que han enviado y recibido. Los usuarios no tendrán acceso a Aprobaciones creadas por otros usuarios, excepto si son respondedores o lectores de la solicitud.

> [!Note]
> A un usuario se le asigna un rol de visor de una solicitud si forma parte del chat o canal donde se creó la aprobación. No tendrán la capacidad de realizar acciones en la solicitud si no se les ha concedido ese rol cuando se creó la aprobación.
