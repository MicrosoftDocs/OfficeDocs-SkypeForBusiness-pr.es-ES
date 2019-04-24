---
title: Crear directorios de conferencia en Skype para Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b124b229-7df5-4b7e-8c11-6661c8c8c051
description: 'Resumen: Obtenga información sobre cómo crear directorios de conferencia en Skype para Business Server.'
ms.openlocfilehash: 9e79ca7e1b2f896746db998cc53983c04c6724ef
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32222754"
---
# <a name="create-conference-directories-in-skype-for-business-server"></a>Crear directorios de conferencia en Skype para Business Server
 
**Resumen:** Obtenga información sobre cómo crear directorios de conferencia en Skype para Business Server.
  
Directorios de conferencia mantienen una asignación entre el identificador de reunión alfanumérico que usa un participante para unirse a una conferencia cuando se usa Skype para la empresa y el identificador de conferencia sólo numérico que usa un participante de la conferencia de acceso telefónico para unirse a la conferencia. 
  
## <a name="create-a-conference-directory"></a>Crear un directorio de conferencia

Si crea varios directorios de conferencia, se asegurará de que los Id. de conferencia se mantienen cortos hasta que se haya creado un número significativo de conferencias. 
  
En una organización con un número establecido de conferencias por usuario, se recomienda crear un directorio de conferencia por cada 999 usuarios en el grupo de servidores. Si aplica esta sugerencia, los id. de conferencia, por lo general, se mantendrán cortos. Sin embargo, cuando el número de directorios de conferencia (en los grupos) exceda de 9, la longitud del id. de conferencia aumentará para dar soporte a otras conferencias.
  
El formato de un identificador de conferencia es el siguiente: 
  
```
  <housekeeping digit (1 digit)><conference directory (usually 1-2 digits> 
  <conference number (variable number of digits><check digit (1 digit)>
```

Para crear un directorio de conferencia, use el cmdlet **New-CsConferenceDirectory**. Por ejemplo, el siguiente comando crea un directorio de conferencia con la identidad 42, hospedado en el grupo atl-cs-001.litwareinc.com:
  
```
New-CsConferenceDirectory -Identity 42 -HomePool "atl-cs-001.litwareinc.com"
```

Para obtener más información, vea [New-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/new-csconferencedirectory?view=skype-ps).
  

