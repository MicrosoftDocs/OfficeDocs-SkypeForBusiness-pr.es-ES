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
localization_priority: Normal
ms.assetid: 216abec2-d354-4ee3-9999-0a6b350a4a5f
description: El cmdlet Convert-CcIsoToVhdx crea un archivo de disco duro virtual base (VHDX) mediante un archivo ISO de Windows Server 2012 R2 proporcionado por el cliente. El archivo VHDX se usará durante la implementación de Skype Empresarial Cloud Connector Edition.
ms.openlocfilehash: 780002c54a77746c51f418cae077ffcc9b1fb608
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2020
ms.locfileid: "41001350"
---
# <a name="convert-ccisotovhdx"></a>Convert-CcIsoToVhdx
 
El cmdlet Convert-CcIsoToVhdx crea un archivo de disco duro virtual base (VHDX) mediante un archivo ISO de Windows Server 2012 R2 proporcionado por el cliente. El archivo VHDX se usará durante la implementación de Skype Empresarial Cloud Connector Edition.
  
```powershell
Convert-CcIsoToVhdx [[-IsoFilePath] <string>] [-GeneralizeOnly] [-PauseBeforeUpdate]
```

## <a name="parameters"></a>Parámetros

|**Parámetro**|**Requerida.**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|:-----|
|IsoFilePath  <br/> | Requerido <br/> |System.String  <br/> | La ruta de acceso al archivo ISO de Windows Server 2012 R2.  <br/> |
|GeneralizeOnly  <br/> |Opcional  <br/> |System.Management.Automation.SwitchParameter  <br/> |Si se produce un error en el proceso de conversión durante la actualización de Windows, puede intentar configurar una red y un proxy, y actualizar Windows manualmente. Después de completar las tareas manuales, podrá ejecutar este cmdlet con el parámetro -GeneralizeOnly para que finalicen los trabajos restantes.   <br/> |
|PauseBeforeUpdate  <br/> |Opcional  <br/> |System.Management.Automation.SwitchParameter  <br/> |Para actualizar Windows, podría ser necesario realizar una configuración manual de la red o del proxy en la máquina virtual base. El proceso de conversión se pondrá en pausa antes de la actualización de Windows si se proporciona este parámetro. Al finalizar la configuración manual, podrá reanudar el proceso.   <br/> |
   
## <a name="examples"></a>Ejemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Ejemplo 1

El siguiente ejemplo prepara el archivo VHDX base mediante un archivo ISO de Windows Server 2012 R2 que se encuentra en "C:\Windows_Server_2012_R2-EN-US-x64.ISO":  
  
```powershell
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" 
```

### <a name="example-2"></a>Ejemplo 2

Si se produce un error en el cmdlet Convert-CcIsoToVhdx durante la actualización de Windows, probablemente se deba a una configuración incorrecta de la red o el proxy. Puede seguir las instrucciones del mensaje de error e iniciar sesión en la máquina virtual base para corregir el problema y actualizar Windows manualmente. Después de completar las tareas manuales, ejecute el cmdlet de nuevo con el parámetro -GeneralizeOnly para que finalicen los trabajos restantes: 
  
```powershell
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" -GeneralizeOnly
```

### <a name="example-3"></a>Ejemplo 3

Si se requiere la configuración manual para actualizar Windows, puede usar el parámetro -PauseBeforeUpdate. Con este parámetro, Cloud Connector se detendrá antes del proceso de Windows Update. Después podrá completar la configuración manual y reanudar el proceso de conversión de la siguiente manera:
  
```powershell
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" -PauseBeforeUpdate 
```

## <a name="detailed-description"></a>Descripción detallada
<a name="DetailedDescription"> </a>

El cmdlet Convert-CcIsoToVhdx crea en primer lugar una VM básica, instala algunos componentes básicos de los que depende Cloud Connector y, después, instala actualizaciones de Windows. Por último, generaliza la máquina virtual (Sysprep) para obtener un archivo VHDX básico que las máquinas virtuales de un dispositivo de conector de nube usarán. 
  
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Ninguno. El cmdlet Convert-CcIsoToVhdx no acepta entradas canalizadas. 
  
## <a name="return-types"></a>Tipos de valores devueltos
<a name="ReturnTypes"> </a>

Ninguno 
  
## <a name="see-also"></a>Consulte también
<a name="ReturnTypes"> </a>

Ninguno
  

