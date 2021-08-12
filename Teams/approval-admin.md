---
title: Aprobaciones de disponibilidad de aplicaciones en Teams
author: cichur
ms.author: v-cichur
ms.reviewer: farhazk
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
ms.openlocfilehash: ffcb99684c3f92bcc442c5f732d41643bf549b3f3c1d2aca7e5cb42df4269ebe
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54288428"
---
# <a name="teams-approvals-app-availability"></a>Disponibilidad de la aplicación Aprobaciones de Teams

La aplicación Aprobaciones está disponible como una aplicación personal para todos los usuarios de Microsoft Teams.
La aplicación Aprobaciones ofrece una forma sencilla de ejercer las auditorías, el cumplimiento, la responsabilidad y los flujos de trabajo tanto a Aprobaciones estructuradas y no estructuradas en Teams.

 ![muestra la aplicación de aprobaciones](media/approvals-selection.png)

Los usuarios pueden anclar la aplicación Aprobaciones para guardarla en la barra de menús.

 ![muestra la aplicación de aprobaciones con la opción de ancla](media/approvalApp-pin.png)

La primera aprobación creada a partir de la aplicación Aprobaciones desencadenará el aprovisionamiento de la solución de aprobación en el entorno predeterminado del Servicio de datos comunes (CDS). Las aprobaciones creadas a partir de la aplicación Aprobaciones se almacenarán en el entorno de CDS predeterminado.

En este artículo se describen los roles y requisitos de la aplicación Aprobaciones.

> [!NOTE]
> Esta característica aún no se ha publicado para Government Community Cloud (GCC), Government Community Cloud High (GCCH) y los usuarios del Departamento de Defensa (DOD).

## <a name="required-permissions-and-licenses"></a>Permisos y licencias necesarios

Para usar la aplicación Aprobaciones, necesita permisos para los elementos siguientes:

- Permisos para crear una base de datos de CDS de Microsoft.

