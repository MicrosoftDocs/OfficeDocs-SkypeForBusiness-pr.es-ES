---
title: Disponibilidad de la aplicación de aprobaciones en Teams
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
description: Obtenga más información sobre la disponibilidad de la aplicación aprobaciones en Microsoft Teams.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4326408b7e27aa19af8e6c404d7275d26ba90969
ms.sourcegitcommit: d73d732591944b899a9366f79b4ea97f4a7f2260
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/15/2020
ms.locfileid: "49675198"
---
# <a name="teams-approvals-app-availability"></a>Disponibilidad de la aplicación de aprobaciones de Teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

La aplicación aprobaciones está disponible como una aplicación personal para todos los usuarios de Microsoft Teams.
La aplicación aprobaciones ofrece una manera sencilla de realizar auditorías, cumplimiento, responsabilidad y flujos de trabajo tanto de aprobaciones estructuradas como sin estructurar en Teams.

 ![muestra la aplicación aprobaciones](media/approvals-selection.png)

Los usuarios pueden anclar la aplicación aprobaciones para guardarla en la barra de menús.

 ![muestra la aplicación aprobaciones con la opción PIN](media/approvalApp-pin.png)

La primera aprobación creada desde la aplicación aprobaciones desencadenará el aprovisionamiento de la solución de aprobación en el entorno predeterminado de Common Data Service (CD). Las aprobaciones creadas desde la aplicación aprobaciones se almacenarán en el entorno de CDS predeterminado.

En este artículo se describen los requisitos y los roles de la aplicación aprobaciones.

## <a name="required-permissions-and-licenses"></a>Permisos y licencias necesarios

Para usar la aplicación aprobaciones, necesita permiso para los siguientes elementos:

- Permisos para crear una base de datos de Microsoft CD.

- Una cuenta en [Flow.Microsoft.com](https://flow.microsoft.com/)

- Rol de administrador en el entorno de destino.

- Licencia para una [automatización de potencia](https://docs.microsoft.com/power-automate/get-started-approvals), un Office 365 o un Dynamics 365.

## <a name="storage-with-cds"></a>Almacenamiento con CD

El modelo de datos común (CDM) es el idioma de datos compartidos que usan las aplicaciones empresariales y analíticas en los CD. Consta de un conjunto de esquemas de datos estandarizados y extensibles publicados por Microsoft y nuestros socios que permiten la coherencia de los datos y su significado entre las aplicaciones y los procesos empresariales. Obtenga más información sobre el [modelo de datos común de la plataforma Power de Microsoft](https://docs.microsoft.com/power-automate/get-started-approvals).

Obtenga más información sobre el [flujo de trabajo de aprobación](https://docs.microsoft.com/power-automate/modern-approvals).

## <a name="approvals-teams-app-permissions"></a>Permisos de la aplicación Teams de aprobaciones

La aplicación equipos de aprobaciones le permite acceder a las siguientes características:

- Reciba los mensajes y los datos que le proporcione.

- Envíale mensajes y notificaciones.

- Representar cuadros de diálogo y aplicaciones personales sin un encabezado proporcionado por Teams.

- Obtenga acceso a la información de su perfil, como el nombre, la dirección de correo electrónico, el nombre de la empresa y el idioma preferido.

- Recibir mensajes y datos que los miembros del equipo proporcionan a él en un canal.

- Enviar mensajes y notificaciones en un canal.

- Obtener acceso a la información de su equipo:
  - nombre del equipo
  - lista de canales
  - lista (nombres de los miembros del equipo y direcciones de correo electrónico).

- Use la información del equipo para ponerse en contacto con él.

## <a name="disable-the-approvals-app"></a>Deshabilitar la aplicación aprobaciones

La aplicación aprobaciones está disponible de forma predeterminada. Puede deshabilitar la aplicación en el centro de administración de Teams.

  1. Inicie sesión en el centro de administración de Teams.

  2. Expanda **aplicaciones de Teams** y seleccione **Administrar aplicaciones**.

  3. Busque la aplicación aprobaciones.

![muestra la navegación del centro de administración con aplicaciones de Teams > administrar aplicaciones resaltadas](media/manage-approval-apps.png)

  4. Seleccione aprobaciones.

  5. Seleccione el botón de alternancia para deshabilitar la aplicación de su organización.

![muestra los detalles de la aplicación aprobaciones](media/approvals-details.png)

## <a name="retention-policy"></a>Directiva de retención

Las aprobaciones creadas desde la aplicación aprobaciones se almacenan en el entorno de CDS predeterminado, que no es compatible con las copias de seguridad en este momento. Más información sobre cómo [realizar copias de seguridad y restaurar entornos: Power Platform de \| Microsoft docs](https://docs.microsoft.com/power-platform/admin/backup-restore-environments).

## <a name="auditing"></a>Auditoría

La aplicación aprobaciones registra los eventos de auditoría en el centro de seguridad y cumplimiento de Microsoft 365. Puede ver el registro de auditoría.

1. Vaya al sitio de cumplimiento de M365.

2. Seleccione la sección **Auditoría** .

3. Buscar actividades en **actividades de aprobaciones de Microsoft Teams**.

Puede buscar las actividades siguientes:

- Crear nueva solicitud de aprobación

- Ver detalles de solicitud de aprobación

- Solicitud de aprobación aprobada

- Solicitud de aprobación rechazada

- Solicitud de aprobación cancelada

- Solicitud de aprobación compartida

- Archivo adjunto a solicitud de aprobación

- Solicitud de aprobación reasignada

- Se ha agregado la firma electrónica a la solicitud de aprobación

Para obtener acceso a más aprobaciones de auditoría dentro del flujo, habilite y configure la auditoría en el entorno predeterminado para la aprobación de las principales entidades de aprobación, la solicitud de aprobación y la respuesta de aprobación. Las operaciones de crear, actualizar y eliminar son eventos que se pueden auditar para registros de aprobación. Obtenga más información sobre los [datos de auditoría y la actividad de los usuarios para seguridad y cumplimiento: plataforma de energía \| Microsoft docs](https://docs.microsoft.com/power-platform/admin/audit-data-user-activity).

La auditoría se puede personalizar en el [centro de seguridad y cumplimiento de Microsoft 365](https://support.office.com/article/go-to-the-office-365-security-compliance-center-7e696a40-b86b-4a20-afcc-559218b7b1b8?ui=en-US&rs=en-US&ad=US).

1. Para usar los informes preconfigurados, inicie sesión en Office 365 Security and Compliance.

2. Seleccione **buscar & investigación**.

3. Busque en el registro de auditoría y seleccione la pestaña **actividades de Dynamics 365** .

Más información sobre [el registro de actividad de Microsoft inverso y aplicaciones controladas por modelos: plataforma de energía](https://docs.microsoft.com/power-platform/admin/enable-use-comprehensive-auditing).

## <a name="security"></a>Seguridad

Desde la aplicación de aprobación de equipos, los usuarios tienen acceso para crear nuevas aprobaciones y ver aprobaciones que hayan enviado y recibido. Los usuarios no tendrán acceso a las aprobaciones creadas por otros usuarios, a menos que sean un respondedor o un visor de la solicitud.

> [!Note]
> Un usuario tendrá la función de visor de una solicitud si forma parte de la conversación o del canal en el que se creó la aprobación. No tendrán la posibilidad de tomar medidas en la solicitud si no se dieron a ese rol cuando se creó la aprobación.
