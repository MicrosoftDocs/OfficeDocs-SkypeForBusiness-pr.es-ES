---
title: Aplicar revisiones o actualizar un servidor de servicios de fondo o un servidor Standard Edition en Skype empresarial Server
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
ms.assetid: f95f8d3a-e039-484e-97bd-d727db21a12b
description: 'Resumen: Aprenda a instalar una actualización o una revisión en un servidor back-end de Skype empresarial Server.'
ms.openlocfilehash: 62c7a0c2e0c958e9f3e6c566d9e73a35d1dd945a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817101"
---
# <a name="patch-or-update-a-back-end-server-or-standard-edition-server-in-skype-for-business-server"></a>Aplicar revisiones o actualizar un servidor de servicios de fondo o un servidor Standard Edition en Skype empresarial Server
 
**Resumen:** Obtenga información sobre cómo instalar una actualización o una revisión en un servidor back-end en Skype empresarial Server.
  
En este tema se explica cómo instalar una actualización en un servidor de servicios de fondo Enterprise Edition o en un servidor Standard Edition.
  
Si un servidor back-end está desactivado durante al menos 30 minutos mientras lo está actualizando, los usuarios pueden entrar en el modo de resistencia. Cuando la actualización se ha completado y los servidores back-end se han conectado de nuevo con los servidores front-end en el grupo, los usuarios se devuelven a la funcionalidad completa. Si la actualización dura menos de 30 minutos, los usuarios no se verán afectados.
  
### <a name="to-update-a-back-end-server-or-standard-edition-server"></a>Para actualizar un servidor back-end o un servidor Standard Edition

1. Inicie sesión en el servidor que desea actualizar como miembro del rol CsAdministrator.
    
2. Descargue la actualización extráigala en el disco duro local.
    
3. Inicie el shell de administración de Skype empresarial Server: haga clic en **Inicio**, haga clic en **todos los programas**, en **Skype empresarial**y, a continuación, haga clic en **consola de administración de Skype empresarial**.
    
4. Detenga los servicios de Skype empresarial Server. En la línea de comandos, escriba:
    
    ```PowerShell
    Stop-CsWindowsService
    ```

5. Detenga el servicio World Wide Web. En la línea de comandos, escriba:
    
    ```PowerShell
    net stop w3svc
   ```

6. Cierre todas las ventanas de Shell de administración de Skype empresarial.
    
7. Instale la actualización.
    
8. Inicie el shell de administración de Skype empresarial Server: haga clic en **Inicio**, haga clic en **todos los programas**, en **Skype empresarial**y, a continuación, haga clic en **consola de administración de Skype empresarial**.
    
9. Detenga de nuevo los servicios de Skype empresarial Server para capturar los ensamblados de la caché de ensamblados global (GAC)-d. En la línea de comandos, escriba:
    
    ```PowerShell
    Stop-CsWindowsService
    ```

10. Reinicie el servicio World Wide Web. En la línea de comandos, escriba:
    
    ```PowerShell
    net start w3svc
    ```

11. Aplique los cambios realizados a las bases de datos de SQL Server mediante uno de los siguientes procedimientos:
    
    - Si se trata de un servidor de servicios de fondo Enterprise Edition y no hay bases de datos colocadas en este servidor, como archivar o supervisar bases de datos, escriba lo siguiente en una línea de comandos:
    
    ```PowerShell
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>
    ```

    - Si se trata de un servidor de servicios de fondo Enterprise Edition y hay bases de datos colocadas en este servidor, escriba lo siguiente en una línea de comandos:
    
    ```PowerShell
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>  -ExcludeCollocatedStores
    ```

    - Si se trata de un servidor Standard Edition, escriba lo siguiente en la línea de comandos:
    
    ```PowerShell
    Install-CsDatabase -Update -LocalDatabases

    ```
