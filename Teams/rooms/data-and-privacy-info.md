---
title: Información de datos y privacidad
author: donnah007
ms.author: v-donnahill
manager: serdars
ms.date: 06/01/2022
ms.reviewer: ''
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Información de datos y privacidad
f1keywords: Microsoft Teams Rooms Managed Service Data and Privacy Information
ms.openlocfilehash: 3fa24a1009c5480c308dfc35306286d470178820
ms.sourcegitcommit: e38776625a3623216b0d5f092fffaff67519b1a6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/13/2022
ms.locfileid: "66057090"
---
# <a name="approach"></a>Enfoque

Los clientes que usan Salas de Microsoft Teams Servicios administrados confían a Microsoft su activo más valioso: los datos. Confían en que se protegerá su privacidad y que solo se utilizará de manera coherente con sus expectativas.

La tecnología sigue procesos de privacidad para asegurarse de que se ajusta a las promesas del cliente en la recopilación y el uso de datos que ejecutan el servicio de forma eficaz.
## <a name="data-collection-and-privacy"></a>Recopilación de datos y privacidad

 Salas de Microsoft Teams Servicios administrados supervisa los dispositivos, recopila datos de contenido de clientes y accede de forma remota a los dispositivos y los administra como administrador. Los datos recopilados se limitan a la información necesaria para supervisar el estado, la causa raíz y los problemas de mitigación identificados en los salones inscritos. Algunos datos recopilados son específicos de una cuenta de salón, no de usuarios individuales.

> [!Note]
> Las referencias incidentales a un usuario individual pueden estar presentes en el registro de actividades durante el uso del dispositivo.

## <a name="who-can-access-data"></a>Quién pueden acceder a los datos

Servicios administrados toma medidas sólidas para ayudar a proteger los datos de los clientes contra el acceso o el uso inadecuados por parte de personas no autorizadas. Entre estas medidas se incluyen restringir el acceso por parte del personal y subcontratistas de Microsoft.

## <a name="zero-standing-access-data-storage"></a>Almacenamiento de datos de Zero Standing Access

Servicios administrados mitiga los riesgos asociados con las cuentas con acceso privilegiado de actores malintencionados, tanto dentro como fuera de una organización, mediante el principio de Acceso permanente cero. Este principio permite que los Servicios administrados funcionen sin privilegios disponibles de forma predeterminada para cualquier usuario. Combinado con los principios de Just-In-Time y Just-Enough-Access, proporciona un marco sólido para ser seguro y compatible de forma predeterminada. Los datos de diagnóstico están disponibles para el equipo de operaciones de servicio de Microsoft a través de un portal interno.

## <a name="data-handling"></a>Tratamiento de datos

Microsoft se rige por normas estrictas para la transmisión, el almacenamiento, el uso y la retención de datos. Microsoft tiene directivas estándar de tratamiento de datos que regulan cómo deben tratarse los datos en función de la clasificación de los datos.



## <a name="technology-description"></a>Descripción de la tecnología

Servicios administrados envía datos a Microsoft con el fin de supervisar, diagnosticar y mitigar cualquier problema de la implementación. Algunos ejemplos son

- Garantizar que el dispositivo esté actualizado (incluida la aplicación, el sistema operativo, los controladores, F/W)
- Garantizar que el dispositivo esté listo para usar (ha iniciado sesión, todos los periféricos informan del estado de mantenimiento, etc.)
- Garantizar que el entorno esté listo (las cuentas aprovisionadas, las velocidades de red son lo suficientemente rápidas, etc.)
- Determinar si puede haber problemas de hardware o problemas de instalación (como cableado suelto)
- Heurística para determinar problemas (reinicios excesivos, etc.)

Servicios administrados administra el dispositivo con las siguientes acciones:

- Actualizar software
- Mitigar problemas mediante reinicios, restablecimiento de conexiones USB & estados
- Recopilar registros específicos para ayudar a diagnosticar problemas

Los Servicios administrados no supervisan ni graban audio, vídeo, multimedia ni contenido de reuniones desde los kits de soluciones.

### <a name="service-collected-data-categories"></a>Categorías de datos recopiladas por el servicio
 
|Categoría|Detalles|Motivo de la consulta|
| :- | :- | :- |
|Recopilación y administración de datos continuos|Dirección IP, identidad de la cuenta de sala (Exchange, Skype Empresarial y/o Teams), coordenadas de ubicación, correos electrónicos y comunicación dentro del portal con Microsoft o software|Identificar y conectarse al sistema bajo gestión; identificar, diagnosticar y mitigar errores; realizar un seguimiento del uso, el análisis y la información; estado de conectividad de consulta y reparación|
|Administración y recopilación de datos ad hoc|Información de registro de eventos, actividad del usuario/identidad del usuario de la sala que ha iniciado sesión en el archivo de registro junto con información de diagnóstico, Windows consultas del sistema (ejemplos: Lista de dispositivos USB, estado de energía, etc.)|Identificar, diagnosticar y mitigar errores y para uso, análisis e información|

Determinados datos confidenciales del registro Actividad de dispositivo se des menoscaban localmente (no se recopilan mediante servicios administrados):

- Asunto y cuerpo de la reunión
- Información de la tarjeta de contacto de los asistentes a la reunión (como el título, el número de teléfono, etc.)
- Contenido del mensaje de mensajería instantánea en la reunión

> [!NOTE]
> A medida que Microsoft evoluciona los Servicios administrados, los datos específicos están sujetos a cambios.

### <a name="enrollment"></a>Inscripción

Servicios administrados se registra con el portal en línea para servicios de supervisión y soporte automatizados, incluidos diagnósticos e informes. La inscripción se realiza a través de comunicaciones de red cifradas con la clave pública basada en el Módulo de plataforma segura (TPM) del dispositivo.

### <a name="unenrollment"></a>Anular la inscripción

Para anular la inscripción del dispositivo, desinstale Servicios administrados. Microsoft también quita el dispositivo de la supervisión back-end durante la retirada y puede eliminar los datos recopilados bajo solicitud.
## <a name="compliance"></a>Cumplimiento

Todos los ingenieros que trabajan en el producto deben someterse a formación de seguridad y conciencia de privacidad. Microsoft también garantiza que todo el personal certifique la aceptación de responsabilidades por los requisitos de privacidad.

Servicios administrados proporciona soporte de residencia de datos regional a través de los centros de datos de Europa (UE), Asia Pacífico (APAC) y los Estados Unidos (EE. UU.). Los clientes del servicio tendrán datos relacionados con la organización almacenados en el centro de datos de su región elegida.

## <a name="more-resources"></a>Más recursos

Salas de Microsoft Teams Seguridad:/microsoftteams/rooms/security Declaración de privacidad de Microsoft: https://aka.ms/privacy Administración de datos en Microsoft: https://www.microsoft.com/trust-center/privacy/data-management Descripción del servicio de Servicios administrados: [Microsoft Teams servicio administrado](microsoft-teams-rooms-premium.md) por salas
