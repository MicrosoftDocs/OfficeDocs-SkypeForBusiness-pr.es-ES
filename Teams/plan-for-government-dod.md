---
title: Plan para Microsoft 365 Administración Pública - Implementaciones de DoD - Microsoft Teams
author: lolajacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: daro
audience: admin
description: Instrucciones para los profesionales de TI para impulsar implementaciones de Office 365 en entidades que controlan datos sujetos a la normativa DoD de Estados Unidos.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9e5031c804242f2927a5fe9f2521682d736d034a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038122"
---
# <a name="plan-for-microsoft-365-government---dod-deployments"></a>Plan para implementaciones de Microsoft 365 administración pública

Esta guía está orientada a los profesionales de ti que están implantando implementaciones de Office 365 en entidades de gobierno federal de los Estados Unidos u otras entidades que tratan datos que están sujetos a los requisitos y las reglamentaciones gubernamentales, donde el uso de Microsoft 365 Government-DoD es adecuado para cumpla con estos requisitos.

> [!NOTE]
> Si su organización ya cumple con los requisitos de elegibilidad de los DoD de Microsoft 365, y ha sido solicitado y ha sido aceptado en el programa, puede omitir los pasos 1 y 2 y ir directamente al paso 3.

## <a name="step-1-determine-whether-your-organization-needs-microsoft-365-government---dod-and-meets-eligibility-requirements"></a>Paso 1. Determine si su organización necesita Microsoft 365 gobierno-DoD y cumple con los requisitos de elegibilidad. 

El entorno Microsoft 365 Government-DoD ofrece cumplimiento de los requisitos del gobierno de los Estados Unidos para servicios en la nube. Además de disfrutar de las características y capacidades de Office 365, las organizaciones se benefician de las siguientes características que son exclusivas de Microsoft 365 administración pública: DoD:

- El contenido del cliente de su organización se separa lógicamente del contenido del cliente en los servicios comerciales de Office 365 de Microsoft.
- El contenido de los clientes de su organización se almacena dentro de los Estados Unidos.
- El acceso al contenido de los clientes de su organización está restringido al personal de Microsoft de la pantalla.
- Microsoft 365 Government – DoD cumple con las certificaciones y acreditaciones necesarias para los clientes del sector público de los Estados Unidos.

