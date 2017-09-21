---
title: "Intervalos de direcciones IP y URL de Office 365 | Soporte técnico de Microsoft"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: overview
ms.service: msteams
description: "Aprenda a configurar correctamente los intervalos de direcciones IP y URL de Office 365, omita el proxy de reenvío cuando esté disponible para las conexiones con el servicio de Microsoft Teams y los requisitos para las directivas de redes y seguridad."
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: a28d816460357135a72de116d4a7b663147ba5a3
ms.sourcegitcommit: 9e217129451afae32eb3cd27fb3ee591874c29c9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
<a name="office-365-urls-and-ip-address-ranges"></a>Direcciones URL e intervalos de direcciones IP de Office 365
=====================================

Eche un vistazo a este enlace para obtener una lista detallada y actualizada de las direcciones IP y los puertos exactos que se deben configurar: [Intervalos de direcciones IP y URL de Office 365](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&rs=en-US&ad=US). Microsoft está mejorando continuamente el servicio de Office 365 y agregando nuevas funcionalidades, por lo que los puertos necesarios, las URL y las direcciones IP pueden cambiar con el paso del tiempo. Consulte la guía [URL de Office 365 e intervalos de direcciones IP](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) para conocer las versiones más actualizadas de puertos y protocolos. También le recomendamos que se [suscriba mediante RSS](https://go.microsoft.com/fwlink/p/?linkid=236301) para recibir notificaciones cuando los puntos de conexión se actualicen o cambien.

Como ya se ha mencionado, la experiencia de llamadas y reuniones de Microsoft Teams se creó a partir de la infraestructura en la nube de próxima generación que también se usa en Skype y Skype Empresarial. Entre estas inversiones tecnológicas se encuentran los servicios en la nube de Azure para señalización y procesamiento de medios, códec de vídeo H.264, códec de audio SILK y Opus, resiliencia de red, telemetría y diagnóstico de calidad. Como tal, hay URL y direcciones IP que son necesarias y puede que estén asociadas con Skype y Skype Empresarial.

Para todas las cargas de trabajo de Office 365, el método de conexión recomendado para los servicios de Microsoft Teams es omitir el proxy de reenvío siempre que sea posible. Cuando un servidor proxy se asienta entre un cliente y los centros de datos de Office 365, es posible que los medios se fuercen a través de TCP en lugar de UDP, lo que afectaría a la calidad de los medios. Puede descargar un archivo PAC de proxy de muestra y usarlo para configurar la omisión del tráfico en la guía [Administración de puntos de conexión de Office 365](https://support.office.com/article/managing-Office-365-endpoints-99cab9d4-ef59-4207-9f2b-3728eb46bf9a).

Si sus directivas de redes y seguridad requieren que el tráfico de Office 365 pase por un servidor proxy, asegúrese de que se cumplen los requisitos anteriores antes de implementar Microsoft Teams en producción (eche un vistazo a [Servidores proxy para Skype Empresarial Online](https://support.office.com/en-us/article/Proxy-Servers-for-Skype-for-Business-Online-7acaf2c2-35fa-490f-84cd-822e446e0fc7?ui=en-US&rs=en-US&ad=US) para más información).
