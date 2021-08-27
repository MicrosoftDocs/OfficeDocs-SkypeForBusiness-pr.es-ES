---
title: Configuración de troncos en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Como parte de Telefonía IP empresarial implementación, puede configurar un tronco entre un servidor de mediación y uno o varios sistemas del mismo nivel para proporcionar conectividad de red telefónica conmutada (RTC) para clientes y dispositivos de Telefonía IP empresarial de la organización.
ms.openlocfilehash: 5f7ce6bac163c481d01e71b3efb4ee13347a49e4
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "58598804"
---
# <a name="configuring-trunks-in-skype-for-business-server"></a>Configuración de troncos en Skype Empresarial Server

Como parte de la implementación Telefonía IP empresarial, puede configurar un tronco entre un servidor de mediación y uno o varios de los siguientes sistemas del mismo nivel para proporcionar conectividad de red telefónica conmutada (RTC) para clientes y dispositivos de Telefonía IP empresarial de su organización:

- Conexión basada en troncos SIP para un proveedor de servicio s de telefonía
- Puerta de enlace RTC
- Central de conmutación (PBX)

Para obtener más información, vea [Plan for PSTN connectivity in Skype Empresarial Server](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).

> [!IMPORTANT]
> Antes de iniciar la configuración de troncos, verifique que se ha creado la topología y que el servidor de mediación y su par se han configurado y asociado entre sí. Para obtener más información, vea [Define a gateway in Topology Builder in Skype Empresarial Server](../../deploy/deploy-enterprise-voice/define-a-gateway.md).

> [!NOTE]
> Como parte de la configuración del tronco, puede habilitar la característica Skype Empresarial Server desvío de medios, que permite a los medios omitir el servidor de mediación. Los troncos pueden configurarse con el desvío de medios habilitado o deshabilitado, aunque le recomendamos que lo habilite. Para obtener más información, vea [Plan for media bypass in Skype Empresarial](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).
