---
title: Convert-CcIsoToVhdx
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
ms.assetid: 216abec2-d354-4ee3-9999-0a6b350a4a5f
description: El cmdlet Convert-CcIsoToVhdx crea un archivo de disco duro virtual base (VHDX) mediante un archivo ISO Windows Server 2012 cliente. El archivo VHDX se usará durante la implementación de Skype for Business Edición de conector de nube.
ms.openlocfilehash: d168155c918ba1e8a3a576e543eed6693d0fb6faa5bd4fc23efd8c95b2b50fa1
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54349552"
---
# <a name="convert-ccisotovhdx"></a>Convert-CcIsoToVhdx
 
El cmdlet Convert-CcIsoToVhdx crea un archivo de disco duro virtual base (VHDX) mediante un archivo ISO Windows Server 2012 cliente. El archivo VHDX se usará durante la implementación de Skype for Business Edición de conector de nube.
  
```powershell
Convert-CcIsoToVhdx [[-IsoFilePath] <string>] [-GeneralizeOnly] [-PauseBeforeUpdate]
```

## <a name="parameters"></a>Parámetros

|**Parámetro**|**Required**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|:-----|
|IsoFilePath  <br/> | Obligatorio <br/> |System.String  <br/> | Ruta de acceso al archivo ISO Windows Server 2012 R2. <br/> |
|GeneralizeOnly  <br/> |Opcional  <br/> |System.Management.Automation.SwitchParameter  <br/> |Si el proceso de conversión falla durante Windows actualización, puede intentar configurar una red/proxy y actualizar Windows manualmente. Una vez finalizado el trabajo manual, puede ejecutar este cmdlet con el parámetro -GeneralizeOnly y completará los trabajos restantes.  <br/> |
|PauseBeforeUpdate  <br/> |Opcional  <br/> |System.Management.Automation.SwitchParameter  <br/> |Para actualizar Windows, es posible que sea necesaria una configuración manual de red o proxy en la máquina virtual base. El proceso de conversión se pausará antes Windows actualización si se proporciona este parámetro. Una vez realizada la configuración manual, puede reanudar el proceso.  <br/> |
   
## <a name="examples"></a>Ejemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Ejemplo 1

En el ejemplo siguiente se prepara el archivo VHDX base con un archivo ISO de Windows Server 2012 R2 ubicado en "C:\Windows_Server_2012_R2-EN-US-x64.ISO": 
  
```powershell
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" 
```

### <a name="example-2"></a>Ejemplo 2

Si el cmdlet Convert-CcIsoToVhdx durante Windows actualización, es probable que se deba a una configuración de red o proxy incorrecta. Puede seguir las instrucciones del mensaje de error e iniciar sesión en la máquina virtual base para solucionar el problema y actualizar Windows manualmente. Una vez finalizado el trabajo manual, vuelva a ejecutar el cmdlet con el parámetro -GeneralizeOnly para completar los trabajos restantes: 
  
```powershell
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" -GeneralizeOnly
```

### <a name="example-3"></a>Ejemplo 3

Si la configuración manual es necesaria para actualizar Windows, puede usar el parámetro -PauseBeforeUpdate. Con este parámetro, Cloud Connector se pausará antes del Windows de actualización. A continuación, puede completar la configuración manual y reanudar el proceso de conversión de la siguiente manera:
  
```powershell
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" -PauseBeforeUpdate 
```

## <a name="detailed-description"></a>Descripción detallada
<a name="DetailedDescription"> </a>

El cmdlet Convert-CcIsoToVhdx crea primero una máquina virtual base, instala algunos componentes básicos de los que depende Cloud Connector y, a continuación, instala Windows actualizaciones. Por último, generaliza la máquina virtual (sysprep) para obtener un archivo VHDX base que usarán las máquinas virtuales de un dispositivo de Cloud Connector. 
  
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Ninguno. El cmdlet Convert-CcIsoToVhdx no acepta entradas canalizadas. 
  
## <a name="return-types"></a>Tipos de valores devueltos
<a name="ReturnTypes"> </a>

Ninguno
  
## <a name="see-also"></a>Consulte también
<a name="ReturnTypes"> </a>

Ninguno
  

