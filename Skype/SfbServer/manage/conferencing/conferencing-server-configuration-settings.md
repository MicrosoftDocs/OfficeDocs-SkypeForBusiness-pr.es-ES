---
title: Administrar las opciones de configuración del servidor de conferencia en Skype empresarial Server
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
ms.assetid: 36bed690-6e22-4e11-88c1-b40a20836c6a
description: 'Resumen: Aprenda a administrar la configuración de la configuración del servidor de conferencias en Skype empresarial Server.'
ms.openlocfilehash: c43734a2d79bf07023486eb163fff7bbef56e73f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818641"
---
# <a name="manage-conferencing-server-configuration-settings-in-skype-for-business-server"></a>Administrar las opciones de configuración del servidor de conferencia en Skype empresarial Server
 
**Resumen:** Aprenda a administrar la configuración de la configuración del servidor de conferencias en Skype empresarial Server.
  
En este tema se describe cómo administrar opciones de configuración de conferencia. Para obtener más información sobre cómo planear e implementar conferencias, consulte [planear la Conferencia en Skype empresarial Server](../../plan-your-deployment/conferencing/conferencing.md) e [implementar conferencias en Skype empresarial Server](../../deploy/deploy-conferencing/deploy-conferencing.md).
  
Las opciones de configuración de conferencias determinan aspectos como el máximo permitido para el contenido y los documentos de la reunión; cantidad máxima de ancho de banda para el servicio de conferencias de uso compartido de aplicaciones; límites de almacenamiento y períodos de expiración; las direcciones URL de las descargas internas y externas del cliente compatible. punteros a direcciones URL internas y externas donde los usuarios pueden obtener ayuda y recursos de conferencias; y los puertos que se usan para compartir aplicaciones, audio de cliente, transferencias de archivos y tráfico de medios. Esta configuración le permite administrar los servidores reales. Esta configuración se puede establecer mediante el shell de administración de Skype empresarial Server.
  
Al instalar Skype empresarial Server, el sistema le proporciona un único conjunto de parámetros de configuración de la Conferencia (la colección global). Si necesita crear una configuración personalizada para un sitio o servicio, puede hacerlo con el cmdlet **New-CsConferencingConfiguration**. Tenga en cuenta que las configuraciones nuevas solo se pueden aplicar al ámbito de sitio o servicio; no puede crear una colección global de opciones de configuración de conferencia, pero puede modificar la colección global con el cmdlet **Set-CsConferencingConfiguration**. Además, ningún sitio ni servicio puede hospedar más de una colección de opciones de configuración. Si intenta crear una configuración para el sitio de Redmond y el sitio ya tiene hospedada una colección de opciones de configuración de conferencia, el comando no se completará.
  
## <a name="manage-conferencing-configuration-settings-by-using-skype-for-business-server-management-shell"></a>Administrar las opciones de configuración de conferencias con el shell de administración de Skype empresarial Server

Para administrar los parámetros de configuración de conferencias con el shell de administración de Skype empresarial Server, use los siguientes cmdlets:
  
**Opciones de configuración de conferencia**

|**Cmdlet**|**Descripción**|
|:-----|:-----|
|[Get-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csconferencingconfiguration?view=skype-ps) <br/> |Devuelve información sobre las opciones de configuración de conferencia para la organización.  <br/> |
|[New-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csconferencingconfiguration?view=skype-ps) <br/> |Crea una nueva colección de opciones de configuración de conferencias.  <br/> |
|[Remove-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingconfiguration?view=skype-ps) <br/> |Quita la colección especificada de opciones de configuración de conferencia.  <br/> |
|[Set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csconferencingconfiguration?view=skype-ps) <br/> |Modifica una colección existente de opciones de configuración de conferencias.  <br/> |
   
El siguiente comando crea una nueva colección de opciones de configuración de conferencia para el sitio de Redmond (site:Redmond). En este ejemplo, se incluye un parámetro adicional (Organization) que se usa para definir el valor de la propiedad Organization en Litwareinc: 
  
```PowerShell
New-CsConferencingConfiguration -Identity site:Redmond -Organization Litwareinc
```

Tenga en cuenta que solo se puede tener una colección de este tipo por sitio; por lo tanto, este comando no se completará si el sitio Redmond ya tiene una colección de opciones de configuración de conferencia. 
  
El ejemplo siguiente define una nueva colección de opciones de configuración de conferencia, que se almacenan en memoria inicialmente y posteriormente se aplican al sitio de Redmond. 
  
El primer comando usa el cmdlet **New-CsConferencingConfiguration** para crear una colección de opciones de configuración en la memoria, almacenada en la variable $x. El parámetro InMemory especifica que la colección se debe crear en la memoria, en lugar de aplicarse de forma inmediata al sitio de Redmond.
  
Una vez creada la colección, el segundo comando establece el valor de la propiedad Organization en Litwareinc. 
  
Por último, el tercer comando usa el cmdlet **Set-CsConferencingConfiguration** para realmente aplicar la nueva configuración al sitio de Redmond:
  
```PowerShell
$x = New-CsConferencingConfiguration -Identity site:Redmond -InMemory
$x.Organization = "Litwareinc"
Set-CsConferencingConfiguration -Instance $x
```

Si no llama al cmdlet **Set-CsConferencingConfiguration**, no se aplicará la nueva configuración. En su lugar, desaparecerá en cuanto finalice la sesión de Windows PowerShell o elimine la variable $x.
  

