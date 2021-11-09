---
title: Revisión o actualización de un servidor back-end o Standard Edition servidor en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: f95f8d3a-e039-484e-97bd-d727db21a12b
description: 'Resumen: obtenga información sobre cómo instalar una actualización o revisión en un servidor back-end en Skype Empresarial Server.'
ms.openlocfilehash: 55d81e97712abe51544a854bf175348526e9f29c
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/08/2021
ms.locfileid: "60858217"
---
# <a name="patch-or-update-a-back-end-server-or-standard-edition-server-in-skype-for-business-server"></a>Revisión o actualización de un servidor back-end o Standard Edition servidor en Skype Empresarial Server
 
**Resumen:** Obtenga información sobre cómo instalar una actualización o revisión en un servidor back-end en Skype Empresarial Server.
  
En este tema se explica cómo instalar una actualización en un Enterprise Edition back-end o en un Standard Edition servidor.
  
Si un servidor back-end está inactivo al menos 30 minutos mientras se actualiza, los usuarios podrían entrar en modo de resistencia. Cuando termine la actualización y los servidores back-end se conecten de nuevo a los servidores front-end del grupo, los usuarios volverán al modo de funcionalidad total. Si la actualización dura menos de 30 minutos, los usuarios no se verán afectados.
  
### <a name="to-update-a-back-end-server-or-standard-edition-server"></a>Para actualizar un servidor back-end o Standard Edition servidor

1. Inicie sesión en el servidor que desea actualizar como miembro del rol CsAdministrator.
    
2. Descargue la actualización extráigala en el disco duro local.
    
3. Inicie el Shell Skype Empresarial Server administración: haga clic en Inicio **,** en Todos los **programas,** haga clic en **Skype Empresarial** y, a continuación, haga clic Skype Empresarial Server Shell **de administración.**
    
4. Detenga Skype Empresarial Server servicios. En la línea de comandos, escriba:
    
    ```PowerShell
    Stop-CsWindowsService
    ```

5. Detenga el servicio World Wide Web. En la línea de comandos, escriba:
    
    ```PowerShell
    net stop w3svc
   ```

6. Cierre todas Skype Empresarial Server del Shell de administración.
    
7. Instale el paquete.
    
8. Inicie el Shell Skype Empresarial Server administración: haga clic en Inicio **,** en Todos los **programas,** haga clic en **Skype Empresarial** y, a continuación, haga clic **en Skype Empresarial Server Shell de administración**.
    
9. Detenga Skype Empresarial Server servicios de nuevo para capturar ensamblados -d de caché global de ensamblados (GAC). En la línea de comandos, escriba:
    
    ```PowerShell
    Stop-CsWindowsService
    ```

10. Reinicie el servicio World Wide Web. En la línea de comandos, escriba:
    
    ```PowerShell
    net start w3svc
    ```

11. Aplique los cambios realizados a las bases SQL Server de datos mediante una de las siguientes acciones:
    
    - Si se trata de un Enterprise Edition back-end y no hay bases de datos en este servidor, como bases de datos de archivado o supervisión, escriba lo siguiente en una línea de comandos:
    
    ```PowerShell
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>
    ```

    - Si se trata de un Enterprise Edition back-end y hay bases de datos collocadas en este servidor, escriba lo siguiente en una línea de comandos:
    
    ```PowerShell
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>  -ExcludeCollocatedStores
    ```

    - Si se trata de un Standard Edition, escriba lo siguiente en una línea de comandos:
    
    ```PowerShell
    Install-CsDatabase -Update -LocalDatabases

    ```
