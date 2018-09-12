---
title: Información general de seguridad y cumplimiento en Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/11/2018
ms.topic: article
ms.service: msteams
ms.reviewer: anach
description: Una descripción general de las características de seguridad y cumplimiento de Microsoft Teams, incluyendo auditoría y creación de informes, búsqueda de contenido de cumplimiento de normas, exhibición de documentos electrónicos y mucho más.
localization_priority: Normal
search.appverid: MET150
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: fc686b520c9bd765539ff5fd9f636bc876583a41
ms.sourcegitcommit: 6732f56535d60a46e6998cde64103e8530dd6452
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/11/2018
ms.locfileid: "23937901"
---
<a name="overview-of-security-and-compliance-in-microsoft-teams"></a>Información general de seguridad y cumplimiento en Microsoft Teams
======================================================

Microsoft Teams está incorporado en la nube empresarial a gran escala de Office 365, proporcionando las funciones avanzadas de seguridad y cumplimiento que esperan nuestros clientes.

En el momento de su lanzamiento, Microsoft Teams cumple con el Nivel C. Esto incluye las siguientes normas: ISO 27001, ISO 27018, SSAE16 SOC 1 y SOC 2, HIPAA y las cláusulas modelo de la UE (EUMC). Dentro del marco de cumplimiento de Microsoft, Microsoft clasifica las aplicaciones y servicios de Office 365 en cuatro categorías. Cada categoría está definida por compromisos de cumplimiento específicos que deben darse para que un servicio de Office 365, o un servicio de Microsoft relacionado, se agregue a dicha categoría.

