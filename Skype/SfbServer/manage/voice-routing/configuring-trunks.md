---
title: Configuración de troncos en Skype para Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Como parte de la implementación de Enterprise Voice, puede configurar un tronco entre un servidor de mediación y uno o más pares para proporcionar conectividad con telefónica conmutada (RTC) para los clientes de Enterprise Voice y dispositivos de la organización.
ms.openlocfilehash: 293685436997833c21dbd7b0d98521202e1beb99
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33896267"
---
# <a name="configuring-trunks-in-skype-for-business-server"></a>Configuración de troncos en Skype para Business Server

Como parte de la implementación de Enterprise Voice, puede configurar un tronco entre un servidor de mediación y uno o varios de los siguientes elementos del mismo nivel para proporcionar conectividad de telefónica conmutada (RTC) de la red de clientes de Enterprise Voice y dispositivos en su organización:

- Conexión basada en troncos SIP para un proveedor de servicio s de telefonía
- Puerta de enlace RTC
- Central de conmutación (PBX)

Para obtener información detallada, consulte [Plan para la conectividad de RTC en Skype para Business Server](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).

> [!IMPORTANT]
> Antes de comenzar la configuración del tronco, compruebe que se ha creado la topología y que el servidor de mediación y su mismo nivel han se han configurado y asociados entre sí. Para obtener más información, consulte [definir una puerta de enlace en el generador de Skype para Business Server](../../deploy/deploy-enterprise-voice/define-a-gateway.md).

> [!NOTE]
> Como parte de la configuración de tronco, puede habilitar la Skype para la característica de omisión de medios Business Server, que permite medios omitir el servidor de mediación. Se pueden configurar troncos con o sin desvío de medios habilitado, pero se recomienda encarecidamente que habilite. Para obtener información detallada, vea [Plan para los medios de desvío en Skype para la empresa](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).
