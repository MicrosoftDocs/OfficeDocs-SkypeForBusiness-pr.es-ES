---
title: Disponibilidad de aplicaciones de aprobación en Teams
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
description: Obtenga información sobre la disponibilidad de la aplicación Aprobaciones en Microsoft Teams.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f916b4e794c862a05a42f075ca2f210a079ff42a
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909524"
---
# <a name="teams-approvals-app-availability"></a>Disponibilidad de la aplicación Aprobaciones de Teams

La aplicación Aprobaciones está disponible como aplicación personal para todos los usuarios de Microsoft Teams.
La aplicación Aprobaciones ofrece una forma sencilla de auditar, cumplir, responsabilidad y flujos de trabajo a aprobaciones estructuradas y no estructuradas en Teams.

 ![muestra la aplicación de aprobaciones](media/approvals-selection.png)

Los usuarios pueden anclar la aplicación Aprobaciones para guardarla en la barra de menús.

 ![muestra la aplicación de aprobaciones con la opción anclar](media/approvalApp-pin.png)

La primera aprobación creada desde la aplicación Aprobaciones desencadenará el aprovisionamiento de la solución de aprobación en el entorno predeterminado del Servicio de datos comunes (CDS). Las aprobaciones creadas desde la aplicación Aprobaciones se almacenarán en el entorno de CDS predeterminado.

En este artículo se describen los requisitos y los roles de la aplicación Aprobaciones.

## <a name="required-permissions-and-licenses"></a>Permisos y licencias necesarios

Para usar la aplicación Aprobaciones, necesita permiso para los siguientes elementos:

- Permisos para crear una base de datos de CDS de Microsoft.

- Una cuenta en [flow.microsoft.com](https://flow.microsoft.com/)

- Rol de administrador en el entorno de destino.

- Licencia para [Power Automate,](https://docs.microsoft.com/power-automate/get-started-approvals)Office 365 o Dynamics 365.

## <a name="storage-with-cds"></a>Almacenamiento con CDS

El modelo de datos común (CDM) es el lenguaje de datos compartido que usan las aplicaciones empresariales y analíticas en los CDS. Se compone de un conjunto de esquemas de datos estandarizados y extensibles publicados por Microsoft y nuestros socios que permite la coherencia de los datos y su significado en todas las aplicaciones y procesos empresariales. Obtenga más información sobre el [modelo de datos común de Microsoft Power Platform.](https://docs.microsoft.com/power-automate/get-started-approvals)

Obtenga más información sobre el flujo [de trabajo Aprobación.](https://docs.microsoft.com/power-automate/modern-approvals)

## <a name="approvals-teams-app-permissions"></a>Permisos de la aplicación de Teams de aprobación

La aplicación Desaprobaciones de Teams le permite acceder a las siguientes características:

- Recibir mensajes y datos que se le proporcionen.

- Envíate mensajes y notificaciones.

- Representar cuadros de diálogo y aplicaciones personales sin un encabezado proporcionado por Teams.

- Obtenga acceso a la información de su perfil, como su nombre, dirección de correo electrónico, nombre de la empresa e idioma preferido.

- Recibir mensajes y datos que los miembros del equipo le proporcionan en un canal.

- Enviar mensajes y notificaciones en un canal.

- Obtenga acceso a la información de su equipo:
  - nombre del equipo
  - lista de canales
  - lista (nombres y direcciones de correo electrónico de los miembros del equipo).

- Use la información del equipo para ponerse en contacto con ellos.

## <a name="disable-the-approvals-app"></a>Deshabilitar la aplicación Aprobaciones

La aplicación Aprobaciones está disponible de forma predeterminada. Puede deshabilitar la aplicación en el Centro de administración de Teams.

  1. Inicie sesión en el Centro de administración de Teams.

  2. Expanda **las aplicaciones de Teams** y seleccione Administrar **aplicaciones.**

  3. Busque la aplicación Aprobaciones.

![muestra la navegación del Centro de administración con las aplicaciones de Teams > Administrar aplicaciones resaltada](media/manage-approval-apps.png)

  4. Seleccione Aprobaciones.

  5. Seleccione el botón de alternancia para deshabilitar la aplicación para su organización.

![muestra los detalles de la aplicación Aprobaciones](media/approvals-details.png)

## <a name="retention-policy"></a>Directiva de retención

Las aprobaciones creadas desde la aplicación Aprobaciones se almacenan en el entorno predeterminado de CDS, que no admite copias de seguridad en este momento. Obtenga más información sobre cómo hacer [copias de seguridad y restaurar entornos: Documentos de Microsoft de la plataforma \| móvil.](https://docs.microsoft.com/power-platform/admin/backup-restore-environments)

## <a name="auditing"></a>Auditoría

La aplicación Aprobaciones registra eventos de auditoría en el Centro de seguridad y cumplimiento de Microsoft 365. Puede ver el registro de auditoría.

1. Vaya al Sitio de cumplimiento de Microsoft 365.

2. Seleccione la **sección** Auditoría.

3. Busque actividades en las **actividades de aprobación de Microsoft Teams.**

Puede buscar las siguientes actividades:

- Crear una nueva solicitud de aprobación

- Ver detalles de la solicitud de aprobación

- Solicitud de aprobación aprobada

- Solicitud de aprobación rechazada

- Solicitud de aprobación cancelada

- Solicitud de aprobación compartida

- Archivo adjunto a la solicitud de aprobación

- Solicitud de aprobación reasignada

- Firma electrónica agregada a la solicitud de aprobación

Para obtener acceso a más aprobaciones de auditoría en Flow, habilite y configure la auditoría en el entorno predeterminado de las entidades de aprobación principales: Aprobación, Solicitud de aprobación y Respuesta de aprobación. Las operaciones crear, actualizar y eliminar son eventos auditables para registros de aprobación. Más información sobre datos [de auditoría y la actividad de usuario para seguridad y cumplimiento: Documentos de Microsoft de la plataforma \| móvil.](https://docs.microsoft.com/power-platform/admin/audit-data-user-activity)

La auditoría puede personalizarse aún más en el Centro de seguridad y cumplimiento [de Microsoft 365.](https://support.office.com/article/go-to-the-office-365-security-compliance-center-7e696a40-b86b-4a20-afcc-559218b7b1b8?ui=en-US&rs=en-US&ad=US)

1. Para usar los informes preconfigurados, inicie sesión en Seguridad y cumplimiento de Microsoft 365.

2. Seleccione **Búsqueda & investigación.**

3. Busque en el registro de auditoría y seleccione la **pestaña actividades de Dynamics 365.**

Más información sobre el registro de actividades de aplicaciones controladas por el modelo y los datos [inversos de Microsoft : Plataforma de energía.](https://docs.microsoft.com/power-platform/admin/enable-use-comprehensive-auditing)

## <a name="security"></a>Seguridad

Desde la aplicación Aprobaciones de Teams, los usuarios tienen acceso para crear nuevas aprobaciones y ver las aprobaciones que han enviado y recibido. Los usuarios no tendrán acceso a las aprobaciones creadas por otros usuarios a menos que sean respondedores o lectores de la solicitud.

> [!Note]
> A un usuario se le asigna el rol de visor de una solicitud si forma parte del chat o del canal en el que se creó la aprobación. No tendrán la capacidad de realizar acciones en la solicitud si no se les ha dado ese rol cuando se creó la aprobación.
