---
title: Una revisión o actualización de un servidor Back-End o servidor Standard Edition en Skype para Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f95f8d3a-e039-484e-97bd-d727db21a12b
description: 'Resumen: Obtenga información sobre cómo instalar una actualización o revisión en un servidor Back-End en Skype para Business Server.'
ms.openlocfilehash: 7919d437e5111d32f3f51fa19a1880714800666b
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30884156"
---
# <a name="patch-or-update-a-back-end-server-or-standard-edition-server-in-skype-for-business-server"></a>Una revisión o actualización de un servidor Back-End o servidor Standard Edition en Skype para Business Server
 
**Resumen:** Obtenga información sobre cómo instalar una actualización o revisión en un servidor Back-End en Skype para Business Server.
  
En este tema se explica cómo instalar una actualización en un servidor de Enterprise Edition Back End o un servidor Standard Edition.
  
Si un servidor Back-End está inactivo durante al menos 30 minutos mientras se está actualizando, los usuarios, a continuación, es posible que vaya a modo de resistencia. Cuando finalice la actualización y los servidores Back-End nuevo se ha conectado con el servidor front-end del grupo de servidores, los usuarios se devuelven a la funcionalidad completa. Si la actualización dura menos de 30 minutos, los usuarios no se verán afectados.
  
### <a name="to-update-a-back-end-server-or-standard-edition-server"></a>Para actualizar un servidor back-end o un servidor Standard Edition

1. Inicie sesión en el servidor que desea actualizar como miembro del rol CsAdministrator.
    
2. Descargue la actualización extráigala en el disco duro local.
    
3. Iniciar el Skype para Shell de administración de negocio Server: haga clic en **Inicio**, haga clic en **Todos los programas**, haga clic en **Skype para la empresa**y, a continuación, haga clic en **Skype para Shell de administración de Business Server**..
    
4. Detener Skype para servicios de Business Server. En la línea de comandos, escriba:
    
    ```
    Stop-CsWindowsService
    ```

5. Detenga el servicio World Wide Web. En la línea de comandos, escriba:
    
    ```
    net stop w3svc
   ```

6. Cierre todos los Skype para windows Business Server Management Shell.
    
7. Instale la actualización.
    
8. Iniciar el Skype para Shell de administración de negocio Server: haga clic en **Inicio**, haga clic en **Todos los programas**, haga clic en **Skype para la empresa**y, a continuación, haga clic en **Skype para Shell de administración de servidor empresarial**.
    
9. Detener Skype para servicios de Business Server nuevo para detectar los ensamblados -d de la memoria caché de ensamblados Global (GAC). En la línea de comandos, escriba:
    
    ```
    Stop-CsWindowsService
    ```

10. Reinicie el servicio World Wide Web. En la línea de comandos, escriba:
    
    ```
    net start w3svc
    ```

11. Aplique los cambios realizados a las bases de datos de SQL Server mediante uno de los siguientes procedimientos:
    
    - Si se trata de un servidor de Enterprise Edition Back End y no existen bases de datos combinadas en este servidor, como el archivado o bases de datos de supervisión, a continuación, escriba lo siguiente en una línea de comandos:
    
    ```
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>
    ```

    - Si se trata de un servidor de Enterprise Edition Back End y hay bases de datos combinadas en este servidor, a continuación, escriba lo siguiente en una línea de comandos:
    
    ```
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>  -ExcludeCollocatedStores
    ```

    - Si se trata de un servidor Standard Edition, escriba lo siguiente en una línea de comandos:
    
    ```
    Install-CsDatabase -Update -LocalDatabases

    ```
