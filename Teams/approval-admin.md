---
title: Administrar la aplicación Aprobaciones en Microsoft Teams
author: LanaChin
ms.author: v-lanachin
ms.reviewer: farhazk
manager: samanro
ms.topic: how-to
audience: admin
ms.service: msteams
searchScope:
- Microsoft Teams
search.appverid: MET150
description: Obtenga información sobre cómo administrar la aplicación Aprobaciones para su organización en Microsoft Teams.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365-frontline
- highpri
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3cf50824119111d34668f4717eaf38f92de8bc64
ms.sourcegitcommit: e6182aa3b15346dc955333a2bc571565ef463a57
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/28/2022
ms.locfileid: "68784335"
---
# <a name="manage-the-approvals-app-in-microsoft-teams"></a>Administrar la aplicación Aprobaciones en Microsoft Teams

La aplicación Aprobaciones está disponible como una aplicación personal para todos los usuarios de Microsoft Teams.
La aplicación Aprobaciones ofrece una forma sencilla de ejercer las auditorías, el cumplimiento, la responsabilidad y los flujos de trabajo tanto a Aprobaciones estructuradas y no estructuradas en Teams.

 ![muestra la aplicación de aprobaciones.](media/approvals-selection.png)

Los usuarios pueden anclar la aplicación Aprobaciones para guardarla en la barra de menús.

 ![muestra la aplicación de aprobaciones con la opción anclar.](media/approvalApp-pin.png)

La primera aprobación creada desde la aplicación Aprobaciones desencadenará el aprovisionamiento de la solución de aprobación en el entorno predeterminado de Microsoft Dataverse. Las aprobaciones creadas desde la aplicación Aprobaciones se almacenarán en el entorno predeterminado de Microsoft Dataverse.

En este artículo se describen los roles y requisitos de la aplicación Aprobaciones.

> [!NOTE]
> Esta característica aún no se ha publicado para los usuarios de Government Community Cloud High (GCCH) ni del Departamento de Defensa (DOD).

## <a name="required-permissions-and-licenses"></a>Permisos y licencias necesarios

Para implementar la aplicación Aprobaciones, necesita permiso para los siguientes elementos:

- Permisos para crear una base de datos de Microsoft Dataverse.

