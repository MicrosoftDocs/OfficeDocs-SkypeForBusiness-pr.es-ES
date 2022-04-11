---
title: Información de datos y privacidad
author: donnah007
ms.author: v-donnahill
manager: serdars
ms.date: 04/07/2022
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
ms.openlocfilehash: 0aea2402705eb817c7f075cf003245c0ad3258fd
ms.sourcegitcommit: b70f01d7eae2e3e6f7495c685518a2037aaece31
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/11/2022
ms.locfileid: "64757145"
---
# <a name="approach"></a>Enfoque

Los clientes que usan servicios administrados confían a Microsoft su activo más valioso: los datos. Confían en que se protegerá su privacidad y que solo se utilizará de manera coherente con sus expectativas.

La tecnología sigue procesos de privacidad para asegurarse de que se ajusta a las promesas del cliente en la recopilación y el uso de datos ejecución del servicio.

## <a name="data-collection"></a>Recopilación de datos

Los datos recopilados por la tecnología se limitan a la información necesaria para supervisar el estado, la causa raíz y mitigar los problemas identificados en los salones inscritos.

La tecnología supervisará los dispositivos, recopilará datos de telemetría y permitirá a Microsoft acceder de forma remota a los dispositivos y administrarlos como administrador.

Los datos de telemetría recopilados son específicos de una cuenta de Sala, no de un usuario individual. Las referencias incidentales a un usuario individual pueden estar presentes en el registro de actividades durante el uso del dispositivo.

### <a name="who-can-access-your-data"></a>Quién pueden acceder a tus datos

El servicio de tecnología toma medidas firmes para ayudar a proteger los datos de los clientes contra el acceso o el uso inadecuados por parte de personas no autorizadas. Esto incluye restringir el acceso por parte del personal y subcontratistas de Microsoft.

### <a name="zero-standing-access-data-storage"></a>Storage de datos de Acceso permanente cero

La tecnología mitiga los riesgos asociados con las cuentas con acceso privilegiado, desde actores malintencionados tanto dentro como fuera de una organización, mediante el principio de Acceso permanente cero. Esto permite que el servicio funcione sin privilegios disponibles de forma predeterminada para cualquier usuario. Combinado con los principios de Just-In-Time y Just-Enough-Access, proporciona un marco sólido para ser seguro y compatible de forma predeterminada. Los datos de diagnóstico están disponibles para nuestro equipo de operaciones de servicio a través de un portal interno.

## <a name="data-handling"></a>Tratamiento de datos

Microsoft se rige por normas estrictas para la transmisión, el almacenamiento, el uso y la retención de datos. Microsoft dispone de directivas estándar de tratamiento de datos en las que se indica cómo deben tratarse los datos en función de la clasificación de los datos.

Microsoft amplía los derechos generales de protección de datos del Reglamento general de protección de datos (RGPD) a todos los clientes de todo el mundo, no solo de Europa.

## <a name="data-classification"></a>Clasificación de datos

La clasificación de datos se puede usar para cumplir con los requisitos y procesos de seguridad, cumplimiento y privacidad para recopilar, almacenar y usar información personal del usuario.


