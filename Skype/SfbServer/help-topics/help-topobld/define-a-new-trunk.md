---
title: Definir un nuevo tronco
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddTrunkPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: e5d97b27-5ae8-41e0-8ee9-0c3f6d5dd123
description: 'Para definir un nuevo un tronco de protocolo de inicio de sesión (SIP) proporcione la información siguiente:'
ms.openlocfilehash: 313eef07ed8156b72fc3f326c779448744bbca8e
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "58619866"
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

[Tronco M:N en Skype Empresarial Server 2015](../../plan-your-deployment/enterprise-voice-solution/m-n-trunk.md)

[¿Cómo implemento el enlace troncal SIP?](/previous-versions/office/lync-server-2013/lync-server-2013-how-do-i-implement-sip-trunking)