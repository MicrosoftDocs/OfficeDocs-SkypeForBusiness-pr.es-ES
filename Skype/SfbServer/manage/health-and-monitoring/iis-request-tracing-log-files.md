---
title: Supervisar archivos de registro de seguimiento de solicitudes de IIS en Skype Empresarial Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6730e92-6d74-4fa7-a83f-50b7bdadbffa
description: 'Resumen: Obtenga información sobre el servicio de movilidad (Mcx) en Skype para soporte técnico de Business Server 2015 para los clientes heredados.'
ms.openlocfilehash: 5ed817290bdf86d11dd4a2cf0e95c83fb4c31d9a
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "20983829"
---
# <a name="monitoring-iis-request-tracing-log-files-in-skype-for-business-server-2015"></a>Supervisar archivos de registro de seguimiento de solicitudes de IIS en Skype Empresarial Server 2015
 
**Resumen:** Obtenga información sobre el servicio de movilidad (Mcx) en Skype para soporte técnico de Business Server 2015 para los clientes heredados.
  
Este tema solo se aplica a las implementaciones que admiten clientes de Lync 2010 Mobile y está pensado para el servicio de movilidad (Mcx).

> [!NOTE]
> Compatibilidad con MCX para los clientes móviles heredados ya no está disponible en Skype para Business Server 2019. Los usuarios deben actualizar a un cliente actual.
  
Cuando se habilita el seguimiento de solicitudes de Internet Information Services (IIS) para el Skype para servicio de movilidad de servidor empresarial (Mcx), los archivos de registro que se generan pueden consumir hasta tres gigabytes de espacio en disco por día. El registro de seguimiento de IIS está habilitado de manera predeterminada. Debe supervisar los servidores Front-End para asegurarse de que no se ejecutan fuera del espacio en disco. 
  
De manera predeterminada, IIS almacena los archivos de registro en %SystemDrive%\inetpub\logs\LogFiles.
  
Para desactivar el seguimiento de solicitudes de IIS para todo un servidor, en la línea de comandos, escriba lo siguiente:
  
```
%SystemDrive%\Windows\System32\inetsrv\appcmd set config /section:httpLogging /dontLog:True
```

Para obtener información detallada sobre el comando **httpLogging** , vea [la referencia de comandos](https://go.microsoft.com/fwlink/p/?linkId=234927).
  

