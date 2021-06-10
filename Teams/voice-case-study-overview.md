---
title: Teams caso práctico de Contoso de voz
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
description: Teams caso de voz para empresas multinacionales
appliesto:
- Microsoft Teams
ms.openlocfilehash: 19200ec5ab1556b0f2b4fda2f389e60bc236015b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51097496"
---
# <a name="contoso-case-study-teams-voice-migration-overview"></a>Caso práctico de Contoso: información Teams de migración de voz

En este artículo se presenta un caso práctico sobre cómo una corporación multinacional ficticia, Contoso, implementó una solución Teams voz para su organización.

Contoso ha implementado Microsoft 365 Enterprise y ha abordado decisiones de diseño importantes y detalles de implementación para lo siguiente: redes, identidad, Windows 10 Enterprise, Office 365 ProPlus, administración de dispositivos móviles, protección de la información, seguridad, actualización de Skype Empresarial a Teams, Sistema telefónico y audioconferencia.  

Este artículo se centra en cómo Contoso ha migrado sus usuarios locales a Teams para una comunicación unificada, colaboración y voz. Para obtener información básica sobre cómo Contoso aceleró su transformación digital mediante los servicios en la nube de Microsoft, vea todos los artículos principales que comienzan con la información general sobre [casos prácticos de Contoso.](/microsoft-365/enterprise/contoso-case-study?view=o365-worldwide)

https://docs.microsoft.com/microsoft-365/enterprise/contoso-case-study?view=o365-worldwide 

En los artículos principales, encontrará información sobre lo siguiente:  

- Necesidades de infraestructura de TI de Contoso
- Redes
- Identidad
- Windows 10 Enterprise
- Office 365 Pro Plus
- Administración de dispositivos móviles
- Protección de la información
- Resumen de la Microsoft 365 Enterprise seguridad
- Equipo para un proyecto secreto
- SharePoint Sitio en línea para activos digitales altamente confidenciales

Para obtener información sobre cómo planear una actualización, querrá empezar con Introducción a la [actualización Microsoft Teams actualización.](upgrade-start-here.md)

## <a name="contoso-business-goals-for-teams"></a>Objetivos empresariales de Contoso para Teams

Para migrar sus usuarios locales a Teams para la comunicación unificada, la colaboración y la voz, Contoso decidió los siguientes objetivos empresariales:

- Teams habilitación 

  El equipo de colaboración y comunicación unificada de Contoso ha Teams con las directivas correctas para gobernar y habilitar la colaboración interna y externa segura. 

- Actualización de Skype Empresarial a Microsoft Teams 

  Skype Empresarial se implementó ampliamente en Contoso. Con la necesidad de salir de los sistemas heredados, Contoso decidió actualizar sus Skype Empresarial usuarios a Teams. Para obtener más información, vea [Caso práctico de Contoso: Teams plan de actualización](voice-case-study-migration-plan.md).

- Sistema telefónico  

  Skype Empresarial con voz empresarial se implementó ampliamente en Contoso. Con la necesidad de quitar los sistemas heredados que eran el siguiente salto para sus servidores de mediación, Contoso migró sus Skype Empresarial de voz empresariales a Sistema telefónico. Los sitios de Contoso usaron Microsoft Calling Plan, Sistema telefónico enrutamiento directo o una combinación de ambos. Para obtener más información, vea [Caso práctico de Contoso: Sistema telefónico](voice-case-study-phone-system.md).

- Enrutamiento basado en ubicación 

  Con ubicaciones de oficina en países regulados por telefonía, Contoso necesitaba volver a crear el enrutamiento de Location-Based que estaba presente en Skype Empresarial en su Sistema telefónico implementación. Para obtener más información, vea [Caso práctico de Contoso: Location-Based enrutamiento](voice-case-study-location-based-routing.md).

- Llamadas de emergencia 

  Cuando se implementó el enrutamiento directo, Contoso estableció las llamadas de emergencia con terceros aprobados. Para obtener más información, vea [Caso práctico de Contoso: Llamadas de emergencia.](voice-case-study-emergency-calling.md)

- Audioconferencia 

  Contoso ha configurado números de servicio de audioconferencia hospedados en su tronco SIP para su proveedor de RTC. Para obtener más información, vea [Caso práctico de Contoso: Audioconferencias.](voice-case-study-audio-conferencing.md) 

- Optimización de medios locales 

  Contoso se ha aprovechado de la optimización de medios locales en ubicaciones en las que tenían un tronco de ruta directa para Teléfono Microsoft sistema que se aprovechaba con sitios remotos. Para obtener más información, vea [Planear la optimización de medios locales](direct-routing-media-optimization.md) y Configurar la [optimización de medios locales.](direct-routing-media-optimization-configure.md)

- Operadores automáticos y colas de llamadas

  Como resultado de Covid-19, Contoso quería proporcionar soporte de recepcionista mientras su personal estaba trabajando de forma remota. Contoso usó operadores automáticos y colas de llamadas para administrar las llamadas entrantes al número de teléfono de su recepcionista. Para obtener más información, vea [Caso práctico de Contoso: Operadores automáticos y Colas de llamadas.](voice-case-study-call-queues.md)