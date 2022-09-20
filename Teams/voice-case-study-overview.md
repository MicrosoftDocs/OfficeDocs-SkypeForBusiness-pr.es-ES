---
title: Información general del caso de estudio de voz de Contoso de Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365solution-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: 'Caso práctico de voz de Teams para corporación multinacional: Introducción a la migración de voz'
appliesto:
- Microsoft Teams
ms.openlocfilehash: ae0d123841e57987346fae304e34bde28e4ffe84
ms.sourcegitcommit: 6754f2d11da0afff067f0872acf778a83fd1595e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/19/2022
ms.locfileid: "67808631"
---
# <a name="contoso-case-study-teams-voice-migration-overview"></a>Caso práctico de Contoso: Introducción a la migración de voz de Teams

En este artículo se presenta un caso práctico sobre cómo una corporación multinacional ficticia, Contoso, implementó una solución de voz de Teams para su organización.

Contoso ha implementado Microsoft 365 Enterprise y abordado las principales decisiones de diseño y detalles de implementación para lo siguiente: redes, identidad, Windows 10 Enterprise, Office 365 ProPlus, administración de dispositivos móviles, protección de la información, seguridad, actualización desde Skype Empresarial a Teams, Sistema telefónico y Audioconferencia.  

Este artículo se centra en cómo Contoso migró sus usuarios locales a Teams para la comunicación unificada, la colaboración y la voz. Para obtener información general sobre cómo Contoso aceleró su transformación digital mediante los servicios en la nube de Microsoft, consulte todos los artículos principales que comienzan con la [información general del caso práctico de Contoso](/microsoft-365/enterprise/contoso-case-study).

[https://learn.microsoft.com/microsoft-365/enterprise/contoso-case-study](/microsoft-365/enterprise/contoso-case-study) 

En los artículos principales, encontrará información sobre lo siguiente:  

- Necesidades de infraestructura de TI de Contoso
- Redes
- Identidad
- Windows 10 Enterprise
- Office 365 Pro Plus
- Administración de dispositivos móviles
- Protección de la información
- Resumen de la seguridad de Microsoft 365 Enterprise
- Equipo para un proyecto de alto secreto
- Sitio de SharePoint Online para activos digitales altamente confidenciales

Para obtener información sobre cómo planear una actualización, le interesará empezar con [Introducción a la actualización de Microsoft Teams](upgrade-start-here.md).

## <a name="contoso-business-goals-for-teams"></a>Objetivos empresariales de Contoso para Teams

Para migrar sus usuarios locales a Teams para una comunicación unificada, colaboración y voz, Contoso decidió los siguientes objetivos empresariales:

- Habilitación de Teams 

  El equipo de colaboración y comunicación unificado de Contoso habilitó Teams con las directivas correctas para gobernar y habilitar la colaboración interna y externa segura. 

- Actualización de Skype Empresarial a Microsoft Teams 

  Skype Empresarial se ha implementado ampliamente en Contoso. Con la necesidad de desconectar los sistemas heredados, Contoso decidió actualizar sus usuarios de Skype Empresarial a Teams. Para obtener más información, consulte [Caso práctico de Contoso: Plan de actualización de Teams](voice-case-study-migration-plan.md).

- Sistema telefónico  

  Skype Empresarial con la voz empresarial se implementó ampliamente en Contoso. Con la necesidad de desactivar sistemas heredados que eran el próximo salto para sus servidores de mediación, Contoso migró sus usuarios de voz empresariales Skype Empresarial a Phone System. Los sitios de Contoso usaban Plan de llamadas de Microsoft, Enrutamiento directo del sistema telefónico o una combinación de ambos. Para obtener más información, consulte [Caso práctico de Contoso: Sistema telefónico](voice-case-study-phone-system.md).

- Enrutamiento basado en ubicación 

  Con las ubicaciones de oficina en países regulados por la telefonía, Contoso necesitaba volver a crear el enrutamiento de Location-Based que estaba presente en Skype Empresarial en su implementación del sistema telefónico. Para obtener más información, consulte [caso práctico de Contoso: enrutamiento Location-Based](voice-case-study-location-based-routing.md).

- Llamadas de emergencia 

  Cuando se implementó enrutamiento directo, Contoso configuró las llamadas de emergencia con terceros aprobados. Para obtener más información, consulte [Caso práctico de Contoso: Llamadas de emergencia](voice-case-study-emergency-calling.md).

- Audioconferencia 

  Contoso configuró los números de servicio de Audioconferencia hospedados en su tronco SIP en su proveedor de RTC. Para obtener más información, consulte [Caso práctico de Contoso: Audioconferencia](voice-case-study-audio-conferencing.md). 

- Optimización de medios locales 

  Contoso ha aprovechado la optimización de medios locales en ubicaciones donde tenían un tronco de ruta directa a Microsoft Phone System que fueron aprovechados por sitios remotos. Para obtener más información, consulta [Planear la optimización de medios locales](direct-routing-media-optimization.md) y [Configurar la optimización de medios locales](direct-routing-media-optimization-configure.md).

- Operadores automáticos y colas de llamadas

  Como resultado de Covid-19, Contoso quería proporcionar soporte de recepcionista mientras su personal trabajaba de forma remota. Contoso usó operadores automáticos y colas de llamadas para administrar las llamadas entrantes al número de teléfono de su recepcionista. Para obtener más información, consulte [caso práctico de Contoso: Operadores automáticos y colas de llamadas](voice-case-study-call-queues.md).