- Una cuenta en [flow.microsoft.com](https://flow.microsoft.com/)

- Rol de administrador en el entorno de destino.

- Licencia para un [Power Automate](/power-automate/get-started-approvals), un Office 365 o una Dynamics 365.

- La licencia de Microsoft Forms es necesaria para que los usuarios configuren nuevas plantillas de aprobación.

## <a name="storage-with-cds"></a>Almacenamiento con CDS

El modelo de datos común (CDM) es el lenguaje de datos compartido que usan las aplicaciones empresariales y de análisis en el CDS. Consiste en un conjunto de esquemas de datos estandarizados y extensibles publicados por Microsoft y nuestros asociados, que permiten la coherencia de los datos y su significado en aplicaciones y procesos empresariales. Obtenga más información sobre los [Modelos de datos común de la plataforma de Microsoft Power](/power-automate/get-started-approvals).

Obtenga más información sobre el [flujo de trabajo de Aprobación](/power-automate/modern-approvals).

Las aprobaciones creadas a partir de una plantilla siguen almacenando datos en CDS, como su título, detalles, id. de plantilla y mucho más. Las respuestas que se envían en la solicitud de aprobación se almacenan en Formularios. Obtenga más información sobre  [el almacenamiento de datos para Microsoft Forms.](https://support.microsoft.com/office/data-storage-for-microsoft-forms-97a34e2e-98e1-4dc2-b6b4-7a8444cb1dc3#:~:text=Where%20data%20is%20stored%20for%20Microsoft%20Forms.%20Microsoft,European-based%20tenants%20is%20stored%20on%20servers%20in%20Europe)

>[!Note]
>Si elimina la plantilla Formulario en el sitio de Microsoft Forms, interrumpirá la plantilla de aprobación y los usuarios no podrán iniciar la solicitud. Los usuarios recibirán un error "CDB TableNotFound" al intentar abrir una plantilla de aprobación que se ha eliminado en Microsoft Forms.

Las plantillas de aprobación se almacenan en Datos de Storage (SDS), que es una plataforma de almacenamiento compatible que solo se usa internamente dentro de Microsoft. Las plantillas de ámbito de la organización se almacenan en "fragmento de espacio empresarial" de SDS y las plantillas de ámbito de equipo se almacenan en "fragmentos de grupo" de SDS. Esto significa que las plantillas de ámbito de organización comparten la misma duración del espacio empresarial y las plantillas de ámbito de grupo comparten la misma duración del equipo. Por lo tanto, la eliminación permanente del equipo elimina las plantillas relacionadas.

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

Permisos de plantilla de aprobación

- Todos los propietarios de equipos pueden crear una plantilla de aprobación para los equipos de su propiedad.

- Cuando un administrador crea una plantilla para toda su organización por primera vez, creará automáticamente un nuevo equipo de Teams para todos los administradores del inquilino, incluidos los administradores globales y de servicio del equipo. Estos administradores se agregarán como propietarios del equipo, para que puedan administrar en coadministraciones las plantillas de la organización. Los administradores que son nuevos en la organización después de crear el equipo deben agregarse manualmente como propietarios de equipos para que tengan los mismos permisos para administrar plantillas de toda la organización.

> [!Note]
> Si un administrador elimina el equipo, tiene un mes para restaurarlo en el portal Azure Active Directory (AAD) para restaurar todos los datos relacionados. Después de un mes, o si el administrador elimina este equipo dentro de la papelera de reciclaje, perderá todos los datos relacionados.

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

Las aprobaciones creadas a partir de la aplicación de Aprobaciones se almacenan en el entorno de CDS predeterminado, que no admite copias de seguridad en este momento. Obtenga más información sobre cómo [Respaldar y restaurar entornos - Power Platform \| Microsoft Docs](/power-platform/admin/backup-restore-environments).

Los datos almacenados en Formularios no se eliminarán hasta que los propietarios del equipo los limpien de la pestaña formularios **eliminados** en la aplicación web Microsoft Forms.

## <a name="data-limitations"></a>Limitaciones de datos

Cada equipo puede contener como máximo 400 plantillas de aprobaciones y cada plantilla puede recopilar un máximo de 50 000 solicitudes en función de la capacidad actual de Microsoft Forms.

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

- Detalles de solicitud de firma electrónica vistas

- Solicitud de firma electrónica revisada

- Solicitud de firma electrónica cancelada

- Crear una plantilla nueva

- Editar una plantilla existente

- Habilitar o deshabilitar una plantilla

- Plantilla vista

Para tener acceso a más aprobaciones de auditoría en Flujo, habilite y configure la auditoría en el entorno predeterminado para las entidades de aprobación primaria Aprobación, solicitud de aprobación y respuesta de aprobación. Las operaciones de creación, actualización y eliminación son eventos auditables para los registros de Aprobación. Obtenga más información sobre [Datos de Auditoría y la actividad de usuario para la seguridad y el cumplimiento: Power Platform \| Microsoft Docs](/power-platform/admin/audit-data-user-activity).

Las auditorías se pueden personalizar aún más en el [Centro de seguridad y cumplimiento de Microsoft 365](https://support.office.com/article/go-to-the-office-365-security-compliance-center-7e696a40-b86b-4a20-afcc-559218b7b1b8?ui=en-US&rs=en-US&ad=US).

1. Para usar los informes preconfigurados, inicie sesión en Seguridad y cumplimiento de Microsoft 365.

2. Seleccione **Búsqueda e investigación**.

3. Busque en el registro de Auditoría y seleccione la pestaña **Actividades de Dynamics 365**.

Obtenga más información sobre el [Registro de actividad de aplicaciones basadas en modelos y Microsoft Dataverse: Power Platform](/power-platform/admin/enable-use-comprehensive-auditing).

## <a name="security"></a>Seguridad

Desde la aplicación Aprobaciones de Teams, los usuarios tienen acceso para crear nuevas aprobaciones y ver las aprobaciones que han enviado y recibido. Los usuarios no tendrán acceso a Aprobaciones creadas por otros usuarios, excepto si son respondedores o lectores de la solicitud.

> [!Note]
> A un usuario se le asigna un rol de visor de una solicitud si forma parte del chat o canal donde se creó la aprobación. No tendrán la capacidad de realizar acciones en la solicitud si no se les ha concedido ese rol cuando se creó la aprobación.

## <a name="approvals-e-signature-integration"></a>Integración de firmas electrónicas de aprobaciones

Las aprobaciones de firma electrónica creadas desde la aplicación Aprobaciones se almacenan en el entorno en la nube del proveedor seleccionado. Para obtener más información sobre el almacenamiento en torno al contrato de firma electrónica, vea la documentación de almacenamiento del proveedor seleccionado.

Para usar la característica de firma electrónica de la aplicación Aprobaciones, necesita los siguientes elementos:

- Licencia para el proveedor de firma electrónico específico que elija usar. Para obtener una licencia para su organización, tendrá que ir al sitio del proveedor.

Para la funcionalidad de firma electrónica Aprobaciones, los partners de firma de terceros aparecerán en la aplicación Teams aprobaciones de forma predeterminada. Puede deshabilitar determinados proveedores de firma electrónica accediendo a la configuración de la aplicación en el Teams de administración.

1. En el Teams de administración, en Administrar **aplicaciones,** seleccione la aplicación Aprobaciones **y** **elija Configuración**.

2. Cada proveedor de firma electrónica tiene un botón de alternancia junto a él que se encuentra en la posición activa (derecha) de forma predeterminada. Deslice el botón de alternancia a la izquierda para deshabilitar un proveedor específico de firma electrónica. Si un Teams deshabilita un proveedor, los usuarios finales no verán el proveedor al crear una aprobación. Los usuarios finales tampoco podrán ver las solicitudes de firma electrónica realizadas con ese proveedor.

Las aprobaciones de firma electrónica creadas desde la aplicación Aprobaciones se almacenan en la nube del proveedor seleccionado. Por lo tanto, tendrá que ir al sitio del proveedor para exportar los datos sobre firmas electrónicas. Consulte la documentación del proveedor sobre la exportación y retención de estos contratos.
