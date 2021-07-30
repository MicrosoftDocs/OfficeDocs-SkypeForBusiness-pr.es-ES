---
title: Información general sobre seguridad y cumplimiento
author: laurawi
ms.author: laurawi
manager: laurawi
ms.topic: conceptual
ms.service: msteams
ms.reviewer: anwara
audience: admin
description: Información general sobre las Microsoft Teams seguridad y cumplimiento normativo, como privacidad y cifrado, auditorías e informes, etc.
localization_priority: Normal
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
ms.openlocfilehash: 4a4c9097c4111ecd7f224bb268f6d90434569c9a
ms.sourcegitcommit: 5c59f9bf5a9477607b378c23fa3c8670930dc428
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/29/2021
ms.locfileid: "53646401"
---
# <a name="security-and-compliance-in-microsoft-teams"></a>Seguridad y cumplimiento en Microsoft Teams

> [!IMPORTANT]
> Para obtener información sobre cómo garantizar mejor la seguridad mientras todos trabajan desde casa durante el brote **de COVID-19,** lea estos artículos:
>  - [Las 12 tareas principales de los equipos de seguridad para dar soporte al trabajo desde casa](/microsoft-365/security/top-security-tasks-for-remote-work)
>  - [Optimizar la conectividad de Microsoft 365 u Office 365 para usuarios remotos que usan túnel dividido de VPN](/Office365/Enterprise/office-365-vpn-split-tunnel)
>  - Actualizado el 2 de abril de 2020: [Teams de seguridad](teams-security-guide.md)


Microsoft Teams se basa en la nube de nivel Microsoft 365 y Office 365 escala hiperespacio empresarial, lo que ofrece las capacidades avanzadas de seguridad y cumplimiento que esperan nuestros clientes. Para obtener más información sobre la planificación de la seguridad en Microsoft 365 o [Office 365,](/microsoft-365/security/office-365-security/security-roadmap) la hoja de ruta de seguridad es un buen lugar para empezar. Para obtener más información sobre la planificación del cumplimiento en Microsoft 365 o Office 365, puede empezar [con Plan de](/microsoft-365/compliance/plan-for-security-and-compliance)seguridad & cumplimiento .


En este artículo se proporcionará más información sobre Teams seguridad y cumplimiento específicos. No se pierda estos vídeos de Microsoft Mechanics sobre seguridad y cumplimiento:

