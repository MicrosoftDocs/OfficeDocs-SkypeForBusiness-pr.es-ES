---
title: Expansor de configuración de tronco
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.TrunkSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3d00e8f4-e599-4094-a4a1-34fd6e8a5580
description: 'Para editar o modificar la configuración de un tronco SIP, efectúe las acciones siguientes:'
ms.openlocfilehash: 13ea9abfb6d53b57333c2c96b8a2f8adde963ebf
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="trunk-settings-expander"></a>Expansor de configuración de tronco
 
Para editar o modificar la configuración de un tronco SIP, efectúe las acciones siguientes:
  
 **Nombre de tronco** es una entrada obligatoria e identifica de manera exclusiva el tronco SIP en la implementación.
  
 **Puerta de enlace RTC asociada**: seleccione una puerta de enlace RTC que se haya definido en la implementación.
  
 **Puerto de escucha para la puerta de enlace IP/RTC**: indica qué puerto TCP/IP usará la puerta de enlace para escuchar solicitudes. El valor predeterminado es el puerto 5067, si bien este puede variar según el proveedor de la puerta de enlace.
  
 **Protocolo de transporte SIP**: el protocolo usado puede ser TCP o TLS. TLS es el valor predeterminado. Consulte la documentación del proveedor de la puerta de enlace para obtener información sobre la compatibilidad de la puerta de enlace. El valor predeterminado es TLS; si la puerta de enlace admite TLS, en principio es la opción más segura.
  
 **Servidor de mediación asociados**: seleccione un servidor de mediación existente en la implementación para asociar a la troncal SIP.
  
> [!NOTE]
> Tronco de raíz puede asociarse con un servidor de mediación de Lync Server 2013 o con Lync Server 2010. 
  
 **Puerto de servidor de mediación asociados**: un valor requerido, se establece en el valor que está configurado el servidor de mediación para escuchar.
  
![Expansor de configuración de tronco](../../media/Trunk_Settings_Expander.jpg)
  
## <a name="see-also"></a>Vea también

#### 

[Lista de comprobación de implementación de SIP Trunking](http://technet.microsoft.com/library/94f4f03e-19d5-4198-92be-e4076dbb959a.aspx)
  
[Componentes y topologías para Troncalización SIP](http://technet.microsoft.com/library/8ed9a9d0-517e-4f36-a131-22cdafa257fa.aspx)

