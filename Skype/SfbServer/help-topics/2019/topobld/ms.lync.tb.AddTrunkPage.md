---
title: Definir un nuevo tronco
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
  - CSH
ms.custom:
  - ms.lync.tb.AddTrunkPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: e5d97b27-5ae8-41e0-8ee9-0c3f6d5dd123
ROBOTS: 'NOINDEX, NOFOLLOW'
description: 'Para definir un nuevo un tronco de protocolo de inicio de sesión (SIP) proporcione la información siguiente:'
---

# <a name="define-a-new-trunk"></a>Definir un nuevo tronco

Para definir un nuevo un tronco de protocolo de inicio de sesión (SIP) proporcione la información siguiente:

- **Nombre del tronco**: nombre único en la topología que identificará este tronco

- **Puerta de enlace RTC asociada**: seleccione una puerta de enlace RTC implementada y configurada de la lista en la implementación

- **Puerto de escucha para la puerta de enlace IP/RTC**: puerto en el que escuchará la puerta de enlace IP-PBX o RTC. Debe ser distinto de todos los demás puertos de escucha de tronco configurados en la implementación

- **Protocolo de transporte SIP**: seleccione TCP o TLS de la lista

- **Servidor de mediación asociado**: seleccione en la lista un servidor de mediación que se implemente y configure en la implementación.

- **Puerto del servidor de mediación** asociado: establezca el valor de puerto igual al valor de puerto TCP o TLS del servidor de mediación que usará este tronco SIP

## <a name="see-also"></a>Vea también

[Tronco M:N en Skype Empresarial Server](../../../plan-your-deployment/enterprise-voice-solution/m-n-trunk.md)

[¿Cómo implemento el enlace troncal SIP?](/previous-versions/office/lync-server-2013/lync-server-2013-how-do-i-implement-sip-trunking)