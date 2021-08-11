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
description: Después de migrar a Microsoft Skype Empresarial Server 2019, debe completar algunas tareas para configurar Skype Empresarial Server 2019 para trabajar con System Center Operations Manager.
ms.openlocfilehash: 477fbd3c405328ffac4aa70a722120d375e95b295bf5a23d19882248d1ece54e
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54279618"
---
# <a name="configure-scom-monitoring"></a>Configurar la supervisión SCOM

Después de migrar a Skype Empresarial Server 2019, debe completar algunas tareas para configurar Skype Empresarial Server 2019 para trabajar con System Center Operations Manager.
  
- Aplicar actualizaciones a un servidor elegido para administrar la lógica de detección central.
    
- Actualice la clave de registro del servidor candidato de detección central.
    
- Configure el servidor de administración System Center Operations Manager para invalidar el nodo de detección central candidato.
    
A continuación se proporcionan instrucciones para realizar cada una de estas tareas.
  
### <a name="apply-updates-to-a-server-elected-to-manage-the-central-discovery-logic"></a>Aplicar actualizaciones a un servidor elegido para administrar la lógica de detección central.

1. Elija un servidor que tenga los archivos del agente System Center Operations Manager instalados y esté configurado como un nodo de detección candidato. 
    
2. Aplicar actualizaciones a este servidor. Vea el tema [Aplicar actualizaciones](apply-updates.md).
    
### <a name="update-the-central-discovery-candidate-server-registry-key"></a>Actualice la clave de registro del servidor candidato de detección central.

1. En el servidor elegido para administrar la lógica de detección central, abra una Windows PowerShell de comandos. 
    
2. En la línea de comandos, escriba lo siguiente:
    
   ```PowerShell
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health"
   ```

   ```PowerShell
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health\CentralDiscoveryCandidate"
   ```

    > [!NOTE]
    > Al cambiar el registro, puede recibir un error que indica que el comando ha fallado si la clave de registro ya existe. Si le pasa esto, puede ignorar el error de forma segura. 
  
### <a name="configure-your-primary-system-center-operations-manager-management-server-to-override-the-candidate-central-discovery-watcher-node"></a>Configure el servidor de System Center de administración de Operations Manager principal para invalidar el nodo de monitor de detección central candidato.

1. En un PC donde se haya instalado la consola de System Center Operations Manager, expanda **Objetos del módulo de administración** y luego seleccione **Detecciones de objetos**.
    
2. Haga clic **en Cambiar ámbito**
    
3. En la página **Objetos de módulo de administración de ámbito**, seleccione **Candidato de detección de LS**.
    
4. Reemplace el **Valor efectivo de Candidato de detección de LS** con el nombre del servidor candidato elegido en el procedimiento anterior. 
    
Para finalizar los cambios, reinicie el servicio de mantenimiento en el System Center de administración raíz de Operations Manager.
  