|Clasificación|Descripción|Ejemplo|
| :- | :- | :- |
|Contenido del cliente|Contenido proporcionado/creado directamente por administradores y usuarios.|<p>- Blob generado por el cliente o datos de almacenamiento estructurados</p><p>- Secretos de propiedad/proporcionado por el cliente (contraseñas, certificados, claves de cifrado, claves de almacenamiento)</p>|
|Información identificable del usuario final (EUII)|Datos que identifican o podrían usarse para identificar al usuario de un servicio Microsoft. EUII no contiene contenido del Cliente.|<p>- Nombre de usuario o nombre para mostrar (DOMINIO\Nombre de usuario)</p><p>- Nombre principal de usuario (name@company.com)</p><p>- Dirección IP específica del usuario</p>|
|Datos de la cuenta|<p>Información de facturación del cliente e información del instrumento de pago, incluida la información de contacto de administrador, como el inquilino</p><p>nombre, dirección o</p><p>número de teléfono.</p>|<p>- Información de contacto del administrador de inquilinos (por ejemplo,</p><p>nombre, dirección, dirección de correo electrónico y número de teléfono del administrador de inquilinos)</p><p>- Aprovisionamiento del cliente</p><p>Información</p>|
|Identificadores pseudonimágenes del usuario final (EUPI)|<p>Identificador creado por Microsoft vinculado al usuario de un servicio Microsoft. Cuando EUPI se combina con otra información, como una tabla de asignación, identifica al usuario final. EUPI no contiene información cargada o creada por el cliente</p><p>(Contenido del cliente o EUII)</p>|<p>- GUID de usuario, GUID o SID</p><p>- Identificadores de sesión</p>|
|Información identificable de la organización (OII)|Datos que se pueden usar para identificar un inquilino, por lo general, datos de configuración o uso. Estos datos no se pueden vincular a un usuario y no contienen contenido del cliente.|<p>- Id. de inquilino (sin GUID)</p><p>- Nombre de dominio en la dirección de correo electrónico (xxx@contoso.com) u otro dominio específico del inquilino</p><p>Información</p>|
|Metadatos del sistema|Datos generados mientras se ejecuta el servicio o programa que no se puede vincular a un usuario o inquilino.|<p>- Registros de eventos</p><p>- Datos de uso</p><p>- Datos de configuración</p>|

Descripción de la tecnología

La tecnología enviará datos a Microsoft con el fin de supervisar, diagnosticar y mitigar cualquier problema de la implementación. Algunos ejemplos son

1. Garantizar que el dispositivo esté actualizado (incluida la aplicación, el sistema operativo, los controladores, F/W)
1. Garantizar que el dispositivo está listo para usar (ha iniciado sesión, todos los periféricos notifican el estado correcto, etc.)
1. Garantizar que el entorno esté listo (las cuentas aprovisionadas, las velocidades de red son lo suficientemente rápidas, etc.)
1. Determinar si puede haber problemas de hardware o problemas de instalación (como cableado suelto)
1. Heurística para determinar problemas (reinicios excesivos, etc.) 

La tecnología administrará el dispositivo con acciones como

1. Actualizar software
1. Mitigar problemas mediante reinicios, restablecimiento de conexiones USB & estados
1. Recopilar registros específicos para ayudar a diagnosticar problemas

La tecnología no supervisa ni graba audio, vídeo, contenido multimedia ni contenido de reuniones desde los Kits de soluciones. 

### <a name="service-collected-data-categories"></a>Categorías de datos recopiladas por el servicio
 
|Categoría|Detalles|Motivo de la consulta|
| :- | :- | :- |
|Administración de & de recopilación de datos continua|Dirección IP, identidad de la cuenta de sala (Exchange, Skype Empresarial y/o Teams), coordenadas de ubicación, correos electrónicos y comunicación en el Portal con Microsoft o software|Identificar y Conectar al sistema bajo gestión; Identificar, diagnosticar y mitigar errores; Realizar un seguimiento del uso, análisis y Ideas; Estado de conectividad de consulta & reparación|
|Administración de & de recopilación de datos ad hoc|<p>Información de registro de eventos, actividad del usuario/identidad del usuario de la sala que ha iniciado sesión en el archivo de registro junto con información\* de diagnósticos, Windows consultas del sistema (ejemplos: lista de dispositivos USB,</p><p>estado de energía, etc.)</p>|Identificar, diagnosticar y mitigar errores y para uso, análisis y Ideas|
|<p>Inscripción de prueba y</p><p>Configuración</p>|<p>consultas del sistema de Windows</p><p>Ejemplos: Lista de dispositivos USB, estado de energía, etc.</p>|<p>Necesario para la inscripción, incorporación, pedido y entrega,</p><p>y configurar para la versión de prueba.</p>|

\* El PII confidencial del registro de actividad de dispositivos se desvía localmente (no se recopila mediante la tecnología):

1. Cuerpo & asunto de la reunión
1. Información de la tarjeta de contacto de los asistentes a la reunión (como título, número de Teléfono, etc.)
1. Contenido del mensaje de mensajería instantánea en la reunión

>> [!NOTE]
>A medida que Microsoft evoluciona la tecnología, los datos específicos están sujetos a cambios. 

### <a name="agent-data-classification"></a>Clasificación de datos de agente

