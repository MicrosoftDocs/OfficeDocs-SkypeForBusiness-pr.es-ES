---
title: Configurar la supervisión SCOM
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Después de migrar a Microsoft Skype empresarial Server 2019, debe completar algunas tareas para configurar la 2019 de Skype empresarial Server para que funcione con System Center Operations Manager.
ms.openlocfilehash: 79398336bf372fd2ca779d2ec2ff58dc5219da61
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813808"
---
# <a name="configure-scom-monitoring"></a>Configurar la supervisión SCOM

Después de migrar a Skype empresarial Server 2019, debe completar algunas tareas para configurar la 2019 de Skype empresarial Server para que funcione con System Center Operations Manager.
  
- Aplicar actualizaciones a un servidor elegido para administrar la lógica de detección centralizada.
    
- Actualice la clave del registro del candidato de detección central.
    
- Configure el servidor de administración principal de System Center Operations Manager para que invalide el nodo de detección central candidato.
    
A continuación se proporcionan instrucciones para llevar a cabo estas tareas.
  
### <a name="apply-updates-to-a-server-elected-to-manage-the-central-discovery-logic"></a>Aplicar actualizaciones a un servidor elegido para administrar la lógica de detección centralizada.

1. Elija un servidor que tenga instalados los archivos del agente System Center Operations Manager y esté configurado como un nodo de detección candidato. 
    
2. Aplicar actualizaciones a este servidor. Vea el tema sobre cómo [aplicar actualizaciones](apply-updates.md).
    
### <a name="update-the-central-discovery-candidate-server-registry-key"></a>Actualice la clave del registro del candidato de detección central.

1. En el servidor elegido para administrar la lógica de detección central, abra una ventana de comandos de Windows PowerShell. 
    
2. En la línea de comandos, escriba:
    
   ```PowerShell
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health"
   ```

   ```PowerShell
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health\CentralDiscoveryCandidate"
   ```

    > [!NOTE]
    > Siempre que edite el registro, es posible que se produzca un error en el comando si la clave del registro ya existe. Si tiene esto, puede ignorar el error sin riesgos. 
  
### <a name="configure-your-primary-system-center-operations-manager-management-server-to-override-the-candidate-central-discovery-watcher-node"></a>Configure su servidor de administración principal de System Center Operations Manager para invalidar el nodo de supervisor de detección central candidato.

1. En un equipo en el que se haya instalado la consola de System Center Operations Manager, expanda los **objetos del módulo de administración** y seleccione **descubrimientos de objetos**.
    
2. Haga clic en **cambiar ámbito** .
    
3. En la página **objetos del módulo de administración del ámbito** , seleccione candidato de detección de **LS**.
    
4. Invalide el **valor efectivo candidato** a la detección de LS al nombre del servidor candidato elegido en el procedimiento anterior. 
    
Para finalizar los cambios, reinicie el servicio de mantenimiento en el servidor de administración de raíz de System Center Operations Manager.
  

