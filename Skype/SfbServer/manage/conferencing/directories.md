---
title: Crear directorios de conferencia en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: b124b229-7df5-4b7e-8c11-6661c8c8c051
description: 'Resumen: obtenga información sobre cómo crear directorios de conferencia en Skype Empresarial Server.'
ms.openlocfilehash: 21b8d6ad362bcabba2bdde2db2be92ea73da0605
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "58609347"
---
# <a name="create-conference-directories-in-skype-for-business-server"></a>Crear directorios de conferencia en Skype Empresarial Server
 
**Resumen:** Obtenga información sobre cómo crear directorios de conferencia en Skype Empresarial Server.
  
Los directorios de conferencia mantienen una asignación entre el identificador de reunión alfanumérico que un participante usa para unirse a una conferencia al usar Skype Empresarial y el identificador de conferencia de solo numérico que usa un participante de conferencia de acceso telefónico local para unirse a la conferencia. 
  
## <a name="create-a-conference-directory"></a>Crear un directorio de conferencias

Si crea varios directorios de conferencia, se asegurará de que los Id. de conferencia se mantienen cortos hasta que se haya creado un número significativo de conferencias. 
  
En una organización con un número establecido de conferencias por usuario, se recomienda crear un directorio de conferencia por cada 999 usuarios en el grupo de servidores. Con esta directriz, los IDs de conferencia generalmente se pueden mantener pequeños. Sin embargo, una vez que el número de directorios de conferencia (en todos los grupos) supere los 9, la longitud del id. de conferencia aumentará para admitir conferencias adicionales.
  
El formato de un identificador de conferencia es el siguiente: 
  
```console
  <housekeeping digit (1 digit)><conference directory (usually 1-2 digits> 
  <conference number (variable number of digits><check digit (1 digit)>
```

Para crear un directorio de conferencia, use el cmdlet **New-CsConferenceDirectory.** Por ejemplo, el siguiente comando crea un directorio de conferencia con la identidad 42, hospedado en el grupo atl-cs-001.litwareinc.com:
  
```PowerShell
New-CsConferenceDirectory -Identity 42 -HomePool "atl-cs-001.litwareinc.com"
```

Para obtener más información, [vea New-CsConferenceDirectory](/powershell/module/skype/new-csconferencedirectory?view=skype-ps).
