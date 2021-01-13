---
title: Aprovisionamiento de la topología para ejecutar la carga en escenarios de esfuerzo y rendimiento
ms.reviewer: ''
ms.author: v-cichur
author: cichur
ms.date: 12/17/2015
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 143cf9bd-b935-494d-817c-a8b0ccc61eb8
description: El aprovisionamiento o los cambios en la topología de Skype Empresarial Server 2015 permiten a los usuarios ejecutar correctamente la herramienta Stress and Performance.
ms.openlocfilehash: 8d422497d11c9e56e4d5b205269a09f96dffc136
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814940"
---
# <a name="provisioning-the-topology-to-run-load-in-stress-and-performance-scenarios"></a>Aprovisionamiento de la topología para ejecutar la carga en escenarios de esfuerzo y rendimiento
 
El aprovisionamiento o los cambios en la topología de Skype Empresarial Server 2015 permiten a los usuarios ejecutar correctamente la herramienta Stress and Performance.
  
Según la configuración y la configuración existentes para la implementación de Skype Empresarial Server 2015, es posible que deba realizar algunos cambios en su entorno. A continuación se muestra una lista de los cambios:
  
1. Establezca la directiva Windows PowerShell ejecución en Sin restricciones. Si no está seguro de a qué está configurado actualmente, puede abrir el Shell de administración de Skype Empresarial Server y ejecutar este comando:
    
   ```PowerShell
   Get-ExecutionPolicy
   ```

   Si no se devuelve el valor Sin restricciones, tendrá que ejecutar lo siguiente:
    
   ```PowerShell
   Set-ExecutionPolicy -Unrestricted
   ```

2. Para configurar Skype Empresarial Server de forma eficaz, tendrá que:
    
    - Familiarícese con la topología de Skype Empresarial Server 2015 (como nombres de equipo, instancias de servicio, nombres de sitio y directivas).
    
    - Asigne algunos de los usuarios que se crean a grupos, como grupos de extensiones de grupo de respuesta (por ejemplo, URI de SIP).
    
3. Para ejecutar un script desde la línea de comandos, puede usar:
    
   ```PowerShell
   PowerShell.exe -file <path to the file>
   ```

4. Normalmente, después de ejecutar un script desde este paquete, los seguimientos resultantes se almacenarán en un archivo en la misma ruta de acceso desde donde se ha ejecutado el script. También hay un formato de nomenclatura, \<scriptname\> $h$m$s.txt. Por lo tanto, si ejecutó la ArchivingPolicy.ps1 a las 12:15 p. m., verá un archivo de registro denominado ArchivingPolicy121500.txt.
    
5. Aunque hemos proporcionado estos ejemplos para la configuración del servidor, es su función modificar la configuración y restaurarla o revertirla una vez que haya terminado de ejecutar las pruebas de carga.
    

