---
title: Configurar la supervisión SCOM
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Después de migrar a Microsoft Skype empresarial Server 2019, debe realizar algunas tareas para configurar Skype empresarial Server 2019 para que funcione con System Center Operations Manager.
ms.openlocfilehash: ef40890cb3ac01d8223c4b9a9cd0c4712e544376
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754050"
---
# <a name="configure-scom-monitoring"></a>Configurar la supervisión SCOM

Después de migrar a Skype empresarial Server 2019, debe realizar algunas tareas para configurar Skype empresarial Server 2019 para que funcione con System Center Operations Manager.
  
- Aplicar actualizaciones a un servidor elegido para administrar la lógica de detección central.
    
- Actualice la clave de registro del servidor candidato de detección central.
    
- Configure el servidor de administración principal de System Center Operations Manager para invalidar el nodo de detección central candidato.
    
A continuación se proporcionan instrucciones para realizar cada una de estas tareas.
  
### <a name="apply-updates-to-a-server-elected-to-manage-the-central-discovery-logic"></a>Aplicar actualizaciones a un servidor elegido para administrar la lógica de detección central.

1. Elija un servidor que tenga los archivos del agente System Center Operations Manager instalados y esté configurado como un nodo de detección candidato. 
    
2. Aplicar actualizaciones a este servidor. Vea el tema [Apply updates](apply-updates.md).
    
### <a name="update-the-central-discovery-candidate-server-registry-key"></a>Actualice la clave de registro del servidor candidato de detección central.

1. En el servidor decidió administrar la lógica de detección central, abra una ventana de comandos de Windows PowerShell. 
    
2. En la línea de comandos, escriba lo siguiente:
    
   ```PowerShell
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health"
   ```

   ```PowerShell
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health\CentralDiscoveryCandidate"
   ```

    > [!NOTE]
    > Al cambiar el registro, puede recibir un error que indica que el comando ha fallado si la clave de registro ya existe. Si le pasa esto, puede ignorar el error de forma segura. 
  
### <a name="configure-your-primary-system-center-operations-manager-management-server-to-override-the-candidate-central-discovery-watcher-node"></a>Configure el servidor de administración principal de System Center Operations Manager para invalidar el nodo de monitor de detección central candidato.

1. En un PC donde se haya instalado la consola de System Center Operations Manager, expanda **Objetos del módulo de administración** y luego seleccione **Detecciones de objetos**.
    
2. Haga clic en **cambiar ámbito**
    
3. En la página **Objetos de módulo de administración de ámbito**, seleccione **Candidato de detección de LS**.
    
4. Reemplace el **Valor efectivo de Candidato de detección de LS** con el nombre del servidor candidato elegido en el procedimiento anterior. 
    
Para finalizar los cambios, reinicie el servicio de mantenimiento en el servidor de administración raíz de System Center Operations Manager.
  

