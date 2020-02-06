---
title: Crear directorios de conferencia en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b124b229-7df5-4b7e-8c11-6661c8c8c051
description: 'Resumen: Aprenda a crear directorios de conferencia en Skype empresarial Server.'
ms.openlocfilehash: 368248f18291b049b3478f20d3de4a11d4ae6f1c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818571"
---
# <a name="create-conference-directories-in-skype-for-business-server"></a>Crear directorios de conferencia en Skype empresarial Server
 
**Resumen:** Aprenda a crear directorios de conferencia en Skype empresarial Server.
  
Los directorios de conferencia mantienen una asignación entre el identificador de reunión alfanumérico que un participante usa para unirse a una conferencia cuando se usa Skype empresarial y el identificador de conferencia de acceso telefónico local que usa un participante de conferencia de acceso telefónico local para unirse a la Conferencia. 
  
## <a name="create-a-conference-directory"></a>Crear un directorio de conferencia

Si crea varios directorios de conferencia, se asegurará de que los Id. de conferencia se mantienen cortos hasta que se haya creado un número significativo de conferencias. 
  
En una organización con un número establecido de conferencias por usuario, se recomienda crear un directorio de conferencia por cada 999 usuarios en el grupo de servidores. Si aplica esta sugerencia, los id. de conferencia, por lo general, se mantendrán cortos. Sin embargo, cuando el número de directorios de conferencia (en los grupos) exceda de 9, la longitud del id. de conferencia aumentará para dar soporte a otras conferencias.
  
El formato de un identificador de conferencia es el siguiente: 
  
```
  <housekeeping digit (1 digit)><conference directory (usually 1-2 digits> 
  <conference number (variable number of digits><check digit (1 digit)>
```

Para crear un directorio de conferencia, use el cmdlet **New-CsConferenceDirectory**. Por ejemplo, el siguiente comando crea un directorio de conferencia con la identidad 42, hospedado en el grupo atl-cs-001.litwareinc.com:
  
```PowerShell
New-CsConferenceDirectory -Identity 42 -HomePool "atl-cs-001.litwareinc.com"
```

Para obtener más información, vea [New-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/new-csconferencedirectory?view=skype-ps).
  

