---
title: Caso práctico de voz de Contoso
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
description: Estudio de casos de voz de Teams para la corporación multinacional
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3a964075dfae514759309a81a7d7140cddd10220
ms.sourcegitcommit: 380a96f1ed2cefb429286854f06546bdb28d7d74
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/17/2020
ms.locfileid: "49701228"
---
# <a name="contoso-case-study-teams-voice-migration-overview"></a>Caso práctico de Contoso: Introducción a la migración de voz de Teams

En este artículo se presenta un caso práctico para el modo en que una corporación multinacional ficticia, Contoso, ha implementado una solución de voz de Teams para su organización.

Contoso ha implementado Microsoft 365 Enterprise y ha abordado las decisiones de diseño más importantes y los detalles de implementación de los siguientes temas: redes, identidad, Windows 10 Enterprise, Office 365 ProPlus, administración de dispositivos móviles, protección de la información, seguridad, actualización de Skype empresarial a equipos, el sistema telefónico y las conferencias de audio.  

Este artículo se centra en el modo en que contoso migró sus usuarios locales a Teams para la comunicación, la colaboración y la voz unificadas. Para obtener información general sobre cómo contoso ha acelerado su transformación digital mediante los servicios en la nube de Microsoft, vea todos los artículos principales comenzando con la [Descripción general de casos prácticos de Contoso](https://docs.microsoft.com/microsoft-365/enterprise/contoso-case-study?view=o365-worldwide).

https://docs.microsoft.com/microsoft-365/enterprise/contoso-case-study?view=o365-worldwide 

En los artículos principales, encontrará información sobre lo siguiente:  

- Necesidades de la infraestructura de TI de Contoso
- Redes
- Identidad
- Windows 10 Enterprise
- Office 365 Pro Plus
- Administración de dispositivos móviles
- Protección de la información
- Resumen de la seguridad de Microsoft 365 Enterprise
- Equipo para un proyecto de clave principal
- Sitio de SharePoint Online para activos digitales altamente confidenciales

Para obtener información sobre cómo planear una actualización, es recomendable empezar con [la introducción a la actualización de Microsoft Teams](upgrade-start-here.md).

## <a name="contoso-business-goals-for-teams"></a>Objetivos empresariales de Contoso para equipos

Para migrar sus usuarios locales a Teams para la comunicación, la colaboración y la voz unificadas, contoso decidió los siguientes objetivos empresariales:

- Habilitación de equipos 

  El equipo de colaboración y colaboración Unificado de Contoso ha habilitado a los equipos con las directivas correctas para regir y habilitar la colaboración interna y externa segura. 

- Actualización de Skype Empresarial a Microsoft Teams 

  Skype empresarial se ha distribuido ampliamente en contoso. Con la necesidad de desplazarse por sistemas heredados, contoso decidió actualizar los usuarios de Skype empresarial a teams. Para obtener más información, vea [caso práctico de Contoso: Plan de actualización de Teams](voice-case-study-migration-plan.md).

- Sistema telefónico  

  Skype empresarial con Enterprise Voice se ha implementado ampliamente en contoso. Con la necesidad de cambiar de sistemas heredados que fueron el próximo paso para sus servidores de mediación, contoso migró sus usuarios de voz de Skype empresarial empresarial a un sistema telefónico. Los sitios de Contoso usaban el plan de llamadas de Microsoft, el enrutamiento directo del sistema telefónico o una combinación de ambos. Para obtener más información, consulte [caso práctico de Contoso: Phone System](voice-case-study-phone-system.md).

- Enrutamiento basado en ubicación 

  Con las ubicaciones de Office en países regulados por telefonía, contoso necesitaba volver a crear el enrutamiento de Location-Based que estaba presente en Skype empresarial en la implementación de sistemas telefónicos. Para obtener más información, vea [caso práctico de Contoso: Location-Based enrutamiento](voice-case-study-location-based-routing.md).

- Llamadas de emergencia 

  Donde se implementó el enrutamiento directo, contoso configure las llamadas de emergencia con terceros aprobados. Para obtener más información, consulte [caso práctico de Contoso: llamadas de emergencia](voice-case-study-emergency-calling.md).

- Audioconferencia 

  Contoso configure los números del servicio de audioconferencia que se hospedaron en su enlace SIP a su proveedor PSTN. Para obtener más información, vea [caso práctico de Contoso: audioconferencia](voice-case-study-audio-conferencing.md). 

- Optimización local de medios 

  Contoso aprovechó la optimización local de medios en ubicaciones en las que tenían un tronco de ruta directa a Microsoft Phone System aprovechado por sitios remotos. Para obtener más información, vea [planear la optimización local de medios](direct-routing-media-optimization.md) y [configurar la optimización local de medios](direct-routing-media-optimization-configure.md).

- Operadores automáticos y colas de llamadas

  Como resultado de Covid-19, contoso quería proporcionar asistencia para la recepcionista mientras el personal estaba trabajando de forma remota. Contoso usó operadores automáticos y colas de llamadas para administrar las llamadas entrantes a su número de teléfono. Para obtener más información, vea [caso práctico de Contoso: operadores automáticos y colas de llamadas](voice-case-study-call-queues.md).  


