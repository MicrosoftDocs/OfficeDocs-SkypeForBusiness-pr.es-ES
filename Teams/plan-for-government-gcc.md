---
title: Plan para Microsoft 365 Administración Pública - Implementaciones de GCC - Microsoft Teams
author: lolajacobsen
ms.author: lehewe
manager: serdars
ms.date: 01/03/2019
ms.topic: article
ms.service: msteams
ms.reviewer: daro
description: Instrucciones para los profesionales de TI a las implementaciones de Office 365 de unidad en las entidades que controlan datos sujetas a regulación gubernamental de EE.
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.openlocfilehash: fcdad8bfbcb873a84d03ec6c0048e4fe49cd5467
ms.sourcegitcommit: 327fe807b461aff18b06449f06b9e51ce393c4bc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/12/2019
ms.locfileid: "29964421"
---
# <a name="plan-for-microsoft-365-government---gcc-deployments"></a>Planeación de Microsoft 365 gobierno - implementaciones GCC

Esta guía es para los profesionales de TI que están llevando a las implementaciones de Office 365 en federal de Estados Unidos, estado, las entidades de gobierno local, tribal o territoriales u otras entidades que controlan los datos que estén sujetos a reglamentaciones gubernamentales y los requisitos, donde el uso de Microsoft Gobierno 365 - GCC es adecuado para cumplir estos requisitos.

> [!NOTE]
> Si su organización ya tiene cumplen el gobierno de 365 Microsoft - requisitos de idoneidad GCC y para aplicar y se han aceptado en el programa, puede omitir los pasos 1 y 2 y vaya directamente al paso 3. 

## <a name="step-1-determine-whether-your-organization-needs-microsoft-365-government---gcc-and-meets-eligibility-requirements"></a>Paso 1. Determinar si la organización necesita Microsoft 365 gobierno - GCC y que cumpla los requisitos de idoneidad. 

El gobierno de Microsoft 365 - entorno GCC proporciona cumplimiento con US los requisitos de gobierno para servicios de nube, incluyendo FedRAMP moderadas y los requisitos de Justicia penal y sistemas de información de impuesto federal (tipos de datos CJI y FTI).

Además de disfrutar de las características y capacidades de Office 365, las organizaciones se benefician de las siguientes características que son exclusivas de Microsoft 365 gobierno - GCC:

-   Contenido de la organización del cliente se aísla lógicamente del contenido del cliente en los servicios de Office 365 comerciales de Microsoft.
-   Contenido de la organización del cliente se almacena dentro de Estados Unidos.
-   Acceso al contenido de la organización del cliente está restringido al personal de Microsoft protegido.
-   Gobierno de Microsoft 365 - GCC cumple con certificaciones y acreditaciones que son necesarios para clientes del Sector público con nosotros.