- [Microsoft Teams Essentials para TI: Seguridad y cumplimiento](https://youtu.be/91lHNKVVvQ4) (12:42 min)
- [Microsoft Teams controles de seguridad y cumplimiento](https://www.youtube.com/watch?v=Km4T4hMM__k) (10:54 min)

> [!IMPORTANT]
> Como cliente de Microsoft 365 o Office 365, usted es el propietario y el control de los datos. Microsoft no usa tus datos para nada que no sea proporcionarte el servicio al que te has suscrito. Como proveedor de servicios, no analizamos su correo electrónico, documentos o equipos para publicidad o para fines que no estén relacionados con el servicio. Microsoft no tiene acceso al contenido cargado. Al OneDrive y SharePoint en Microsoft 365, los datos de clientes permanecen dentro del espacio empresarial. Puede consultar más información sobre nuestra confianza y seguridad en el [Centro de confianza de Microsoft.](https://microsoft.com/trustcenter) Teams sigue las mismas directrices y principios que el Centro de confianza de Microsoft.

## <a name="security"></a>Seguridad

Teams exige la autenticación en dos fases para todo el equipo y para toda la organización, el inicio de sesión único a través de Active Directory y el cifrado de datos en tránsito y en reposo. Los archivos se almacenan en SharePoint y están a SharePoint cifrado. Las notas se almacenan en OneNote y están OneNote cifrado. Los OneNote datos se almacenan en el sitio de SharePoint grupo. La pestaña Wiki también se puede usar para tomar notas y su contenido también se almacena en el sitio de SharePoint grupo.

Lea [Modelos de identidad y autenticación](identify-models-authentication.md) para obtener [](sign-in-teams.md) más información sobre la autenticación y Teams, y Cómo funciona la autenticación moderna ayudará en particular con la autenticación moderna.

Como Teams trabaja en asociación con SharePoint, OneNote, Exchange y mucho más, debería estar cómodo administrando la seguridad en Microsoft 365 o Office 365 todo. Para obtener más información, lea cómo configurar su Microsoft 365 [o Office 365 organización para aumentar la seguridad.](/office365/securitycompliance/tenant-wide-setup-for-increased-security)

> [!NOTE]
> Actualmente, [los canales privados](private-channels.md) admiten características de seguridad y cumplimiento limitadas. Próximamente se ofrece soporte técnico para el conjunto completo de características de seguridad y cumplimiento en canales privados.

### <a name="advanced-threat-protection-atp"></a>Protección contra amenazas avanzada (ATP)

Protección contra amenazas avanzada (ATP) está disponible para Microsoft Teams, junto con SharePoint y OneDrive, aplicaciones que se integran con Teams para la administración de contenido. ATP le permite determinar si el contenido de estas aplicaciones es de naturaleza malintencionada y bloquear este contenido del acceso de los usuarios.

El modo en que se administra el contenido afectado después de la detección está en función de la configuración que haya seleccionado en Microsoft 365 o Office 365. Le recomendamos que tenga en cuenta todas las aplicaciones cuando se trata de configurar ATP y, para obtener más información, [ATP para SharePoint, OneDrive](/microsoft-365/security/office-365-security/atp-for-spo-odb-and-teams) y Microsoft Teams tendrá información detallada sobre cómo empezar.

### <a name="safe-links"></a>Caja fuerte Vínculos

Aunque, en este momento, los vínculos seguros de protección contra amenazas avanzadas [](/microsoft-365/security/office-365-security/atp-safe-links-for-teams) (ATP) no están disponibles en Microsoft Teams, ahora están en versión preliminar pública a través de nuestro Programa de adopción de tecnología (TAP) y, aunque no se establece una fecha de lanzamiento para la disponibilidad general, actualizaremos este artículo cuando llegue esa hora. Mientras tanto, para obtener información sobre Microsoft 365 o Office 365 Caja fuerte vínculos, revisa [Atp Caja fuerte vínculos](/office365/securitycompliance/atp-safe-links#how-to-get-atp-safe-links-protection). Los vínculos Caja fuerte ATP están disponibles tanto en [el Plan 1 de ATP como en el Plan 2 de ATP.](/microsoft-365/security/office-365-security/office-365-atp)

### <a name="safe-attachments"></a>Caja fuerte Datos adjuntos

Caja fuerte datos adjuntos es una característica diseñada para mejorar la seguridad del usuario mediante la comprobación y detección de datos adjuntos malintencionados. Los administradores de [](/microsoft-365/security/office-365-security/set-up-atp-safe-attachments-policies) seguridad o global crean directivas para administrar estos datos adjuntos malintencionados sospechosos para evitar que se envíen a los usuarios, se haga clic y se actúe sobre ellos. Caja fuerte protección de datos adjuntos está disponible para SharePoint, OneDrive y Microsoft Teams, y Microsoft 365 o Office 365 plan avanzado de protección contra amenazas 1 y [2](/microsoft-365/security/office-365-security/office-365-atp) tienen esta capacidad. Obtenga más información sobre Caja fuerte datos adjuntos y cómo pueden ayudar a proteger su organización en Caja fuerte datos adjuntos en [Microsoft Defender para Office 365](/microsoft-365/security/office-365-security/atp-safe-attachments).

### <a name="secure-score"></a>Puntuación segura

Puntuación segura de Microsoft es una medida de la posición de seguridad de una organización, con un número más alto que indica que se han realizado más acciones de mejora. Se puede encontrar en el Microsoft 365 [de seguridad.](https://security.microsoft.com/securescore) Seguir las recomendaciones de puntuación segura puede proteger a su organización de amenazas. Desde un panel centralizado del centro de seguridad Microsoft 365, las organizaciones pueden supervisar y trabajar en la seguridad de sus Microsoft 365 identidades, aplicaciones y dispositivos. Microsoft Teams ahora tiene recomendaciones sobre Puntuación segura y se anima a los administradores a supervisar su posición de seguridad en la plataforma.

Puntuación segura ayuda a las organizaciones:
- Informe sobre el estado actual de la posición de seguridad de la organización.
- Mejore su posición de seguridad proporcionando detectabilidad, visibilidad, guía y control.
- Compare con los puntos de referencia y establezca indicadores clave de rendimiento (KPI).


### <a name="how-conditional-access-policies-work-for-teams"></a>Cómo funcionan las directivas de acceso condicional para Teams

Microsoft Teams depende en gran medida de Exchange Online, SharePoint y Skype Empresarial Online para escenarios de productividad principales, como reuniones, calendarios, chats de interoperabilidad y uso compartido de archivos. Las directivas de acceso condicional que se establecen para estas aplicaciones en la nube se aplican a Microsoft Teams cuando un usuario inicia sesión directamente en Microsoft Teams en cualquier cliente.

Microsoft Teams se admite por separado como una aplicación en la nube en Azure Active Directory de acceso condicional. Las directivas de acceso condicional que se establecen para Microsoft Teams aplicación en la nube se aplican a Microsoft Teams cuando un usuario inicia sesión. Sin embargo, sin las directivas correctas en otras aplicaciones como Exchange Online y SharePoint, es posible que los usuarios puedan acceder a esos recursos directamente. Para obtener más información sobre cómo configurar una directiva de acceso condicional en Azure Portal, [vea Azure Active Directory inicio rápido.](/azure/active-directory/active-directory-conditional-access-azure-portal-get-started)

Microsoft Teams de escritorio para Windows y Mac admiten la autenticación moderna. La autenticación moderna proporciona el inicio de sesión basado en la Azure Active Directory de autenticación (ADAL) para Microsoft Office aplicaciones cliente en todas las plataformas.

Microsoft Teams aplicación de escritorio admite AppLocker.  Para obtener más información sobre los requisitos previos de AppLocker, vea: Requisitos para usar [AppLocker.](/windows/security/threat-protection/windows-defender-application-control/applocker/requirements-to-use-applocker)

## <a name="compliance"></a>Cumplimiento

Teams tiene una amplia gama de información para ayudarle con las áreas de cumplimiento, incluido el cumplimiento de comunicaciones para canales, chats y datos adjuntos, directivas de retención, protección contra pérdida de datos (DLP), exhibición de documentos electrónicos y retención legal para canales, chats y archivos, búsqueda de registros de auditoría, así como administración de aplicaciones móviles con Microsoft Intune. Hemos proporcionado información sobre todos estos temas a continuación y puede ir a la Centro de cumplimiento de Microsoft 365 [para](https://compliance.microsoft.com) administrar esta configuración.

### <a name="information-barriers"></a>Barreras de información

Las barreras de información son directivas establecidas por los administradores de Teams para evitar que personas o grupos se comuniquen entre sí (cuando no hay necesidad empresarial de que lo hagan, o un motivo normativo para impedir que lo hagan), y también le permite establecer directivas relacionadas con cosas como búsquedas y exhibición de documentos electrónicos (que se tratan a continuación). Estas directivas pueden afectar a los usuarios en chats 1:1, chats grupales o a nivel de equipo. La característica Barrera de información está disponible en la nube pública y a partir de enero de 2021 se ha lanzado a GCC nube.

Para obtener más información sobre este tema, vaya a [Barreras de información en Microsoft Teams](information-barriers-in-teams.md).

### <a name="communication-compliance"></a>Cumplimiento de las comunicaciones

El cumplimiento de las comunicaciones en Microsoft 365 le permite agregar usuarios a directivas dentro del ámbito que se pueden configurar para examinar las comunicaciones de Microsoft Teams en busca de lenguaje ofensivo, información confidencial e información relacionada con estándares internos y normativos. Las comunicaciones de chat y los datos adjuntos asociados en canales de Teams públicos y privados, chats individuales y datos adjuntos se pueden analizar para ayudar a minimizar los riesgos de comunicación en su organización. Para obtener más información sobre cómo puede configurar directivas para ayudarle a detectar, capturar y tomar medidas para comunicaciones Teams, vea Cumplimiento de comunicaciones [en Microsoft 365](/microsoft-365/compliance/communication-compliance).

### <a name="retention-policies"></a>Directivas de retención

Las directivas de retención de Microsoft Teams le permiten conservar datos importantes para su organización, por motivos normativos, legales, empresariales u otras razones, y también para quitar contenido y comunicaciones que no son relevantes para conservarse. También puede usar directivas de retención para conservar los datos durante un período de tiempo y, después, eliminarlos. Para obtener más información, consulte [Directivas de retención en Microsoft Teams](retention-policies.md).

## <a name="sensitivity-labels"></a>Etiquetas de confidencialidad

Aplique [etiquetas de confidencialidad](/microsoft-365/compliance/sensitivity-labels) para proteger y regular el acceso al contenido organizativo confidencial creado durante la colaboración en equipos. Por ejemplo, aplique etiquetas que configuren la privacidad (pública o privada) de los equipos, controle el acceso de invitado y el uso compartido externo y administre el acceso desde dispositivos no administrados. Para obtener más información, revise [Etiquetas de confidencialidad en Microsoft Teams](sensitivity-labels.md).

### <a name="data-loss-prevention-dlp"></a>Prevención de pérdida de datos (DLP)

La prevención de pérdida de datos (DLP) en Microsoft Teams, así como el artículo DLP más grande para Microsoft 365 o Office 365, gira en torno a la preparación empresarial a la hora de proteger documentos y datos confidenciales. Tanto si tiene dudas sobre la información confidencial en mensajes o documentos, las directivas DLP podrán ayudar a garantizar que los usuarios no compartan estos datos confidenciales con las personas equivocadas.

Para obtener información sobre prevención de pérdida de datos en Teams, consulte [DLP para Microsoft Teams](/microsoft-365/compliance/dlp-microsoft-teams). Un buen artículo para las preocupaciones de DLP de O365 es Información general sobre la prevención [de pérdida de datos.](/microsoft-365/compliance/data-loss-prevention-policies)

### <a name="ediscovery"></a>eDiscovery

La detección electrónica o exhibición de documentos electrónicos es el aspecto electrónico de identificar, recopilar y producir información almacenada electrónicamente (ESI) en respuesta a una solicitud de producción en un procedimiento legal o una investigación. Las capacidades incluyen la administración de casos, la conservación, la búsqueda, el análisis y la exportación de Teams datos. Esto incluye chat, mensajería y archivos, resúmenes de reuniones y llamadas. Para Teams reuniones y llamadas, se crea un resumen de los eventos ocurridos en la reunión y la llamada y se hace disponible en eDiscovery.

Para obtener más información sobre cómo Microsoft 365 o Office 365 exhibición de documentos electrónicos en el centro de seguridad y el centro de cumplimiento y ejecutar la búsqueda de contenido de cumplimiento para el contenido Teams, vaya a los vínculos siguientes:

 - [eDiscovery](/microsoft-365/compliance/manage-legal-investigations)

 - [Búsqueda de contenido](/microsoft-365/compliance/search-for-content)

Tenemos un artículo Teams específico para obtener más información, [eDiscovery de chats](eDiscovery-investigation.md)de invitado a invitado.

Los clientes pueden aprovechar eDiscovery [o Advanced eDiscovery](/microsoft-365/compliance/office-365-advanced-ediscovery) según sus requisitos. La siguiente tabla muestra las diferencias entre estos dos métodos:

|&nbsp; |eDiscovery  |eDiscovery avanzado  |
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

Durante el litigio, es posible que necesite que todos los datos asociados con un usuario (custodio) o un equipo se conserven como inmutables, de modo que se puedan usar como evidencia para el caso. Para ello, coloque a un usuario (buzón de usuario) o a un equipo en retención legal. Para una retención legal del equipo, el buzón del equipo se puede colocar en las siguientes retenciones:

- In-Place (un subconjunto del buzón o la colección de sitios a través de consultas dirigidas o el contenido filtrado se pone en espera) o
- Retención por juicio (todo el buzón o la colección de sitios está en espera).

En cualquier caso, una vez establecida la retención, se asegura de que, incluso si los usuarios finales eliminan o editan mensajes de canal que están en el buzón de grupo, las copias inmutables de ese contenido se mantienen y están disponibles mediante la búsqueda de exhibición de documentos electrónicos. Las retenciones legales se aplican generalmente en el contexto de un caso de exhibición de documentos electrónicos.

Vea Información [general sobre las directivas de retención](/microsoft-365/compliance/retention-policies) para obtener más información sobre la conservación y las retenciones en el Centro de cumplimiento de Microsoft 365. Para obtener más Teams información específica sobre la retención legal, también tenemos colocar un usuario o equipo de Microsoft Teams en retención [legal](legal-hold.md) para que obtenga más información.

### <a name="compliance-content-search"></a>Búsqueda de contenido de cumplimiento

La búsqueda de contenido se puede usar para buscar todos los Teams a través de funcionalidades de filtrado enriquecido. Los datos resultantes se pueden exportar a un contenedor específico para soporte técnico de cumplimiento y litigios. Esto se puede hacer con o sin un caso de exhibición de documentos electrónicos. Esto permite a los administradores de cumplimiento recopilar Teams datos entre todos los usuarios, revisarlos y exportarlos para su procesamiento posterior. Consulte Búsqueda [](/microsoft-365/compliance/content-search) de contenido para obtener más información sobre cómo realizar una búsqueda de contenido de cumplimiento para Microsoft Teams y otros Microsoft 365 o Office 365 contenido en el Centro de cumplimiento de Microsoft 365.

> [!TIP]
> Con la búsqueda de contenido, puede filtrar hacia abajo para que solo Microsoft Teams contenido, como chat y mensajes de canal, reuniones y llamadas, si es necesario.

Si desea obtener más información Teams específica sobre cómo configurar la búsqueda de contenido, revise Búsqueda de [contenido en Microsoft Teams](content-search.md).

### <a name="auditing-and-reporting"></a>Auditoría y generación de informes

La búsqueda de registros de auditoría se conecta directamente al Centro de cumplimiento de Microsoft 365 y le ofrece la capacidad de establecer alertas, así como de informar sobre eventos de auditoría, al permitir la exportación de conjuntos de eventos específicos o genéricos de carga de trabajo para el uso de administradores y la investigación en una escala de tiempo de auditoría ilimitada. Puede configurar alertas para todos los datos de registro de auditoría dentro del Centro de cumplimiento de Microsoft 365 y filtrar y exportar estos datos para un análisis más exhaustivo. Consulte Buscar en [el registro](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance) de auditoría para obtener más información sobre cómo realizar una búsqueda de registro de auditoría Microsoft 365 o Office 365. Para obtener más información sobre cómo buscar Microsoft Teams eventos en el Centro de cumplimiento de Microsoft 365, también tenemos Activar la [auditoría](audit-log-events.md) en Teams para que lo revise.

## <a name="customer-key"></a>Clave de cliente

Microsoft 365 ofrece una capa adicional de cifrado sobre el cifrado de servicio para el contenido. Con las claves que proporcione, clave de cliente cifra varios tipos diferentes de datos en Microsoft Teams. Con clave de cliente en el nivel de aplicación, clave de cliente cifra Teams archivos almacenados en SharePoint en línea. Para obtener información, vea [Cifrado de servicio con clave de cliente.](/microsoft-365/compliance/customer-key-overview) 

Con la clave de cliente en el nivel de inquilino, clave de cliente cifra:
- Teams de chat (chats de 1:1, chats grupales, chats de reunión y conversaciones de canal)
- Teams multimedia (imágenes, fragmentos de código, vídeos e imágenes wiki)
- Teams llamadas y reuniones almacenadas en Teams almacenamiento
- Teams de chat
- Teams sugerencias de chat de Cortana
- Teams mensajes de estado Para obtener más información, vea Información general sobre la clave de cliente de [Microsoft 365](/microsoft-365/compliance/customer-key-tenant-level) en el nivel de inquilino y lea el blog de Microsoft Teams que trata el soporte técnico de clave de cliente [para Microsoft Teams](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/customer-key-support-for-microsoft-teams-now-in-public-preview/ba-p/1999893)ahora en vista previa pública. Para obtener información sobre la Microsoft Information Protection que incluía clave de cliente en el nivel de inquilino, lea Anunciar nuevas capacidades de Microsoft Information Protection para conocer y proteger los [datos confidenciales.](https://techcommunity.microsoft.com/t5/microsoft-security-and/announcing-new-microsoft-information-protection-capabilities-to/ba-p/1999692)

## <a name="privacy"></a>Privacidad

En Microsoft, proteger los datos es nuestra prioridad más alta. Para obtener información sobre nuestras prácticas de privacidad, lea:  

- [Privacidad en Microsoft](https://www.microsoft.com/trust-center/privacy)
- [Nuestro compromiso con la privacidad y la seguridad en Microsoft Teams](https://www.microsoft.com/en-us/microsoft-365/blog/2020/04/06/microsofts-commitment-privacy-security-microsoft-teams/)
- [Para profesionales de TI: Privacidad y seguridad en Microsoft Teams](https://www.microsoft.com/en-us/microsoft-365/blog/2020/04/06/it-professionals-privacy-security-microsoft-teams/#:~:text=We%20safeguard%20your%20privacy%20by,and%20distribution%20of%20your%20data.)

## <a name="information-protection-architecture"></a>Arquitectura de protección de la información

La siguiente ilustración indica el flujo de ingestión de Teams datos a Exchange y SharePoint para Teams archivos y mensajes.

> [!div class="mx-imgBorder"]
> ![Diagrama del flujo de trabajo Teams datos a Exchange y SharePoint](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image1.png)

La siguiente ilustración indica el flujo de ingestión de Teams reuniones y llamadas a Exchange.

> [!div class="mx-imgBorder"]
> ![Diagrama del flujo de trabajo de Teams reuniones y llamadas a Exchange](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image1a.png)

> [!IMPORTANT]
> Puede haber hasta un retraso de 24 horas para descubrir Teams contenido.

## <a name="licensing"></a>Licencias

Cuando se trata de las capacidades de protección de la información, Microsoft 365 suscripciones, Office 365 suscripciones y las licencias independientes asociadas determinarán el conjunto de características disponibles.

Para obtener información sobre cómo determinar las necesidades de [](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance) licencias para implementar características de seguridad y cumplimiento, revise los requisitos de licencia para las características de seguridad y cumplimiento.

> [!NOTE]
> La búsqueda de contenido y la exhibición de documentos electrónicos no tienen por qué estar habilitadas en el Centro de & cumplimiento para funcionar.

## <a name="location-of-data-in-teams"></a>Ubicación de los datos en Teams

Los datos de Teams residen en la región geográfica asociada con su organización de Microsoft 365 u Office 365. Para ver qué regiones son compatibles actualmente, revise [Ubicación de los](location-of-data-in-teams.md)datos en Microsoft Teams .

Si necesita ver qué región aloja los datos [](https://portal.office.com/adminportal/home)de su inquilino, vaya al Centro de administración de Microsoft 365  >  **Configuración**  >  **de la organización.** Desplácese hacia abajo hasta **Ubicación de datos**.

> [!div class="mx-imgBorder"]
> ![Captura de pantalla de la tabla Ubicación de datos Teams en el Centro de administración](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image5.png)

## <a name="compliance-standards"></a>Estándares de cumplimiento

Teams los siguientes estándares: [ISO 27001](/microsoft-365/compliance/offering-iso-27001), [ISO 27018,](/microsoft-365/compliance/offering-iso-27018) [SSAE18 SOC 1 y SOC 2,](/microsoft-365/compliance/offering-soc) [HIPAA](/microsoft-365/compliance/offering-hipaa-hitech)y Cláusulas modelo de la UE [(EUMC).](/microsoft-365/compliance/offering-eu-model-clauses) Dentro del marco de cumplimiento de Microsoft, Microsoft clasifica Microsoft 365 y Office 365 aplicaciones y servicios en cuatro categorías. Cada categoría se define por compromisos de cumplimiento específicos que deben cumplirse para que un servicio de Microsoft 365 o Office 365, o un servicio de Microsoft relacionado, aparezca en esa categoría.

Los detalles se pueden encontrar en los [Recursos de protección de datos.](https://servicetrust.microsoft.com/ViewPage/TrustDocumentsV3?command=Download&downloadType=Document&downloadId=b7d05b86-c69b-41ba-8245-21161b9febf9&tab=7f51cb60-3d6c-11e9-b2af-7bb9f5d2d913&docTab=7f51cb60-3d6c-11e9-b2af-7bb9f5d2d913_Compliance_Guides) Teams también es compatible con el cumplimiento de Cloud Security Alliance.

## <a name="related-topics"></a>Temas relacionados

[Microsoft 365 Seguridad](/microsoft-365/security/)

[Microsoft 365 Cumplimiento normativo](/microsoft-365/compliance/)

[Ofertas de cumplimiento de Microsoft](/microsoft-365/compliance/offering-home)
