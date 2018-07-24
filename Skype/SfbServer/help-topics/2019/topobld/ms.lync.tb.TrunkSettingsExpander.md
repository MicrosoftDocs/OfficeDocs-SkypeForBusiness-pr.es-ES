---
title: Expansor de configuración de tronco
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.TrunkSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3d00e8f4-e599-4094-a4a1-34fd6e8a5580
description: 'Para editar o modificar la configuración de un tronco SIP, efectúe las acciones siguientes:'
ms.openlocfilehash: 4f8f6e2f0851b00f9e7702391ce051a42dd686c3
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "20985836"
---
# <a name="trunk-settings-expander"></a>Expansor de configuración de tronco
 
Para editar o modificar la configuración de un tronco SIP, efectúe las acciones siguientes:
  
 **Nombre de tronco** es una entrada obligatoria e identifica de manera exclusiva el tronco SIP en la implementación.
  
 **Puerta de enlace RTC asociada**: seleccione una puerta de enlace RTC que se haya definido en la implementación.
  
 **Puerto de escucha para la puerta de enlace IP/RTC**: indica qué puerto TCP/IP usará la puerta de enlace para escuchar solicitudes. El valor predeterminado es el puerto 5067, si bien este puede variar según el proveedor de la puerta de enlace.
  
 **Protocolo de transporte SIP**: el protocolo usado puede ser TCP o TLS. TLS es el valor predeterminado. Consulte la documentación del proveedor de la puerta de enlace para obtener información sobre la compatibilidad de la puerta de enlace. El valor predeterminado es TLS; si la puerta de enlace admite TLS, en principio es la opción más segura.
  
 **Servidor de mediación asociado**: seleccione un servidor de mediación existente de la implementación para asociarlo con el tronco SIP.
  
> [!NOTE]
> Únicamente el tronco raíz puede asociarse con un servidor de mediación. 
  
 **Puerto del servidor de mediación asociado**: un valor obligatorio, esto se establece en el valor que el servidor de mediación está configurado para escuchar en.
  
![Expansor de configuración de tronco](../../../media/Trunk_Settings_Expander.jpg)
  
## <a name="see-also"></a>Vea también

[Lista de comprobación para implementación de enlace troncal SIP](http://technet.microsoft.com/library/94f4f03e-19d5-4198-92be-e4076dbb959a.aspx)
  
[Componentes y topologías para el enlace troncal SIP](http://technet.microsoft.com/library/8ed9a9d0-517e-4f36-a131-22cdafa257fa.aspx)