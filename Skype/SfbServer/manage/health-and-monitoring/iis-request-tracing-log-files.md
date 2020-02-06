---
title: Supervisar archivos de registro de seguimiento de solicitudes de IIS en Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b6730e92-6d74-4fa7-a83f-50b7bdadbffa
description: 'Resumen: Obtenga información sobre el servicio de movilidad (MCX) en la compatibilidad de Skype empresarial Server 2015 para clientes heredados.'
ms.openlocfilehash: 982e5842499e5cb2f6ff21ff884d1baa45075627
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817930"
---
# <a name="monitoring-iis-request-tracing-log-files-in-skype-for-business-server-2015"></a>Supervisar archivos de registro de seguimiento de solicitudes de IIS en Skype Empresarial Server 2015
 
**Resumen:** Obtenga más información sobre el servicio de movilidad (MCX) en la compatibilidad de Skype empresarial Server 2015 para clientes heredados.
  
Este tema solo se aplica a las implementaciones que admiten clientes de Lync 2010 Mobile y está pensado para el servicio de movilidad (Mcx).

> [!NOTE]
> La compatibilidad con MCX (Mobility Service) para clientes móviles heredados ya no está disponible en Skype empresarial Server 2019. Todos los clientes móviles actuales de Skype empresarial ya usan la API Web de comunicaciones unificadas (UCWA) para admitir la mensajería instantánea, la presencia y los contactos. Los usuarios con clientes heredados que usen MCX deberán actualizar a un cliente actual.
  
Al habilitar el seguimiento de solicitudes de servicios de Internet Information Server (IIS) para el servicio de movilidad de Skype empresarial (MCX), los archivos de registro que se generan pueden consumir hasta tres gigabytes de espacio en el disco por día. El registro de seguimiento de IIS está habilitado de manera predeterminada. Debe supervisar los servidores front-end para asegurarse de que no se quede sin espacio en disco. 
  
De manera predeterminada, IIS almacena los archivos de registro en %SystemDrive%\inetpub\logs\LogFiles.
  
Para desactivar el seguimiento de solicitudes de IIS para todo un servidor, en la línea de comandos, escriba lo siguiente:
  
```console
%SystemDrive%\Windows\System32\inetsrv\appcmd set config /section:httpLogging /dontLog:True
```

Para obtener más información sobre el comando **httpLogging** , vea [la referencia de comandos](https://go.microsoft.com/fwlink/p/?linkId=234927).
  

