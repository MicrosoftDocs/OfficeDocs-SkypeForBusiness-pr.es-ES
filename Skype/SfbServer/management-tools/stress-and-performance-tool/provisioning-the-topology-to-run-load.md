---
title: Aprovisionamiento de la topología para ejecutar la carga en escenarios de estrés y rendimiento
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
ms.date: 12/17/2015
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 143cf9bd-b935-494d-817c-a8b0ccc61eb8
description: Skype Empresarial Server la topología de 2015 o el aprovisionamiento para permitir que los usuarios ejecuten correctamente la herramienta De esfuerzo y rendimiento.
---

# <a name="provisioning-the-topology-to-run-load-in-stress-and-performance-scenarios"></a>Aprovisionamiento de la topología para ejecutar la carga en escenarios de estrés y rendimiento
 
Skype Empresarial Server la topología de 2015 o el aprovisionamiento para permitir que los usuarios ejecuten correctamente la herramienta De esfuerzo y rendimiento.
  
Según la configuración y la configuración existentes para la implementación de Skype Empresarial Server 2015, es posible que deba realizar algunos cambios en el entorno. A continuación se muestra una lista de estos cambios:
  
1. Establezca la directiva Windows PowerShell ejecución en Sin restricciones. Si no está seguro de a qué está establecido actualmente, puede abrir el Shell de administración de Skype Empresarial Server y ejecutar este comando:
    
   ```PowerShell
   Get-ExecutionPolicy
   ```

   Si no se devuelve el valor Unrestricted, tendrá que ejecutar lo siguiente:
    
   ```PowerShell
   Set-ExecutionPolicy -Unrestricted
   ```

2. Para configurar Skype Empresarial Server, deberás:
    
    - Familiarícese con Skype Empresarial Server topología de 2015 (como nombres de equipo, instancias de servicio, nombres de sitio y directivas).
    
    - Asigne algunos de los usuarios que se crean a grupos, como grupos de extensiones de grupo de respuesta (por ejemplo, URI de SIP).
    
3. Para ejecutar un script desde la línea de comandos, puede usar:
    
   ```PowerShell
   PowerShell.exe -file <path to the file>
   ```

4. Normalmente, después de ejecutar un script desde este paquete, los seguimientos resultantes se almacenarán en un archivo en la misma ruta de acceso desde la que se ha ejecutado el script. También hay un formato de nomenclatura, \<scriptname\>$h $m$s.txt. Por lo tanto, si ejecutó el ArchivingPolicy.ps1 a las 12:15 p. m., tendrá un archivo de registro denominado ArchivingPolicy121500.txt.
    
5. Aunque hemos proporcionado estos ejemplos para la configuración del servidor, es su función modificar la configuración y restaurarla o revertirla una vez que haya terminado de ejecutar las pruebas de carga.
    

