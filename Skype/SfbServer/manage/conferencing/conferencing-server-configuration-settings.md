---
title: Administrar opciones de configuración del servidor de conferencias en Skype Empresarial Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 36bed690-6e22-4e11-88c1-b40a20836c6a
description: 'Resumen: Obtenga información sobre cómo administrar los valores de configuración de servidor de conferencia en Skype para Business Server 2015.'
ms.openlocfilehash: e59bfce2a1317d67b1a77f7277996d5a964a314f
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/05/2018
ms.locfileid: "19569466"
---
# <a name="manage-conferencing-server-configuration-settings-in-skype-for-business-server-2015"></a>Administrar opciones de configuración del servidor de conferencias en Skype Empresarial Server 2015
 
**Resumen:** Obtenga información sobre cómo administrar los valores de configuración de servidor de conferencia en Skype para Business Server 2015.
  
En este tema se describe cómo administrar opciones de configuración de conferencia. Para obtener más información acerca de cómo planear e implementar una conferencia, vea [Plan para las conferencias en Skype para Business Server 2015](../../plan-your-deployment/conferencing/conferencing.md) y [conferencia de implementar en Skype para Business Server 2015](../../deploy/deploy-conferencing/deploy-conferencing.md).
  
Determinación de la configuración de conferencia elementos tales como el tamaño máximo permitido para el contenido de las reuniones y los documentos; cantidad máxima de ancho de banda para el servicio de conferencia de uso compartido de la aplicación; límites de almacenamiento y períodos de expiración; descargas de las direcciones URL internas y externas del cliente compatible; punteros a las direcciones URL internas y externas donde los usuarios pueden obtener ayuda de conferencia y recursos; y los puertos usados para el uso compartido de aplicaciones, audio de cliente, las transferencias de archivos y el tráfico de medios. Estas opciones permiten administrar los servidores reales. Estas opciones de configuración se pueden establecer mediante el uso de Skype para Shell de administración de servidor empresarial.
  
Al instalar Skype para Business Server, el sistema proporciona una única colección de conferencia de opciones de configuración (la recopilación global). Si necesita crear una configuración personalizada para un sitio o servicio, puede hacerlo con el cmdlet **New-CsConferencingConfiguration**. Tenga en cuenta que las configuraciones nuevas solo se pueden aplicar al ámbito de sitio o servicio; no puede crear una colección global de opciones de configuración de conferencia, pero puede modificar la colección global con el cmdlet **Set-CsConferencingConfiguration**. Además, ningún sitio ni servicio puede hospedar más de una colección de opciones de configuración. Si intenta crear una configuración para el sitio de Redmond y el sitio ya tiene hospedada una colección de opciones de configuración de conferencia, el comando no se completará.
  
## <a name="manage-conferencing-configuration-settings-by-using-skype-for-business-server-management-shell"></a>Administrar la configuración de conferencia mediante el uso de Skype para Shell de administración de servidor empresarial

Para administrar la configuración de conferencia mediante el uso de Skype para Shell de administración de servidor empresarial, use los cmdlets siguientes:
  
**La configuración de conferencia**

|**Cmdlet**|**Descripción**|
|:-----|:-----|
|[Get-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csconferencingconfiguration?view=skype-ps) <br/> |Devuelve información sobre las opciones de configuración de conferencia para la organización.  <br/> |
|[New-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csconferencingconfiguration?view=skype-ps) <br/> |Crea una nueva colección de opciones de configuración de conferencias.  <br/> |
|[Remove-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingconfiguration?view=skype-ps) <br/> |Quita la colección especificada de opciones de configuración de conferencia.  <br/> |
|[Set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csconferencingconfiguration?view=skype-ps) <br/> |Modifica una colección existente de opciones de configuración de conferencias.  <br/> |
   
El siguiente comando crea una nueva colección de opciones de configuración de conferencia para el sitio de Redmond (site:Redmond). En este ejemplo, se incluye un parámetro adicional (Organization) que se usa para definir el valor de la propiedad Organization en Litwareinc: 
  
```
New-CsConferencingConfiguration -Identity site:Redmond -Organization Litwareinc
```

Tenga en cuenta que solo se puede tener una colección de este tipo por sitio; por lo tanto, este comando no se completará si el sitio Redmond ya tiene una colección de opciones de configuración de conferencia. 
  
El ejemplo siguiente define una nueva colección de opciones de configuración de conferencia, que se almacenan en memoria inicialmente y posteriormente se aplican al sitio de Redmond. 
  
El primer comando usa el cmdlet **New-CsConferencingConfiguration** para crear una colección de opciones de configuración en la memoria, almacenada en la variable $x. El parámetro InMemory especifica que la colección se debe crear en la memoria, en lugar de aplicarse de forma inmediata al sitio de Redmond.
  
Una vez creada la colección, el segundo comando establece el valor de la propiedad Organization en Litwareinc. 
  
Por último, el tercer comando usa el cmdlet **Set-CsConferencingConfiguration** para realmente aplicar la nueva configuración al sitio de Redmond:
  
```
$x = New-CsConferencingConfiguration -Identity site:Redmond -InMemory
$x.Organization = "Litwareinc"
Set-CsConferencingConfiguration -Instance $x
```

Si no llama al cmdlet **Set-CsConferencingConfiguration**, no se aplicará la nueva configuración. En su lugar, desaparecerá en cuanto finalice la sesión de Windows PowerShell o elimine la variable $x.
  

