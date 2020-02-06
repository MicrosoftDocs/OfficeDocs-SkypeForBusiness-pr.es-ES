---
title: Configuración de troncos en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Como parte de la implementación de telefonía IP empresarial, puede configurar un tronco entre un servidor de mediación y uno o más homólogos para proporcionar conectividad de red telefónica conmutada (RTC) a los clientes y dispositivos de telefonía empresarial de su organización.
ms.openlocfilehash: 41e92f994606ea2153359546d408335d13a21f88
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817020"
---
# <a name="configuring-trunks-in-skype-for-business-server"></a>Configuración de troncos en Skype empresarial Server

Como parte de la implementación de telefonía IP empresarial, puede configurar un tronco entre un servidor de mediación y uno o más de los siguientes elementos para proporcionar conectividad de red telefónica conmutada (RTC) pública para los clientes y dispositivos de voz de su organización:

- Conexión basada en troncos SIP para un proveedor de servicio s de telefonía
- Puerta de enlace RTC
- Central de conmutación (PBX)

Para obtener más información, consulte [planear la conectividad RTC en Skype empresarial Server](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).

> [!IMPORTANT]
> Antes de comenzar con la configuración troncal, verifique que se haya creado la topología y que el servidor de mediación y sus pares se hayan configurado y asociado entre sí. Para obtener más información, vea [definir una puerta de enlace en el generador de topologías de Skype empresarial Server](../../deploy/deploy-enterprise-voice/define-a-gateway.md).

> [!NOTE]
> Como parte de la configuración troncal, puede habilitar la característica de omisión de medios de Skype empresarial Server, que permite a los medios eludir el servidor de mediación. Los troncos se pueden configurar con o sin omisión de medios habilitados, pero le recomendamos encarecidamente que lo habilite. Para obtener más información, consulte [planear la omisión de medios en Skype empresarial](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).
