---
title: Plan para Microsoft 365 Administración Pública - Implementaciones de GCC - Microsoft Teams
author: lolajacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: daro
audience: admin
description: Instrucciones para los profesionales de TI para impulsar implementaciones de Office 365 en entidades que controlan datos sujetos a la normativa del gobierno de Estados Unidos
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e4228210fa7b6d9518fa060b2bdd555f434ed6f2
ms.sourcegitcommit: dc240b123efb03d5ab0545d650a973bf60d04506
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/17/2019
ms.locfileid: "40069311"
---
# <a name="plan-for-microsoft-365-government---gcc-deployments"></a>Plan para implementaciones de Microsoft 365 administración pública-GCC

Esta guía está orientada a los profesionales de ti que están implantando implementaciones de Office 365 en Estados Unidos federales, estatales, locales, tribal o territoriales entidades gubernamentales u otras entidades que administran datos que están sujetos a reglamentaciones y requisitos gubernamentales, donde el uso de Microsoft 365 gubernamental: GCC es adecuado para cumplir con estos requisitos.

> [!NOTE]
> Si su organización ya cumple con los requisitos de idoneidad de Microsoft 365 Government-GCC y ha sido aplicado y ha sido aceptado en el programa, puede omitir los pasos 1 y 2 y ir directamente al paso 3. 

## <a name="step-1-determine-whether-your-organization-needs-microsoft-365-government---gcc-and-meets-eligibility-requirements"></a>Paso 1. Determine si su organización necesita Microsoft 365 pública-GCC y cumple con los requisitos de elegibilidad. 

El entorno Microsoft 365 Government-GCC ofrece cumplimiento de los requisitos del gobierno de los Estados Unidos para servicios en la nube, incluidos los FedRAMP moderados, y requisitos para los sistemas de información de la justicia y los impuestos federales (CJI y FTI tipos de datos).

Además de disfrutar de las características y capacidades de Office 365, las organizaciones se benefician de las siguientes características que son exclusivas de Microsoft 365 administración pública-GCC:

-   El contenido del cliente de su organización se separa lógicamente del contenido del cliente en los servicios comerciales de Office 365 de Microsoft.
-   El contenido de los clientes de su organización se almacena dentro de los Estados Unidos.
-   El acceso al contenido de los clientes de su organización está restringido al personal de Microsoft de la pantalla.
-   Microsoft 365 Government-GCC cumple con las certificaciones y acreditaciones necesarias para los clientes del sector público de los Estados Unidos.

