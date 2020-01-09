---
title: Aprovisionamiento de la topología para ejecutar la carga en escenarios de estrés y rendimiento
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 12/17/2015
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 143cf9bd-b935-494d-817c-a8b0ccc61eb8
description: El cambio o el aprovisionamiento de la topología de Skype empresarial Server 2015 permite a los usuarios ejecutar correctamente la herramienta de estrés y rendimiento.
ms.openlocfilehash: e58bfce5e618c6e62f272c0acb0b415cbb471d40
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992497"
---
# <a name="provisioning-the-topology-to-run-load-in-stress-and-performance-scenarios"></a>Aprovisionamiento de la topología para ejecutar la carga en escenarios de estrés y rendimiento
 
El cambio o el aprovisionamiento de la topología de Skype empresarial Server 2015 permite a los usuarios ejecutar correctamente la herramienta de estrés y rendimiento.
  
En función de la configuración y la configuración actuales de su implementación de Skype empresarial Server 2015, es posible que tenga que realizar algunos cambios en su entorno. A continuación se muestra una lista de esos cambios:
  
1. Establezca la Directiva de ejecución de Windows PowerShell en no restringido. Si no está seguro de lo que está configurado en este momento, puede abrir el shell de administración de Skype empresarial Server y ejecutar este comando:
    
   ```PowerShell
   Get-ExecutionPolicy
   ```

   Si no se devuelve el valor Unrestricted, tendrá que ejecutar lo siguiente:
    
   ```PowerShell
   Set-ExecutionPolicy -Unrestricted
   ```

2. Para configurar de forma eficaz Skype empresarial Server, necesitará lo siguiente:
    
    - Familiarícese con su topología de 2015 de Skype empresarial Server (como nombres de equipos, instancias de servicios, nombres de sitios y directivas).
    
    - Asigne algunos de los usuarios que se crean a grupos, por ejemplo, grupos de captura de grupo de respuesta (por ejemplo, URI de SIP).
    
3. Para ejecutar un script desde la línea de comandos, puede usar:
    
   ```PowerShell
   PowerShell.exe -file <path to the file>
   ```

4. Normalmente, después de ejecutar un script desde este paquete, la traza resultante se almacenará en un archivo en la misma ruta desde la que se ejecutó el script. También hay un formato de nombre, \<scriptName\>$h $ m $ s. txt. Por tanto, si ejecutaste el ArchivingPolicy. PS1 en 12:15 PM, recibirás un archivo de registro denominado ArchivingPolicy121500. txt.
    
5. Aunque proporcionamos estos ejemplos para la configuración del servidor, usted puede modificar la configuración y restaurarla o revertirla una vez que haya terminado de ejecutar las pruebas de carga.
    

