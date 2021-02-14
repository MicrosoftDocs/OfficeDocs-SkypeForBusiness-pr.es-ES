---
title: 'Aplicación Pacientes de auditoría para administradores de TI y cumplimiento de Teams '
author: dstrome
ms.author: dstrome
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
ms.reviewer: anach
description: Más información sobre la auditoría de la aplicación Pacientes para administradores de Teams
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: ce1851b6d424203f6a4aed8a871209e3a65ce5f8
ms.sourcegitcommit: beaaee10019f4eda746f348888a4a3c2aaa6f196
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2020
ms.locfileid: "48803518"
---
# <a name="audit-logs-for-patients-app"></a>Registros de auditoría de la aplicación Pacientes

> [!NOTE]
> A partir del 30 de octubre de 2020, la aplicación Pacientes se ha retirado y reemplazado por la [aplicación Listas](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) en Teams. Los datos de la aplicación Pacientes se almacenan en el buzón de grupo del grupo de Office 365 que copia de seguridad del equipo. Todos los datos asociados a la aplicación Pacientes se conservan en este grupo, pero ya no se puede acceder a ellos a través de la interfaz de usuario. Los usuarios pueden volver a crear sus listas con la [aplicación Listas.](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)
>
>Con Listas, los equipos de cuidado de su organización sanitaria pueden crear listas de pacientes para situaciones que van desde rounds y reuniones de equipo interdisciplinarias hasta la supervisión general del paciente. Consulte la plantilla Pacientes en Listas para empezar. Para obtener más información sobre cómo administrar la aplicación Listas de su organización, vea [Administrar la aplicación Listas.](../../manage-lists-app.md)

Un registro de auditoría para la actividad de la aplicación Pacientes permite a los equipos de respuesta después de incidentes revisar los cambios en los registros médicos electrónicos (AND) o la información de salud del paciente (FI) y determinar si se necesitan cambios o mejoras en la directiva o procedimiento para el acceso de FI en las herramientas de productividad. Las acciones de portada de eventos del registro de auditoría realizadas a través de la interfaz de usuario de la aplicación Pacientes.

## <a name="meet-hipaa-requirements"></a>Cumplir los requisitos de HIPAA

De acuerdo con las directrices de HIPAA, los proveedores de servicios médicos deben conservar los registros de todo el acceso a la FI, por lo que es posible que los cambios se auditan. Microsoft se compromete a sus clientes empresariales a usar Microsoft Teams y a ayudarles a cumplir los requisitos y controles de HIPAA. El acceso a FI a través de la aplicación Pacientes se realiza un seguimiento completo y los registros están disponibles en el Centro de cumplimiento de Microsoft 365, tal y como se describe en el artículo sobre la funcionalidad de búsqueda de registros [de](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance) auditoría.

> [!IMPORTANT]
> La carga de mantener la privacidad de los pacientes se coloca en el proveedor de atención sanitaria por ley. La ley permite a los pacientes la privacidad y requiere que un administrador de TI o controlador de HIPAA pueda determinar fácilmente a qué enfermera, médicos o trabajadores sociales accedieron o modificaron los registros del paciente. Uno de los ejemplos más comunes de una infracción de acceso de FI es el acceso a pacientes VIP. La funcionalidad del registro de auditoría es necesaria para llevar a cabo investigaciones de cualquier infracción de acceso fi y para cumplir los requisitos de HIPAA.

<!-- add an image from the security and compliance center audit log search page showing an event, Ansuman please let me know whether we need to copy an existing screen shot (and which one) or grab a new one -->

## <a name="enable-audit-logs-for-the-patients-app"></a>Habilitar registros de auditoría para la aplicación Pacientes

Una auditoría depende de varias configuraciones anteriores:

1. El administrador tendría que trabajar con su proveedor de servicios FCONTR para tener LAN en un formato utilizado por la aplicación Pacientes. Consulte [Integración de registros sanitarios electrónicos en Microsoft Teams.](patients-app.md)
2. Un administrador del proveedor de atención sanitaria tendría que habilitar la aplicación Pacientes en el Centro de administración de Teams. Vea [Administrar directivas de configuración de aplicaciones en Microsoft Teams](../../teams-app-setup-policies.md) y artículos relacionados para obtener más información.
3. El administrador tendría que habilitar las auditorías de actividad, del mismo [](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance#before-you-begin) modo que habilitan cualquier auditoría de registro de actividades, como se describe en Antes de comenzar y activar o desactivar la búsqueda de registros [de auditoría.](https://docs.microsoft.com/office365/securitycompliance/turn-audit-log-search-on-or-off#turn-on-audit-log-search) Si el registro de auditoría ya está habilitado, no se necesita nada especial para la aplicación Pacientes. Cada vez que un proveedor de servicios médicos instala y ejecuta la aplicación en un equipo, los registros de auditoría registran su actividad de FI.
4. Entonces, el administrador tendría que anunciar la disponibilidad de la aplicación Pacientes y los trabajadores de salud tendrían que empezar a generar actividad para incluirla en una auditoría.

<!-- add link out to client doc when available -->

## <a name="run-an-audit"></a>Ejecutar una auditoría

Para obtener instrucciones sobre cómo ejecutar una búsqueda del registro de actividades, vea [Buscar en el registro de auditoría.](https://docs.microsoft.com/office365/securitycompliance/search-the-audit-log-in-security-and-compliance#search-the-audit-log)

## <a name="logged-activities-for-patients-app"></a>Actividades registradas en la aplicación Pacientes

La aplicación Pacientes tiene sus propias actividades registradas, enumeradas en la tabla siguiente:

|Nombre descriptivo |Operación|Descripción|
|:---|:---|:---|
| Lista de pacientes consultada | PatientListView | Un usuario ha visto una lista de pacientes.|
| Lista de pacientes eliminada | PatientListDelete | Un usuario eliminó una lista de pacientes.|
| Se ha agregado un paciente a la lista | PatientListAddAddEnt | Se agregó un paciente a una lista de pacientes. |
| Nota agregada para el paciente | PatientNoteAdd | Se agregó una nota al registro de un paciente. |
| Esquema de paciente creado | PatientSchemaCreate | Se creó un conjunto de columnas usadas en el registro del paciente. |
| El usuario ha iniciado una exportación | ExportInitiation | Los datos del paciente se exportaron desde la aplicación Pacientes a un archivo de Excel. El archivo se guardará en el sitio de SharePoint del equipo. |
| Lista de pacientes creada | PatientListCreate | Un usuario ha creado una lista de pacientes.|
| Establecer la lista de pacientes predeterminada| PatientListDefaultSet| Un usuario establece una lista concreta como lista predeterminada.|
| Pacientes eliminados de la lista| PatientListRemoveEnt | Se quitó a un paciente de una lista de pacientes. |
| Paciente buscado | PatientSearch | Se ha buscado el registro de un paciente en el servicio de EHR. |
| Esquema del paciente actualizado | PatientSchemaUpdate  | Se ha actualizado un conjunto de columnas existente que se usa en el registro del paciente. |<!-- | Paciente movido a una lista diferente| PatientMoved | El registro del paciente se movió de una lista a otra. |-->
| Lista de pacientes con nombre cambiado | PatientListRename | Se cambió el nombre de una lista de pacientes. |
| Columnas editadas en la lista de pacientes | PatientListEditColumns | Se editó (agregó o eliminó) una columna de una lista de pacientes. |
| Detalles del paciente vistos | PatientView | Un usuario ha visto el registro de un paciente.|
| Detalles editados del paciente | PatientDetailsEdit | Se editó un detalle del registro de un paciente. |
| Establecer conexión EHR | EHRConnectionSet | Establezca la dirección URL usada para conectarse a la conexión del servicio EHR FCONTR. Ejemplo: https://<span>api-v8-dstu2.hspconsortium.org/ContosoHospital/open</span>  |
||||

Puede personalizar la auditoría según sea necesario para buscar o filtrar cualquiera de estas actividades registradas.

Las actividades registradas de Microsoft Teams en general se describen en las [actividades de Microsoft Teams.](https://docs.microsoft.com/office365/securitycompliance/search-the-audit-log-in-security-and-compliance#microsoft-teams-activities)

## <a name="related-topics"></a>Temas relacionados

[Buscar en el registro de auditoría](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)

[Integración de registros sanitarios electrónicos en Microsoft Teams](patients-app.md)