Puede encontrar más información sobre la oferta de Microsoft 365 administración pública-GCC para clientes del gobierno de los Estados Unidos en [Office 365 planes gubernamentales](https://products.office.com/government/compare-office-365-government-plans), incluidos [los requisitos de elegibilidad](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements).

La [Descripción del servicio del gobierno de Office 365 Estados](https://technet.microsoft.com/library/mt774581.aspx) Unidos describe los beneficios de la plataforma, que se centran en los requisitos de cumplimiento de las reuniones de los Estados Unidos.

> [!Tip]
> Es posible que desee transferir las tablas de información de la descripción del servicio a un libro de Excel y agregar dos columnas: **relevante para mi organización y/n** y **satisface las necesidades de mi organización y/n**. Después, puede revisar esta lista con sus colegas para confirmar que este servicio cumple con las necesidades de su organización.

|    |     |
|-----------|------------|
| ![Un icono que representa los puntos de decisión](media/audio_conferencing_image7.png) <br/>Puntos de decisión|<ul><li>Decida si Microsoft 365 Government-GCC es adecuado para su organización.</li><li>Confirme que su organización cumple con los requisitos de elegibilidad.</li></ul> |

> [!Note]
> Microsoft 365 Government-GCC solo está disponible en los Estados Unidos. Los clientes que no sean Estados Unidos pueden elegir entre varios [planes de Office 365 administración pública](https://products.office.com/en/government/compare-office-365-government-plans).


## <a name="step-2-apply-for-microsoft-365-government---gcc"></a>Paso 2. Solicitar Microsoft 365 administración pública-GCC

Tras haber decidido que este servicio es adecuado para su organización, aquí tiene que iniciar el proceso de [solicitar este servicio](https://products.office.com/government/eligibility-validation).

## <a name="step-3-understand-microsoft-365-government---gcc-default-security-settings"></a>Paso 3. Comprender la configuración de seguridad predeterminada de Microsoft 365 Government-GCC.

Le recomendamos que tome el tiempo de revisar detenidamente la [configuración de administrador y seguridad](enable-features-office-365.md) antes de modificarla, y considere la posibilidad de repercusiones en el cumplimiento antes de realizar cambios en la configuración de seguridad predeterminada.

|    |     |
|-----------|------------|
| ![Un icono que muestra un punto de decisión](media/audio_conferencing_image7.png) <br/>Punto de decisión|<ul><li>Decida si modificará cualquiera de los valores de seguridad predeterminados de Microsoft 365 administración pública-GCC y se resolverá para comprender primero el impacto de los cambios que puede realizar.</li></ul> |

## <a name="step-4-understand-which-capabilities-are-currently-unavailable-or-disabled-by-default"></a>Paso 4. Comprender qué características no están disponibles o deshabilitadas de forma predeterminada. 

Para cumplir con los requisitos de nuestros clientes gubernamentales en la nube, existen algunas diferencias entre los planes de Microsoft 365 gubernamentales-GCC y Enterprise. Consulte la tabla siguiente para ver qué características están disponibles.

|                             | Característica                     | GCC            |
|-----------------------------|-----------------------------|----------------|
| Básica | Inicio de sesión | Disponible |
| | Presence | Disponible |
| | Presencia unificada (Skype empresarial y equipos unificados) | Disponible |
| Actividades | Suministros | Disponible |
|  | Mi actividad | Disponible |
| Chat | Llamada | Disponible |
| | Archivos | Disponible |
| | Organigrama | Disponible |
| | Actividades | Disponible |
| | Interoperabilidad (1:1 equipos-conversación de Skype empresarial) | Disponible |
| Teams | Mensaje de canal | Disponible |
| | Archivos de canal | Disponible |
| | Pestaña OneNote | En el trabajo pendiente del gobierno |
| | Enviar por correo electrónico un canal | No disponible |
| | Agregar miembro | Disponible |
| | Acceso de invitado | Disponible |
| Reuniones | Programar reunión | Disponible |
| | Unirse a la reunión | Disponible |
| | Reunión de VoIP | Disponible |
| | Compartir escritorio | Disponible |
| | Conceder y tomar el control en el uso compartido | Disponible |
| | Conectarse desde una sala de conferencias | Disponible |
| | Unirse anónimamente | Disponible |
| | Grabación en la nube | Disponible |
| | Notas de la reunión | Disponible |
| | Eventos en directo | Disponible |
| | Reuniones federadas | Disponible |
| | Compatibilidad con Surface Hub | Disponible |
| Llamadas | Contactos | Disponible |
| | Suprimi | Disponible |
| | Correo de voz | Disponible |
| | Llamada de VoIP | Disponible |
| | Skype empresarial: llamadas de equipo | Disponible |
| | Planes de llamadas | Disponible |
| | Audioconferencias (al permitir que los participantes de la reunión se unan a través de RTC) | Disponible |
| | Enrutamiento directo de Microsoft Phone System | Disponible |
| | Sala de llamadas RTC | Disponible |
| | Cola de llamadas | Disponible |
| | Soporte de los jefes y los delegados | Disponible |
| | Las transferencias consultiva y segura | Disponible |
| | No molestar en el avance | Disponible |
| | Timbre distintivo | Disponible |
| | 1:1 a escalado de llamadas grupales con equipos, Skype empresarial y participantes de la RTC | Disponible |
| | Reenviar al grupo | Disponible |
| | Transferir a llamada RTC | Disponible |
| | Planes de llamadas de emergencia | Disponible |
| | Compatibilidad con los teléfonos SIP certificados existentes | Disponible |
| | HID USB | Disponible |
| | eDiscovery para las llamadas y las reuniones | Disponible |
| | Operador automático de la organización | Disponible |
| | Consumidor de Skype-asistencia para llamadas de equipo | Disponible |
| Archivos | Recientes | Disponible |
| | Microsoft Teams | Disponible |
| Guarde | App Store | En el trabajo pendiente del gobierno |
| Búsqueda | Mensajes | Disponible |
| | Personas | Disponible |
| | Archivos | Disponible |
| | Comandos de barra diagonal | Disponible |
| Respeto | Búsqueda de contenido de cumplimiento | Disponible |
| | Policy | Disponible |
| | Búsqueda de registros de auditoría | Disponible |
| | Retención legal | Disponible |
| | eDiscovery | Disponible |

> [!Note]

> Una vez que otras cargas de trabajo estén completamente disponibles en la nube de GCC, estarán disponibles en Teams cuando se complete todo el trabajo de integración adicional.


|    |     |
|-----------|------------|
| ![Un icono que muestra un punto de decisión](media/audio_conferencing_image7.png) <br/>Punto de decisión|<ul><li>Decida si el conjunto de características de Teams cumple con las necesidades de su organización.</li></ul> |

## <a name="step-5-plan-for-governance"></a>Paso 5. Planear la gobernanza

Determina los requisitos de gobierno y cómo puedes reunirse. Para obtener más información, vaya a [plan de gobierno en Teams](plan-teams-governance.md) .

|    |     |
|-----------|------------|
| ![Un icono que muestra un punto de decisión](media/audio_conferencing_image7.png) <br/>Punto de decisión|<ul><li>Determine y documente sus requisitos de gobierno, siguiendo las pautas de [Plan for Governance in Teams](plan-teams-governance.md).</li></ul> |

## <a name="step-6-deploy-teams-for-collaboration"></a>Paso 6. Implementar Teams para la colaboración

Después de que se haya incorporado a Microsoft 365 administración pública – GCC, siga la ruta de implementación recomendada, [que se describe en cómo implementar Microsoft Teams](How-to-roll-out-teams.md). Asegúrese de participar en el equipo de administración de cambios y la adopción y en los expertos de Teams.

También puede trabajar con [FastTrack](https://www.microsoft.com/fasttrack) o con su socio elegido para incorporar el servicio.

## <a name="step-7-deploy-teams-for-meetings-and-voice"></a>Paso 7. Implementar equipos para reuniones y voz

Este es también un buen momento para usar Teams con su grupo más amplio de participantes para empezar a planear la implementación de reuniones y [características de voz en la nube](cloud-voice-deployment.md).