**Descripción detallada de todos los datos que recopila el agente MTRP durante la supervisión continua**
|Descripción de los datos recopilados|Clasificación|
| :- | :- |
|Identidad de un dispositivo compartido|OII|
|Id. de cliente|OII|
|Ubicación del directorio del agente MMR|Metadatos del sistema|
|Ubicación del directorio de registros de la aplicación MTR|Metadatos del sistema|
|Número de serie del dispositivo|Metadatos del sistema|
|Información del Bios del dispositivo|Metadatos del sistema|

|Versión del agente MMR|Metadatos del sistema|
| :- | :- |
|Versión de la aplicación MTR|Metadatos del sistema|
|Versión de la aplicación Teams|Metadatos del sistema|
|Hora del trabajo de mantenimiento nocturno para la aplicación MTR|Metadatos del sistema|
|DIRECCIÓN URL de actualización del agente MMR|Metadatos del sistema|
|Anillo de agente MMR|Metadatos del sistema|
|versión del sistema operativo Windows|Metadatos del sistema|
|Usuario actualmente conectado|Metadatos del sistema|
|GUID de sesión de agente MMR|Metadatos del sistema|
|Nombre de dominio|Metadatos del sistema|
|Tiempo desde el último reinicio del sistema operativo|Metadatos del sistema|
|Tiempo desde el inicio del último agente MMR|Metadatos del sistema|
|Marca y modelo de dispositivo MTR|Metadatos del sistema|
|Estado del dispositivo en uso|Metadatos del sistema|
|Tipo de incorporación de dispositivo|Metadatos del sistema|
|Número de monitores conectados|Metadatos del sistema|
|Detalles del orador MTR|Metadatos del sistema|
|Detalles del micrófono MTR|Metadatos del sistema|
|Detalles predeterminados del altavoz MTR|Metadatos del sistema|
|Configuración de uso compartido automático de pantalla de la aplicación MTR|Metadatos del sistema|
|Configuración de anuncios Bluetooth aplicación MTR|Metadatos del sistema|
|Fecha de la última vez que se cambió la contraseña|Metadatos del sistema|
|Configuración de rotación de contraseña MTR|Metadatos del sistema|
|Configuración de Teams o Skype Empresarial de la aplicación MTR|Metadatos del sistema|
|Anillo de actualización de aplicaciones MTR|Metadatos del sistema|
|Configuración de cámara de contenido de la aplicación MTR|Metadatos del sistema|
|Configuración de nombres de reuniones de la aplicación MTR|Metadatos del sistema|
|Configuración de la aplicación MTR delante de las pantallas de sala|Metadatos del sistema|
|GUID de la aplicación MTR|Metadatos del sistema|
|Puerto y dirección del proxy|Metadatos del sistema|
|Estado del dispositivo MTR|Metadatos del sistema|
|Detalles de la cuenta de sala MTR|OII|
|Dirección IPV4 y dirección IPV6|OII|
|Longitud y latitud|OII|
|Nombre de host del dispositivo MTR|OII|
|Zona horaria del dispositivo MTR|Metadatos del sistema|
|Estado de la aplicación MTR|Metadatos del sistema|
|Detalles del servicio crestron|Metadatos del sistema|
|Versión de firmware logitech y versión de sincronización logitech|Metadatos del sistema|
|Porcentaje total de CPU en uso|Metadatos del sistema|
|RAM total en uso|Metadatos del sistema|
|CPU que usa MTR Skype o aplicaciones de Teams|Metadatos del sistema|
|Temperatura del dispositivo MTR|Metadatos del sistema|
|Estado de las unidades de disco internas|Metadatos del sistema|
|Detalles de cualquier aplicación MTR que se bloquee|Metadatos del sistema|
|Detalles de cualquier pérdida de memoria detectada por las aplicaciones en el dispositivo|Metadatos del sistema|

