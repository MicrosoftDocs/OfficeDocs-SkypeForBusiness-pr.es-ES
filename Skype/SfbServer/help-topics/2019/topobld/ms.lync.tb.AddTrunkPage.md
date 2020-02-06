---
title: Definir un nuevo tronco
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 'Para definir un nuevo tronco de protocolo de inicio de sesión (SIP), proporcione la siguiente información:'
ms.openlocfilehash: 17f6b72f1234813e717cfc72be60bb5f0352134a
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41794319"
---
# <a name="define-a-new-trunk"></a>Definir un nuevo tronco

Para definir un nuevo tronco de protocolo de inicio de sesión (SIP), proporcione la siguiente información:

- **Nombre del tronco**: nombre único de la topología que identificará este tronco

- **Puerta de enlace RTC asociada**: Seleccione una puerta de enlace RTC implementada y configurada en la implementación de la lista

- **Puerto de escucha para la puerta de enlace IP/RTC**: puerto en el que escuchará la puerta de enlace IP o RTC. Debe ser único de todos los demás puertos de escucha de troncal configurados en su implementación

- **Protocolo de transporte SIP**: seleccione de la lista TCP o TLS.

- **Servidor de mediación asociado**: seleccione en la lista un servidor de mediación implementado y configurado en su implementación.

- **Puerto de servidor de mediación asociado**: establezca el valor de puerto igual al valor del puerto TCP o TLS del servidor de mediación que usará este tronco de SIP.

## <a name="see-also"></a>Vea también

[M:N troncal en Skype empresarial Server](../../../plan-your-deployment/enterprise-voice-solution/m-n-trunk.md)

[¿Cómo implemento la Troncalización SIP?](https://technet.microsoft.com/library/273a22b1-8a4c-4187-acf8-c57d5c6598ce.aspx)
