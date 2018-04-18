---
title: What are dial plans?
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz
ms.topic: article
ms.assetid: 2f0cfb59-1ca1-4e31-84ce-09d0b1a7ce1b
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
- Strat_SB_PSTN
description: 'Learn what type of dial calling plans (PSTN Calling dial plans) are available with Office 365 and how to choose one for your organization.  '
search.appverid:
- MED150
- MOE150
ms.openlocfilehash: c24727dec0a9d938b3b0e40ef6f47501944e70e1
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2018
---
# <a name="what-are-dial-plans"></a>What are dial plans?

[] Un plan de marcado es un conjunto determinado de reglas de normalización que traducen los números de teléfono marcados por un usuario individual a un formato alternativo (generalmente E.164) para fines de autorización y enrutamiento de llamada.
  
A dial plan consists of one or more normalization rules that define how phone numbers expressed in various formats are translated to an alternate format. The same dial string may be interpreted and translated differently in different dial plans, so depending on which dial plan is assigned to a given user, the same dialed number may be translated and routed differently.
  
See [Create and manage dial plans](create-and-manage-dial-plans.md) to create and manage tenant dial plans.
  
## <a name="tenant-dial-plan-scope"></a>Alcance de un plan de marcado inquilino

El alcance de un plan de marcado determina el nivel jerárquico en el que se puede aplicar. The scopes are different than in a Skype for Business Server 2015 on-premises deployment. Los clientes obtienen el plan de marcado adecuado a través de la configuración de abastecimiento provista automáticamente cuando los usuarios se registran en Skype Empresarial Online. Como administrador, usted puede gestionar y asignar niveles de alcance del plan de marcado con PowerShell remoto.
  
In Skype for Business Online, there are two types of dial plans - service scoped and tenant (which is for your organization) scoped. A service scoped dial plan is defined for every country/region where the Office 365 Phone System is available. Each user is automatically assigned the service country dial plan that matches the Office 365 Usage Location assigned to the user. You can't change the service country dial plan, but you can create tenant scoped dial plans, which augment the service country dial plan. As clients are provisioned, they obtain an "effective dial plan," which is a combination of the service country dial plan and the appropriately scoped tenant dial plan. Por lo tanto, no es necesario definir todas las reglas de normalización de los planes de marcado de inquilino ya que es posible que existan en el plan de marcado del país de servicio.
  
Los planes de marcado de inquilino se pueden dividir en dos alcances: el alcance de inquilino o el alcance de usuario. Si un inquilino define y asigna un plan de marcado de alcance de usuario, ese usuario recibirá un plan de marcado efectivo del plan de marcado del país de servicio del usuario y el plan de marcado del usuario asignado. Si un inquilino define un plan de marcado de alcance de inquilino pero no asigna un plan de marcado de alcance de usuario, ese usuario recibirá un plan de marcado efectivo del plan de marcado del país de servicio del usuario y el plan de marcado de inquilino.
  
El siguiente es el modelo de herencia de los planes de marcado en Skype Empresarial Online.
  
![How dial plans are inherited in Skype for Business Online.](../images/b2744f33-ebbd-4c23-bfba-1747312ab178.png)
  
Los siguientes son los posibles planes de marcado efectivos:
  
 **Service Country** If no tenant scoped dial plan is defined and no tenant user scoped dial plan is assigned to the provisioned user, the user will receive an effective dial plan mapped to the service country associated with their Office 365 Usage Location.
  
 **Tenant Global - Service Country** If a tenant user dial plan is defined but not assigned to a user, the provisioned user will receive an effective dial plan consisting of a merged tenant dial plan and the service country dial plan associated with their Office 365 Usage Location.
  
 **Tenant User - Service Country** If a tenant user dial plan is defined and assigned to a user, the provisioned user will receive an effective dial plan consisting of the merged tenant user dial plan and the service country dial plan associated with their Office 365 Usage Location.
  
See [Create and manage dial plans](create-and-manage-dial-plans.md) to create your tenant dial plans.
  
## <a name="planning-for-tenant-dial-plans"></a>Diseño de planes de marcado de inquilino

Para planificar los planes de marcado de inquilino siga estos pasos:
  
- **Step 1** Decide whether a custom dial plan is needed to enhance the user dialing experience. Typically, the need for one would be to support non-E.164 dialing, such as extensions or abbreviated national dialing.
    
