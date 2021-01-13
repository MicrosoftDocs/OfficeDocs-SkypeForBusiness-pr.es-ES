---
title: Definir un nuevo tronco
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddTrunkPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e5d97b27-5ae8-41e0-8ee9-0c3f6d5dd123
ROBOTS: NOINDEX, NOFOLLOW
description: 'Para definir un nuevo un tronco de protocolo de inicio de sesión (SIP) proporcione la información siguiente:'
ms.openlocfilehash: db98c6d6f6aacf31b4e0b228dbe499f40ea01bdf
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800900"
---
# <a name="define-a-new-trunk"></a>Definir un nuevo tronco

Para definir un nuevo un tronco de protocolo de inicio de sesión (SIP) proporcione la información siguiente:

- **Nombre del tronco**: nombre único en la topología que identificará este tronco

- **Puerta de enlace RTC asociada**: seleccione una puerta de enlace RTC implementada y configurada de la lista en la implementación

- **Puerto de escucha para la puerta de enlace IP/RTC**: puerto en el que escuchará la puerta de enlace IP-PBX o RTC. Debe ser distinto de todos los demás puertos de escucha de tronco configurados en la implementación

- **Protocolo de transporte SIP**: seleccione TCP o TLS de la lista

- **Servidor de mediación asociado:** seleccione en la lista un servidor de mediación que se implemente y configure en la implementación.

- **Puerto del servidor de mediación** asociado: establezca el valor de puerto igual al valor del puerto TCP o TLS del servidor de mediación que usará este tronco SIP.

## <a name="see-also"></a>Vea también

[Tronco M:N en Skype Empresarial Server](../../../plan-your-deployment/enterprise-voice-solution/m-n-trunk.md)

[¿Cómo puedo implementar el enlace troncal SIP?](https://technet.microsoft.com/library/273a22b1-8a4c-4187-acf8-c57d5c6598ce.aspx)
