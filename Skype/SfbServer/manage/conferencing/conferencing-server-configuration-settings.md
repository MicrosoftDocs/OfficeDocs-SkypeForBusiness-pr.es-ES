---
title: Administrar las opciones de configuración del servidor de conferencias en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 36bed690-6e22-4e11-88c1-b40a20836c6a
description: 'Resumen: obtenga información sobre cómo administrar las opciones de configuración del servidor de conferencias en Skype Empresarial Server.'
ms.openlocfilehash: 7f8714a4098285e955b559b2baf70d74957159a1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828290"
---
# <a name="manage-conferencing-server-configuration-settings-in-skype-for-business-server"></a>Administrar las opciones de configuración del servidor de conferencias en Skype Empresarial Server
 
**Resumen:** Obtenga información sobre cómo administrar las opciones de configuración del servidor de conferencias en Skype Empresarial Server.
  
En este tema se describe cómo administrar las opciones de configuración de conferencia. Para obtener más información acerca de cómo planear e implementar conferencias, vea [Plan for conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md) and Deploy [conferencing in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).
  
Las opciones de configuración de conferencia determinan aspectos como el tamaño máximo permitido para el contenido y los artículos de reuniones; cantidad máxima de ancho de banda para el servicio de conferencia de uso compartido de aplicaciones; límites de almacenamiento y períodos de expiración; las direcciones URL de las descargas internas y externas del cliente admitido; punteros a direcciones URL internas y externas donde los usuarios pueden obtener recursos y ayuda para conferencias; y los puertos usados para el uso compartido de aplicaciones, el audio del cliente, las transferencias de archivos y el tráfico multimedia. Esta configuración le permite administrar los propios servidores reales. Esta configuración se puede establecer mediante el Shell de administración de Skype Empresarial Server.
  
Al instalar Skype Empresarial Server, el sistema le proporciona una única colección de opciones de configuración de conferencia (la colección global). Si necesita crear una configuración personalizada para un sitio o servicio, puede hacerlo con el cmdlet **New-CsConferencingConfiguration**. Tenga en cuenta que la nueva configuración solo se puede aplicar en el ámbito de sitio o servicio; no puede crear una nueva colección global de opciones de configuración de conferencia, pero puede modificar la recopilación global mediante el cmdlet **Set-CsConferencingConfiguration.** Además, ningún sitio ni servicio puede hospedar más de una colección de opciones de configuración. Si intenta crear una configuración para el sitio de Redmond y el sitio ya tiene hospedada una colección de opciones de configuración de conferencia, el comando no se completará.
  
## <a name="manage-conferencing-configuration-settings-by-using-skype-for-business-server-management-shell"></a>Administrar las opciones de configuración de conferencia mediante el Shell de administración de Skype Empresarial Server

Para administrar las opciones de configuración de conferencia mediante el Shell de administración de Skype Empresarial Server, use los cmdlets siguientes:
  
**Opciones de configuración de conferencia**

|**Cmdlet**|**Descripción**|
|:-----|:-----|
|[Get-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csconferencingconfiguration?view=skype-ps) <br/> |Devuelve información sobre las opciones de configuración de conferencia de su organización.  <br/> |
|[New-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csconferencingconfiguration?view=skype-ps) <br/> |Crea una nueva colección de opciones de configuración de conferencia.  <br/> |
|[Remove-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingconfiguration?view=skype-ps) <br/> |Quita la colección especificada de opciones de configuración de conferencia.  <br/> |
|[Set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csconferencingconfiguration?view=skype-ps) <br/> |Modifica una colección existente de opciones de configuración de conferencias.  <br/> |
   
El siguiente comando crea una nueva colección de opciones de configuración de conferencia para el sitio redmond (site:Redmond). En este ejemplo, se incluye un parámetro adicional (Organization) que se usa para establecer el valor de la propiedad Organization en Litwareinc: 
  
```PowerShell
New-CsConferencingConfiguration -Identity site:Redmond -Organization Litwareinc
```

Tenga en cuenta que solo puede tener una colección de este tipo por sitio, por lo que este comando produciría un error si el sitio Redmond ya tiene una colección de opciones de configuración de conferencia. 
  
En el siguiente ejemplo se define una nueva colección de opciones de configuración de conferencia, que se almacenan inicialmente en la memoria y, a continuación, se aplican al sitio Redmond más adelante. 
  
El primer comando usa el cmdlet **New-CsConferencingConfiguration** para crear una nueva colección en memoria de configuraciones almacenadas en la variable $x. El parámetro InMemory especifica que la colección debe crearse en la memoria en lugar de aplicarse inmediatamente al sitio Redmond.
  
Una vez creada la colección, el segundo comando define el valor de la propiedad Organization en Litwareinc. 
  
Por último, el tercer comando usa el cmdlet **Set-CsConferencingConfiguration** para aplicar realmente la nueva configuración al sitio Redmond:
  
```PowerShell
$x = New-CsConferencingConfiguration -Identity site:Redmond -InMemory
$x.Organization = "Litwareinc"
Set-CsConferencingConfiguration -Instance $x
```

Si no llama al cmdlet **Set-CsConferencingConfiguration,** la nueva configuración nunca tendrá efecto. En su lugar, desaparecerán en cuanto finalice la sesión Windows PowerShell sesión o elimine la variable $x.
  