- Una cuenta en [powerautomate.microsoft.com](https://powerautomate.microsoft.com/)

- Rol de administrador en el entorno de destino.

- Licencia de [Power Automate](/power-automate/get-started-approvals), Office 365 o Dynamics 365.

- Se requiere licencia para Microsoft Forms para que los usuarios configuren nuevas plantillas de aprobación.

Para usar la aplicación Aprobaciones, necesita una licencia de Power Automate y su cuenta se agrega automáticamente al rol Usuario de aprobaciones en el entorno de destino en la primera asignación de aprobación.

## <a name="storage-with-microsoft-dataverse"></a>Almacenamiento con Microsoft Dataverse

El modelo de datos común (CDM) es el lenguaje de datos compartido que usan las aplicaciones empresariales y analíticas en Microsoft Dataverse. Se compone de un conjunto de esquemas de datos estandarizados y extensibles publicados por Microsoft y nuestros asociados que permite la coherencia de los datos y su significado en las aplicaciones y los procesos empresariales. Obtenga más información sobre los [Modelos de datos común de la plataforma de Microsoft Power](/power-automate/get-started-approvals).

Obtenga más información sobre el [flujo de trabajo de Aprobación](/power-automate/modern-approvals).

Las aprobaciones que se crean a partir de una plantilla siguen almacenando datos en Microsoft Dataverse, como su título, detalles, id. de plantilla y mucho más. Las respuestas que se envían en la solicitud de aprobación se almacenan en Forms. Obtenga más información sobre [Almacenamiento de datos para Microsoft Forms](https://support.microsoft.com/office/data-storage-for-microsoft-forms-97a34e2e-98e1-4dc2-b6b4-7a8444cb1dc3#:~:text=Where%20data%20is%20stored%20for%20Microsoft%20Forms.%20Microsoft,European-based%20tenants%20is%20stored%20on%20servers%20in%20Europe).

>[!Note]
>Si elimina la plantilla de formulario en el sitio Microsoft Forms, se romperá la plantilla Aprobación y los usuarios no podrán iniciar la solicitud. Los usuarios reciben el error "CDB TableNotFound" al intentar abrir una plantilla de Aprobación que se elimina en Microsoft Forms.

Las plantillas de ámbito de organización comparten la misma duración del inquilino y las plantillas de ámbito de equipo comparten la misma duración del equipo. Por lo tanto, al eliminar permanentemente el equipo, se eliminan las plantillas relacionadas.

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

- Todos los propietarios de equipos pueden crear una plantilla de aprobación para los equipos de los que son propietarios.

- Cuando un administrador crea una plantilla para toda la organización por primera vez, se crea automáticamente un nuevo grupo de Azure Active Directory (AAD) para todos los administradores del inquilino, incluidos los administradores globales y de servicios de Teams. Estos administradores se agregan como propietarios del grupo, por lo que pueden coadministrar plantillas organizativas. Los administradores que son nuevos en la organización después de crear el equipo deben agregarse manualmente como propietarios del grupo para que tengan los mismos permisos para administrar las plantillas de toda la organización.

> [!Note]
> Si un administrador elimina el grupo, dispone de un mes para restaurarlo en el portal de Azure Active Directory (AAD) para restaurar todos los datos relacionados. Después de un mes, o si el administrador elimina este grupo dentro de la Papelera de reciclaje, perderá todos los datos relacionados.

## <a name="disable-the-approvals-app"></a>Administrar la aplicación Aprobaciones

La aplicación Aprobaciones está disponible de forma predeterminada. Puede deshabilitar la aplicación en el Centro de administración de Microsoft Teams.

  1. Inicie la sesión en el Centro de administración de Teams

  2. Vaya a **Aplicaciones de Teams** > **Administrar aplicaciones**.

  3. Busque la aplicación Aprobaciones.

     ![muestra la navegación del centro de Administración con Las aplicaciones de Teams > Administrar aplicaciones resaltado.](media/manage-approval-apps.png)

  4. Seleccione **Aprobaciones**.

  5. Seleccione el botón de alternancia para deshabilitar la aplicación para su organización.

     :::image type="content" alt-text="muestra los detalles de la aplicación Aprobaciones." source="media/approvals-details-new.png" lightbox="media/approvals-details-new.png":::

## <a name="pin-approvals-to-teams"></a>Anclar aprobaciones a Teams

### <a name="use-the-tailored-frontline-app-experience-to-pin-approvals-and-other-apps-to-teams"></a>Usar la experiencia de aplicación de primera línea adaptada para anclar Aprobaciones y otras aplicaciones a Teams

La experiencia de aplicación de primera línea adaptada en Teams ancla las aplicaciones más relevantes en Teams para los usuarios que tienen una [licencia F](https://www.microsoft.com/microsoft-365/enterprise/frontline#office-SKUChooser-0dbn8nt). Entre las aplicaciones ancladas se incluyen Aprobaciones, Walkie Talkie, Tareas y Turnos. De forma predeterminada, esta característica está activada, lo que ofrece a sus trabajadores de primera línea una experiencia predefinida que se adapta a sus necesidades.

Las aplicaciones se anclan en la barra de aplicaciones (la barra situada en el lateral del cliente de escritorio de Teams y en la parte inferior de los clientes móviles de Teams), donde los usuarios pueden acceder a ellas de forma rápida y sencilla.

Para obtener más información, incluido cómo funciona la experiencia con las directivas de aplicaciones que establezca, consulte [Personalizar las aplicaciones de Teams para los trabajadores de primera línea](/microsoft-365/frontline/pin-teams-apps-based-on-license?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoftteams%2ftoc.json).

### <a name="use-an-app-setup-policy-to-pin-approvals-to-teams"></a>Usar una directiva de configuración de aplicaciones para anclar Aprobaciones a Teams

Las directivas de configuración de aplicaciones le permiten personalizar Teams para anclar las aplicaciones que son más importantes para los usuarios de sus usuarios.

Para anclar la aplicación Aprobaciones para los usuarios, puede editar la directiva global (predeterminada para toda la organización) o crear y asignar una directiva personalizada en la directiva de configuración de la aplicación. Para obtener más información, consulte [Administrar las directivas de configuración de aplicaciones en Teams](teams-app-setup-policies.md).

## <a name="retention-policy"></a>Directiva de retención

Las aprobaciones creadas desde la aplicación Aprobaciones se almacenan en el entorno predeterminado de Microsoft Dataverse, que no admite copias de seguridad en este momento. Obtenga más información sobre cómo [Respaldar y restaurar entornos - Power Platform \| Microsoft Docs](/power-platform/admin/backup-restore-environments).

Los datos almacenados en Forms no se eliminarán hasta que los propietarios del equipo los limpien de la pestaña **formularios eliminados** de la aplicación web de Microsoft Forms.

## <a name="conditional-access-policies"></a>Directivas de acceso condicional

Actualmente, la aplicación Aprobaciones en Teams no es compatible con las directivas de acceso condicional establecidas para Microsoft Teams.

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

- Detalles de la solicitud de firma electrónica consultada

- Solicitud de firma electrónica revisada

- Solicitud de firma electrónica cancelada

- Crear una nueva plantilla

- Editar una plantilla existente

- Habilitar o deshabilitar una plantilla

- Plantilla visualizada

Para obtener acceso a más aprobaciones de auditoría en Power Automate, habilite y configure la auditoría en el entorno predeterminado para las entidades de aprobación principales Aprobación, Solicitud de aprobación y Respuesta de aprobación. Las operaciones de creación, actualización y eliminación son eventos auditables para los registros de Aprobación. Obtenga más información sobre [Datos de Auditoría y la actividad de usuario para la seguridad y el cumplimiento: Power Platform \| Microsoft Docs](/power-platform/admin/audit-data-user-activity).

Las auditorías se pueden personalizar aún más en el [Centro de seguridad y cumplimiento de Microsoft 365](https://support.office.com/article/go-to-the-office-365-security-compliance-center-7e696a40-b86b-4a20-afcc-559218b7b1b8?ui=en-US&rs=en-US&ad=US).

1. Para usar los informes preconfigurados, inicie sesión en Seguridad y cumplimiento de Microsoft 365.

2. Seleccione **Búsqueda e investigación**.

3. Busque en el registro de Auditoría y seleccione la pestaña **Actividades de Dynamics 365**.

Obtenga más información sobre el [Registro de actividad de aplicaciones basadas en modelos y Microsoft Dataverse: Power Platform](/power-platform/admin/enable-use-comprehensive-auditing).

## <a name="security"></a>Seguridad

Desde la aplicación Aprobaciones de Teams, los usuarios tienen acceso para crear nuevas aprobaciones y ver las aprobaciones que han enviado y recibido. Los usuarios no tendrán acceso a Aprobaciones creadas por otros usuarios, excepto si son respondedores o lectores de la solicitud.

>[!Note]
> A un usuario se le asigna un rol de visor de una solicitud si forma parte del chat o canal en el que se creó la aprobación. No tendrán la capacidad de realizar acciones en la solicitud si no se les ha concedido ese rol cuando se creó la aprobación.

## <a name="approvals-e-signature-integration"></a>Integración de firma electrónica de aprobaciones

Para usar la característica de firma electrónica de la aplicación Aprobaciones, necesita una licencia para el proveedor de firmas electrónicas específico que desee usar. Para obtener una licencia para su organización, tendrá que ir al sitio del proveedor.

### <a name="enable-or-disable-e-signature-providers"></a>Habilitar o deshabilitar proveedores de firmas electrónicas

Puede usar el Centro de administración de Teams para controlar qué proveedores de firmas electrónicas de terceros están disponibles para los usuarios en la aplicación Aprobaciones. De forma predeterminada, los proveedores de firmas electrónicas están habilitados en la aplicación Aprobaciones. Al deshabilitar un proveedor de firmas electrónicas, los usuarios no tendrán acceso a ese proveedor cuando creen aprobaciones. Los usuarios tampoco podrán ver solicitudes de firma electrónica creadas con ese proveedor.

1. En el panel izquierdo del Centro de administración de Teams, vaya a Aplicaciones  > **de Teams****Administrar aplicaciones**.
2. Busque la aplicación Aprobaciones y selecciónela.
3. Ve a la pestaña **Configuración** y, a continuación, realiza una o varias de las siguientes acciones:

    - Para habilitar o deshabilitar Adobe Sign, cambie el botón de alternancia a **Activado** o **Desactivado**.
    - Para habilitar o deshabilitar DocuSign, cambie el botón de alternancia a **Activado** o **Desactivado**.
4. Selecciona **Enviar**.

Las aprobaciones de firma electrónica creadas desde la aplicación Aprobaciones se almacenan en el entorno en la nube del proveedor seleccionado. Para exportar datos sobre firmas electrónicas, deberá ir al sitio del proveedor. Para obtener más información sobre el almacenamiento, la exportación y la retención de contratos de firma electrónica, consulte la documentación del proveedor.
