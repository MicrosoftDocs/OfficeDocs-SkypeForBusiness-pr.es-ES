---
title: Configurar la supervisión de SCOM
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Después de migrar a Microsoft Skype para Business Server 2019, debe completar algunas tareas para configurar Skype para Business Server 2019 trabajar con System Center Operations Manager.
ms.openlocfilehash: c54038bc89c62a9911e684e451a66f4f12a23124
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "25373745"
---
# <a name="configure-scom-monitoring"></a>Configurar la supervisión de SCOM

Después de migrar a Skype para Business Server 2019, debe completar algunas tareas para configurar Skype para Business Server 2019 trabajar con System Center Operations Manager.
  
- Aplique las actualizaciones a un servidor elegido para administrar la lógica de detección central.
    
- Actualizar la clave del registro de detección central candidato server.
    
- Configure el servidor de administración de System Center Operations Manager principal para invalidar el nodo de detección central candidato.
    
A continuación se proporcionan instrucciones para llevar a cabo cada una de estas tareas.
  
### <a name="apply-updates-to-a-server-elected-to-manage-the-central-discovery-logic"></a>Aplique las actualizaciones a un servidor elegido para administrar la lógica de detección central.

1. Elija a un servidor que tiene System Center Operations Manager archivos del agente se instala y se configura como un nodo de detección candidato. 
    
2. Aplicar actualizaciones a este servidor. Vea el tema [aplicar actualizaciones](apply-updates.md).
    
### <a name="update-the-central-discovery-candidate-server-registry-key"></a>Actualizar la clave del registro de detección central candidato server.

1. En el servidor elegido para administrar la lógica de detección central, abra una ventana de comandos de Windows PowerShell. 
    
2. En la línea de comandos, escriba:
    
   ```
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health"
   ```

   ```
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health\CentralDiscoveryCandidate"
   ```

    > [!NOTE]
    > Cada vez que edite el registro, puede experimentar un error que el comando no se pudo si ya existe la clave del registro. Si sucede esto, puede ignorar el error. 
  
### <a name="configure-your-primary-system-center-operations-manager-management-server-to-override-the-candidate-central-discovery-watcher-node"></a>Configurar el servidor principal de administración de System Center Operations Manager para invalidar el nodo de Monitor de detección central candidato.

1. En un equipo donde se ha instalado la consola de System Center Operations Manager, expanda **Objetos del módulo de administración** y, a continuación, seleccione **Detecciones de objetos**.
    
2. Haga clic en **Cambiar ámbito**
    
3. En la página **Objetos del módulo de administración de ámbito** , seleccione **Candidato de detección de LS**.
    
4. Reemplazar el **Valor efectivo de candidato de detección de LS** en el nombre de servidor candidato elegido en el procedimiento anterior. 
    
Para finalizar los cambios, reinicie el servicio de mantenimiento en el servidor de administración de System Center Operations Manager raíz.
  

