---
title: Get-CcApplianceDirectory
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c2fda202-db2f-4122-b630-7df11a697c5f
description: 'El cmdlet Get-CcApplianceDirectory recupera el directorio de trabajo del servidor host de Skype Empresarial Cloud Connector Edition. Todos los archivos de implementación se almacenan en este directorio. '
ms.openlocfilehash: c5c445e6017d8af81b681b70bbabcf2ba8bedd78
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="get-ccappliancedirectory"></a>Get-CcApplianceDirectory
 
El cmdlet Get-CcApplianceDirectory recupera el directorio de trabajo del servidor host de Skype Empresarial Cloud Connector Edition. Todos los archivos de implementación se almacenan en este directorio.  
  
Este cmdlet se aplica a Skype Empresarial Cloud Connector Edition 1.4.1, 1.4.2.
  
```
Get-CcApplianceDirectory
```

## <a name="parameters"></a>Parámetros

Ninguno
  
## <a name="examples"></a>Ejemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Ejemplo 1

En el ejemplo siguiente se muestra la carpeta actual donde se almacenan los archivos de configuración y la máquina virtual de componentes del conector de la nube:
  
```
Get-CcApplianceDirectory
```

## <a name="detailed-description"></a>Descripción detallada
<a name="DetailedDescription"> </a>

La muestra del cmdlet Get-CcApplianceDirectory donde se almacenan todos los archivos de configuración y la máquina virtual, registros y certificados externos para el dispositivo conector de nube.
  
Cada dispositivo conector de nube tiene cuatro componentes: un controlador de dominio, servidor perimetral, almacén de Administración Central y servidor de mediación. La carpeta predeterminada es C:\Users\%userprofile%\CloudConnector\ApplianceRoot. Puede cambiar esta carpeta usando el cmdlet Set-CCApplianceDirectory.
  
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Ninguno. El cmdlet Get-CCApplianceDirectory no acepta entradas canalizadas.
  
## <a name="return-types"></a>Tipos de valores devueltos
<a name="ReturnTypes"> </a>

El comando devuelve una ruta de archivo.
  
## <a name="see-also"></a>Consulte también
<a name="ReturnTypes"> </a>

[Conjunto de CcApplianceDirectory](set-ccappliancedirectory.md)
  

