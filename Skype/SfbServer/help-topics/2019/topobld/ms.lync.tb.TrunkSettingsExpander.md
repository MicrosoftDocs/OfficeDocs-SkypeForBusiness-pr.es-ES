---
title: Expansor de configuración de tronco
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.TrunkSettingsExpander
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 3d00e8f4-e599-4094-a4a1-34fd6e8a5580
ROBOTS: NOINDEX, NOFOLLOW
description: 'Para editar o modificar la configuración de un tronco SIP, efectúe las acciones siguientes:'
ms.openlocfilehash: d9484dd6ab7a9589507808045f8516f0cd9ce70f
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2021
ms.locfileid: "58729269"
---
# <a name="trunk-settings-expander"></a>Expansor de configuración de tronco

Para editar o modificar la configuración de un tronco SIP, efectúe las acciones siguientes:

 **Nombre del tronco** es una entrada obligatoria e identifica de manera exclusiva el tronco SIP en la implementación.

 **Puerta de enlace RTC asociada**: seleccione una puerta de enlace RTC que se haya definido en la implementación.

 **Puerto de escucha de la puerta de enlace IP/RTC**: indica qué puerto TCP/IP usará la puerta de enlace para escuchar solicitudes. El valor puede variar según el proveedor de la puerta de enlace; sin embargo, el valor predeterminado es el puerto 5067.

 **Protocolo de transporte SIP**: el protocolo usado puede ser TCP o TLS. TLS es el valor predeterminado. Consulte la documentación del proveedor de la puerta de enlace para obtener información sobre la compatibilidad de la puerta de enlace. El valor predeterminado es TLS; si la puerta de enlace admite TLS, en principio es la opción más segura.

 **Servidor de mediación asociado:** seleccione un servidor de mediación existente de la implementación para asociarlo con el tronco SIP.

> [!NOTE]
> Solo el tronco raíz se puede asociar a un servidor de mediación.

 **Puerto del servidor de mediación** asociado: un valor necesario, que se establece en el valor en el que el servidor de mediación está configurado para escuchar.

![Expansor Configuración tronco.](../../../media/Trunk_Settings_Expander.jpg)

## <a name="see-also"></a>Vea también

[Lista de comprobación de implementación de enlace troncal SIP](/previous-versions/office/lync-server-2013/lync-server-2013-sip-trunk-deployment-checklist)

[Componentes y topologías del tronco SIP](/previous-versions/office/lync-server-2013/lync-server-2013-components-and-topologies-for-sip-trunking)