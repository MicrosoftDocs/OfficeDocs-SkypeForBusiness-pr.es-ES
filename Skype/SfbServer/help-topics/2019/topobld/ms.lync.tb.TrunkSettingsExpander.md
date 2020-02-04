---
title: Expansor de configuración de tronco
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.TrunkSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3d00e8f4-e599-4094-a4a1-34fd6e8a5580
ROBOTS: NOINDEX, NOFOLLOW
description: 'Para editar o modificar la configuración de un tronco SIP, efectúe las acciones siguientes:'
ms.openlocfilehash: b2401dd561891b5c54f22003b0a29f61933b0277
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2020
ms.locfileid: "41687943"
---
# <a name="trunk-settings-expander"></a>Expansor de configuración de tronco

Para editar o modificar la configuración de un tronco SIP, efectúe las acciones siguientes:

 **Nombre de tronco** es una entrada obligatoria e identifica de manera exclusiva el tronco SIP en la implementación.

 **Puerta de enlace RTC asociada**: seleccione una puerta de enlace RTC que se haya definido en la implementación.

 **Puerto de escucha para la puerta de enlace IP/RTC**: indica qué puerto TCP/IP usará la puerta de enlace para escuchar solicitudes. El valor predeterminado es el puerto 5067, si bien este puede variar según el proveedor de la puerta de enlace.

 **Protocolo de transporte SIP**: el protocolo usado puede ser TCP o TLS. TLS es el valor predeterminado. Consulte la documentación del proveedor de la puerta de enlace para obtener información sobre la compatibilidad de la puerta de enlace. El valor predeterminado es TLS; si la puerta de enlace admite TLS, en principio es la opción más segura.

 **Servidor de mediación asociado**: Seleccione un servidor de mediación existente de la implementación para asociarlo con el tronco del SIP.

> [!NOTE]
> Solo se puede asociar el tronco raíz con un servidor de mediación.

 **Puerto de servidor de mediación asociado**: un valor obligatorio, se establece en el valor en el que el servidor de mediación está configurado para escuchar.

![Expansor de configuración de tronco](../../../media/Trunk_Settings_Expander.jpg)

## <a name="see-also"></a>Vea también

[Lista de comprobación de implementación de Troncalización SIP](https://technet.microsoft.com/library/94f4f03e-19d5-4198-92be-e4076dbb959a.aspx)

[Componentes y topologías para Troncalización SIP](https://technet.microsoft.com/library/8ed9a9d0-517e-4f36-a131-22cdafa257fa.aspx)
