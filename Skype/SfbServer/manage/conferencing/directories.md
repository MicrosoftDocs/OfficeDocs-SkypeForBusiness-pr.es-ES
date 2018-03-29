---
title: Crear directorios de conferencia en Skype Empresarial Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b124b229-7df5-4b7e-8c11-6661c8c8c051
description: 'Resumen: Conozca cómo crear directorios de conferencia en Skype para Business Server 2015.'
ms.openlocfilehash: aa261dbe92507fad2721f57d743be57bea89de2a
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="create-conference-directories-in-skype-for-business-server-2015"></a>Crear directorios de conferencia en Skype Empresarial Server 2015
 
**Resumen:** Aprenda a crear directorios de conferencia en Skype para Business Server 2015.
  
Directorios de conferencia mantienen una asignación entre el ID alfanumérico que un participante se utiliza para unirse a una conferencia al utilizar Skype para el negocio y el ID de conferencia sólo numérico que un participante de la conferencia de acceso telefónico utiliza para unirse a la conferencia. 
  
## <a name="create-a-conference-directory"></a>Crear un directorio de conferencia

Si crea varios directorios de conferencia, se asegurará de que los Id. de conferencia se mantienen cortos hasta que se haya creado un número significativo de conferencias. 
  
En una organización con un número establecido de conferencias por usuario, se recomienda crear un directorio de conferencia por cada 999 usuarios en el grupo de servidores. Si aplica esta sugerencia, los id. de conferencia, por lo general, se mantendrán cortos. Sin embargo, cuando el número de directorios de conferencia (en los grupos) exceda de 9, la longitud del id. de conferencia aumentará para dar soporte a otras conferencias.
  
El formato de un identificador de conferencia es el siguiente: 
  
```
<housekeeping digit (1 digit)><conference directory (usually 1-2 digits)><conference number (variable number of digits><check digit (1 digit)>

```

Para crear un directorio de conferencia, use el cmdlet **New-CsConferenceDirectory**. Por ejemplo, el siguiente comando crea un directorio de conferencia con la identidad 42, hospedado en el grupo atl-cs-001.litwareinc.com:
  
```
New-CsConferenceDirectory -Identity 42 -HomePool "atl-cs-001.litwareinc.com"

```

Para obtener más información, consulte [CsConferenceDirectory de nuevo](https://docs.microsoft.com/powershell/module/skype/new-csconferencedirectory?view=skype-ps).
  

