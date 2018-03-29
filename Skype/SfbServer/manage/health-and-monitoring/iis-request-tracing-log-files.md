---
title: Supervisar archivos de registro de seguimiento de solicitudes de IIS en Skype Empresarial Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6730e92-6d74-4fa7-a83f-50b7bdadbffa
description: 'Resumen: Conozca el servicio de movilidad (Mcx) en Skype para 2015 de Business Server compatibilidad con clientes heredados.'
ms.openlocfilehash: 51913162603203333cd201c64ed21770825bdaf7
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="monitoring-iis-request-tracing-log-files-in-skype-for-business-server-2015"></a>Supervisar archivos de registro de seguimiento de solicitudes de IIS en Skype Empresarial Server 2015
 
**Resumen:** Obtenga información acerca del servicio de movilidad (Mcx) en Skype para 2015 de Business Server compatibilidad con clientes heredados.
  
Este tema solo se aplica a las implementaciones que admiten clientes de Lync 2010 Mobile y está pensado para el servicio de movilidad (Mcx).
  
Al habilitar el seguimiento de la solicitud de servicios de Internet Information Server (IIS) para el Skype para servicio de movilidad Business Server (Mcx), los archivos de registro que se generan pueden consumir hasta tres gigabytes de espacio en disco por día. El registro de seguimiento de IIS está habilitado de manera predeterminada. Debe supervisar los servidores frontales para asegurarse de que no se ejecutan fuera del espacio en disco. 
  
De manera predeterminada, IIS almacena los archivos de registro en %SystemDrive%\inetpub\logs\LogFiles.
  
Para desactivar el seguimiento de solicitudes de IIS para todo un servidor, en la línea de comandos, escriba lo siguiente:
  
```
%SystemDrive%\Windows\System32\inetsrv\appcmd set config /section:httpLogging /dontLog:True
```

Para obtener más información acerca del comando **httpLogging** , consulte [la referencia de comandos](https://go.microsoft.com/fwlink/p/?linkId=234927).
  

