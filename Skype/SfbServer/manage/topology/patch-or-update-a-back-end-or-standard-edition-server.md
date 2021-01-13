---
title: Revisión o actualización de un servidor back-end o un servidor Standard Edition en Skype Empresarial Server
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
ms.assetid: f95f8d3a-e039-484e-97bd-d727db21a12b
description: 'Resumen: obtenga información sobre cómo instalar una actualización o revisión en un servidor back-end en Skype Empresarial Server.'
ms.openlocfilehash: 3e5e0cda1604f3144e853cfa3bf7bcc45e7d0c2f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826310"
---
# <a name="patch-or-update-a-back-end-server-or-standard-edition-server-in-skype-for-business-server"></a>Revisión o actualización de un servidor back-end o un servidor Standard Edition en Skype Empresarial Server
 
**Resumen:** Obtenga información sobre cómo instalar una actualización o revisión en un servidor back-end en Skype Empresarial Server.
  
En este tema se explica cómo instalar una actualización en un servidor back-end Enterprise Edition o en un servidor Standard Edition.
  
Si un servidor back-end está inactivo al menos 30 minutos mientras se actualiza, los usuarios podrían entrar en modo de resistencia. Cuando termine la actualización y los servidores back-end se conecten de nuevo a los servidores front-end del grupo, los usuarios volverán al modo de funcionalidad total. Si la actualización dura menos de 30 minutos, los usuarios no se verán afectados.
  
### <a name="to-update-a-back-end-server-or-standard-edition-server"></a>Para actualizar un servidor back-end o un servidor Standard Edition

1. Inicie sesión en el servidor que desea actualizar como miembro del rol CsAdministrator.
    
2. Descargue la actualización extráigala en el disco duro local.
    
3. Inicie el Shell de administración de Skype Empresarial Server: Haga clic en **Inicio,** en Todos los **programas,** en **Skype** Empresarial y, a continuación, en Shell de administración de Skype Empresarial **Server.**
    
4. Detenga los servicios de Skype Empresarial Server. En la línea de comandos, escriba:
    
    ```PowerShell
    Stop-CsWindowsService
    ```

5. Detenga el servicio World Wide Web. En la línea de comandos, escriba:
    
    ```PowerShell
    net stop w3svc
   ```

6. Cierre todas las ventanas del Shell de administración de Skype Empresarial Server.
    
7. Instale el paquete.
    
8. Inicie el Shell de administración de Skype Empresarial Server: Haga clic en **Inicio,** en Todos los **programas,** en **Skype** Empresarial y, a continuación, en Shell de administración de Skype Empresarial **Server.**
    
9. Vuelva a detener los servicios de Skype Empresarial Server para capturar ensamblados -d de caché global de ensamblados (GAC). En la línea de comandos, escriba:
    
    ```PowerShell
    Stop-CsWindowsService
    ```

10. Reinicie el servicio World Wide Web. En la línea de comandos, escriba:
    
    ```PowerShell
    net start w3svc
    ```

11. Aplique los cambios realizados a las bases SQL Server de datos mediante una de las siguientes acciones:
    
    - Si se trata de un servidor back-end Enterprise Edition y no hay bases de datos en este servidor, como bases de datos de archivado o supervisión, escriba lo siguiente en una línea de comandos:
    
    ```PowerShell
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>
    ```

    - Si se trata de un servidor back-end Enterprise Edition y hay bases de datos colocadas en este servidor, escriba lo siguiente en una línea de comandos:
    
    ```PowerShell
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>  -ExcludeCollocatedStores
    ```

    - Si se trata de un servidor Standard Edition, escriba lo siguiente en una línea de comandos:
    
    ```PowerShell
    Install-CsDatabase -Update -LocalDatabases

    ```