- **Step 2** Determine whether tenant global or tenant user scoped dial plans are needed, or both. Los planes de marcado de alcance de usuario son necesarios y los usuarios tienen diferentes requisitos de marcado local.
    
- **Paso 3** Identificar una cantidad válida de patrones para cada plan de marcado necesario. Únicamente son necesarios los patrones de números que no están definidos en los planes de marcado del país de nivel de servicios.
    
- **Paso 4** Desarrollar un esquema a nivel de la organización para nombrar los planes de marcado. Al adoptar un esquema de denominación estándar se asegura la coherencia en una organización y se facilita el mantenimiento y las actualizaciones.
    
The [FastTrack](https://fasttrack.microsoft.com/microsoft365/capabilities?view=voice) has additional resources and partners that can assist you with implementing tenant dial plans.
  
## <a name="creating-your-new-tenant-dial-plan"></a>Crear su nuevo plan de marcado de inquilino

Al crear un nuevo plan de marcado, debe ingresar la información que se solicita.
  
### <a name="name-and-simple-name"></a>Nombre y nombre simple

For user dial plans, you should specify a descriptive name that identifies to the users the dial plan will be assigned. El Nombre simple del plan de marcado se completa previamente con una línea que se deriva del nombre del plan de marcado. El campo Nombre simple se puede editar, y esto le permite crear una convención de denominación más descriptiva para sus planes de marcado. El valor Nombre simple no puede estar en blanco y debe ser único. Es una buena práctica desarrollar una convención de denominación para toda su organización y usarla de manera coherente en todos los sitios y usuarios.
  
### <a name="description"></a>Descripción

Le recomendamos que escriba el nombre común y reconocible de la ubicación geográfica o el grupo de usuarios a los que se aplica el plan de marcado correspondiente.
  
### <a name="external-access-prefix"></a>Prefijo de acceso externo

> [!CAUTION]
> El prefijo de acceso externo aún no es compatible. 
  
Puede especificar un prefijo de acceso externo de hasta 4 caracteres (#, * y 0-9) si los usuarios deben marcar un dígito adicional o más (por ejemplo, 9) para obtener una línea externa.
  
> [!NOTE]
> Si especifica un prefijo de acceso externo, no es necesario crear una regla de normalización adicional para incorporar el prefijo. 
  
See [Create and manage dial plans](create-and-manage-dial-plans.md) to create your tenant dial plans.
  
## <a name="normalization-rules"></a>Reglas de normalización

Las reglas de normalización definen cómo se traducen los números expresados en varios formatos. La misma línea de número se puede interpretar y traducir de diferentes maneras, según la ubicación desde la que se marca. Las reglas de normalización pueden ser necesarias y los usuarios deben tener la capacidad de marcar números internos y externos abreviados.
  
Se debe asignar una regla de normalización o más al plan de marcado. Normalization rules are matched from top to bottom, so the order in which they appear in a tenant dial plan is important. Por ejemplo, si un plan de marcado inquilino tiene 10 reglas de normalización, se probará la lógica de coincidencia del número marcado a partir de la primera regla de normalización, luego pasará a la segunda, y así sucesivamente. Si se produce una coincidencia, se usará esa regla y no se intentará que coincida con las otras reglas definidas. Un plan de marcado inquilino determinado puede tener un máximo de 25 reglas de normalización.
  
### <a name="determining-the-required-normalization-rules"></a>Determinar las reglas de normalización necesarias

Como todo plan de marcado inquilino se combina efectivamente con un plan de marcado del país de servicio de un usuario dado, es probable que las reglas de normalización del plan de marcado del país de servicio deban ser evaluadas para determinar cuáles de ellas son necesarias por parte del plan de marcado inquilino. Se puede utilizar efectivamente el cmdlet de **Get-CsEffectiveTenantDialPlan** para este propósito. El cmdlet toma la identidad del usuario como parámetro de entrada y devolverá todas las reglas de normalización aplicables al usuario.
  
### <a name="creating-normalization-rules"></a>Crear reglas de normalización

Las reglas de normalización utilizan expresiones regulares de .NET Framework para especificar los patrones de coincidencia numérica que utiliza el servidor para traducir líneas de marcado a formato E.164 para realizar la búsqueda inversa de número. Las reglas de normalización se pueden crear al especificar la expresión habitual para la coincidencia y la traducción que se debe realizar al encontrarla. Al terminar puede ingresar un número de prueba para verificar que la regla de normalización funcione según lo esperado.
  
For details about using .NET Framework regular expressions, see [.NET Framework Regular Expressions](https://go.microsoft.com/fwlink/p/?linkId=140927).
  
See [Create and manage dial plans](create-and-manage-dial-plans.md) to create and manage normalization rules for your tenant dial plans.
  
### <a name="sample-normalization-rules"></a>Reglas de normalización de muestra

La siguiente tabla muestra reglas de normalización de muestra que se escriben como expresiones regulares de .NET Framework. Las muestras son meramente ejemplos y no sirven como referencia prescriptiva para crear sus propias reglas de normalización.
  
 **Normalization rules using .NET Framework regular expressions**
  
||||||
|:-----|:-----|:-----|:-----|:-----|
|**Nombre de la regla** <br/> |**Descripción** <br/> |**Patrón de números** <br/> |**Traducción** <br/> |**Ejemplo** <br/> |
|4digitExtension  <br/> |Traduce extensiones de 4 dígitos.  <br/> |^(\\d{4})$  <br/> |+1425555$1  <br/> |0100 se traduce a +14255550100  <br/> |
|5digitExtension  <br/> |Traduce extensiones de 5 dígitos.  <br/> |^5(\\d{4})$  <br/> |+1425555$1  <br/> |50100 se traduce a +14255550100  <br/> |
|7digitcallingRedmond  <br/> |Traduce números de 7 dígitos a números locales de Redmond.  <br/> |^(\\d{7})$  <br/> |+1425$1  <br/> |5550100 se traduce a +14255550100  <br/>|
|RedmondOperator  <br/> |Traduce 0 a Operador de Redmond.  <br/> |^0$  <br/> |+14255550100  <br/> |0 se traduce a +14255550100  <br/> |
|RedmondSitePrefix  <br/> |Traduce números con un prefijo de red (6) y el código de sitio de Redmond (222).  <br/> |^6222(\\d{4})$  <br/> |+1425555$1  <br/> |62220100 se traduce a +14255550100  <br/> |
|5digitRange  <br/> |Traduce extensiones de 5 dígitos a partir del rango de dígitos entre 3 y 7 inclusive.  <br/> |^([3-7]\\d{4})$  <br/> |+142570$1  <br/> |54567 se traduce a +14255554567  <br/> |
|PrefixAdded  <br/> |Añade un prefijo de país delante de un número de 9 dígitos con restricciones en el primer y el tercer dígito.  <br/> |^([2-9]\\d\\d[2-9]\\d{6})$  <br/> |1$1  <br/> |4255554567 se traduce a 14255554567  <br/> |
|NoTranslation  <br/> |Coinciden 5 dígitos pero no hay traducción.  <br/> |^(\\d{5})$  <br/> |$1  <br/> |34567 se traduce a 34567  <br/> |
   
 **Plan de marcado de Redmond basado en las reglas de normalización que se describen anteriormente.**
  
La siguiente tabla ilustra un plan de marcado de muestra para Redmond, Washington, Estados Unidos, basado en las reglas de normalización que se muestran en la tabla anterior.
|:-----| |**Redmond dial plan** <br/> | |5digitExtension <br/> | |7digitcallingRedmond <br/> | |RedmondSitePrefix <br/> | |RedmondOperator <br/> |
   
> [!NOTE]
> Los nombres de las reglas de normalización que se muestran en la tabla anterior no incluyen espacios, pero esto es opcional. Por ejemplo, el primer nombre de la tabla podría haberse escrito como "extensión de 5 dígitos" o "Extensión de 5 dígitos" y ser igualmente válido. 
  
## <a name="related-topics"></a>See also
[Crear y administrar planes de marcado](create-and-manage-dial-plans.md)

Puede obtener más información en [Conferencias de acceso telefónico en Office 365](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).

[Preguntas comunes sobre la transferencia de números de teléfono](transferring-phone-numbers-common-questions.md)

[Diferentes tipos de números de teléfono que se usan para Planes de llamada](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[Administrar los números de teléfono para su organización](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[Términos y condiciones de las llamadas de emergencia](emergency-calling-terms-and-conditions.md)

[Skype Empresarial Online: Etiqueta de aviso de declinación de responsabilidades de las llamadas de emergencia](https://go.microsoft.com/fwlink/?LinkID=692099)

  
 