Los servicios en las categorías de cumplimiento C y D que tienen compromisos de cumplimiento están habilitados de manera predeterminada. Los servicios en las categorías A y B incluyen controles para activar o desactivar estos servicios para una organización entera. Los detalles se pueden encontrar en el [Marco de cumplimiento normativo de estándares y regulaciones del sector](https://go.microsoft.com/fwlink/?linkid=855777). Teams también cumple con los requisitos de Cloud Security Alliance.

Los equipos también se aplica a todo el equipo y toda la organización autenticación en dos fases, inicio de sesión único a través de Active Directory y el cifrado de datos en tránsito y en reposo. Los archivos se almacenan en SharePoint y se realizan mediante el cifrado de SharePoint. Las notas se almacenan en OneNote y se realizan mediante el cifrado de OneNote. Los datos de OneNote se almacenan en el sitio de SharePoint del equipo. También se puede usar la ficha sitio Wiki para tomar notas y su contenido también se almacena en el sitio de SharePoint del equipo.

También hemos agregado compatibilidad con la búsqueda en el registro de auditoría, eDiscovery y la suspensión legal para los canales, los chats y los archivos, así como la administración de aplicaciones móviles con Microsoft Intune. Vaya al centro de seguridad de Office 365 y cumplimiento para administrar esta configuración. 

## <a name="auditing-and-reporting"></a>Auditoría y generación de informes

Búsqueda de registro de auditoría derecha en el centro de cumplimiento y seguridad de Office 365 se conecta y expone capacidades para establecer alertas o informar sobre eventos de auditoría haciendo que estén disponibles, exportar de carga de trabajo específica o evento genérico se establece para el uso de administración y de investigación, a través de un escala de tiempo de auditoría ilimitado. Todos los datos de registro de auditoría está disponibles para la configuración de alertas en el centro de cumplimiento y seguridad de Office 365, así como para filtrar y exportar para realizar un análisis. Consulte este [vínculo](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security-Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c) para obtener más información acerca de cómo llevar a cabo una búsqueda de registro de auditoría para eventos de Microsoft Teams en el centro de seguridad de Office 365 y cumplimiento de normas. 

## <a name="compliance-content-search"></a>Búsqueda de contenido de cumplimiento

Búsqueda de contenido puede se usa para buscar todos los datos de los equipos a través de capacidades de filtrado de enriquecido y exportar a un contenedor específico para la compatibilidad con el cumplimiento de normas y litigios. Esto puede realizarse con o sin un caso de exhibición de documentos electrónicos. Esto permite que los administradores de cumplimiento recopilar datos de los equipos a través de todos los usuarios, revisar y exportar para continuar el procesamiento. Consulte este [vínculo](https://support.office.com/article/content-search-in-office-365-53390468-eec6-45cb-b6cd-7511f9c909e4) para obtener más información acerca de cómo realizar una búsqueda de contenido de cumplimiento de normas de contenido de Microsoft Teams en el centro de seguridad de Office 365 y cumplimiento de normas. 

Sugerencia: Puede usará el MicrosoftTeams kind para filtrar a través de a Microsoft Teams contenido únicamente, es decir, Chat y mensajes de canal, reuniones y llamadas. 

## <a name="ediscovery"></a>eDiscovery

La exhibición de documentos electrónicos es el aspecto electrónico de identificación, recolección y producción de información almacenada por medios electrónicos (ESI) en respuesta a una solicitud para la producción en una demanda legal o una investigación. Capacidades incluyen la administración de casos, conservación, búsqueda, análisis y exportación de datos de los equipos. Esto incluye los resúmenes de chat, mensajería y archivos, reuniones y llamadas. Para las reuniones de los equipos y las llamadas, un resumen de los eventos que se realizaron en la reunión y la llamada se crean y está disponible en la exhibición de documentos electrónicos. 

Para obtener más información acerca de cómo llevar a cabo la exhibición de documentos electrónicos en el centro de seguridad y cumplimiento de normas y búsqueda de contenido de cumplimiento de normas de ejecución para el contenido de los equipos, vaya a los siguientes vínculos: 

[eDiscovery](https://support.office.com/article/manage-legal-investigations-in-office-365-2e5fbe9f-ee4d-4178-8ff8-4356bc1b168e) 

[Búsqueda de contenido](https://support.office.com/article/search-for-content-in-office-365-df2d1e0f-b476-42c9-aade-4a260b24f193)

Los clientes pueden aprovechar por sus requisitos de exhibición de documentos electrónicos en contexto o [avanzada exhibición de documentos electrónicos] (https://support.office.com/article/Office-365-Advanced-eDiscovery-fd53438a-a760-45f6-9df4-861b50161ae4). La siguiente tabla muestra las diferencias entre estos dos métodos:


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

Durante un litigio, a menudo es necesario que todos los datos asociados con un usuario (custodia) o un equipo se conserva inalterados por lo que se puede usar como evidencia para el caso. Esto se logra mediante la colocación de un usuario (buzón de correo del usuario) o a un equipo con retención legal. Cuando cualquier equipo dentro de los equipos se pone en conservación local (subconjunto de la colección de sitio o buzón de correo a través de las consultas de destinadas o contenido filtrado) o juicio (colección completa de buzón de correo o sitio), la suspensión se coloca en el buzón de grupos. Esto garantiza que, incluso si los usuarios finales eliminar o editar los mensajes de canal que se ingestión en el buzón de correo de grupo, inmutables copias de que el contenido se conservan y disponibles en la búsqueda de eDisscovery. Las suspensiones legales suelen aplicarse en el contexto de un caso de eDiscovery. Consulte [este](https://support.office.com/article/overview-of-preservation-policies-9c3b1d52-40ce-4ba3-a520-9ae0be15538a) artículo para conocer más información acerca de la conservación y las suspensiones en el centro de seguridad de Office 365 y cumplimiento de normas de ayuda. 

## <a name="information-protection-architecture-for-microsoft-teams"></a>Arquitectura de protección de la información para los equipos de Microsoft. 

En la siguiente figura se indica el flujo de recopilación de datos de los equipos a Exchange y SharePoint para los archivos de los equipos y los mensajes. 

![Diagrama del flujo de trabajo de los datos de Teams en Exchange y SharePoint.](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image1.png)

En la siguiente figura se indica el flujo de ingesta de las reuniones de los equipos y los datos que llama a Exchange.

![Diagrama de flujo de trabajo de reuniones de los equipos y los datos que llama a Exchange.](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image1a.png)

> [!IMPORTANT]
> Puede haber un retraso de 24 horas para descubrir el contenido de los equipos de hasta.

## <a name="retention-policies"></a>Directivas de retención

Las conversaciones de los equipos son persistentes y retenidas para siempre de forma predeterminada. Con la introducción de las directivas de retención, los administradores pueden configurar las directivas de retención (conservación y eliminación) en el centro de seguridad y cumplimiento de mensajes de chat y canal de los equipos. Esto ayuda a las organizaciones retener datos para el cumplimiento (es decir, la directiva de conservación) durante un período específico o deshacerse de datos (es decir, la directiva de eliminación) si se considera una responsabilidad después de un período específico. Las directivas de retención de los equipos Asegúrese de que al eliminar datos, se elimina de todas las ubicaciones de almacenamiento de datos permanente en el servicio de los equipos. 

Para administrar las directivas de retención de los equipos works usar los cmdlets y la configuración en el centro de seguridad de Office 365 y cumplimiento en **Datos gobierno** > **retención**.

Son compatibles con las directivas de retención de los equipos: 
    
- Conservación: Conservar los datos de los equipos por una duración especificada y, a continuación, no haga nada
- Conservación y, a continuación, eliminar: conservar los datos de los equipos por una duración especificada y, a continuación, eliminar
- Eliminación: Eliminar datos de los equipos tras una duración especificada

Aún no admiten las directivas de retención de los equipos:

- Las directivas de retención avanzadas no se aplican a conversaciones en los equipos y ubicaciones de mensajes de canal de los equipos
- Duración de menos de 30 días

Los administradores pueden configurar las directivas de retención independiente para chats privadas de los equipos (1:1 o 1: muchas chats) y los mensajes del canal de los equipos. En muchos casos, las organizaciones, tenga en cuenta los datos de chat privado como más de un pasivo que no son mensajes de canal, que suelen ser más conversaciones relacionados con el proyecto. Configurar estas directivas en el centro de seguridad y cumplimiento, el **Gobierno de datos** > **retención**. Activar **los mensajes del canal de los equipos** y **los equipos de chat** y, a continuación, defina las directivas de retención para estas ubicaciones (también se muestra en el diagrama siguiente). 

Cuando se activa en **los equipos de los mensajes del canal**, puede especificar los equipos a los que se aplicará esta directiva. Por ejemplo, para equipos de X, Y y Z, el administrador puede establecer las directivas de eliminación para 1 año (seleccionando esos equipos de forma individual) y aplicar una directiva de eliminación de 3 años para el resto de los equipos. 

Puede hacer lo mismo para **los equipos de chat** mediante la selección de usuarios específicos y aplicar las directivas de retención único. 

![Diagrama del flujo de trabajo de los datos de Teams en Exchange y SharePoint.](media/Retention-Policies.png)


> [!IMPORTANT]
> Las ubicaciones de mensaje de canal de los equipos y las ubicaciones de los equipos charlas dirección sólo las conversaciones de los equipos almacenadas en los buzones de Exchange Online (buzones de usuario y de grupo). Los mensajes se eliminan de todas las ubicaciones de almacenamiento de información relevante, es decir, los buzones de correo, sustrato y servicio de chat. 
> 
> Para administrar las directivas de retención para los archivos de los equipos, que se almacenan en OneDrive para profesionales y SharePoint, use sus directivas de retención.




Por diseño, se configuran las directivas de eliminación para los archivos de los equipos a través de SharePoint Online y OneDrive para las ubicaciones de negocio. Como resultado, es posible que una directiva pudo eliminar un archivo al que hace referencia en un mensaje de chat o canal de los equipos antes de que se eliminan los mensajes. En este caso, el archivo aún se mostrará en el mensaje de los equipos, pero si hace clic en el archivo, obtendrá un error de "Archivo no encontrado" (también puede suceder en ausencia de una directiva, si alguien elimina manualmente un archivo de SharePoint Online o OneDrive para la empresa).


Para obtener información detallada acerca de cómo configurar las directivas de retención para Office 365, lea [información general de las directivas de retención](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423).
 

## <a name="retention-policies-faq"></a>Preguntas más frecuentes sobre las políticas de retención

### <a name="what-types-of-policies-can-i-setup-in-retention-policies-and-how-do-they-work"></a>¿Qué tipos de directivas puedo configurar en las directivas de retención y cómo funcionan?

En el centro de seguridad y cumplimiento, al configurar una directiva de retención, para los equipos o para cualquier otra carga de trabajo, puede configurar dos tipos principales de directivas: 
- Conservación: Estas directivas Asegúrese de que los datos se conserven durante un período determinado de tiempo, independientemente de lo que sucede en las herramientas de usuario final. Garantizan que los datos se conservan por motivos de cumplimiento de normas y expira disponibles en la exhibición de documentos electrónicos hasta este momento. Después de que expire el tiempo, la directiva puede indicar si no hace nada o eliminar los datos. En los equipos, si crea una directiva de conservación durante siete años, incluso si los usuarios finales eliminar sus mensajes de los equipos, estos mensajes se conservan aún para exhibición de documentos electrónicos durante siete años.
- Eliminación: Estas directivas Asegúrese de que los datos no están un pasivo para la organización. Después de la duración especificada, los datos se eliminan de todo el almacenamiento relevante en los equipos. 

### <a name="can-we-include-teams-in-org-wide-policies"></a>¿Podemos incluir los equipos de directivas en toda la organización? 

No, no actualmente. Debe crear directivas específicas para mensajes de chat y canal de los equipos con la fila de la ubicación de los equipos o los cmdlets de estos equipos: [New-TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-teamsretentioncompliancepolicy?view=exchange-ps) & [TeamsComplianceRetentionRule de nuevo](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-teamsretentioncompliancerule?view=exchange-ps). Estos cmdlets tienen get y establecer así como las versiones.

### <a name="are-these-retention-policies-retroactive"></a>¿Son retroactivos estas directivas de retención? 

Sí, son. Si crea una directiva de retención para eliminar los datos de más de 60 días, eliminará los datos de los equipos creados hace más de 60 días. 

### <a name="what-is-the-default-retention-policy"></a>¿Qué es la directiva de retención predeterminada? 

De forma predeterminada, se conservan una eternidad chat, canal y datos de los archivos de los equipos. Un usuario puede eliminar algo, pero en ausencia de las directivas de retención, los datos de los equipos, siempre se archivan en buzones de Exchange online (de usuario y de grupo) y permanece en su ubicación de exhibición de documentos electrónicos. 

### <a name="can-i-target-sets-of-users-or-teams-in-a-policy"></a>¿Puedo destinados a conjuntos de usuarios o equipos en una directiva? 

Sí, hacer. En el Asistente para la creación de directivas, en el paso de ubicaciones, puede incluir o excluir (de**los equipos de los mensajes del canal**) a equipos o usuarios (**chat de equipos**) y crear directivas de destino para su organización. 

### <a name="what-is-the-main-difference-between-using-the-group-mailbox-location-row-and-teams-channel-messages-location-row-in-retention-policies"></a>¿Qué es la principal diferencia entre el uso de la fila de ubicación de buzón de correo de grupo y la fila de ubicación de los mensajes de canal de los equipos en las directivas de retención? 

Si usa el buzón de correo de grupo y las filas de ubicación de buzón de correo de usuario para Exchange Online, se eliminarán los datos de los equipos de los buzones de correo especificados. Sin embargo, esto quita sólo datos desde el buzón de correo. No elimina otros datos de los equipos, como el servicio de charlas. Se recomienda que utilice las directivas de retención de los equipos para administrar correctamente todos los datos de los equipos. Una directiva de retención de los equipos quita los datos de los equipos de todas las ubicaciones, los buzones de correo, Chat servicio de almacenamiento, los clientes de los equipos. 

Nota: Lanzamiento de la característica de directivas de retención para los equipos se asegura de que las directivas de los equipos sólo eliminación elementos de los equipos almacenados dentro de las ubicaciones de buzón de correo de Exchange (usuario o grupo). El programa de instalación de otra directivas de buzones de correo no puede afectar a los elementos de los equipos. Era true en el pasado, pero se ha corregido con el lanzamiento de la función de las directivas de retención. 

### <a name="what-happens-to-skype-for-business-online-and-teams-interop-chats--are-they-affected-by-retention-policies"></a>¿Qué sucede con Skype para chats de interoperabilidad en línea de negocio y equipos – ¿están afectadas por las directivas de retención?

Sí, Skype para profesionales en línea y chats de interoperabilidad de los equipos funcionan del mismo modo. Una vez que el Skype para chat en línea de negocio entra en los equipos, se convierte en un mensaje en un subproceso de chat de los equipos y obtiene ingestión en el buzón apropiado. Por lo que el mismo flujo de works – directivas de eliminación de los equipos eliminará estos mensajes desde el subproceso de los equipos. Sin embargo, si el historial de conversaciones está activado para Skype para profesionales en línea y desde el Skype para cliente empresarial en línea los que se guardan en un buzón de correo, estos datos de chat no está controlados por una directiva de retención de los equipos.

### <a name="can-i-do-these-through-security--compliance-center-cmdlets-what-should-i-use"></a>¿Puede hacer a través de los cmdlets de centro de seguridad y cumplimiento? ¿Qué debo usar? 

Absolutamente. Puede crear directivas de retención de los equipos con [seguridad y cumplimiento del centro de los cmdlets de Powershell]( https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps). Recuerde que estos no son los cmdlets de Exchange Online. Estos son los cmdlets que hemos creado para los equipos. Siguen nomenclatura existente y el estilo de los cmdlets de retención disponibles actualmente en el centro de seguridad y cumplimiento.

|Directiva|Regla|
|---|---|
|[Nueva TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-teamsretentioncompliancepolicy?view=exchange-ps)| [Nueva TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-teamsretentioncompliancerule?view=exchange-ps)|
|[Get-TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-teamsretentioncompliancepolicy?view=exchange-ps)| [Get-TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-teamsretentioncompliancerule?view=exchange-ps)|
|[Set-TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-teamsretentioncompliancepolicy?view=exchange-ps)| [Set-TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-teamsretentioncompliancerule?view=exchange-ps)|
|[Remove-TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-teamsretentioncompliancepolicy?view=exchange-ps)| [Remove-TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-teamsretentioncompliancerule?view=exchange-ps)|

### <a name="if-there-are-multiple-retention-policies-for-teams-with-varying-durations-which-one-wins"></a>¿Si hay varias directivas de retención para los equipos con distintas duraciones, cuál wins?

Se siguen los [principios de las políticas de retención](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423)y se recomienda que haga lo demasiado. La respuesta breve es: 
-   Conservación siempre wins a través de eliminación
-   Período de conservación más larga siempre wins
-   Inclusión explícita wins a través de inclusión implícita en términos de ubicaciones
-   Más cortas wins período de eliminación



## <a name="retention-policies-known-issues"></a>Problemas conocidos de las directivas de retención

1. Bajo Elija los equipos en la fila de ubicación de los mensajes de canal de los equipos, es posible que vea Office 365 grupos que están no también los equipos. Esto se solucionará en el futuro.

1. En Elegir usuarios en la fila de la ubicación de los equipos de Chat, es posible que vea invitados y los usuarios de buzones que no sean. Las directivas de retención no están pensadas para establecerse para invitados, y estamos trabajando para quitar estos elementos de la lista. 

1. Asistente de ciclo de vida de Exchange (ELC) se ejecuta a diario, pero tiene un SLA de 7 días. Como resultado, es posible que, si tiene una directiva de retención de los equipos para eliminar los elementos de más de 60 días, pueden conservar estos elementos de 67 días. Esto no es una situación nueva - sigue el modelo de Exchange. Por supuesto, en la mayoría de los casos, no hay ningún retraso.


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
|![Icono de Siguientes pasos.](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image4.png)    |Pasos siguientes         |Revise la licencia actual de la organización y confirme que cumple con todos los requisitos de negocio de cumplimiento y seguridad.         |

Antes de habilitar alguna de estas características, asegúrese de que tiene acceso al Centro de seguridad y cumplimiento en el Centro de administración de Office 365. De manera predeterminada, los administradores de inquilinos tienen acceso.

Búsqueda de contenido y exhibición de documentos electrónicos no requieren activación en el centro de cumplimiento y seguridad.

<a name="location-of-data-in-teams"></a>Ubicación de los datos en Teams
-------------------------

Los datos de Teams residen en la región geográfica asociada con su inquilino de Office 365. Actualmente, los equipos admite las regiones Australia, Canadá, India, Japón, Reino Unido, América, APAC y EMEA. 

> [!IMPORTANT]
> Los equipos actualmente ofrece residencia de datos en Australia, Canadá, India, Japón y Reino Unido para sólo los inquilinos nuevo. Un inquilino nuevo se define como cualquier inquilino que no ha tenido ningún usuario desde el inicio de sesión del inquilino en Teams. Los inquilinos existentes de Australia, India y Japón seguirán tienen sus datos de los equipos almacenados en el área de APAC. Los inquilinos existentes en Canadá y Reino Unido tendrá sus datos almacenados en América y EMEA región, respectivamente.

Si desea conocer más detalles sobre el inicio de la residencia de datos en India y Reino Unido, lea la publicación [Microsoft Teams launches India Data Residency, other geos coming soon](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-Launches-Australia-and-Japan-Data-Residency/ba-p/237827) (Microsoft Teams iniciará la residencia de datos de India y otras zonas geográficas muy pronto) en el blog de Ansuman Acharya. 

Para obtener más información en residencia de datos de Canadá para los equipos, lea la entrada de blog de Varun Sagar, [residencia de datos de Microsoft los equipos inicia Canadá, Australia y Japón próximamente](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-Launches-Canada-Data-Residency-Australia-and/ba-p/227178). 

Para obtener más información sobre el lanzamiento de Australia y Japón residencia de datos para los equipos, Leer entrada de blog de Varun Sagar, [Microsoft equipos inicia Australia y Japón datos residencia ](https://go.microsoft.com/fwlink/?linkid=867773). 

Para ver qué región aloja los datos de su inquilino, vaya al [Centro de administración de Office 365](https://portal.office.com/adminportal/home) > **Configuración** > **Perfil de organización**. Desplácese hasta **Data location** (Ubicación de datos). 

![Captura de pantalla de la tabla de la ubicación de datos, incluido Teams, en el Centro de administración de Office 365.](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image5.png)

<a name="how-do-conditional-access-policies-work-for-teams"></a>¿Cómo funcionan las directivas de acceso condicional para los equipos?
-------------------------

Microsoft Teams depende en gran medida en Exchange Online, SharePoint Online y Skype para empresarial en línea para los escenarios de productividad de núcleo, al igual que las reuniones, calendarios, chats interoperabilidad y uso compartido de archivos. Las directivas de acceso condicional que se han establecido para estas aplicaciones en la nube se aplican a Microsoft Teams cuando un usuario directamente inicia sesión en Microsoft Teams - en cualquier cliente. 

Microsoft Teams se admite por separado como una aplicación de nube en las directivas de acceso condicional de Azure Active Directory. Las directivas de acceso condicional que se han establecido para la aplicación de nube de Microsoft Teams se aplican a Microsoft Teams cuando un usuario inicia sesión. Sin embargo, sin las directivas correctas en otras aplicaciones como Exchange Online y SharePoint Online, los usuarios aún podrán tener acceso a esos recursos directamente. Para obtener más información acerca de cómo configurar una directiva de acceso condicional en el portal de azure, vaya a: ()https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal-get-started) 

Los clientes de escritorio de Microsoft Teams para Windows y Mac admiten la autenticación moderna. Autenticación moderna aporta funcionalidad de inicio de sesión basado en la Azure Active Directory autenticación biblioteca (ADAL) para aplicaciones cliente de Microsoft Office a través de plataformas.

Aplicación de escritorio de Microsoft Teams admite AppLocker.  Para obtener más información sobre los requisitos previos de AppLocker, consulte: requisitos para usar AppLocker (https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/requirements-to-use-applocker).

<a name="privacy-in-teams"></a>Privacidad en Teams
--------------------------

Como cliente de Office 365, el usuario posee y controla sus propios datos. Microsoft no usa los datos para ninguna otra finalidad que proporcionarle el servicio para el que se ha suscrito. Como proveedores de servicios, no examinamos el correo electrónico, los documentos o los equipos para enviar publicidad o para otras finalidades que no estén relacionadas con el servicio. Microsoft no tiene acceso al contenido cargado. Tal como ocurre en OneDrive para la Empresa y SharePoint Online, los datos de los clientes permanecen en el inquilino.

Consulte más detalles sobre nuestra información de confianza y seguridad en el [Centro de confianza de Office 365](https://go.microsoft.com/fwlink/?linkid=855779). Microsoft Teams sigue los mismos principios y directrices que el Centro de confianza de Office 365.
