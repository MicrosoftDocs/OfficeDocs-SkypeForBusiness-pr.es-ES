---
title: Información general de seguridad y cumplimiento en Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
ms.reviewer: anach
description: Descripción general de las características de seguridad y cumplimiento de Microsoft Teams, que incluye auditoría y generación informes, búsqueda de contenido de cumplimiento, eDiscovery y mucho más.
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 857e4b691256ff13b6f9308bcd9fb12dfb10297d
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/03/2018
---
<a name="overview-of-security-and-compliance-in-microsoft-teams"></a>Información general de seguridad y cumplimiento en Microsoft Teams
======================================================

Microsoft Teams está incorporado en la nube empresarial a gran escala de Office 365, proporcionando las funciones avanzadas de seguridad y cumplimiento que esperan nuestros clientes.

En el momento de su lanzamiento, Microsoft Teams cumple con el Nivel C. Esto incluye las siguientes normas: ISO 27001, ISO 27018, SSAE16 SOC 1 y SOC 2, HIPAA y las cláusulas modelo de la UE (EUMC). Dentro del marco de cumplimiento de Microsoft, Microsoft clasifica las aplicaciones y servicios de Office 365 en cuatro categorías. Cada categoría está definida por compromisos de cumplimiento específicos que deben darse para que un servicio de Office 365, o un servicio de Microsoft relacionado, se agregue a dicha categoría.

