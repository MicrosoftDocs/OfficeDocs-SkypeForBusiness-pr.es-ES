---
title: Get-CcApplianceDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c2fda202-db2f-4122-b630-7df11a697c5f
description: El Get-CcApplianceDirectory recupera el directorio de trabajo en el servidor host de Skype Empresarial Cloud Connector Edition. Todos los archivos de implementación se almacenan en este directorio.
ms.openlocfilehash: 04764f312138132fb34c0979423da5dc4696ee63
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41800850"
---
# <a name="get-ccappliancedirectory"></a>Get-CcApplianceDirectory
 
El Get-CcApplianceDirectory recupera el directorio de trabajo en el servidor host de Skype Empresarial Cloud Connector Edition. Todos los archivos de implementación se almacenan en este directorio. 
  
Este cmdlet se aplica a Skype Empresarial Cloud Connector Edition 1.4.1, 1.4.2.
  
```powershell
Get-CcApplianceDirectory
```

## <a name="parameters"></a>Parámetros

Ninguno
  
## <a name="examples"></a>Ejemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Ejemplo 1

En el siguiente ejemplo se muestra la carpeta actual donde se almacenan los archivos de configuración y de máquina virtual de los componentes de Cloud Connector:
  
```powershell
Get-CcApplianceDirectory
```

## <a name="detailed-description"></a>Descripción detallada
<a name="DetailedDescription"> </a>

El cmdlet Get-CcApplianceDirectory muestra dónde se almacenan todos los archivos de configuración y máquina virtual, registros y certificados externos para el dispositivo de Cloud Connector.
  
Cada dispositivo de Cloud Connector tiene cuatro componentes: servidor de mediación, almacén de administración central, servidor perimetral y controlador de dominio. La carpeta predeterminada es C:\Users \% userprofile%\CloudConnector\ApplianceRoot. Puede cambiar esta carpeta mediante el cmdlet Set-CCApplianceDirectory.
  
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Ninguno. El Get-CCApplianceDirectory no acepta entradas canalizadas.
  
## <a name="return-types"></a>Tipos de valores devueltos
<a name="ReturnTypes"> </a>

El comando devuelve una ruta de acceso de archivo.
  
## <a name="see-also"></a>Vea también
<a name="ReturnTypes"> </a>

[Set-CcApplianceDirectory](set-ccappliancedirectory.md)
  

