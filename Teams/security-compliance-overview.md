---
title: Información general sobre seguridad y cumplimiento
author: MSFTTracyP
ms.author: tracyp
manager: laurawi
ms.date: 04/12/2022
ms.topic: conceptual
ms.service: msteams
ms.reviewer: anwara
audience: admin
description: Información general sobre Microsoft Teams características de seguridad y cumplimiento, como privacidad y cifrado, auditoría e informes, etc.
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
- remotework
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.securityandcompliance
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1c41ac53e95c179fc62b5e2e469bb614cbdcd516
ms.sourcegitcommit: 7d5266ae7e4a440ee45ab1873a30f4056bdcca1f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2022
ms.locfileid: "65031905"
---
# <a name="security-and-compliance-in-microsoft-teams"></a>Seguridad y cumplimiento en Microsoft Teams

> [!IMPORTANT]
> Para obtener información sobre cómo garantizar mejor la **seguridad mientras todos trabajan desde casa durante el brote de COVID-19**, lea estos artículos:
>  - [Las 12 tareas principales de los equipos de seguridad para dar soporte al trabajo desde casa](/microsoft-365/security/top-security-tasks-for-remote-work)
>  - [Optimizar la conectividad de Microsoft 365 u Office 365 para usuarios remotos que usan túnel dividido de VPN](/Office365/Enterprise/office-365-vpn-split-tunnel)
>  - Actualizado el 2 de abril de 2020: [guía de seguridad de Teams](teams-security-guide.md)


Microsoft Teams se basa en la Microsoft 365 y Office 365 nube de nivel empresarial a gran escala, lo que ofrece las capacidades avanzadas de seguridad y cumplimiento que nuestros clientes esperan. Para obtener más información sobre la planeación de la seguridad en Microsoft 365 o Office 365, [el plan de seguridad](/microsoft-365/security/office-365-security/security-roadmap) es un buen punto de partida. Para obtener más información sobre la planeación del cumplimiento en Microsoft 365 o Office 365, puede empezar con [Planear el cumplimiento de & de seguridad](/microsoft-365/compliance/plan-for-security-and-compliance).


En este artículo se proporciona más información sobre Teams seguridad y cumplimiento específicos. No te pierdas estos vídeos de Microsoft Mechanics sobre seguridad y cumplimiento:

- [Microsoft Teams Essentials para TI: Seguridad y cumplimiento](https://youtu.be/91lHNKVVvQ4) (12:42 min)
- [Microsoft Teams Controles de seguridad y cumplimiento](https://www.youtube.com/watch?v=Km4T4hMM__k) (10:54 min)

> [!IMPORTANT]
> Como cliente de Microsoft 365 o Office 365, usted es el propietario y el control de sus datos. Microsoft no usa sus datos con ningún otro fin que proporcionarle el servicio al que se ha suscrito. Como proveedor de servicios, no analizamos su correo electrónico, documentos ni equipos para obtener publicidad o para fines que no estén relacionados con el servicio. Microsoft no tiene acceso al contenido cargado. Al igual que OneDrive y SharePoint en Microsoft 365, los datos de los clientes permanecen en el inquilino. Puede consultar más información sobre nuestra información relacionada con la confianza y la seguridad en el [Centro de confianza de Microsoft](https://microsoft.com/trustcenter). Teams sigue las mismas directrices y principios que el Centro de confianza de Microsoft.

## <a name="security"></a>Seguridad

Teams exige la autenticación en dos fases para todo el equipo y la organización, el inicio de sesión único a través de Active Directory y el cifrado de datos en tránsito y en reposo. Los archivos se almacenan en SharePoint y son respaldados por el cifrado de SharePoint. Las notas se almacenan en OneNote y se respaldan mediante cifrado de OneNote. Los datos OneNote se almacenan en el sitio de SharePoint de grupo. La pestaña Wiki también se puede usar para tomar notas y su contenido también se almacena en el sitio SharePoint grupo.

Lea [Modelos de identidad y autenticación](identify-models-authentication.md) para obtener más información sobre la autenticación y la Teams, y [Cómo funciona la autenticación moderna](sign-in-teams.md) en particular con la autenticación moderna.

Dado que Teams trabaja en asociación con SharePoint, OneNote, Exchange y mucho más, debería sentirse cómodo administrando la seguridad en Microsoft 365 o Office 365 todo. Para obtener más información, lea [cómo configurar su Microsoft 365 o Office 365 organización para aumentar la seguridad](/office365/securitycompliance/tenant-wide-setup-for-increased-security).

> [!NOTE]
> Actualmente, [los canales privados](private-channels.md) admiten características limitadas de seguridad y cumplimiento. Muy pronto se admitirá el conjunto completo de características de seguridad y cumplimiento en canales privados.

### <a name="microsoft-defender-for-office-365"></a>Microsoft Defender para Office 365

Microsoft Defender para Office 365 está disponible para Microsoft Teams, junto con SharePoint y OneDrive, aplicaciones que se integran con Teams para la administración de contenidos. Defender para Office 365 le permite determinar si el contenido de estas aplicaciones es malintencionado y bloquear el acceso de los usuarios a este contenido.

La forma en que se administra el contenido afectado después de la detección depende de la configuración que haya seleccionado en Microsoft 365 o Office 365. Le recomendamos encarecidamente que tenga en cuenta todas las aplicaciones a la hora de configurar Defender para Office 365 y, para una lectura más detallada, una [descripción general de cómo funcionan los vínculos seguros y los pasos para configurarlos, encontrará](/microsoft-365/security/office-365-security/safe-links?view=o365-worldwide) información detallada para empezar.

### <a name="safe-links-in-microsoft-teams"></a>Vínculos de Caja fuerte en Microsoft Teams

Defender para Office 365 vínculos seguros están disponibles en Microsoft Teams. Para obtener más información sobre qué son los vínculos seguros y qué hacer con esta característica, lea [configuración segura de vínculos para Teams](/microsoft-365/security/office-365-security/safe-links?view=o365-worldwide). Caja fuerte vínculos están disponibles en [Defender para Office 365 Plan 1 y Plan 2](/microsoft-365/security/office-365-security/overview?view=o365-worldwide).

### <a name="safe-attachments"></a>Caja fuerte datos adjuntos

Caja fuerte datos adjuntos es una característica diseñada para mejorar la seguridad del usuario mediante la comprobación y detección de datos adjuntos malintencionados. Los administradores globales o de seguridad [activan la característica](/microsoft-365/security/office-365-security/turn-on-mdo-for-spo-odb-and-teams?view=o365-worldwide) y [crean directivas](/microsoft-365/security/office-365-security/set-up-safe-attachments-policies?view=o365-worldwide) para controlar estos datos adjuntos malintencionados sospechosos para evitar que se envíen a los usuarios, se haga clic y se actúe sobre ellos.

Caja fuerte protección de datos adjuntos está disponible para SharePoint, OneDrive y Microsoft Teams, y Microsoft 365 o Office 365 en [ Microsoft Defender para Office 365 Plan 1 y Plan 2](/microsoft-365/security/office-365-security/overview?view=o365-worldwide). Obtenga más información sobre Caja fuerte Datos adjuntos y cómo pueden ayudar a proteger su organización en [este artículo](/microsoft-365/security/office-365-security/set-up-safe-attachments-policies?view=o365-worldwide).

### <a name="secure-score"></a>Puntuación segura

Puntuación segura de Microsoft es una medición de la posición de seguridad de una organización, con un número más alto que indica más acciones de mejora realizadas. Se puede encontrar en la [Centro de seguridad de Microsoft 365](https://security.microsoft.com/securescore). Si sigue las recomendaciones de puntuación segura, podrá proteger su organización contra amenazas. Desde un panel centralizado de la Centro de seguridad de Microsoft 365, las organizaciones pueden supervisar y trabajar en la seguridad de sus Microsoft 365 identidades, aplicaciones y dispositivos. Microsoft Teams ahora tiene recomendaciones sobre la Puntuación segura y se anima a los administradores a supervisar su postura de seguridad en la plataforma.

Puntuación segura ayuda a las organizaciones a:
- Informe sobre el estado actual de la postura de seguridad de la organización.
- Mejore su postura de seguridad proporcionando detectabilidad, visibilidad, orientación y control.
- Compare con pruebas comparativas y establezca indicadores clave de rendimiento (KPI).

### <a name="how-conditional-access-policies-work-for-teams"></a>Cómo funcionan las directivas de acceso condicional para Teams

Microsoft Teams depende en gran medida de Exchange Online, SharePoint y Skype Empresarial Online para los escenarios de productividad principales, como reuniones, calendarios, chats de interoperabilidad y uso compartido de archivos. Las directivas de acceso condicional que se establecen para estas aplicaciones en la nube se aplican a Microsoft Teams cuando un usuario inicia sesión directamente en Microsoft Teams en cualquier cliente.

Microsoft Teams se admite por separado como aplicación en la nube en Azure Active Directory directivas de acceso condicional. Las directivas de acceso condicional que se establecen para la aplicación en la nube Microsoft Teams se aplican a Microsoft Teams cuando un usuario inicia sesión. Sin embargo, sin las directivas correctas en otras aplicaciones, como Exchange Online y SharePoint, es posible que los usuarios puedan seguir accediendo a esos recursos directamente. Para obtener más información sobre cómo configurar una directiva de acceso condicional en el Azure Portal, vea [Azure Active Directory Inicio rápido](/azure/active-directory/active-directory-conditional-access-azure-portal-get-started).

Microsoft Teams clientes de escritorio para Windows y Mac admiten la autenticación moderna. La autenticación moderna incorpora el inicio de sesión basado en la biblioteca de autenticación de Azure Active Directory (ADAL) a Microsoft Office aplicaciones cliente en todas las plataformas.

Microsoft Teams aplicación de escritorio admite AppLocker.  Para obtener más información sobre los requisitos previos de AppLocker, consulta: Requisitos para usar [AppLocker](/windows/security/threat-protection/windows-defender-application-control/applocker/requirements-to-use-applocker).

## <a name="compliance"></a>Cumplimiento

Teams tiene una amplia gama de información para ayudarle con las áreas de cumplimiento, como el cumplimiento de comunicaciones para canales, chats y datos adjuntos, directivas de retención, prevención de pérdida de datos (DLP), exhibición de documentos electrónicos y conservación legal de canales, chats y archivos, búsqueda de registros de auditoría, así como administración de aplicaciones móviles con Microsoft Intune. Hemos proporcionado información sobre todos estos temas a continuación y puede ir a la [Centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com) para administrar esta configuración.

### <a name="information-barriers"></a>Barreras de la información

Las barreras de la información de Microsoft Purview son directivas que los administradores de Teams aplican para hacer cosas como impedir que las personas o grupos se comuniquen entre sí (cuando no haya necesidad empresarial para que lo hagan o una razón normativa para impedir que lo hagan) y también le permiten establecer directivas relacionadas con cosas como búsquedas y exhibición de documentos electrónicos (se incluye a continuación). Estas directivas pueden afectar a los usuarios en chats individuales, chats grupales o a nivel de equipo. La característica De barrera de la información está disponible en la nube pública y a partir de enero de 2021 se ha implementado en la nube de GCC.

Para obtener más información sobre este tema, vaya a [Barreras de la información en Microsoft Teams](information-barriers-in-teams.md).

### <a name="communication-compliance"></a>Cumplimiento de las comunicaciones

Microsoft Purview Communication Compliance le permite agregar usuarios a directivas de ámbito que se pueden configurar para examinar las comunicaciones de Microsoft Teams en busca de lenguaje ofensivo, información confidencial e información relacionada con los estándares internos y normativos. Las comunicaciones de chat y los datos adjuntos asociados en canales de Teams públicos y privados, chats individuales y datos adjuntos se pueden analizar para ayudar a minimizar los riesgos de comunicación en su organización. Para obtener más información sobre cómo configurar directivas para ayudarle a detectar, capturar y tomar medidas para comunicaciones de Teams inapropiadas, vea [Obtener información sobre el cumplimiento de las comunicaciones](/microsoft-365/compliance/communication-compliance).

### <a name="sensitivity-labels"></a>Etiquetas de confidencialidad

Aplique [etiquetas de confidencialidad](/microsoft-365/compliance/sensitivity-labels) para proteger y regular el acceso al contenido confidencial de la organización creado durante la colaboración dentro de los equipos. Por ejemplo, aplique etiquetas que configuren la privacidad (pública o privada) de los equipos, controle el acceso de invitado y el uso compartido externo, y administre el acceso desde dispositivos no administrados. Para obtener más información, revise [las etiquetas de confidencialidad en Microsoft Teams](sensitivity-labels.md).

### <a name="microsoft-purview-data-loss-prevention-dlp"></a>Prevención de pérdida de datos de Microsoft Purview (DLP)

La prevención de pérdida de datos (DLP) en Microsoft Teams, así como la historia DLP más grande de Microsoft Purview, gira en torno a la preparación empresarial a la hora de proteger documentos y datos confidenciales. Tanto si le preocupa la información confidencial de los mensajes o documentos, las directivas DLP le ayudarán a garantizar que los usuarios no compartan estos datos confidenciales con las personas equivocadas.

Para obtener información sobre la prevención de pérdida de datos en Teams, revise [DLP para Microsoft Teams](/microsoft-365/compliance/dlp-microsoft-teams). Un buen artículo para las preocupaciones de DLP es [Obtener información sobre la prevención de pérdida de datos](/microsoft-365/compliance/dlp-learn-about-dlp).

### <a name="customer-key"></a>Clave del cliente

Microsoft 365 ofrece una capa adicional de cifrado sobre el cifrado de servicio para su contenido. Con las claves que proporcione, Clave del cliente cifra varios tipos diferentes de datos en Microsoft Teams. Al usar Clave de cliente en el nivel de aplicación, Clave del cliente cifra los archivos Teams almacenados en SharePoint Online. Para obtener más información, consulte [Cifrado de servicio con clave de cliente de Microsoft Purview](/microsoft-365/compliance/customer-key-overview).

Al usar clave de cliente en el nivel de inquilino, Clave de cliente cifra:
- Teams mensajes de chat (chats individuales, chats grupales, chats de reuniones y conversaciones de canal)
- Teams mensajes multimedia (imágenes, fragmentos de código, vídeos e imágenes wiki)
- Teams grabaciones de llamadas y reuniones almacenadas en Teams almacenamiento
- Teams notificaciones de chat
- Teams sugerencias de chat Cortana
- Teams mensajes de estado

Para obtener más información, vea [Información general sobre la clave de cliente en el nivel de inquilino](/microsoft-365/compliance/customer-key-tenant-level) y lea el blog de Microsoft Teams que cubre [el soporte técnico de la clave del cliente para Microsoft Teams ahora en versión preliminar pública](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/customer-key-support-for-microsoft-teams-now-in-public-preview/ba-p/1999893). Para obtener información sobre la versión de Microsoft Information Protection que incluía la clave de cliente en el nivel de inquilino, lea [Anunciar nuevas capacidades de Microsoft Information Protection para conocer y proteger sus datos confidenciales](https://techcommunity.microsoft.com/t5/microsoft-security-and/announcing-new-microsoft-information-protection-capabilities-to/ba-p/1999692).

### <a name="retention-policies"></a>Directivas de retención

Las directivas de retención de Microsoft Teams le permiten conservar datos importantes para su organización, por motivos normativos, legales, empresariales u otros motivos, así como quitar contenido y comunicaciones que no sean relevantes para conservarse. También puede usar directivas de retención para conservar los datos durante un período de tiempo y, después, eliminarlos. Para obtener más información, revise [las directivas de retención en Microsoft Teams](retention-policies.md).

### <a name="ediscovery"></a>eDiscovery

El descubrimiento electrónico, o eDiscovery, es el aspecto electrónico de identificar, recopilar y producir información almacenada electrónicamente (ESI) en respuesta a una solicitud de producción en una demanda legal o investigación. Entre las capacidades se incluyen la administración de casos, la conservación, la búsqueda, el análisis y la exportación de datos de Teams. Esto incluye los resúmenes de chat, mensajes y archivos, reuniones y llamadas. Para Teams reuniones y llamadas, se crea un resumen de los eventos que han sucedido en la reunión y la llamada y se pone a disposición en eDiscovery.

Para obtener más información sobre cómo usar las herramientas de exhibición de documentos electrónicos en el portal de cumplimiento de Microsoft Purview para buscar Teams contenido, vaya a los vínculos siguientes:

- [eDiscovery](/microsoft-365/compliance/manage-legal-investigations)

- [Búsqueda de contenido](/microsoft-365/compliance/search-for-content)

Tenemos un artículo específico de Teams para obtener más información en [Dirigir una investigación de exhibición de documentos electrónicos del contenido de Microsoft Teams](eDiscovery-investigation.md).

Los clientes pueden usar eDiscovery o [eDiscovery (Premium)](/microsoft-365/compliance/office-365-advanced-ediscovery) según sus requisitos. La siguiente tabla muestra las diferencias entre estos dos métodos:

|&nbsp; |eDiscovery  |Exhibición de documentos electrónicos (Premium)  |
|---------|---------|---------|
|Administración de casos     |X        |X         |
|Control de acceso  |X         |X         |
|Búsquedas de contenido     |X         | X        |
|Suspensiones   |X         | X        |
|Exportación     |X         |X         |
|Detección de duplicados     |-         |X         |
|Búsquedas por relevancia con aprendizaje automático    |-         |X         |
|Análisis de datos estructurados      |-         |X         |

### <a name="legal-hold"></a>Suspensión legal

Durante los litigios, es posible que necesite que todos los datos asociados con un usuario (custodio) o un equipo se conserven como inmutables, de modo que se puedan usar como evidencia para el caso. Para ello, puede colocar un usuario (buzón de usuario) o un equipo en retención legal. Para una retención legal del equipo, el buzón del equipo se puede poner en las siguientes retenciones:

- In-Place en espera (se pone en espera un subconjunto del buzón o la colección de sitios a través de consultas de destino o contenido filtrado), o bien
- Retención por juicio (todo el buzón o la colección de sitios se pone en espera).

En cualquier caso, una vez establecida la retención, se asegura de que, incluso si los usuarios finales eliminan o editan los mensajes del canal que están en el buzón de grupo, se mantienen y están disponibles copias inmutables de ese contenido a través de la búsqueda de exhibición de documentos electrónicos. Las retenciones legales se aplican generalmente en el contexto de un caso de exhibición de documentos electrónicos.

Consulte [Información general sobre las directivas de retención](/microsoft-365/compliance/retention-policies) para obtener más información sobre la conservación y las retenciones en el portal de cumplimiento de Microsoft Purview. Para obtener más información Teams específica sobre la retención legal, también tenemos [Poner en espera legal a un usuario o equipo de Microsoft Teams](legal-hold.md) para que pueda obtener más información.

### <a name="content-search"></a>Búsqueda de contenido

La búsqueda de contenido se puede usar para buscar todos los datos de Teams a través de capacidades de filtrado enriquecidas. Los datos resultantes se pueden exportar a un contenedor específico para obtener soporte técnico de cumplimiento normativo y litigios. Esto se puede hacer con o sin un caso de exhibición de documentos electrónicos. Esto permite a los administradores de cumplimiento recopilar Teams datos entre todos los usuarios, revisarlos y exportarlos para su procesamiento posterior. Consulte Búsqueda de [contenido](/microsoft-365/compliance/content-search) para obtener más información sobre cómo llevar a cabo una búsqueda de contenido de cumplimiento para Microsoft Teams y otros Microsoft 365 o contenido Office 365 en el portal de cumplimiento de Microsoft Purview.

> [!TIP]
> Con la búsqueda de contenido, puede filtrar hacia abajo para Microsoft Teams solo contenido, como mensajes de chat y de canal, reuniones y llamadas, si es necesario.

Si desea obtener más información Teams específica sobre cómo configurar la búsqueda de contenido, revise Búsqueda de contenido [en Microsoft Teams](content-search.md).

### <a name="auditing"></a>Auditoría

La búsqueda de registros de auditoría se conecta directamente al portal de cumplimiento de Microsoft Purview y le ofrece la posibilidad de establecer alertas, así como informar sobre eventos de auditoría, al permitir la exportación de conjuntos de eventos genéricos o específicos de carga de trabajo para su uso por parte del administrador y la investigación a través de una escala de tiempo de auditoría ilimitada. Puede configurar alertas para todos los datos de registro de auditoría en el portal de cumplimiento de Microsoft Purview y filtrar y exportar estos datos para analizarlos más a fondo. Para obtener más información sobre cómo buscar eventos de Microsoft Teams en el portal de cumplimiento de Microsoft Purview, vea [Buscar eventos en el registro de auditoría de Microsoft Teams](audit-log-events.md).

## <a name="privacy"></a>Privacidad

En Microsoft, proteger los datos es nuestra máxima prioridad. Para obtener información sobre nuestras prácticas de privacidad, lea:  

- [Privacidad en Microsoft](https://www.microsoft.com/trust-center/privacy)
- [Nuestro compromiso con la privacidad y la seguridad en Microsoft Teams](https://www.microsoft.com/en-us/microsoft-365/blog/2020/04/06/microsofts-commitment-privacy-security-microsoft-teams/)
- [Para profesionales de TI: Privacidad y seguridad en Microsoft Teams](https://www.microsoft.com/en-us/microsoft-365/blog/2020/04/06/it-professionals-privacy-security-microsoft-teams/#:~:text=We%20safeguard%20your%20privacy%20by,and%20distribution%20of%20your%20data.)

## <a name="information-protection-architecture"></a>Arquitectura de Information Protection

La siguiente ilustración indica el flujo de ingestión de datos de Teams a Exchange y SharePoint de archivos y mensajes de Teams.

> [!div class="mx-imgBorder"]
> ![Diagrama del flujo de trabajo de los datos de Teams en Exchange y SharePoint.](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image1.png)

La figura siguiente indica el flujo de ingestión de Teams Reuniones y datos de llamadas a Exchange.

> [!div class="mx-imgBorder"]
> ![Diagrama del flujo de trabajo de Teams reuniones y datos de llamadas a Exchange.](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image1a.png)

> [!IMPORTANT]
> Puede haber un retraso de hasta 24 horas para descubrir Teams contenido.

## <a name="licensing"></a>Licencias

En lo que respecta a las capacidades de protección de la información, las suscripciones de Microsoft 365, las suscripciones de Office 365 y las licencias independientes asociadas determinarán el conjunto de características disponible.

Para obtener información sobre cómo determinar las necesidades de licencia para implementar características de seguridad y cumplimiento, revise los [requisitos de licencia](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance) para las características de seguridad y cumplimiento.

> [!NOTE]
> No es necesario habilitar la búsqueda de contenido, la exhibición de documentos electrónicos (estándar) ni la exhibición de documentos electrónicos (Premium) en el portal de cumplimiento de Microsoft Purview. Para obtener más información, vea [Microsoft 365 soluciones de eDiscovery](/microsoft-365/compliance/ediscovery).

## <a name="location-of-data-in-teams"></a>Ubicación de los datos en Teams

Los datos de Teams residen en la región geográfica asociada con su organización de Microsoft 365 u Office 365. Para ver qué regiones son compatibles actualmente, revisa [Ubicación de los datos en Microsoft Teams](location-of-data-in-teams.md).

Si necesita ver qué región aloja los datos de su inquilino, vaya al perfil [Centro de administración de Microsoft 365](https://portal.office.com/adminportal/home) >  **Configuración** >  **Organización**. Desplácese hacia abajo hasta **Ubicación de datos**.

> [!div class="mx-imgBorder"]
> ![Captura de pantalla de la tabla Ubicación de datos con Teams en el centro de administración.](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image5.png)

## <a name="compliance-standards"></a>Estándares de cumplimiento

Teams usa las siguientes normas: [ISO 27001](/microsoft-365/compliance/offering-iso-27001), [ISO 27018](/microsoft-365/compliance/offering-iso-27018), [SSAE18 SOC 1 y SOC 2](/microsoft-365/compliance/offering-soc), [HIPAA](/microsoft-365/compliance/offering-hipaa-hitech) y [cláusulas modelo de la UE (EUMC)](/microsoft-365/compliance/offering-eu-model-clauses). Dentro del marco de cumplimiento normativo de Microsoft, Microsoft clasifica las aplicaciones y servicios Microsoft 365 y Office 365 en cuatro categorías. Cada categoría está definida por compromisos de cumplimiento específicos que deben cumplirse para que un servicio de Microsoft 365 o Office 365, o un servicio de Microsoft relacionado, aparezca en esa categoría.

Encontrará detalles en los [Recursos de protección de datos](https://servicetrust.microsoft.com/ViewPage/TrustDocumentsV3?command=Download&downloadType=Document&downloadId=b7d05b86-c69b-41ba-8245-21161b9febf9&tab=7f51cb60-3d6c-11e9-b2af-7bb9f5d2d913&docTab=7f51cb60-3d6c-11e9-b2af-7bb9f5d2d913_Compliance_Guides). Teams también es compatible con el cumplimiento de Cloud Security Alliance.

## <a name="related-topics"></a>Temas relacionados

[seguridad de Microsoft 365](/microsoft-365/security/)

[cumplimiento de Microsoft 365](/microsoft-365/compliance/)

[Ofertas de cumplimiento de Microsoft](/microsoft-365/compliance/offering-home)
