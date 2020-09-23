---
title: Expansor de configuración de tronco
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.TrunkSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3d00e8f4-e599-4094-a4a1-34fd6e8a5580
description: 'Para editar o modificar la configuración de un tronco SIP, efectúe las acciones siguientes:'
ms.openlocfilehash: 6393ef52859f32ad93d363faf36af3bd34530a9b
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "48215941"
---
# <a name="trunk-settings-expander"></a>Expansor de configuración de tronco

Para editar o modificar la configuración de un tronco SIP, efectúe las acciones siguientes:

 **Nombre del tronco** es una entrada obligatoria e identifica de manera exclusiva el tronco SIP en la implementación.

 **Puerta de enlace RTC asociada**: seleccione una puerta de enlace RTC que se haya definido en la implementación.

 **Puerto de escucha de la puerta de enlace IP/RTC**: indica qué puerto TCP/IP usará la puerta de enlace para escuchar solicitudes. El valor puede variar según el proveedor de la puerta de enlace; sin embargo, el valor predeterminado es el puerto 5067.

 **Protocolo de transporte SIP**: el protocolo usado puede ser TCP o TLS. TLS es el valor predeterminado. Consulte la documentación del proveedor de la puerta de enlace para obtener información sobre la compatibilidad de la puerta de enlace. El valor predeterminado es TLS; si la puerta de enlace admite TLS, en principio es la opción más segura.

 **Servidor de mediación asociado**: Seleccione un servidor de mediación existente de la implementación para asociarlo con el tronco SIP.

> [!NOTE]
> Solo el tronco raíz se puede asociar con un servidor de mediación de Lync Server 2010 o Lync Server 2013.

 **Puerto del servidor de mediación asociado**: un valor obligatorio, que se establece en el valor en el que el servidor de mediación está configurado para escuchar.

![Expansor de configuración de tronco](../../media/Trunk_Settings_Expander.jpg)

## <a name="see-also"></a>Vea también

[Lista de comprobación de implementación de troncal SIP](https://technet.microsoft.com/library/94f4f03e-19d5-4198-92be-e4076dbb959a.aspx)

[Componentes y topologías del tronco SIP](https://technet.microsoft.com/library/8ed9a9d0-517e-4f36-a131-22cdafa257fa.aspx)
