---
title: Definir un nuevo tronco
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddTrunkPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e5d97b27-5ae8-41e0-8ee9-0c3f6d5dd123
description: 'Para definir un nuevo tronco de protocolo de inicio de sesión (SIP), proporcione la siguiente información:'
ms.openlocfilehash: c66d5999d6aa5bad0e9c16f8d466d82b941a630b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34305926"
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

[Tronco M:N en Skype Empresarial Server 2015](../../plan-your-deployment/enterprise-voice-solution/m-n-trunk.md)

[¿Cómo implemento la Troncalización SIP?](https://technet.microsoft.com/library/273a22b1-8a4c-4187-acf8-c57d5c6598ce.aspx)
