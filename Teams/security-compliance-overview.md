---
title: Información general de seguridad y cumplimiento en Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/11/2018
ms.topic: conceptual
ms.service: msteams
ms.reviewer: anach
audience: admin
description: Una descripción general de las características de seguridad y cumplimiento de Microsoft Teams, entre las que se incluyen auditoría e informes, búsqueda de contenido de cumplimiento, exhibición de eDiscovery y más.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1keywords:
- ms.teamsadmincenter.dashboard.helparticle.securityandcompliance
appliesto:
- Microsoft Teams
ms.openlocfilehash: 95f8910005121faceb261a399ed64a4f68e5cad4
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2020
ms.locfileid: "40988805"
---
<a name="overview-of-security-and-compliance-in-microsoft-teams"></a>Información general de seguridad y cumplimiento en Microsoft Teams
======================================================

Microsoft Teams está incorporado en la nube empresarial a gran escala de Office 365, proporcionando las funciones avanzadas de seguridad y cumplimiento que esperan nuestros clientes.

Teams es compatible con el nivel D. Esto incluye los siguientes estándares: ISO 27001, ISO 27018, SSAE16 SOC 1 y SOC 2, HIPAA y las cláusulas de modelo de la UE (EUMC). En Microsoft Compliance Framework, Microsoft clasifica las aplicaciones y servicios de Office 365 en cuatro categorías. Cada categoría está definida por compromisos de cumplimiento específicos que deben cumplirse para que un servicio de Office 365, o un servicio de Microsoft relacionado, se muestre en esa categoría.

