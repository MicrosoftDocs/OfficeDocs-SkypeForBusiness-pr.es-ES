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
description: El Convert-CcIsoToVhdx cmdlet crea un archivo de disco duro virtual base (VHDX) mediante un archivo ISO de Windows Server 2012 R2 proporcionado por el cliente. El archivo VHDX se usará durante la implementación de Skype Empresarial Cloud Connector Edition.
ms.openlocfilehash: f6b16c27b82919f24b9ee0e3094fb03fffa6443b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802430"
---
# <a name="convert-ccisotovhdx"></a>Convert-CcIsoToVhdx
 
El Convert-CcIsoToVhdx cmdlet crea un archivo de disco duro virtual base (VHDX) mediante un archivo ISO de Windows Server 2012 R2 proporcionado por el cliente. El archivo VHDX se usará durante la implementación de Skype Empresarial Cloud Connector Edition.
  
```powershell
Convert-CcIsoToVhdx [[-IsoFilePath] <string>] [-GeneralizeOnly] [-PauseBeforeUpdate]
```

## <a name="parameters"></a>Parámetros

|**Parámetro**|**Required**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|:-----|
|IsoFilePath  <br/> | Obligatorio <br/> |System.String  <br/> | La ruta de acceso al archivo ISO de Windows Server 2012 R2. <br/> |
|GeneralizeOnly  <br/> |Opcional  <br/> |System.Management.Automation.SwitchParameter  <br/> |Si se produce un error en el proceso de conversión durante la actualización de Windows, puedes intentar configurar una red o proxy y actualizar Windows manualmente. Una vez finalizado el trabajo manual, puede ejecutar este cmdlet con el parámetro -GeneralizeOnly y completará los trabajos restantes.  <br/> |
|PauseBeforeUpdate  <br/> |Opcional  <br/> |System.Management.Automation.SwitchParameter  <br/> |Para actualizar Windows, es posible que sea necesario realizar alguna configuración manual de red o proxy en la máquina virtual base. El proceso de conversión se pausará antes de la actualización de Windows si se proporciona este parámetro. Una vez realizada la configuración manual, puede reanudar el proceso.  <br/> |
   
## <a name="examples"></a>Ejemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Ejemplo 1

En el siguiente ejemplo se prepara el archivo VHDX base mediante un archivo ISO de Windows Server 2012 R2 ubicado en "C:\Windows_Server_2012_R2-EN-US-x64.ISO": 
  
```powershell
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" 
```

### <a name="example-2"></a>Ejemplo 2

Si se produce Convert-CcIsoToVhdx cmdlet durante la actualización de Windows, es probable que se deba a una configuración de red o proxy incorrecta. Puede seguir las instrucciones del mensaje de error e iniciar sesión en la máquina virtual base para solucionar el problema y actualizar Windows manualmente. Una vez finalizado el trabajo manual, vuelva a ejecutar el cmdlet con el parámetro -GeneralizeOnly para completar los trabajos restantes: 
  
```powershell
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" -GeneralizeOnly
```

### <a name="example-3"></a>Ejemplo 3

Si la configuración manual es necesaria para actualizar Windows, puedes usar el parámetro -PauseBeforeUpdate. Con este parámetro, Cloud Connector se pausará antes del proceso de actualización de Windows. A continuación, puede completar la configuración manual y reanudar el proceso de conversión de la siguiente manera:
  
```powershell
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" -PauseBeforeUpdate 
```

## <a name="detailed-description"></a>Descripción detallada
<a name="DetailedDescription"> </a>

El cmdlet Convert-CcIsoToVhdx crea primero una máquina virtual base, instala algunos componentes básicos de los que depende Cloud Connector y, a continuación, instala las actualizaciones de Windows. Por último, generaliza la máquina virtual (sysprep) para obtener un archivo VHDX base que usarán las máquinas virtuales de un dispositivo de Cloud Connector. 
  
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Ninguno. El Convert-CcIsoToVhdx no acepta entradas canalizadas. 
  
## <a name="return-types"></a>Tipos de valores devueltos
<a name="ReturnTypes"> </a>

Ninguno
  
## <a name="see-also"></a>Vea también
<a name="ReturnTypes"> </a>

Ninguno
  