Puede encontrar más información sobre la oferta de administración pública de Microsoft 365, para clientes del gobierno de los Estados Unidos en [Office 365 planes gubernamentales](https://products.office.com/government/compare-office-365-government-plans), incluidos [los requisitos de elegibilidad](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements).

La [Descripción del servicio del gobierno de Office 365 Estados](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) Unidos describe los beneficios de la plataforma, que están centrados en cumplir los requisitos de cumplimiento de las normas de los Estados Unidos.


> [!Tip]
> Es posible que desee transferir las tablas de información de la descripción del servicio a un libro de Excel y agregar dos columnas: **relevante para mi organización y/n** y **satisface las necesidades de mi organización y/n**. Después, puede revisar esta lista con sus colegas para confirmar que este servicio cumple con las necesidades de su organización.


|    |     |
|-----------|------------|
| ![Un icono que representa los puntos de decisión](media/audio_conferencing_image7.png) <br/>Puntos de decisión|<ul><li>Decida si Microsoft 365 Government-DoD es adecuado para su organización.</li><li>Confirme que su organización cumple con los requisitos de elegibilidad.</li></ul> |

> [!Note]
> Microsoft 365 Government-DoD solo está disponible en los Estados Unidos. Los clientes que no sean Estados Unidos pueden elegir entre varios [planes de Office 365 administración pública](https://products.office.com/en/government/compare-office-365-government-plans).

## <a name="step-2-apply-for-microsoft-365-government---dod"></a>Paso 2. Solicitar Microsoft 365 administración pública-DoD

Tras haber decidido que este servicio es adecuado para su organización, inicie el proceso de [solicitud de este servicio](https://products.office.com/government/eligibility-validation).


## <a name="step-3-understand-microsoft-365-government---dod-default-security-settings"></a>Paso 3. Comprender la configuración de seguridad predeterminada de Microsoft 365 administración pública.

Le recomendamos que tome el tiempo de revisar detenidamente la [configuración de administrador y seguridad](enable-features-office-365.md) antes de modificarla, y considere la posibilidad de repercusiones en el cumplimiento antes de realizar cambios en la configuración de seguridad predeterminada.

|    |     |
|-----------|------------|
| ![Un icono que muestra un punto de decisión](media/audio_conferencing_image7.png) <br/>Punto de decisión|<ul><li>Decida si necesita modificar cualquiera de los valores predeterminados de la configuración de seguridad de Microsoft 365 gubernamentales-DoD, resolviendo primero el impacto de los cambios que puede realizar.</li></ul> |


## <a name="step-4-understand-which-teams-capabilities-are-currently-available-in-microsoft-365-government---dod"></a>Paso 4. Comprender qué capacidades de Teams están disponibles actualmente en Microsoft 365 gobierno-DoD

Para cumplir con los requisitos de nuestros clientes gubernamentales de la nube, existen algunas diferencias entre los equipos de Microsoft 365 gubernamentales-DoD y los equipos de los planes empresariales. Consulte la tabla siguiente para ver qué características están disponibles.

|                             | Característica                     | Requisito       |
|-----------------------------|-----------------------------|----------------|
| Básica | Inicio de sesión | Disponible |
| | Presence | Disponible |
| | Presencia unificada (Skype empresarial y equipos unificados) | En el trabajo pendiente del gobierno |
| Actividades | Suministros | Disponible |
|  | Mi actividad | Disponible |
| Chat | Llamada | Disponible |
| | Archivos | Disponible |
| | Organigrama | Disponible |
| | Actividades | Disponible |
| | Interoperabilidad (1:1 equipos-conversación de Skype empresarial) | En el trabajo pendiente del gobierno |
| Teams | Mensaje de canal | Disponible |
| | Archivos de canal | Disponible |
| | Pestaña OneNote | En el trabajo pendiente del gobierno |
| | Enviar por correo electrónico un canal | No disponible |
| | Agregar miembro | Disponible |
| | Acceso de invitado | En el trabajo pendiente del gobierno |
| Reuniones | Programar reunión | Disponible |
| | Unirse a la reunión | Disponible |
| | Reunión de VoIP | Disponible |
| | Compartir escritorio | Disponible |
| | Conceder y tomar el control en el uso compartido | Disponible |
| | Conectarse desde una sala de conferencias | Disponible |
| | Grabación en la nube | En el trabajo pendiente del gobierno |
| | Notas de la reunión | Disponible |
| | Reuniones de difusión | En el trabajo pendiente del gobierno |
| | Reuniones federadas (DoD a DoD) dentro de la nube | Disponible |
| | Compatibilidad con Surface Hub | En el trabajo pendiente del gobierno |
| Llamadas | Contactos | Disponible |
| | Suprimi | Disponible |
| | Correo de voz | Disponible |
| | Llamada de VoIP | Disponible |
| | Skype empresarial: llamadas de equipo | Disponible |
| | Planes de llamadas | No disponible |
| | Audioconferencias (al permitir que los participantes de la reunión se unan a través de RTC) | Disponible |
| | Enrutamiento directo de Microsoft Phone System | En el trabajo pendiente del gobierno |
| | Sala de llamadas RTC | En el trabajo pendiente del gobierno |
| | Cola de llamadas | En el trabajo pendiente del gobierno |
| | Soporte de los jefes y los delegados | En el trabajo pendiente del gobierno |
| | Las transferencias consultiva y segura | En el trabajo pendiente del gobierno |
| | No molestar en el avance | En el trabajo pendiente del gobierno |
| | Timbre distintivo | En el trabajo pendiente del gobierno |
| | 1:1 a escalado de llamadas grupales con equipos, Skype empresarial y participantes de la RTC | En el trabajo pendiente del gobierno |
| | Reenviar al grupo | En el trabajo pendiente del gobierno |
| | Transferir a llamada RTC | En el trabajo pendiente del gobierno |
| | Planes de llamadas de emergencia | En el trabajo pendiente del gobierno |
| | Compatibilidad con los teléfonos SIP certificados existentes | En el trabajo pendiente del gobierno |
| | HID USB | Disponible |
| | eDiscovery para las llamadas y las reuniones | Disponible |
| | Operador automático de la organización | En el trabajo pendiente del gobierno |
| | Consumidor de Skype-asistencia para llamadas de equipo | No disponible |
| Archivos | Recientes | Disponible |
| | Microsoft Teams | Disponible |
| Guarde | App Store | No disponible |
| Búsqueda | Mensajes | Disponible |
| | Personas | Disponible |
| | Archivos | Disponible |
| | Comandos de barra diagonal | Disponible |
| Respeto | Búsqueda de contenido de cumplimiento | Disponible |
| | Policy | Disponible |
| | Búsqueda de registros de auditoría | Disponible |
| | Retención legal | Disponible |
| | eDiscovery | Disponible |

|    |     |
|-----------|------------|
| ![Un icono que muestra un punto de decisión](media/audio_conferencing_image7.png) <br/>Punto de decisión|<ul><li>Decida si el conjunto de características de Teams cumple con las necesidades de su organización.</li></ul> |

## <a name="step-5-plan-for-governance"></a>Paso 5. Planear la gobernanza

Determina los requisitos de gobierno y cómo puedes reunirse. Para obtener más información, vaya a [plan de gobierno en Teams](plan-teams-governance.md) .

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting a decision point"/>|Punto de decisión |<ul><li>Determine y documente sus requisitos de gobierno, siguiendo las pautas de [Plan for Governance in Teams](plan-teams-governance.md). </li></ul>|

## <a name="step-6-deploy-teams-for-collaboration"></a>Paso 6. Implementar Teams para la colaboración

Después de que se haya incorporado a Microsoft 365 Government, consulte la ruta de implementación recomendada que se describe en [cómo implementar Microsoft Teams](How-to-roll-out-teams.md). Asegúrese de participar en el equipo de administración de cambios y la adopción y en los expertos de Teams.

También puede trabajar con [FastTrack](https://www.microsoft.com/fasttrack) o con su socio elegido para incorporar el servicio.