Los servicios en las categorías de cumplimiento C y D que tienen compromisos de cumplimiento están habilitados de manera predeterminada. Los servicios en las categorías A y B incluyen controles para activar o desactivar estos servicios para una organización entera. Los detalles se pueden encontrar en el [Marco de cumplimiento normativo de estándares y regulaciones del sector](https://download.microsoft.com/download/1/4/3/1434ABAB-B8E9-412D-8C3A-187B5FCB7A2F/Compliance%20Framework%20document.pdf). Teams también cumple con los requisitos de Cloud Security Alliance.

Teams también aplica la autenticación en dos fases de todo el equipo y de toda la organización, el inicio de sesión único a través de Active Directory y el cifrado de datos en tránsito y en reposo. Los archivos se almacenan en SharePoint y están respaldados por el cifrado de SharePoint. Las notas se almacenan en OneNote y están respaldadas por el cifrado de OneNote. Los datos de OneNote se almacenan en el sitio de SharePoint de grupo. La ficha wiki también se puede usar para tomar notas y su contenido también se almacena en el sitio de SharePoint de grupo.

También hemos agregado compatibilidad con la búsqueda en el registro de auditoría, eDiscovery y la suspensión legal para los canales, los chats y los archivos, así como la administración de aplicaciones móviles con Microsoft Intune. Vaya al centro de cumplimiento de & de seguridad de Office 365 para administrar esta configuración. 

Para obtener más información sobre la seguridad y el cumplimiento de Office 365, lea [configurar el inquilino de office 365 para mayor seguridad](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security).

> [!NOTE]
> En la actualidad, los [canales privados](private-channels.md) admiten características de seguridad y cumplimiento limitadas. La compatibilidad con el conjunto completo de características de seguridad y cumplimiento de los canales privados estará disponible próximamente.

## <a name="auditing-and-reporting"></a>Auditoría y generación de informes

Los complementos de búsqueda de registros de auditoría directamente en el centro de cumplimiento de la & de seguridad de Office 365 y exponen las funciones para establecer alertas y/o informar sobre eventos de auditoría haciendo que estén disponibles, exportando los conjuntos de eventos genéricos o específicos de la carga de trabajo para su uso y investigación sin límites Todos los datos del registro de auditoría están disponibles para configurar alertas en el centro de cumplimiento de & de seguridad de Office 365, además de filtrar y exportar para realizar análisis adicionales. Consulte este [vínculo](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security-Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c) para obtener más información sobre cómo realizar una búsqueda de registros de auditoría de eventos de Microsoft Teams en el centro de cumplimiento de & de seguridad de Office 365. 

## <a name="compliance-content-search"></a>Búsqueda de contenido de cumplimiento

La búsqueda de contenido se puede usar para buscar todos los datos de Teams mediante capacidades de filtrado avanzadas y exportarlos a un contenedor específico para ofrecer compatibilidad con litigios y cumplimiento. Esto puede hacerse con o sin un caso de exhibición de eDiscovery. Esto permite a los administradores de cumplimiento recopilar datos de Teams en todos los usuarios, revisarlos y exportarlos para su procesamiento posterior. Consulte este [vínculo](https://support.office.com/article/content-search-in-office-365-53390468-eec6-45cb-b6cd-7511f9c909e4) para obtener más información sobre cómo realizar una búsqueda de contenido de cumplimiento de contenido de Microsoft Teams en el centro de cumplimiento de & de seguridad de Office 365. 

Sugerencia: el tipo Microsoft Teams se puede usar para filtrar a solo contenido de Microsoft Teams es decir, mensajes instantáneos y de canal, reuniones y llamadas.

## <a name="ediscovery"></a>eDiscovery

La exhibición de documentos electrónicos es el aspecto electrónico de identificación, recolección y producción de información almacenada por medios electrónicos (ESI) en respuesta a una solicitud para la producción en una demanda legal o una investigación. Las capacidades incluyen administración de casos, preservación, búsqueda, análisis y exportación de datos de equipos. Esto incluye chat, mensajería y archivos, reuniones y resúmenes de llamadas. Para las reuniones y las llamadas de Teams, se crea un resumen de los eventos que se produjeron en la reunión y la llamada en eDiscovery. 

Para obtener más información sobre cómo realizar eDiscovery en la seguridad & centro de cumplimiento y ejecutar la búsqueda de contenido de Teams para el contenido de Teams, vaya a los siguientes vínculos: 

[eDiscovery](https://support.office.com/article/manage-legal-investigations-in-office-365-2e5fbe9f-ee4d-4178-8ff8-4356bc1b168e) 

[Búsqueda de contenido](https://support.office.com/article/search-for-content-in-office-365-df2d1e0f-b476-42c9-aade-4a260b24f193)

Los clientes pueden aprovechar eDiscovery local o [Advanced eDiscovery] según sus requisitos (https://support.office.com/article/Office-365-Advanced-eDiscovery-fd53438a-a760-45f6-9df4-861b50161ae4). La siguiente tabla muestra las diferencias entre estos dos métodos:


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

Durante un litigio, a menudo es necesario que todos los datos asociados con un usuario (custodia) o un equipo se conserven como inmutables para que se puedan usar como evidencias para el caso. Esto se logra colocando un usuario (buzón de usuario) o un equipo en retención legal. Cuando cualquier equipo de Teams se ponga en conservación local (subconjunto del buzón o la colección de sitios a través de consultas de destino o contenido filtrado) o retención por juicio (toda la colección de sitios o buzones), la retención se colocará en el buzón de grupos. Esto garantiza que incluso si los usuarios finales eliminan o editan los mensajes de canal que se encuentran informados en el buzón de correo del grupo, se mantienen las copias inmutables de ese contenido y están disponibles en la búsqueda de eDiscovery. Las suspensiones legales suelen aplicarse en el contexto de un caso de eDiscovery. Consulte [este](https://support.office.com/article/overview-of-preservation-policies-9c3b1d52-40ce-4ba3-a520-9ae0be15538a) artículo de la ayuda para conocer más acerca de la preservación y la retención en el centro de cumplimiento de & de seguridad de Office 365. 

## <a name="information-protection-architecture-for-microsoft-teams"></a>Arquitectura de protección de la información para Microsoft Teams. 

La siguiente ilustración indica el flujo de recopilación de datos de Teams para archivos y mensajes de Exchange y SharePoint para Teams. 

![Diagrama del flujo de trabajo de datos de Teams para Exchange y SharePoint](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image1.png)

La siguiente ilustración indica el flujo de recopilación de las reuniones de Teams y los datos de llamadas a Exchange.

![Diagrama del flujo de trabajo de reuniones de Teams y datos de llamadas a Exchange](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image1a.png)

> [!IMPORTANT]
> Puede haber un retraso de hasta 24 horas para descubrir el contenido de un equipo.

<a name="licensing"></a>Licencias
---------------

En lo que se refiere a las funciones de protección de información, las suscripciones de Office 365 y las licencias autónomas asociadas determinarán el conjunto de características disponible.


| Funcionalidad de protección de información | Office 365 Business Essentials | Office 365 Empresa Premium | Office 365 Enterprise E1 | Office 365 Enterprise E3/E4 | Office 365 Enterprise E5 |
|-----------------------------------|--------------------------------|-----------------------------|--------------------------|-----------------------------|--------------------------|
|              Archivo              |               -                |              -              |            -             |             Sí             |           Sí            |
|        eDiscovery local        |               -                |              -              |            -             |             Sí             |           Sí            |
|        eDiscovery avanzado        |               -                |              -              |            -             |              -              |           Sí            |
|            Suspensión legal             |               -                |              -              |            -             |             Sí             |           Sí            |
|     Búsqueda de contenido de cumplimiento     |               -                |             Sí             |           Sí            |             Sí             |           Sí            |
|      Auditoría y generación de informes       |              Sí               |             Sí             |           Sí            |             Sí             |           Sí            |
|       Acceso condicional\*        |              Sí               |             Sí             |           Sí            |             Sí             |           Sí            |

> [!NOTE]
> \*El acceso condicional requiere licencias adicionales


| |  |  |
|---------|---------|---------|
|![Un icono que representa un punto de decisión](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image3.png)     |Puntos de decisión         |¿Su organización tiene las licencias necesarias para cumplir con los requisitos empresariales de seguridad y cumplimiento?         |
|![Un icono que representa los pasos siguientes](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image4.png)    |Siguientes pasos         |Revise las licencias actuales de su organización y confirme que cumple con todos los requisitos empresariales de cumplimiento y seguridad.         |

Antes de habilitar cualquiera de estas características, asegúrese de que tiene acceso al centro de cumplimiento de & de seguridad en el centro de administración de Microsoft 365. De manera predeterminada, los administradores de inquilinos tienen acceso.

La búsqueda de contenido y la exhibición de eDiscovery no requieren la habilitación en el centro de cumplimiento de & de seguridad.

<a name="location-of-data-in-teams"></a>Ubicación de los datos en Teams
-------------------------

Los datos de Teams residen en la región geográfica asociada con su inquilino de Office 365. En la actualidad, Teams es compatible con las regiones Australia, Canadá, Francia, India, Japón, Reino Unido, Corea del sur, Sudáfrica, Sudamérica y Asia. 

> [!IMPORTANT]
> En la actualidad, Teams ofrece residencia de datos en Australia, Canadá, Francia, India, Japón, el Reino Unido, Corea del sur y Sudáfrica solo para inquilinos nuevos. Un inquilino nuevo se define como cualquier inquilino que no ha tenido ningún usuario desde el inicio de sesión del inquilino en Teams. Los inquilinos existentes de Australia, India, Japón y Corea del sur seguirán teniendo los datos de sus equipos almacenados en la región de APAC. Los inquilinos existentes de Canadá seguirán teniendo sus datos almacenados en América. Los inquilinos existentes en Francia, Reino Unido y Sudáfrica seguirán teniendo sus datos almacenados en la región de EMEA.

Puede encontrar más información sobre la residencia de datos de Sudáfrica para Teams en la publicación de blog de Varun Sagar, [Microsoft Teams lanza la residencia de datos de Sudáfrica](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-South-Africa-Data-Residency/ba-p/776611).

Más información sobre la residencia de datos de Corea del sur para equipos viene cortesía de la entrada de blog de Varun Sagar, [Microsoft Teams lanza la residencia de datos de Corea del sur](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-South-Korea-Data-Residency/ba-p/789171).

Si desea conocer más detalles sobre el inicio de la residencia de datos en India y Reino Unido, lea la publicación [Microsoft Teams launches India Data Residency, other geos coming soon](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-Launches-Australia-and-Japan-Data-Residency/ba-p/237827) (Microsoft Teams iniciará la residencia de datos de India y otras zonas geográficas muy pronto) en el blog de Ansuman Acharya. 

Para obtener más información sobre la residencia de datos de Canadá para Teams, consulte la publicación de blog de Varun Sagar, [Microsoft Teams lanza la residencia de datos de Canadá, Australia y Japón próximamente](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-Launches-Canada-Data-Residency-Australia-and/ba-p/227178). 

Para obtener más información sobre el lanzamiento de la residencia de datos de Australia y Japón para Teams, consulte la publicación de blog de Varun Sagar, [Microsoft Teams lanza la residencia de datos de Australia y Japón](https://go.microsoft.com/fwlink/?linkid=867773). 

Para obtener más información sobre el lanzamiento de la residencia de datos de Francia para Teams, consulte la publicación de blog de Varun Sagar, [Microsoft Teams lanza la residencia de datos de Francia](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-France-Data-Residency/ba-p/364466).

Para ver qué región hospeda los datos de su inquilino, vaya al**perfil**de la organización**configuración** > del [Centro](https://portal.office.com/adminportal/home) > de administración de 365 de Microsoft. Desplácese hasta **Data location** (Ubicación de datos). 

![Captura de pantalla de la tabla de ubicación de datos que incluye equipos en el centro de administración](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image5.png)

<a name="how-do-conditional-access-policies-work-for-teams"></a>¿Cómo funcionan las directivas de acceso condicional para Teams?
-------------------------

Microsoft Teams depende en gran medida de Exchange Online, SharePoint Online y Skype empresarial online para escenarios de productividad esenciales, como reuniones, calendarios, chats interoperativos y archivos compartidos. Las directivas de acceso condicional que se configuran para estas aplicaciones en la nube se aplican a Microsoft Teams cuando un usuario inicia sesión directamente en Microsoft Teams, en cualquier cliente. 

Microsoft Teams se admite por separado como una aplicación de nube en las directivas de acceso condicional de Azure Active Directory. Las directivas de acceso condicional que se establecen para la aplicación en la nube de Microsoft Teams se aplican a Microsoft Teams cuando un usuario inicia sesión. Sin embargo, sin las directivas correctas en otras aplicaciones como Exchange Online y SharePoint Online, los usuarios pueden seguir teniendo acceso directamente a esos recursos. Para obtener más información sobre cómo configurar una directiva de acceso condicional en el portal de Azure, vaya a: (https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal-get-started) 

Los clientes de escritorio de Microsoft Teams para Windows y Mac son compatibles con la autenticación moderna. La autenticación moderna ofrece inicio de sesión basado en la biblioteca de autenticación de Azure Active Directory (ADAL) para las aplicaciones cliente de Microsoft Office en todas las plataformas.

La aplicación de escritorio de Microsoft Teams es compatible con AppLocker.  Para obtener más información sobre los requisitos previos de AppLocker, consulte: requisitos para usarhttps://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/requirements-to-use-applocker)AppLocker (.

<a name="privacy-in-teams"></a>Privacidad en Teams
--------------------------

Como cliente de Office 365, el usuario posee y controla sus propios datos. Microsoft no usa los datos para ninguna otra finalidad que proporcionarle el servicio para el que se ha suscrito. Como proveedores de servicios, no examinamos el correo electrónico, los documentos o los equipos para enviar publicidad o para otras finalidades que no estén relacionadas con el servicio. Microsoft no tiene acceso al contenido cargado. Tal como ocurre en OneDrive para la Empresa y SharePoint Online, los datos de los clientes permanecen en el inquilino.

Consulte más información sobre la confianza y la información relacionada con la seguridad en el [centro de confianza de Microsoft](https://microsoft.com/trustcenter). Teams sigue las mismas instrucciones y principios que el centro de confianza de Microsoft.

<a name="related-topics"></a>Temas relacionados
----------------------
[Vínculos seguros de Office 365 ATP](https://docs.microsoft.com/office365/securitycompliance/atp-safe-links#how-to-get-atp-safe-links-protection)
