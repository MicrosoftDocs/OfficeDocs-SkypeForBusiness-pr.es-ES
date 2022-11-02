---
title: Datos de Entrenador profesional e información de cumplimiento
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: ''
search.appverid: MET150
f1keywords: ''
description: Obtenga información sobre las medidas de privacidad, cumplimiento y ámbito profesional adoptadas por Microsoft en relación con la educación o el Entrenador profesional de edu.
appliesto:
- Microsoft Teams
ms.localizationpriority: high
ms.openlocfilehash: 0f28381aad61cbe7fecf21e189bc5ab278ce3008
ms.sourcegitcommit: 9ea1ed450ba89e9cbc094018a832bd25c08e92e4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/02/2022
ms.locfileid: "68825692"
---
# <a name="career-coach-data-and-compliance"></a>Datos y cumplimiento de Entrenador profesional

En este artículo se describe cómo usar la funcionalidad desde la aplicación, así como otras herramientas para ayudarle a encontrar datos personales o información personal e información personal para responder a la solicitud del interesado (DSR) en cumplimiento de sus obligaciones con el RGPD. El Entrenador profesional clasifica ampliamente los datos en dos categorías: el contenido del cliente y los registros generados por el sistema. En el Entrenador profesional, el contenido del cliente incluye datos de usuario, datos de configuración de inquilinos y datos de actividad de estudiantes, mientras que los registros generados por el sistema incluyen registros y datos relacionados generados por Microsoft que ayudan a Microsoft a proporcionar servicios empresariales a los usuarios.

## <a name="customer-content"></a>Contenido del cliente

### <a name="user-data"></a>Datos de usuario

Los datos de usuario recopilados por el Entrenador profesional incluyen información de perfil como objetivos y progreso de actividades, campo de estudio, año escolar, habilidades guardadas, carreras guardadas, currículos cargados y transcripciones.

#### <a name="deleting-user-data"></a>Eliminar datos de usuario

Siga estos pasos para eliminar los datos de usuario del Entrenador profesional:

