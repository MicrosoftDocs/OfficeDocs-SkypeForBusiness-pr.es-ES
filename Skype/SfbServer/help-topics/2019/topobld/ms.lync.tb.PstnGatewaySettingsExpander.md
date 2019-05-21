---
title: Expansor de configuración de puerta de enlace RTC
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.PstnGatewaySettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0fd103df-150d-4ea8-b522-18dbc50f5061
ROBOTS: NOINDEX, NOFOLLOW
description: 'Modifique los siguientes campos para editar o modificar la configuración de una puerta de enlace de la red telefónica conmutada (RTC):'
ms.openlocfilehash: 80e3f6b0f6e0afa4b28b384cfe9a64ac8bbd6ebc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34302185"
---
# <a name="pstn-gateway-settings-expander"></a>Expansor de configuración de puerta de enlace RTC
 
Modifique los siguientes campos para editar o modificar la configuración de una puerta de enlace de la red telefónica conmutada (RTC):
  
El nombre de dominio completo o la dirección IP de la puerta de enlace es una entrada necesaria, que define el **Nombre de dominio completo (FQDN)** de la puerta de enlace de RTC según un registro de host (A) del sistema de nombres de dominio (DNS), una entrada de archivo de hosts estático, o bien la dirección IP de la puerta de enlace RTC.
  
El protocolo de transporte de SIP puede ser el Protocolo de control de transmisión (TCP) o la Seguridad de la capa de transporte (TLS). TLS es el valor predeterminado. Consulte la documentación del proveedor de la puerta de enlace para obtener información sobre la compatibilidad de la puerta de enlace. El valor predeterminado es TLS; si la puerta de enlace admite TLS, en principio es la opción más segura.
  
Seleccione si desea habilitar IPv4 e IPv6 para la puerta de enlace.
  
La **dirección IP de medios alternativos** es una definición para el servidor de mediación para la que la puerta de enlace RTC implementada tiene una dirección IP diferente para el tráfico de medios que la dirección IP configurada predeterminada, que normalmente se dedica al tráfico SIP. Si este parámetro se define, la puerta de enlace RTC admite una ruta de acceso o una interfaz de red distintas para el medio. Si esta dirección se deja en blanco, la puerta de enlace RTC no admitirá la ruta de acceso alternativa para el medio.
  

