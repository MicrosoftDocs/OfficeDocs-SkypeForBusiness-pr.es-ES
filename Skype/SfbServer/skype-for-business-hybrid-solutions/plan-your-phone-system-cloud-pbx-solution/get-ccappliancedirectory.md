---
title: Get-CcApplianceDirectory
ms.reviewer: ''
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
ms.openlocfilehash: bcd80018b2286865945638f66c13e4c5198346dc
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30891486"
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

En el ejemplo siguiente se muestra la carpeta actual donde se almacenan los archivos de configuración y la máquina virtual de los componentes de conector en la nube:
  
```
Get-CcApplianceDirectory
```

## <a name="detailed-description"></a>Descripción detallada
<a name="DetailedDescription"> </a>

El cmdlet Get-CcApplianceDirectory muestra donde se almacenan todos los archivos de configuración y la máquina virtual, los registros y los certificados externos para el dispositivo de conector en la nube.
  
Cada dispositivo de conector en la nube tiene cuatro componentes: el servidor de mediación, el almacén de Administración Central, el servidor perimetral y un controlador de dominio. La carpeta predeterminada es C:\Users\%userprofile%\CloudConnector\ApplianceRoot. Puede cambiar esta carpeta usando el cmdlet Set-CCApplianceDirectory.
  
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Ninguno. El cmdlet Get-CCApplianceDirectory no acepta entradas canalizadas.
  
## <a name="return-types"></a>Tipos de valores devueltos
<a name="ReturnTypes"> </a>

El comando devuelve una ruta de archivo.
  
## <a name="see-also"></a>Consulte también
<a name="ReturnTypes"> </a>

[Set-CcApplianceDirectory](set-ccappliancedirectory.md)
  

