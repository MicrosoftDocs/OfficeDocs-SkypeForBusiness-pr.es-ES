---
title: "Información general de seguridad y cumplimiento en Microsoft Teams | Soporte técnico de Microsoft"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "Descripción general de las características de seguridad y cumplimiento de Microsoft Teams, que incluye auditoría y generación informes, búsqueda de contenido de cumplimiento, eDiscovery y mucho más."
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: 6cca28ee5cd96d24e4b0da0a29748e0cf383eb0c
ms.sourcegitcommit: a315fbbb6a5337c32c9312550ee05fd9185020db
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/02/2017
---
<a name="overview-of-security-and-compliance-in-microsoft-teams"></a>Información general de seguridad y cumplimiento en Microsoft Teams
======================================================

Microsoft Teams está incorporado en la nube empresarial a gran escala de Office 365, proporcionando las funciones avanzadas de seguridad y cumplimiento que esperan nuestros clientes.

En el momento de su lanzamiento, Microsoft Teams cumple con el Nivel C. Esto incluye las siguientes normas: ISO 27001, ISO 27018, SSAE16 SOC 1 y SOC 2, HIPAA y las cláusulas modelo de la UE (EUMC). Dentro del marco de cumplimiento de Microsoft, Microsoft clasifica las aplicaciones y servicios de Office 365 en cuatro categorías. Cada categoría está definida por compromisos de cumplimiento específicos que deben darse para que un servicio de Office 365, o un servicio de Microsoft relacionado, se agregue a dicha categoría.

