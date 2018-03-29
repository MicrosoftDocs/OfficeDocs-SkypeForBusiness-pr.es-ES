---
title: Revisar o actualizar un servidor back-end o un servidor Standard Edition en Skype Empresarial Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f95f8d3a-e039-484e-97bd-d727db21a12b
description: 'Resumen: Conozca cómo instalar una actualización o una revisión en un servidor de fondo detrás de Skype para Business Server.'
ms.openlocfilehash: 14acff1aea501bf47dff95053259187570d2f990
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="patch-or-update-a-back-end-server-or-standard-edition-server-in-skype-for-business-server-2015"></a>Revisar o actualizar un servidor back-end o un servidor Standard Edition en Skype Empresarial Server 2015
 
**Resumen:** Obtenga información acerca de cómo instalar una actualización o una revisión en un servidor de fondo detrás de Skype para Business Server.
  
Este tema explica cómo instalar una actualización en un servidor de Enterprise Edition atrás final o un servidor Standard Edition.
  
Si un servidor de fondo atrás está inactivo durante al menos 30 minutos mientras se está actualizando, los usuarios pueden vaya al modo de resistencia. Cuando finalice la actualización y los servidores de fondo detrás otra vez ha conectado con los servidores frontales en el grupo, los usuarios se devuelven a la funcionalidad completa. Si la actualización dura menos de 30 minutos, los usuarios no se verán afectados.
  
### <a name="to-update-a-back-end-server-or-standard-edition-server"></a>Para actualizar un servidor back-end o un servidor Standard Edition

1. Inicie sesión en el servidor que desea actualizar como miembro del rol CsAdministrator.
    
2. Descargue la actualización extráigala en el disco duro local.
    
3. Iniciar el Skype para el Shell de administración de servidor empresarial: haga clic en **Inicio**, seleccione **Todos los programas**, haga clic en **Skype para negocios 2015**y, a continuación, haga clic en **Skype para el Shell de administración de servidor de Business**..
    
4. Dejar de Skype para Business Server services. En la línea de comandos, escriba:
    
    ```
    Stop-CsWindowsService
    ```

5. Detenga el servicio World Wide Web. En la línea de comandos, escriba:
    
    ```
    net stop w3svc
   ```

6. Cierre todos los Skype para windows de Shell de administración de servidor empresarial.
    
7. Instale la actualización.
    
8. Iniciar el Skype para el Shell de administración de servidor empresarial: haga clic en **Inicio**, seleccione **Todos los programas**, haga clic en **Skype para negocios 2015**y, a continuación, haga clic en **Skype para el Shell de administración de servidor de Business**..
    
9. Dejar de Skype para servicios Business Server nuevo para detectar -d ensamblados de la caché de ensamblados Global (GAC). En la línea de comandos, escriba:
    
    ```
    Stop-CsWindowsService
    ```

10. Reinicie el servicio World Wide Web. En la línea de comandos, escriba:
    
    ```
    net start w3svc
    ```

11. Aplique los cambios realizados a las bases de datos de SQL Server mediante uno de los siguientes procedimientos:
    
    - Si se trata de un servidor de Enterprise Edition atrás final y no existen bases de datos colocadas en este servidor, como el archivado o bases de datos de supervisión, a continuación, escriba lo siguiente en una línea de comandos:
    
    ```
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>
    ```

    - Si se trata de un servidor de Enterprise Edition atrás final y hay colocadas las bases de datos en este servidor, a continuación, escriba lo siguiente en una línea de comandos:
    
    ```
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>  -ExcludeCollocatedStores
    ```

    - Si se trata de un servidor Standard Edition, escriba lo siguiente en una línea de comandos:
    
    ```
    Install-CsDatabase -Update -LocalDatabases

    ```


