---
title: Supervisión de archivos de registro de seguimiento de solicitudes IIS en Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b6730e92-6d74-4fa7-a83f-50b7bdadbffa
description: 'Resumen: obtenga información sobre el servicio de movilidad (Mcx) en la compatibilidad de Skype Empresarial Server 2015 para clientes heredados.'
ms.openlocfilehash: 5fb9e66efa468e8755fe369c3ce4f2a4b8979e57
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823510"
---
# <a name="monitoring-iis-request-tracing-log-files-in-skype-for-business-server-2015"></a>Supervisión de archivos de registro de seguimiento de solicitudes IIS en Skype Empresarial Server 2015
 
**Resumen:** Obtenga información sobre el servicio de movilidad (Mcx) en la compatibilidad de Skype Empresarial Server 2015 para clientes heredados.
  
Este tema se aplica solo a las implementaciones que admiten clientes de Lync 2010 Lync Mobile y está destinado al servicio de movilidad (Mcx).

> [!NOTE]
> La compatibilidad con MCX (Mobility Service) para clientes móviles heredados ya no está disponible en Skype Empresarial Server 2019. Todos los clientes móviles actuales de Skype Empresarial ya usan la API web de comunicaciones unificadas (UCWA) para admitir la mensajería instantánea (MI), la presencia y los contactos. Los usuarios con clientes heredados que usen MCX tendrán que actualizar a un cliente actual.
  
Cuando habilita el seguimiento de solicitudes de Internet Information Services (IIS) para el servicio de movilidad de Skype Empresarial Server (Mcx), los archivos de registro que se generan pueden consumir hasta tres gigabytes de espacio en disco por día. El registro de seguimiento de IIS está habilitado de forma predeterminada. Debe supervisar los servidores front-end para asegurarse de que no se quedas sin espacio en disco. 
  
De forma predeterminada, IIS almacena los archivos de registro en %SystemDrive%\inetpub\logs\LogFiles.
  
Para desactivar el seguimiento de solicitudes IIS para todo un servidor, en la línea de comandos, escriba lo siguiente:
  
```console
%SystemDrive%\Windows\System32\inetsrv\appcmd set config /section:httpLogging /dontLog:True
```

Para obtener más información sobre **el comando httpLogging,** vea [la referencia del comando.](https://go.microsoft.com/fwlink/p/?linkId=234927)
  

