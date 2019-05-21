---
title: Configurar la supervisión SCOM
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Después de migrar a Microsoft Skype empresarial Server 2019, debe completar algunas tareas para configurar la 2019 de Skype empresarial Server para que funcione con System Center Operations Manager.
ms.openlocfilehash: 141154a8bd678f15fcc919b2dd70a50ca9d4dcca
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34284504"
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
    
   ```
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health"
   ```

   ```
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health\CentralDiscoveryCandidate"
   ```

    > [!NOTE]
    > Siempre que edite el registro, es posible que se produzca un error en el comando si la clave del registro ya existe. Si tiene esto, puede ignorar el error sin riesgos. 
  
### <a name="configure-your-primary-system-center-operations-manager-management-server-to-override-the-candidate-central-discovery-watcher-node"></a>Configure su servidor de administración principal de System Center Operations Manager para invalidar el nodo de supervisor de detección central candidato.

1. En un equipo en el que se haya instalado la consola de System Center Operations Manager, expanda los **objetos del módulo de administración** y seleccione descubrimientos de **objetos**.
    
2. Haga clic en **cambiar ámbito** .
    
3. En la página **objetos del módulo de administración del ámbito** , seleccione candidato de detección de **LS**.
    
4. Invalide el **valor efectivo candidato** a la detección de LS al nombre del servidor candidato elegido en el procedimiento anterior. 
    
Para finalizar los cambios, reinicie el servicio de mantenimiento en el servidor de administración de raíz de System Center Operations Manager.
  

