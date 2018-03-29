---
title: Aprovisionamiento de la topología para ejecutar la carga en situaciones de estrés y rendimiento
ms.author: heidip
author: microsoftheidi
ms.date: 12/17/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 143cf9bd-b935-494d-817c-a8b0ccc61eb8
description: Skype para cambios de topología de servidor de negocios 2015 o provisioning para permitir a los usuarios ejecutar correctamente la herramienta de carga y rendimiento.
ms.openlocfilehash: 825dd56a7f2cb343eddd8cbed7e811cdc5154b9c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="provisioning-the-topology-to-run-load-in-stress-and-performance-scenarios"></a>Aprovisionamiento de la topología para ejecutar la carga en situaciones de estrés y rendimiento
 
Skype para cambios de topología de servidor de negocios 2015 o provisioning para permitir a los usuarios ejecutar correctamente la herramienta de carga y rendimiento.
  
Dependiendo de la configuración existente y la configuración de la implementación de Skype para Business Server 2015, puede que necesite realizar algunos cambios en su entorno. La siguiente es una lista de los cambios:
  
1. Establecer la directiva de ejecución de Windows PowerShell en Irrestricto. Si no estás seguro de lo que es establecido en la actualidad, puede abrir el Skype para el Shell de administración de servidor de Business y ejecute este comando:
    
  ```
  Get-ExecutionPolicy
  ```

  Si no se devuelve el valor Unrestricted, necesitará ejecutar este a continuación:
    
  ```
  Set-ExecutionPolicy -Unrestricted
  ```

2. Para configurar eficazmente Skype para Business Server, necesitará:
    
    - Estar familiarizado con su Skype para Business Server 2015 topología (por ejemplo, nombres de equipo, las instancias de servicio, los nombres de sitio y directivas).
    
    - Asignar algunos de los usuarios que se crean a grupos, como grupo de respuesta de captura de grupos (por ejemplo, URI de SIP).
    
3. Para ejecutar un script desde la línea de comandos, puede utilizar:
    
  ```
  PowerShell.exe -file <path to the file>
  ```

4. Normalmente, una vez ejecutado un script de este paquete, los seguimientos resultantes se guardará en un archivo en la misma ruta de acceso desde donde se ejecutó la secuencia de comandos. Hay también un formato de nombre \<scriptname\>$h$m$s.txt. Así que si ejecutó el ArchivingPolicy.ps1 a las 12:15 P.M., obtendrá un archivo de registro denominado ArchivingPolicy121500.txt.
    
5. Mientras que la configuración del servidor le hemos proporcionado en estos ejemplos, incumbe a usted para modificar su configuración y restaurar o hacerla girar después de que haya terminado de ejecutar las pruebas de carga.
    

