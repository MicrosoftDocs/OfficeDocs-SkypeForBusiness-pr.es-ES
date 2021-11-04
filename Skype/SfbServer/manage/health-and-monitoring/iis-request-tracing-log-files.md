---
title: Supervisión de archivos de registro de seguimiento de solicitudes iis en Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: b6730e92-6d74-4fa7-a83f-50b7bdadbffa
description: 'Summary: Learn about the Mobility Service (Mcx) in Skype Empresarial Server 2015 support for legacy clients.'
ms.openlocfilehash: 36a376428191723d8cc4d2d6e100391646c7e7c9
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2021
ms.locfileid: "60767678"
---
# <a name="monitoring-iis-request-tracing-log-files-in-skype-for-business-server-2015"></a>Supervisión de archivos de registro de seguimiento de solicitudes iis en Skype Empresarial Server 2015
 
**Resumen:** Obtenga información sobre el Servicio de movilidad (Mcx) en Skype Empresarial Server 2015 para clientes heredados.
  
Este tema se aplica solo a las implementaciones que admiten clientes de Lync 2010 Lync Mobile y está destinado al Servicio de movilidad (Mcx).

> [!NOTE]
> La compatibilidad con MCX (Mobility Service) para clientes móviles heredados ya no está disponible en Skype Empresarial Server 2019. Todos los clientes Skype Empresarial móviles ya usan la API web de comunicaciones unificadas (UCWA) para admitir mensajería instantánea (MI), presencia y contactos. Los usuarios con clientes heredados que usen MCX tendrán que actualizar a un cliente actual.
  
Cuando habilita el seguimiento de solicitudes de Internet Information Services (IIS) para el servicio de movilidad de Skype Empresarial Server (Mcx), los archivos de registro que se generan pueden consumir hasta tres gigabytes de espacio en disco al día. El registro de seguimiento de IIS está habilitado de forma predeterminada. Debe supervisar los servidores front-end para asegurarse de que no se quedas sin espacio en disco. 
  
De forma predeterminada, IIS almacena los archivos de registro en %SystemDrive%\inetpub\logs\LogFiles.
  
Para desactivar el seguimiento de solicitudes de IIS para todo un servidor, en la línea de comandos, escriba lo siguiente:
  
```console
%SystemDrive%\Windows\System32\inetsrv\appcmd set config /section:httpLogging /dontLog:True
```

Para obtener más información sobre **el comando httpLogging,** consulte [la referencia de comando](/previous-versions/iis/settings-schema/aa347466(v=vs.90)).