Los servicios en las categorías de cumplimiento C y D que tiene compromisos de cumplimiento están habilitados de manera predeterminada. Los servicios en las categorías A y B incluyen controles para activar o desactivar estos servicios para una organización entera. Los detalles se pueden encontrar en el [Marco de cumplimiento normativo de estándares y regulaciones del sector](https://go.microsoft.com/fwlink/?linkid=855777). Microsoft Teams también cumple con los requisitos de Cloud Security Alliance.

Microsoft Teams también emplea la autenticación en dos fases para todos los miembros del equipo y de la organización, el inicio de sesión único a través de Active Directory y el cifrado de datos en tránsito y en reposo. Los archivos se almacenan en SharePoint y utilizan el cifrado de SharePoint. Las notas se almacenan en OneNote y utilizan el cifrado de OneNote.

También hemos agregado compatibilidad con la búsqueda en el registro de auditoría, eDiscovery y la suspensión legal para los canales, los chats y los archivos, así como la administración de aplicaciones móviles con Microsoft Intune.

Estas herramientas se encuentran en el Portal de seguridad y cumplimiento de Office 365, y proporcionan las siguiente características:

-   Auditoría y generación de informes

    -   La búsqueda en el registro de auditoría se conecta directamente al Centro de seguridad y cumplimiento de Office 365, y expone la capacidad de establecer alertas y de notificar eventos de auditoría, exportar conjuntos de eventos de carga de trabajo específicos o genéricos para investigación y uso administrativo, en toda una línea de tiempo de auditoría ilimitada. Todos los datos de registro de auditoría están disponibles para la configuración de alertas en el Centro de seguridad y cumplimiento de Office 365, así como para el filtrado y la exportación para un mayor análisis.

-   Búsqueda de contenido de cumplimiento

    -   La búsqueda de contenido se puede usar para buscar en Microsoft Teams mediante capacidades avanzadas de filtrado y se puede exportar a un contenedor específico para utilizarlo en relación con el cumplimiento y los litigios. Esto se puede hacer tanto con un caso de eDiscovery como sin él.

-   eDiscovery

    -   La exhibición de documentos electrónicos es el aspecto electrónico de identificación, recolección y producción de información almacenada por medios electrónicos (ESI) en respuesta a una solicitud para la producción en una demanda legal o una investigación.

    -   Las capacidades incluyen la administración de casos, la conservación, la búsqueda, el análisis y la exportación de datos de Microsoft Teams. Esto incluye los datos de los chats, los mensajes y los archivos.

    -   Los clientes pueden aprovechar eDiscovery local o [eDiscovery avanzado](https://support.office.com/en-us/article/Office-365-Advanced-eDiscovery-fd53438a-a760-45f6-9df4-861b50161ae4).

    -   La siguiente tabla muestra las diferencias entre estos dos métodos:


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


-   Suspensión legal

    -   Cuando cualquier equipo de Microsoft Teams se pone en suspensión local o suspensión por juicio, la suspensión se pone en los buzones de los grupos.

    -   Las suspensiones legales suelen aplicarse en el contexto de un caso de eDiscovery.

La siguiente imagen muestra el flujo de trabajo de los datos de Teams en Exchange y SharePoint.

![Diagrama del flujo de trabajo de los datos de Teams en Exchange y SharePoint.](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image1.png)


> [!IMPORTANT]
> Puede haber hasta un máximo de 24 horas de retraso en la detección del contenido de Teams.

Además, Microsoft tiene pensada la probabilidad de proporcionar las siguientes características de seguridad a Microsoft Teams. Cuando estén disponibles, se proporcionarán instrucciones sobre cómo los clientes pueden aprovechar las características:

-   Directiva de retención específica de inquilinos

-   Prevención de pérdida de datos (DLP)

-   Caja de seguridad del cliente

-   Administración de derechos


| | | |
|---------|---------|---------|
|![Icono de Punto de decisión.](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image3.png)     |Punto de decisión         |¿Qué características de seguridad y cumplimiento requiere su organización? ¿Su organización tiene las licencias necesarias para cumplir con los requisitos empresariales de seguridad y cumplimiento?         |
|![Icono de Siguientes pasos.](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image4.png)     |Siguientes pasos         |Documente las características requeridas de seguridad y cumplimiento en la tabla siguiente.         |

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
\*El acceso condicional requiere licencias adicionales


| |  |  |
|---------|---------|---------|
|![Icono de Punto de decisión.](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image3.png)     |Punto de decisión         |¿Su organización tiene las licencias necesarias para cumplir con los requisitos empresariales de seguridad y cumplimiento?         |
|![Icono de Siguientes pasos.](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image4.png)    |Siguientes pasos         |Revise las licencias actuales de su organización y confirme si cumplen todos los requisitos empresariales de cumplimiento y seguridad.         |

Antes de habilitar alguna de estas características, asegúrese de que tiene acceso al Centro de seguridad y cumplimiento en el Centro de administración de Office 365. De manera predeterminada, los administradores de inquilinos tienen acceso.

La búsquedas de contenido y eDiscovery no necesitan estar habilitadas en el Centro de seguridad y cumplimiento.

<a name="location-of-data-in-microsoft-teams"></a>Ubicación de los datos en Microsoft Teams
-----------------------------------

Los datos de Microsoft Teams se encuentran en la región según la afinidad de los inquilinos. Actualmente, Microsoft Teams admite las regiones de América, EMEA y APAC. 

Desde el 1 de noviembre de 2017, Teams ofrece residencia de datos en Reino Unido solo para los nuevos inquilinos. Un nuevo inquilino se define como cualquier inquilino que no ha tenido ningún usuario desde el inicio de sesión del inquilino en Microsoft Teams.

> [!NOTE]
> Los inquilinos existentes del Reino Unido seguirán en EMEA hasta que se publique un plan de migración (que está previsto para 2018).

Si desea más información, consulte la [entrada de blog](https://go.microsoft.com/fwlink/p/?linkid=862275) de la comunidad tecnológica de Microsoft Teams.

<a name="privacy-in-microsoft-teams"></a>Privacidad en Microsoft Teams
--------------------------

Como cliente de Office 365, el usuario posee y controla sus propios datos. Microsoft no usa los datos para ninguna otra finalidad que proporcionarle el servicio para el que se ha suscrito. Como proveedores de servicios, no examinamos el correo electrónico, los documentos o los equipos para enviar publicidad o para otras finalidades que no estén relacionadas con el servicio. Microsoft no tiene acceso al contenido cargado. Tal como ocurre en OneDrive para la Empresa y SharePoint Online, los datos de los clientes permanecen en el inquilino.

Consulte más detalles sobre nuestra información de confianza y seguridad en el [*Centro de confianza de Office 365*](https://go.microsoft.com/fwlink/?linkid=855779). Microsoft Teams sigue los mismos principios y directrices que el Centro de confianza de Office 365.
