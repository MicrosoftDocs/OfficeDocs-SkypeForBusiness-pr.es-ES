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
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: f080d90f0a384bfdc4010a80d7c84a1b51a10754
ms.sourcegitcommit: ea6ee8ce28e82fcd7c07554c3428ae242d6f04da
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/07/2018
ms.locfileid: "27201368"
---
<a name="overview-of-security-and-compliance-in-microsoft-teams"></a>Información general de seguridad y cumplimiento en Microsoft Teams
======================================================

Microsoft Teams está incorporado en la nube empresarial a gran escala de Office 365, proporcionando las funciones avanzadas de seguridad y cumplimiento que esperan nuestros clientes.

Los equipos es compatible con niveles D. Esto incluye los siguientes estándares: certificación ISO 27001, ISO 27018, SSAE16 seguridad social 1 y 2 de la seguridad social, HIPAA y cláusulas de modelo de la UE (EUMC). En el marco de cumplimiento de normas de Microsoft, Microsoft clasifica las aplicaciones de Office 365 y servicios en cuatro categorías. Cada categoría se define mediante los compromisos de cumplimiento de normas específicas que deben cumplirse para que un servicio de Office 365, o un servicio de Microsoft relacionado, que se mostrarán en esa categoría.

Los servicios en las categorías de cumplimiento C y D que tienen compromisos de cumplimiento están habilitados de manera predeterminada. Los servicios en las categorías A y B incluyen controles para activar o desactivar estos servicios para una organización entera. Los detalles se pueden encontrar en el [Marco de cumplimiento normativo de estándares y regulaciones del sector](https://go.microsoft.com/fwlink/?linkid=855777). Teams también cumple con los requisitos de Cloud Security Alliance.

Los equipos también se aplica a todo el equipo y toda la organización autenticación en dos fases, inicio de sesión único a través de Active Directory y el cifrado de datos en tránsito y en reposo. Los archivos se almacenan en SharePoint y se realizan mediante el cifrado de SharePoint. Las notas se almacenan en OneNote y se realizan mediante el cifrado de OneNote. Los datos de OneNote se almacenan en el sitio de SharePoint del equipo. También se puede usar la ficha sitio Wiki para tomar notas y su contenido también se almacena en el sitio de SharePoint del equipo.

También hemos agregado compatibilidad con la búsqueda en el registro de auditoría, eDiscovery y la suspensión legal para los canales, los chats y los archivos, así como la administración de aplicaciones móviles con Microsoft Intune. Vaya a la seguridad de Office 365 & Centro de cumplimiento para administrar esta configuración. 

## <a name="auditing-and-reporting"></a>Auditoría y generación de informes

Búsqueda de registro de auditoría derecha en el centro de cumplimiento y seguridad de Office 365 se conecta y expone capacidades para establecer alertas o informar sobre eventos de auditoría haciendo que estén disponibles, exportar de carga de trabajo específica o evento genérico se establece para el uso de administración y de investigación, a través de un escala de tiempo de auditoría ilimitado. Todos los datos de registro de auditoría está disponibles para la configuración de alertas en el centro de cumplimiento y seguridad de Office 365, así como para filtrar y exportar para realizar un análisis. Consulte este [vínculo](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security-Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c) para obtener más información acerca de cómo llevar a cabo una búsqueda de registro de auditoría para eventos de Microsoft Teams en el centro de cumplimiento y seguridad de Office 365. 

## <a name="compliance-content-search"></a>Búsqueda de contenido de cumplimiento

Búsqueda de contenido puede se usa para buscar todos los datos de los equipos a través de capacidades de filtrado de enriquecido y exportar a un contenedor específico para la compatibilidad con el cumplimiento de normas y litigios. Esto puede realizarse con o sin un caso de exhibición de documentos electrónicos. Esto permite que los administradores de cumplimiento recopilar datos de los equipos a través de todos los usuarios, revisar y exportar para continuar el procesamiento. Consulte este [vínculo](https://support.office.com/article/content-search-in-office-365-53390468-eec6-45cb-b6cd-7511f9c909e4) para obtener más información acerca de cómo realizar una búsqueda de contenido de cumplimiento de normas de contenido de Microsoft Teams en el centro de cumplimiento y seguridad de Office 365. 

Sugerencia: El tipo Microsoft Teams puede usará para filtrar a través de para Microsoft Teams solo contenido, es decir, Chat y mensajes de canal, reuniones y llamadas. 

## <a name="ediscovery"></a>eDiscovery

La exhibición de documentos electrónicos es el aspecto electrónico de identificación, recolección y producción de información almacenada por medios electrónicos (ESI) en respuesta a una solicitud para la producción en una demanda legal o una investigación. Capacidades incluyen la administración de casos, conservación, búsqueda, análisis y exportación de datos de los equipos. Esto incluye los resúmenes de chat, mensajería y archivos, reuniones y llamadas. Para las reuniones de los equipos y las llamadas, un resumen de los eventos que se realizaron en la reunión y la llamada se crean y está disponible en la exhibición de documentos electrónicos. 

Para obtener más información acerca de cómo realizar la exhibición de documentos electrónicos en el centro de cumplimiento y seguridad y ejecute la búsqueda de contenido de cumplimiento para el contenido de los equipos, vaya a los siguientes vínculos: 

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

Durante un litigio, a menudo es necesario que todos los datos asociados con un usuario (custodia) o un equipo se conserva inalterados por lo que se puede usar como evidencia para el caso. Esto se logra mediante la colocación de un usuario (buzón de correo del usuario) o a un equipo con retención legal. Cuando cualquier equipo dentro de los equipos se pone en conservación local (subconjunto de la colección de sitio o buzón de correo a través de las consultas de destinadas o contenido filtrado) o juicio (colección completa de buzón de correo o sitio), la suspensión se coloca en el buzón de grupos. Esto garantiza que, incluso si los usuarios finales eliminar o editar los mensajes de canal que se ingestión en el buzón de correo de grupo, inmutables copias de que el contenido se conservan y disponibles en la búsqueda de exhibición de documentos electrónicos. Las suspensiones legales suelen aplicarse en el contexto de un caso de eDiscovery. Consulte [este](https://support.office.com/article/overview-of-preservation-policies-9c3b1d52-40ce-4ba3-a520-9ae0be15538a) artículo para conocer más información acerca de la conservación y las suspensiones en el centro de cumplimiento y seguridad de Office 365 de ayuda. 

## <a name="information-protection-architecture-for-microsoft-teams"></a>Arquitectura de protección de la información para los equipos de Microsoft. 

En la siguiente figura se indica el flujo de recopilación de datos de los equipos a Exchange y SharePoint para los archivos de los equipos y los mensajes. 

![Diagrama del flujo de trabajo de los datos de Teams en Exchange y SharePoint.](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image1.png)

En la siguiente figura se indica el flujo de ingesta de las reuniones de los equipos y los datos que llama a Exchange.

![Diagrama de flujo de trabajo de reuniones de los equipos y los datos que llama a Exchange.](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image1a.png)

> [!IMPORTANT]
> Puede haber un retraso de 24 horas para descubrir el contenido de los equipos de hasta.

<a name="licensing"></a>Licencias
---------------

En lo que se refiere a las funciones de protección de información, las suscripciones de Office 365 y las licencias autónomas asociadas determinarán el conjunto de características disponible.


| Funcionalidad de protección de información | Office 365 Business Essentials | Office 365 Business Premium | Office 365 Enterprise E1 | Office 365 Enterprise E3/E4 | Office 365 Enterprise E5 |
|-----------------------------------|--------------------------------|-----------------------------|--------------------------|-----------------------------|--------------------------|
|              Archivo              |               -                |              -              |            -             |             Sí             |           Sí            |
|        eDiscovery local        |               -                |              -              |            -             |             Sí             |           Sí            |
|        eDiscovery avanzado        |               -                |              -              |            -             |              -              |           Sí            |
|            Suspensión legal             |               -                |              -              |            -             |             Sí             |           Sí            |
|     Búsqueda de contenido de cumplimiento     |               -                |              -              |            -             |             Sí             |           Sí            |
|      Auditoría y generación de informes       |              Sí               |             Sí             |           Sí            |             Sí             |           Sí            |
|       Acceso condicional\*        |              Sí               |             Sí             |           Sí            |             Sí             |           Sí            |

> [!NOTE]
> \*El acceso condicional requiere licencias adicionales


| |  |  |
|---------|---------|---------|
|![Icono de Punto de decisión.](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image3.png)     |Puntos de decisión         |¿Su organización tiene las licencias necesarias para cumplir con los requisitos empresariales de seguridad y cumplimiento?         |
|![Icono de Siguientes pasos.](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image4.png)    |Pasos siguientes         |Revise la licencia actual de la organización y confirme que cumple con todos los requisitos de negocio de cumplimiento y seguridad.         |

Antes de habilitar cualquiera de estas características, asegúrese de que tener acceso a la seguridad y el centro de cumplimiento en el centro de administración de Office 365. De manera predeterminada, los administradores de inquilinos tienen acceso.

Búsqueda de contenido y exhibición de documentos electrónicos no requieren activación en el centro de cumplimiento y seguridad.

<a name="location-of-data-in-teams"></a>Ubicación de los datos en Teams
-------------------------

Los datos de Teams residen en la región geográfica asociada con su inquilino de Office 365. Actualmente, los equipos admite las regiones Australia, Canadá, India, Japón, Reino Unido, América, APAC y EMEA. 

> [!IMPORTANT]
> Los equipos actualmente ofrece residencia de datos en Australia, Canadá, India, Japón y Reino Unido para sólo los inquilinos nuevo. Un inquilino nuevo se define como cualquier inquilino que no ha tenido ningún usuario desde el inicio de sesión del inquilino en Teams. Los inquilinos existentes de Australia, India y Japón seguirán tienen sus datos de los equipos almacenados en el área de APAC. Los inquilinos existentes en Canadá y Reino Unido tendrá sus datos almacenados en América y EMEA región, respectivamente.

Si desea conocer más detalles sobre el inicio de la residencia de datos en India y Reino Unido, lea la publicación [Microsoft Teams launches India Data Residency, other geos coming soon](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-Launches-Australia-and-Japan-Data-Residency/ba-p/237827) (Microsoft Teams iniciará la residencia de datos de India y otras zonas geográficas muy pronto) en el blog de Ansuman Acharya. 

Para obtener más información en residencia de datos de Canadá para los equipos, lea la entrada de blog de Varun Sagar, [residencia de datos de Microsoft los equipos inicia Canadá, Australia y Japón próximamente](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-Launches-Canada-Data-Residency-Australia-and/ba-p/227178). 

Para obtener más información sobre el lanzamiento de Australia y Japón residencia de datos para los equipos, Leer entrada de blog de Varun Sagar, [Microsoft equipos inicia Australia y Japón datos residencia ](https://go.microsoft.com/fwlink/?linkid=867773). 

Para ver qué región contiene datos para el inquilino, vaya al [Centro de administración de Office 365](https://portal.office.com/adminportal/home) > **configuración de** > **el perfil de organización**. Desplácese hasta **Data location** (Ubicación de datos). 

![Captura de pantalla de la tabla de la ubicación de datos, incluidos los equipos, en el centro de administración de Office 365.](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image5.png)

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