1. Un administrador global debe [abrir una incidencia](https://edusupport.microsoft.com/support?product_id=career_coach) de soporte técnico que indique claramente la solicitud de una operación  **DSR de eliminación del RGPD (solicitudes del interesado). No hay ninguna capacidad para limitar el conjunto de datos o el intervalo de tiempo de la eliminación**.
2. La solicitud debe indicar claramente el tipo de datos que debe eliminarse:
    1. Todos los datos de usuario del inquilino.
    2. Datos de usuario de un usuario específico. Incluya el OID (identificadores de objeto) del usuario como parte de la solicitud de eliminación.
3. Una vez presentada, la incidencia de soporte técnico se abordará después de una semana para cumplir con la directiva de retención mínima del cumplimiento. Puede cancelar la operación durante este tiempo.
4. Después de una semana, el equipo de Entrenador profesional elimina todos los datos relacionados con el inquilino. El soporte técnico de Microsoft supervisa el vale y le notificará cuando se complete el proceso de eliminación **, en un máximo de 30 días**.

#### <a name="exporting-user-data"></a>Exportar datos de usuario

Siga estos pasos para exportar datos de usuario desde el Entrenador profesional:

1. [Abrir Entrenador](https://aka.ms/Career_Coach_App)  profesional y ver tu perfil.
1. Desplázate hasta la sección privacidad y seguridad.
1. Selecciona "Descargar" para exportar todos los datos de cliente de tu cuenta.

### <a name="tenant-configuration-data"></a>Datos de configuración de inquilino

Los datos del inquilino incluyen información cargada o generada como parte de la configuración de la aplicación Entrenador profesional. Estos datos incluyen la información de marca de un inquilino, el logotipo y el icono de aprendizaje, el catálogo del curso, la dirección URL de la escuela de LinkedIn, los campos de la lista de estudio y el resto de los datos agregados durante la configuración del inquilino de Entrenador profesional en el Centro de administración de Teams.

#### <a name="deleting-tenant-configuration-data"></a>Eliminar datos de configuración de inquilino

Siga estos pasos para eliminar los datos de configuración de inquilino del Entrenador profesional:

1. Un administrador global debe [abrir una incidencia de soporte](https://edusupport.microsoft.com/support?product_id=career_coach) técnico indicando claramente la solicitud de eliminar los datos de configuración de su inquilino.  **No hay ninguna capacidad para limitar el conjunto de datos o el intervalo de tiempo de la eliminación**.
1. Una vez presentada, la incidencia de soporte técnico se abordará después de una semana para cumplir con la directiva de retención mínima del cumplimiento. Puede cancelar la operación durante este tiempo.
1. Después de una semana, el equipo de Entrenador profesional elimina todos los datos relacionados con el inquilino. El soporte técnico de Microsoft supervisa el vale y le notificará cuando se complete el proceso de eliminación **, en un máximo de 30 días**.

### <a name="student-activity-data"></a>Datos de actividad de los alumnos

El Entrenador profesional almacena los datos de actividad de los alumnos en la misma ubicación  [que Insights para Educación](class-insights.md). Los datos agregados se exponen dentro de la experiencia de información de la actividad de los alumnos del Entrenador profesional. Los datos de uso de alumnos capturados para alimentar esta característica se almacenan y conservan durante un año.

#### <a name="deleting-student-activity-data"></a>Eliminar datos de actividad de alumnos

Para quitar los datos de actividad de los alumnos de una persona o inquilino, siga los pasos de [Cómo eliminar datos de usuario de Información de Educación](class-insights.md#how-to-delete-user-data-from-education-insights).

## <a name="system-generated-logs"></a>Registros generados por el sistema

Los registros generados por el sistema incluyen registros y datos relacionados generados por Microsoft que ayudan a Microsoft a proporcionar servicios empresariales a los usuarios. Los registros generados por el sistema contienen principalmente datos seudonimizados, como identificadores únicos (normalmente un número generado por el sistema) que no pueden identificar por sí mismos a una persona individual, pero se usan para proporcionar los servicios empresariales a los usuarios. Algunos ejemplos de estos datos son:

- Datos de uso de productos y servicios, como los registros de actividad de usuario.
- Solicitudes de búsqueda de usuario y datos de consulta.
- Datos generados por productos y servicios como producto de la funcionalidad del sistema y la interacción por parte de usuarios u otros sistemas.

> [!NOTE]
> La capacidad de restringir o rectificar los datos en los registros generados por el sistema no es compatible. Los datos de los registros generados por el sistema constituyen acciones objetivas realizadas dentro de la nube de Microsoft y datos de diagnóstico, y las modificaciones a dichos datos comprometerían el registro histórico de acciones y aumentarían los riesgos de fraude y seguridad. Entrenador profesional conserva registros generados por el sistema durante 30 días.

### <a name="exporting-and-deleting-system-generated-logs"></a>Exportar y eliminar registros generados por el sistema

El administrador global de inquilinos es la única persona de la organización que puede tener acceso a los registros generados por el sistema asociados con el uso que hace un usuario determinado de los servicios y aplicaciones de Office 365. Entrenador profesional se alinea con [el proceso de acceso y exportación de registros generados por el sistema proporcionados por Office 365](https://learn.microsoft.com/compliance/regulatory/gdpr-dsr-Office365#accessing-and-exporting-system-generated-logs).

## <a name="more-information"></a>Más información

- [Introducción al Entrenador profesional de Microsoft Teams](career-coach.md)
- [Preguntas más frecuentes sobre privacidad](https://privacy.microsoft.com/faq)
- [Productos de Microsoft y sus datos: Privacidad de Microsoft](https://privacy.microsoft.com/privacy-in-our-products)
- [Configuración de privacidad de la cuenta de Microsoft](https://account.microsoft.com/account/privacy?refd=privacy.microsoft.com&ru=https%3A%2F%2Faccount.microsoft.com%2Fprivacy%2F%3Frefd%3Dprivacy.microsoft.com&destrt=privacy-dashboard)
