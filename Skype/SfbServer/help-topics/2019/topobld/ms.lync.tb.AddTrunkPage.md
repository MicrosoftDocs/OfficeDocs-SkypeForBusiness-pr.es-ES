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
ms.openlocfilehash: 49411ca6416a99d30d7a889aca0151f3ef89b9f7a8b7e559c39366c585144378
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54295427"
---
# <a name="define-a-new-trunk"></a>Definir un nuevo tronco

Para definir un nuevo un tronco de protocolo de inicio de sesión (SIP) proporcione la información siguiente:

- **Nombre del tronco**: nombre único en la topología que identificará este tronco

- **Puerta de enlace RTC asociada**: seleccione una puerta de enlace RTC implementada y configurada de la lista en la implementación

- **Puerto de escucha para la puerta de enlace IP/RTC**: puerto en el que escuchará la puerta de enlace IP-PBX o RTC. Debe ser distinto de todos los demás puertos de escucha de tronco configurados en la implementación

- **Protocolo de transporte SIP**: seleccione TCP o TLS de la lista

- **Servidor de mediación asociado:** seleccione en la lista un servidor de mediación que se implemente y configure en la implementación.

- **Puerto del servidor de mediación** asociado: establezca el valor de puerto igual al valor de puerto TCP o TLS del servidor de mediación que usará este tronco SIP

## <a name="see-also"></a>Consulte también

[Tronco M:N en Skype Empresarial Server](../../../plan-your-deployment/enterprise-voice-solution/m-n-trunk.md)

[¿Cómo implemento el enlace troncal SIP?](/previous-versions/office/lync-server-2013/lync-server-2013-how-do-i-implement-sip-trunking)