Puede encontrar más información sobre el gobierno de 365 Microsoft - GCC que ofrece para los clientes de gobierno de Estados Unidos en [que planes de gobierno de Office 365](https://products.office.com/government/compare-office-365-government-plans), incluidos [los requisitos de idoneidad](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements).

La [Descripción del servicio de gobierno de Estados Unidos de Office 365](https://technet.microsoft.com/library/mt774581.aspx) describe las ventajas de la plataforma, que se centran en cumplimiento de requisitos dentro de los Estados Unidos.

> [!Tip]
> Es posible que desee transferir las tablas de información en la descripción del servicio a un libro de Excel y agregue dos columnas: **pertinente para mi organización Y o N** y **satisfaga las necesidades de mi organización Y o N**. A continuación, puede revisar esta lista con sus compañeros para confirmar que este servicio satisface las necesidades de su organización.

|    |     |
|-----------|------------|
| ![](media/audio_conferencing_image7.png) <br/>Puntos de decisión|<ul><li>Decidir si Microsoft 365 gobierno - GCC es adecuada para su organización.</li><li>Confirme que la organización cumpla con los requisitos de idoneidad.</li></ul> |

> [!Note]
> Gobierno de Microsoft 365 - GCC sólo está disponible en los Estados Unidos. Los clientes de gobierno de los EE: no pueden elegir entre un número de [planes de gobierno de Office 365](https://products.office.com/en/government/compare-office-365-government-plans).


## <a name="step-2-apply-for-microsoft-365-government---gcc"></a>Paso 2. Aplicar para Microsoft 365 gobierno - GCC

Tener decidido que este servicio es el adecuado para su organización, iniciar el proceso de la [aplicación para este servicio aquí](https://products.office.com/government/eligibility-validation).

## <a name="step-3-understand-microsoft-365-government---gcc-default-security-settings"></a>Paso 3. Descripción de Microsoft 365 gobierno - configuración de seguridad predeterminada GCC.

Se recomienda que tenga tiempo para revisar detenidamente la [configuración de administración y seguridad](enable-features-office-365.md) antes de modificarlos y considere la posibilidad de impactos en cumplimiento antes de realizar cualquier cambio en la configuración de seguridad predeterminada.

|    |     |
|-----------|------------|
| ![](media/audio_conferencing_image7.png) <br/>Puntos de decisión|<ul><li>Decidir si va modificar cualquiera del valor predeterminado de Microsoft 365 gobierno - configuración de seguridad GCC, resolver en primer lugar comprender el impacto de los cambios que es posible que realice.</li></ul> |

## <a name="step-4-understand-which-capabilities-are-currently-unavailable-or-disabled-by-default"></a>Paso 4. Comprender las características que actualmente no están disponibles o deshabilitados de forma predeterminada. 

Para dar cabida a los requisitos de nuestros clientes de nube de gobierno, existen algunas diferencias entre Microsoft 365 gobierno - GCC y planes de empresa. Hacer referencia a la tabla siguiente para ver las características que están disponibles.

|                             | Característica                     | GCC            |
|-----------------------------|-----------------------------|----------------|
| Base | Inicio de sesión | Disponible |
| | Presencia | Disponible |
| | Presencia unificada (Skype para profesionales y los equipos unificados) | Disponible |
| Actividad | Fuente | Disponible |
|  | Mi actividad | Disponible |
| Chat | Conversación | Disponible |
| | Archivos | Disponible |
| | Organigrama | Disponible |
| | Actividad | Disponible |
| | Interoperabilidad (1:1 los equipos-Skype para chat empresarial) | Disponible |
| Microsoft Teams | Mensaje de canal | Disponible |
| | Archivos de canal | Disponible |
| | Ficha de OneNote | En el trabajo pendiente del gobierno |
| | Un canal de correo electrónico | No disponible |
| | Agregar miembros | Disponible |
| | Acceso de invitado | Disponible |
| Reuniones | Programar reunión | Disponible |
| | Unirse a la reunión | Disponible |
| | Reunión de VoIP | Disponible |
| | Compartir escritorio | Disponible |
| | Dar y tomar control de uso compartido | Disponible |
| | Conectar desde una sala de conferencias | Disponible |
| | Unión anónima | Disponible |
| | Grabación de nube | En el trabajo pendiente del gobierno |
| | Notas de la reunión | Disponible |
| | Difusión de presentaciones de reuniones | En el trabajo pendiente del gobierno |
| | Reuniones federadas | Disponible |
| | Compatibilidad de concentradores de superficie (vista previa) | Disponible |
| Llamadas | Contactos | Disponible |
| | Historial de | Disponible |
| | Correo de voz | Disponible |
| | Llamada de VoIP | Disponible |
| | Skype para la empresa - equipos de llamada | Disponible |
| | Planes de llamadas | Disponible |
| | Conferencias de audio (permitiendo que los participantes de la reunión para unirse a través de RTC) | Disponible |
| | Enrutamiento directo de sistema telefónico de Microsoft | Disponible |
| | Sala de espera para los autores de llamadas de RTC | Disponible |
| | Cola de llamada | Disponible |
| | Compatibilidad con el jefe y delegado | Disponible |
| | Transferencia de consultoría y segura | Disponible |
| | No molestar innovadora | Disponible |
| | Timbre distintivo | Disponible |
| | 1:1 a la extensión de la llamada de grupo con los equipos de Skype para la empresa y los participantes de RTC | Disponible |
| | Reenviar a grupo | Disponible |
| | Transferir a la llamada de RTC | Disponible |
| | Llamadas de emergencia - planes de llamada | Disponible |
| | Soporte técnico para los teléfonos SIP certificados existentes | Disponible |
| | USB HID | Disponible |
| | exhibición de documentos electrónicos para las llamadas y las reuniones | Disponible |
| | Operador automático de organización | Disponible |
| | Consumidor de Skype - compatibilidad con llamadas de los equipos | Disponible |
| Archivos | Recientes | Disponible |
| | Microsoft Teams | Disponible |
| Almacén | Tienda de aplicaciones | En el trabajo pendiente del gobierno |
| Búsqueda | Mensajes | Disponible |
| | Personas | Disponible |
| | Archivos | Disponible |
| | Comandos de barra diagonal | Disponible |
| Cumplimiento de normas | Búsqueda de contenido de cumplimiento | Disponible |
| | Retención | Disponible |
| | Búsqueda de registro de auditoría | Disponible |
| | Retención legal | Disponible |
| | eDiscovery | Disponible |

> [!Note]

> Una vez que están completamente disponibles otras cargas de trabajo en la nube GCC, a continuación, estarán disponibles en los equipos cuando se complete todo el trabajo de integración adicional.


|    |     |
|-----------|------------|
| ![](media/audio_conferencing_image7.png) <br/>Puntos de decisión|<ul><li>Decidir si el conjunto de características de los equipos cumple las necesidades de su organización.</li></ul> |

## <a name="step-5-plan-for-governance"></a>Paso 5. Plan de gobierno

Determinar los requisitos para el gobierno y cómo puede cumplirlos. Para obtener más información, vaya a la [planeación de gobierno en los equipos](plan-teams-governance.md) .

|    |     |
|-----------|------------|
| ![](media/audio_conferencing_image7.png) <br/>Puntos de decisión|<ul><li>Determinar y documentar los requisitos de gobierno, siga las instrucciones en el [Plan de gobierno en los equipos](plan-teams-governance.md).</li></ul> |

## <a name="step-6-deploy-teams-for-collaboration"></a>Paso 6. Implementación de los equipos para colaboración

Una vez que se ha estado onboarded a Microsoft 365 gobierno - GCC, puede seguir el enfoque de implementación estándar de usar [FastTrack](https://www.microsoft.com/fasttrack) y su socio elegido incorporado para el servicio.

Cuando esté listo, implemente los equipos para [Permitir la colaboración dentro de la organización a través de los equipos y los canales](teams-overview.md). Asegúrese de integrarse con su equipo de adopción y administración de cambios o Campeones de los equipos.

## <a name="step-7-deploy-teams-for-meetings-and-voice"></a>Paso 7. Implementación de los equipos para las reuniones y voz

También es un buen momento para usar los equipos con el grupo más amplio de los participantes para empezar a planear para implantar las reuniones y [las características de voz en la nube](cloud-voice-deployment.md).

