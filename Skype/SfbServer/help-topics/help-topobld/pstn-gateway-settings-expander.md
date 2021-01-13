---
title: Expansor de configuración de puerta de enlace de RTC
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.PstnGatewaySettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0fd103df-150d-4ea8-b522-18dbc50f5061
description: 'Para editar o modificar la configuración de una puerta de enlace de la red telefónica conmutada (RTC), modifique los campos siguientes:'
ms.openlocfilehash: 56f26a4113841b7563e42180aa51a80eedb2f859
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823730"
---
# <a name="pstn-gateway-settings-expander"></a>Expansor de configuración de puerta de enlace de RTC
 
Para editar o modificar la configuración de una puerta de enlace de la red telefónica conmutada (RTC), modifique los campos siguientes:
  
Se necesita el nombre de dominio completo o la dirección IP de la puerta de enlace, que define el **Nombre de dominio completo (FQDN)** de la puerta de enlace de RTC según un registro de host (A) del sistema de nombres de dominio (DNS), una entrada de archivo de hosts estático o bien la dirección IP de la puerta de enlace de RTC.
  
El protocolo de transporte de SIP puede ser el Protocolo de control de transmisión (TCP) o la Seguridad de la capa de transporte (TLS). TLS es el valor predeterminado. Consulte la documentación del proveedor de la puerta de enlace para obtener información sobre la compatibilidad de la puerta de enlace. El valor predeterminado es TLS; si la puerta de enlace admite TLS, en principio es la opción más segura.
  
Seleccione si desea habilitar IPv4 e IPv6 para la puerta de enlace.
  
La **Dirección IP de medios alternativa** es una definición para el servidor de mediación para el cual la puerta de enlace de RTC implementada tiene una dirección IP para el tráfico de medios diferente de la dirección IP predeterminada, que en general se dedica a tráfico SIP. Si se define este parámetro, la puerta de enlace de RTC admite una ruta o una interfaz de red distintas para el medio. Si esta dirección se deja en blanco, la puerta de enlace de RTC no admite la ruta alternativa para el medio.
  

