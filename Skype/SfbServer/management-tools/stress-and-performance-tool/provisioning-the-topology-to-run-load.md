---
title: Aprovisionamiento de la topología para ejecutar la carga en escenarios de esfuerzo y rendimiento
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 12/17/2015
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 143cf9bd-b935-494d-817c-a8b0ccc61eb8
description: Skype para aprovisionamiento o cambios en la topología empresarial Server 2015 para permitir a los usuarios ejecutar correctamente la herramienta de esfuerzo y rendimiento.
ms.openlocfilehash: 446c8d8154992540ffd8bfe18b07af7c54e864fe
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33906644"
---
# <a name="provisioning-the-topology-to-run-load-in-stress-and-performance-scenarios"></a>Aprovisionamiento de la topología para ejecutar la carga en escenarios de esfuerzo y rendimiento
 
Skype para aprovisionamiento o cambios en la topología empresarial Server 2015 para permitir a los usuarios ejecutar correctamente la herramienta de esfuerzo y rendimiento.
  
Dependiendo de la configuración existente y la configuración para la implementación de Skype para Business Server 2015, es posible que necesite realizar algunos cambios en el entorno. La siguiente es una lista de los cambios:
  
1. Establecer la directiva de ejecución de Windows PowerShell para Unrestricted. Si no está seguro de qué es establecer en la actualidad, puede abrir el Skype para Shell de administración de servidor empresarial y ejecute este comando:
    
   ```
   Get-ExecutionPolicy
   ```

   Si no se devuelve el valor Unrestricted, necesita ejecutar este a continuación:
    
   ```
   Set-ExecutionPolicy -Unrestricted
   ```

2. Para configurar de forma eficaz Skype para Business Server, necesitará:
    
    - Estar familiarizado con su Skype para topología empresarial Server 2015 (por ejemplo, los nombres de equipo, instancias de servicio, los nombres de sitios y las directivas).
    
    - Asignar algunos de los usuarios que se crean a grupos, como grupo de respuesta (por ejemplo, los URI de SIP) de grupos de extensiones.
    
3. Para ejecutar una secuencia de comandos desde la línea de comandos, puede usar:
    
   ```
   PowerShell.exe -file <path to the file>
   ```

4. Normalmente, una vez ejecutado una secuencia de comandos de este paquete, los seguimientos resultantes se almacenará en la misma ruta de acceso desde donde se ejecutó la secuencia de comandos en un archivo. No hay un formato de nomenclatura así, \<NombreDeSecuenciaDeComandos\>$h$m$s.txt. Por lo que si ejecutó el ArchivingPolicy.ps1 a las 12:15 P.M., obtendrá un archivo de registro denominado ArchivingPolicy121500.txt.
    
5. Mientras Adjuntamos estos ejemplos para la configuración del servidor, es le para modificar la configuración y para restaurar o deshaga el después de que haya terminado de ejecutar las pruebas de carga.
    