Los servicios en las categorías de cumplimiento C y D que tienen compromisos de cumplimiento están habilitados de manera predeterminada. Los servicios en las categorías A y B incluyen controles para activar o desactivar estos servicios para una organización entera. Los detalles se pueden encontrar en el [Marco de cumplimiento normativo de estándares y regulaciones del sector](https://go.microsoft.com/fwlink/?linkid=855777). Teams también cumple con los requisitos de Cloud Security Alliance.

Microsoft Teams también emplea la autenticación en dos fases para todos los miembros del equipo y de la organización, el inicio de sesión único a través de Active Directory y el cifrado de datos en tránsito y en reposo. Los archivos se almacenan en SharePoint y utilizan el cifrado de SharePoint. Las notas se almacenan en OneNote y utilizan el cifrado de OneNote.

También hemos agregado compatibilidad con la búsqueda en el registro de auditoría, eDiscovery y la suspensión legal para los canales, los chats y los archivos, así como la administración de aplicaciones móviles con Microsoft Intune. Ir al centro de seguridad de Office 365 y cumplimiento para administrar esta configuración. 

## <a name="auditing-and-reporting"></a>Auditoría y generación de informes

La búsqueda en el registro de auditoría se conecta directamente al Centro de seguridad y cumplimiento de Office 365, y expone la capacidad de establecer alertas y de notificar eventos de auditoría, exportar conjuntos de eventos de carga de trabajo específicos o genéricos para investigación y uso administrativo, en toda una línea de tiempo de auditoría ilimitada. Todos los datos de registro de auditoría están disponibles para la configuración de alertas en el Centro de seguridad y cumplimiento de Office 365, así como para el filtrado y la exportación para un mayor análisis.

## <a name="compliance-content-search"></a>Búsqueda de contenido de cumplimiento

La búsqueda de contenido se puede usar para buscar en Teams mediante capacidades avanzadas de filtrado y se puede exportar a un contenedor específico para utilizarlo en relación con el cumplimiento y los litigios. Esto se puede hacer tanto con un caso de eDiscovery como sin él.

## <a name="ediscovery"></a>eDiscovery

La exhibición de documentos electrónicos es el aspecto electrónico de identificación, recolección y producción de información almacenada por medios electrónicos (ESI) en respuesta a una solicitud para la producción en una demanda legal o una investigación.

Las capacidades incluyen administración de casos, preservación, búsqueda, análisis y exportación de datos de los equipos. Esto incluye datos de chat, mensajería y archivo.

Los clientes pueden aprovechar eDiscovery local o [eDiscovery avanzado](https://support.office.com/article/Office-365-Advanced-eDiscovery-fd53438a-a760-45f6-9df4-861b50161ae4).

La siguiente tabla muestra las diferencias entre estos dos métodos:


| |eDiscovery local  |eDiscovery avanzado  |
|---------|---------|---------|
|Administración de casos     |X        |X         |
|Control de acceso  |X         |X         |
|Búsquedas de contenido     |X         | X        |
|Suspensiones   |X         | X        |
|Exportación     |X         |X         |
|Detección de duplicados     |-         |X         |
|Búsquedas por relevancia con aprendizaje automático    |-         |X         |
|Análisis de datos estructurados      |-         |X         |


## <a name="legal-hold"></a>Suspensión legal

Cuando cualquier equipo de Teams se pone en suspensión local o suspensión por juicio, la suspensión se pone en los buzones de los grupos.

Las suspensiones legales suelen aplicarse en el contexto de un caso de eDiscovery.

La siguiente imagen muestra el flujo de trabajo de los datos de Teams en Exchange y SharePoint.

![Diagrama del flujo de trabajo de los datos de Teams en Exchange y SharePoint.](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image1.png)


> [!IMPORTANT]
> Puede haber hasta un máximo de 24 horas de retraso en la detección del contenido de Teams.


## <a name="retention-policies"></a>Políticas de retención

Las conversaciones de los equipos son persistentes y retenidas por siempre de forma predeterminada. Con la introducción de las políticas de retención, los administradores pueden configurar políticas de retención (conservación y eliminación) en el centro de seguridad y cumplimiento para mensajes de chat y canal de equipos. Esto ayuda a las organizaciones retener datos para cumplimiento de normas (es decir, la directiva de conservación) para un período específico o deshacerse de los datos (es decir, la directiva de eliminación) si se considera un pasivo después de un período específico. Las políticas de retención de equipos garantizan que cuando se eliminan datos, se quitará todas las ubicaciones de almacenamiento permanente de datos en el servicio de los equipos. 

Para administrar las políticas de retención de equipos works utiliza la configuración y los cmdlets en el centro de seguridad de Office 365 y cumplimiento en el **Manejo de datos** > **retención**.

Apoyar las políticas de retención de los equipos: 
    
- Conservación: Mantener los datos de los equipos durante un tiempo especificado y, a continuación, no hacer nada
- Conservación y, a continuación, eliminar: mantener los datos de los equipos durante un tiempo especificado y, a continuación, eliminar
- Eliminación: Eliminar datos de equipos tras una duración especificada

Todavía no admiten directivas de retención de los equipos:

- Las políticas de retención avanzadas no se aplican a charla de equipos y ubicaciones de mensajes del canal de los equipos
- Duración de menos de 30 días

Administradores pueden establecer directivas de retención independiente para charlas de equipos privados (1:1 o 1: muchas charlas) y mensajes de canal de los equipos. En muchos casos, las organizaciones considerar datos de chat privado como más de un pasivo de mensajes del canal, que suelen ser conversaciones más relacionados con el proyecto. Configurar estas directivas en el centro de seguridad y cumplimiento, **manejo de datos** > **retención**. Activar **mensajes de canal de los equipos** y **chats de equipos** y, a continuación, definir políticas de retención para estas ubicaciones (también se muestra en el diagrama siguiente). 

Al activar **mensajes de canal de los equipos**, puede especificar los equipos a los que se aplicará esta directiva. Por ejemplo, para equipos de X, Y y Z, el administrador puede configurar las directivas de eliminación durante 1 año (seleccionando los equipos individualmente) y aplicar una política de eliminación de 3 años al resto de los equipos. 

Puede hacer lo mismo para **chats de equipos** seleccionando usuarios específicos y aplicar políticas de retención único. 

![Diagrama del flujo de trabajo de los datos de Teams en Exchange y SharePoint.](media/Retention-Policies.png)


> [!IMPORTANT]
> Las localidades de mensajes de canal de equipos y ubicaciones de charlas de equipos dirección sólo las conversaciones de los equipos almacenadas en los buzones de Exchange Online (buzones de usuario y de grupo). Los mensajes se eliminan de todas las ubicaciones de almacenamiento de información relevante, a saber, los buzones, sustrato y el servicio de charla. 
> 
> Para administrar las políticas de retención para los archivos de los equipos, que se almacenan en OneDrive para el negocio y SharePoint, utilice sus políticas de retención.




Por diseño, políticas de eliminación de archivos de los equipos se configuran a través de SharePoint Online y OneDrive para la empresa. Como resultado, es posible que una directiva puede eliminar el archivo hace referencia a un mensaje de chat o canal de equipos antes de que los mensajes se eliminan. En este caso, el archivo todavía aparecerá en el mensaje de los equipos, pero si hace clic en el archivo, obtendrá un error de "Archivo no encontrado" (Esto también podría ocurrir en ausencia de una directiva, si alguien elimina manualmente un archivo de SharePoint Online o OneDrive para el negocio).


Para obtener información detallada acerca de cómo configurar las políticas de retención para Office 365, lea el [Resumen de las políticas de retención](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423).
 

## <a name="retention-policies-faq"></a>Preguntas más frecuentes de las políticas de retención

### <a name="what-types-of-policies-can-i-setup-in-retention-policies-and-how-do-they-work"></a>¿Qué tipos de políticas puedo configurar en las políticas de retención y cómo funcionan?

En el centro de seguridad y cumplimiento, al configurar una política de retención, para equipos o para cualquier otra carga de trabajo, puede configurar dos tipos de directivas: 
- Conservación: Estas directivas garantizan que los datos se conserven durante un período determinado de tiempo, independientemente de lo que sucede en las herramientas de usuario final. Garantizan que los datos se conservan por razones de cumplimiento de normas y caduca disponible en eDiscovery hasta ese momento. Cuando termina el tiempo, la directiva puede indicar si no hacen nada o eliminar los datos. En los equipos, si crea una directiva de conservación durante 7 años, incluso si los usuarios finales eliminar los mensajes de sus equipos, estos mensajes se conservan para eDiscovery durante siete años.
- Eliminación: Estas directivas garantizan que los datos no son una responsabilidad de la organización. Después del tiempo especificado, los datos se eliminan de todo el almacenamiento en equipos relevante. 

### <a name="can-we-include-teams-in-org-wide-policies"></a>¿Podemos incluir equipos en políticas en toda la organización? 

No, no actualmente. Debe crear directivas específicas para mensajes de chat y canal de equipos mediante la fila de la ubicación de los equipos o estos cmdlets de equipos: nuevo TeamsRetentionCompliancePolicy & TeamsComplianceRetentionRule de nuevo. Estos cmdlets tienen get y establecer también versiones.

### <a name="are-these-retention-policies-retroactive"></a>¿Son estas políticas de retención retroactivos? 

Sí, son. Si crea una directiva de retención para eliminar datos de más de 60 días, eliminará datos de equipos creados hace más de 60 días. 

### <a name="what-is-the-default-retention-policy"></a>¿Cuál es la política de retención predeterminado? 

De forma predeterminada, se mantienen siempre equipos chat, canal y datos de archivos. Un usuario puede eliminar algo, pero en la ausencia de políticas de retención, datos de equipos siempre se archivan en buzones de Exchange en línea (usuario y grupo) y permanecen allí para eDiscovery. 

### <a name="can-i-target-sets-of-users-or-teams-in-a-policy"></a>¿Puedo destinados a conjuntos de usuarios o equipos en una directiva? 

Sí, hacer. En el Asistente para la creación de directivas, en el paso de ubicaciones, puede incluir o excluir equipos (**equipos de canal mensajes**) o usuarios (**charla de equipos**) y crear políticas específicas para la organización. 

### <a name="what-is-the-main-difference-between-using-the-group-mailbox-location-row-and-teams-channel-messages-location-row-in-retention-policies"></a>¿Cuál es la diferencia principal entre utilizar la fila de ubicación de buzón de grupo y la fila de ubicación de mensajes de canal de los equipos en las políticas de retención? 

Si utiliza el buzón de grupo y las filas de ubicación de buzón de usuario de Exchange Online, se eliminarán los datos de los equipos desde los buzones especificados. Sin embargo, esto sólo quita datos del buzón. No elimina otros datos de equipos, como el servicio de charlas. Recomendamos que utilice las políticas de retención de equipos para administrar correctamente todos los datos de los equipos. Una política de retención de equipos elimina los datos de los equipos de todas las ubicaciones, buzones, Chat servicio de almacenamiento, los clientes de equipos. 

### <a name="what-happens-to-skype-for-business-online-and-teams-interop-chats--are-they-affected-by-retention-policies"></a>¿Qué ocurre con Skype para los negocios en línea y equipos charlas interoperabilidad – ¿están afectadas por las políticas de retención?

Sí, Skype para los negocios en línea y chats de interoperabilidad de los equipos funcionan del mismo modo. Una vez que el Skype para chat en línea Business entra en equipos, se convierte en un mensaje en un subproceso de conversación de equipos y obtiene ingerida en el buzón apropiado. Para que el mismo flujo de trabajos – políticas de eliminación de equipos eliminarán estos mensajes desde el subproceso de equipos. Sin embargo, si el historial de las conversaciones está activado para Skype para los negocios en línea y desde el Skype para los negocios en línea del cliente los que se guardan en un buzón, los datos de esta charla no está controlados por una política de retención de los equipos.

### <a name="can-i-do-these-through-security--compliance-center-cmdlets-what-should-i-use"></a>¿Puedo hacer a través de los cmdlets de centro de seguridad y cumplimiento? ¿Qué debo utilizar? 

Absolutamente. Puede crear políticas de retención de equipos con [seguridad y cumplimiento centrar cmdlets de Powershell]( https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps). Recuerde que estos no son los cmdlets de Exchange Online. Aquí están los cmdlets que creamos para los equipos. Siguen la nomenclatura existente y el estilo de los cmdlets de retención disponibles actualmente en el centro de seguridad y cumplimiento.

|Directiva|Regla|
|---|---|
|Nueva TeamsRetentionCompliancePolicy| Nueva TeamsRetentionComplianceRule|
|Get-TeamsRetentionCompliancePolicy| Get-TeamsRetentionComplianceRule|
|Get - TeamsRetentionCompliancePolicy| Set - TeamsRetentionComplianceRule|
|Remove - TeamsRetentionCompliancePolicy| Remove - TeamsRetentionComplianceRule|

### <a name="if-there-are-multiple-retention-policies-for-teams-with-varying-durations-which-one-wins"></a>¿Si hay varias políticas de retención para equipos con diferentes duraciones, cuál gana?

Seguimos [los principios de las políticas de retención](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423)y recomendamos que lo haga demasiado. La respuesta corta es: 
-   Preservación siempre gana sobre eliminación
-   Mayor período de conservación siempre gana
-   Inclusión explícita gana sobre inclusión implícita en términos de ubicaciones
-   Wins período de eliminación más corta



## <a name="retention-policies-known-issues"></a>Problemas conocidos de las políticas de retención

1. Bajo Elija los equipos en la fila de ubicación de mensajes de canal de los equipos, puede que vea Office 365 grupos de equipos no también. Este problema se solucionará en el futuro.

1. En elegir a los usuarios en la fila de ubicación equipos Chat, verás no buzones de usuarios e invitados. Las políticas de retención no están pensadas para establecerse para invitados y estamos trabajando para quitar estos elementos de la lista. 

1. Asistente de ciclo de vida de Exchange (ELC) se ejecuta diariamente, pero tiene un SLA de 7 días. Como resultado, es posible que, si tiene una política de retención de los equipos para eliminar los elementos de más de 60 días, estos elementos podrían conservar hasta 67 días. Esto no es una situación nueva - sigue el modelo de Exchange. Por supuesto, en la mayoría de los casos, no hay ningún retraso.


| | | |
|---------|---------|---------|
|![Icono de Punto de decisión.](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image3.png)     |Puntos de decisión         |¿Qué características de seguridad y cumplimiento requiere su organización? ¿Su organización tiene las licencias necesarias para cumplir con los requisitos empresariales de seguridad y cumplimiento?         |
|![Icono de Siguientes pasos.](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image4.png)     |Pasos siguientes         |Documentar las características de seguridad y cumplimiento de normas necesarias.         |

<a name="licensing"></a>Licencias
---------------

En lo que se refiere a las funciones de protección de información, las suscripciones de Office 365 y las licencias autónomas asociadas determinarán el conjunto de características disponible.

|Funcionalidad de protección de información   |Office 365 Business Essentials   |Office 365 Business Premium   |Office 365 Enterprise E1   |Office 365 Enterprise E3/E4   |Office 365 Enterprise E5   |
|---|---|---|---|---|---|
|Archivo|-  |-   |-   |Sí   |Sí   |
|eDiscovery local|-   |-   |-   |Sí   |Sí   |
|eDiscovery avanzado|-   |-   |-   |-   |Sí   |
|Suspensión legal|-   |-   |-   |Sí   |Sí   |
|Búsqueda de contenido de cumplimiento|- |- |- |Sí |Sí |
|Auditoría y generación de informes|Sí |Sí |Sí |Sí |Sí |
|Acceso condicional* |Sí |Sí |Sí |Sí |Sí |
> [!NOTE]
> \*El acceso condicional requiere licencias adicionales


| |  |  |
|---------|---------|---------|
|![Icono de Punto de decisión.](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image3.png)     |Puntos de decisión         |¿Su organización tiene las licencias necesarias para cumplir con los requisitos empresariales de seguridad y cumplimiento?         |
|![Icono de Siguientes pasos.](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image4.png)    |Pasos siguientes         |Revise la licencia actual de su organización y confirme cumple todos los requerimientos del negocio para el cumplimiento de normas y seguridad.         |

Antes de habilitar alguna de estas características, asegúrese de que tiene acceso al Centro de seguridad y cumplimiento en el Centro de administración de Office 365. De manera predeterminada, los administradores de inquilinos tienen acceso.

EDiscovery y búsqueda de contenido no requieren activación en el centro de cumplimiento de normas y seguridad.

<a name="location-of-data-in-teams"></a>Ubicación de los datos en Teams
-------------------------

Los datos de Teams residen en la región geográfica asociada con su inquilino de Office 365. Actualmente, Microsoft Teams admite las regiones de América, EMEA y APAC. 

> [!IMPORTANT]
> En este momento, Teams ofrece residencia de datos en Reino Unido e Indica solo para los nuevos inquilinos. Un inquilino nuevo se define como cualquier inquilino que no ha tenido ningún usuario desde el inicio de sesión del inquilino en Teams. Los inquilinos existentes del Reino Unido y la India seguirán en las regiones de EMEA y APAC respectivamente hasta que se publique un plan de migración (que está previsto para 2018).

Si desea conocer más detalles sobre el inicio de la residencia de datos en India y Reino Unido, lea la publicación [Microsoft Teams launches India Data Residency, other geos coming soon](https://go.microsoft.com/fwlink/?linkid=867773) (Microsoft Teams iniciará la residencia de datos de India y otras zonas geográficas muy pronto) en el blog de Ansuman Acharya.

Para ver qué región aloja los datos de su inquilino, vaya al [Centro de administración de Office 365](https://portal.office.com/adminportal/home) > **Configuración** > **Perfil de organización**. Desplácese hasta **Data location** (Ubicación de datos). 

![Captura de pantalla de la tabla de la ubicación de datos, incluido Teams, en el Centro de administración de Office 365.](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image5.png)

<a name="privacy-in-teams"></a>Privacidad en Teams
--------------------------

Como cliente de Office 365, el usuario posee y controla sus propios datos. Microsoft no usa los datos para ninguna otra finalidad que proporcionarle el servicio para el que se ha suscrito. Como proveedores de servicios, no examinamos el correo electrónico, los documentos o los equipos para enviar publicidad o para otras finalidades que no estén relacionadas con el servicio. Microsoft no tiene acceso al contenido cargado. Tal como ocurre en OneDrive para la Empresa y SharePoint Online, los datos de los clientes permanecen en el inquilino.

Descubre más acerca de nuestra confianza y seguridad relacionadas con la información en el [Centro de confianza de Office 365](https://go.microsoft.com/fwlink/?linkid=855779). Microsoft Teams sigue los mismos principios y directrices que el Centro de confianza de Office 365.
