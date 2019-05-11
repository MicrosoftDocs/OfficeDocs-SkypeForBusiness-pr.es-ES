---
title: Definir un nuevo tronco
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddTrunkPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e5d97b27-5ae8-41e0-8ee9-0c3f6d5dd123
description: 'Definir un tronco de protocolo (SIP) de inicio de sesión nuevo al proporcionar la siguiente información:'
ms.openlocfilehash: 669f896e9a51a2f7f229a065a867f8ce8e48bcdc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33903785"
---
# <a name="define-a-new-trunk"></a>Definir un nuevo tronco

Definir un tronco de protocolo (SIP) de inicio de sesión nuevo al proporcionar la siguiente información:

- **Nombre del tronco**: nombre único en la topología que identificará este tronco

- **Puerta de enlace de RTC asociada**: seleccione una puerta de enlace RTC implementada y configurada en la implementación de la lista

- **Puerto de escucha para la puerta de enlace IP/RTC**: puerto en el que escuchará la puerta de enlace IP-PBX o RTC. Debe ser único entre todos los otros puertos de escucha de tronco configurados en la implementación

- **Protocolo de transporte SIP**: seleccione en la lista TCP o TLS

- **Servidor de mediación asociado**: seleccione en la lista de un servidor de mediación que se ha implementado y configurado en la implementación

- **Puerto del servidor de mediación asociado**: establecer el valor de puerto igual que el valor de puerto TCP o TLS del servidor de mediación que va a usar este tronco SIP

## <a name="see-also"></a>Vea también

[Tronco M:N en Skype Empresarial Server 2015](../../plan-your-deployment/enterprise-voice-solution/m-n-trunk.md)

[¿Cómo se puede implementar el enlace troncal SIP?](https://technet.microsoft.com/library/273a22b1-8a4c-4187-acf8-c57d5c6598ce.aspx)