|<p>Detalles de los errores de pantalla azul del dispositivo que se han producido en la</p><p>últimas 24 horas</p>|Metadatos del sistema|
| :- | :- |
|<p>Detalles de los errores que la aplicación MTR ha detectado durante las reuniones en</p><p>el dispositivo</p>|Metadatos del sistema|
|Detalles del software instalado|Metadatos del sistema|
|Detalles de las correcciones de acceso rápido instaladas, pendientes o que faltan|Metadatos del sistema|
|Detalles de hardware reconocidos|Metadatos del sistema|
|Detalles de todos los controladores del dispositivo|Metadatos del sistema|
|Detalles de las correcciones de dispositivos MMR|Metadatos del sistema|
|Detalles del uso de la sala durante las últimas 24 horas, tiempo y recuentos de reuniones|Metadatos del sistema|
|Detalles de las actualizaciones automáticas de Windows Store|Metadatos del sistema|
|Detalles de las actualizaciones del sistema operativo Windows|Metadatos del sistema|
|Detalles de trituración del agente MMR|Metadatos del sistema|
|Detalles del error de conexión del agente MMR|Metadatos del sistema|
|Detalles sobre si está habilitada la seguridad tpm|Metadatos del sistema|
|Detalles del estado de conexión del dispositivo MTR|Metadatos del sistema|

**Datos que recopila el agente de MTRP para diagnóstico y corrección de incidentes**
|Descripción de los datos recopilados|Clasificación|
| :- | :- |
|<p>Registros de eventos: Sistema, Aplicación, Skype Room System, Microsoft- Windows-AppXDeploymentServer%4Operational, Microsoft-Windows- PowerShell%4Operational, Microsoft-Windows- AppXDeployment%4Operational,Microsoft-Windows- AppXDeploymentServer%4Operational, Microsoft-Windows - TWinUI%4Operational, Microsoft Managed Rooms, Microsoft-Windows-</p><p>TaskScheduler%4Operational, Seguridad</p>|Metadatos del sistema|
|Registros de aplicaciones MTR desededed\*|Metadatos del sistema|
|Registros de Microsoft Teams|Metadatos del sistema|
|Agente MMR sqlLitedb|Metadatos del sistema|
|Detalles de la información del estado de energía del dispositivo|Metadatos del sistema|
|Información de directiva de grupo de dispositivos|Metadatos del sistema|
|Seguimiento de auditoría de todas las acciones de agente MMR|Metadatos del sistema|
\* El PII confidencial del registro Actividad de dispositivo se desvía localmente.

### <a name="enrollment"></a>Inscripción


Esta tecnología se registrará en el portal en línea para servicios automatizados de supervisión y soporte, incluyendo diagnósticos e informes. La inscripción se realiza a través de comunicaciones de red cifradas con la clave pública basada en el Módulo de plataforma segura (TPM) del dispositivo.

### <a name="un-enrollment"></a>Anular inscripción

El dispositivo se puede anular la inscripción desinstalando la tecnología. Microsoft también quitará el dispositivo de la supervisión back-end durante la retirada y puede eliminar los datos recopilados bajo solicitud.

### <a name="data-flow"></a>Flujo de datos

La tecnología agregará un flujo de datos desde el agente a servicios administrados de MTR.

![flujo de datos desde el agente a servicios administrados de MTR](../media/data-and-privacy-info-005.png)

Habilitar la integración de Microsoft Defender para punto de conexión introducirá un flujo de datos adicional desde el Agente MDE a la infraestructura de Microsoft Defender.

![flujo de datos adicional del agente MDE a Defender](../media/data-and-privacy-info-006.png)

## <a name="compliance"></a>Cumplimiento

Todos los ingenieros que trabajan en el producto deben someterse a un entrenamiento de seguridad y conciencia de privacidad. Microsoft también garantiza que todo el personal certifique la aceptación de responsabilidades por los requisitos de privacidad.

La tecnología proporciona soporte de residencia de datos regional a través de los centros de datos de Europa (UE), Asia Pacífico (APAC) y los Estados Unidos (EE. UU.). Esto significa que los clientes del servicio tendrán datos relacionados con la organización almacenados en el centro de datos de su región elegida.

## <a name="additional-resources"></a>Recursos adicionales

Salas de Microsoft Teams Seguridad:/microsoftteams/rooms/security Declaración de privacidad de Microsoft: https://aka.ms/privacy Administración de datos en Microsoft: https://www.microsoft.com/trust-center/privacy/data-management Descripción del servicio de tecnología: [Microsoft Teams servicio administrado](microsoft-teams-rooms-premium.md) por salas
