---
title: ¿Qué son los planes de marcado?
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
- highpri
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.voice.dialplans.overview
- Calling Plans
description: 'Obtenga información sobre qué tipo de planes de llamadas de marcado (planes de marcado de llamadas RTC) están disponibles con Teams y cómo elegir uno para su organización.  '
ms.openlocfilehash: 77ee7801d43bd6a7cf9ae9a9e3fc74c302f8caa0
ms.sourcegitcommit: f0e2a5928e9b959daf45202b9f256f65c2087195
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68614253"
---
# <a name="what-are-dial-plans"></a>¿Qué son los planes de marcado?

Un plan de marcado es un conjunto con nombre de reglas de normalización que traducen los números de teléfono marcados por un usuario individual a un formato alternativo (típicamente E.164) con fines de autorización y enrutamiento de voz.

Un plan de marcado consiste en una o más reglas de normalización que definen cómo los números de teléfono expresados en varios formatos se traducen a un formato alternativo. La misma cadena de marcado puede interpretarse y traducirse de manera diferente en diferentes planes de marcado, por lo que, según el plan de marcado asignado a un usuario determinado, el mismo número marcado se puede traducir y enrutar de forma diferente. Puede haber un máximo de 1000 planes de marcado inquilino.

Consulte [Crear y administrar planes de marcado](create-and-manage-dial-plans.md) para crear y administrar planes de marcado inquilinos.

## <a name="tenant-dial-plan-scope"></a>Alcance de un plan de marcado inquilino

El alcance de un plan de marcado determina el nivel jerárquico en el que se puede aplicar. Los clientes obtienen el plan de marcado adecuado a través de la configuración de aprovisionamiento que se proporciona automáticamente cuando los usuarios inician sesión en Teams. Como administrador, puede administrar y asignar niveles de ámbito del plan de marcado mediante el Centro de administración de Microsoft Teams o PowerShell remoto.

En Teams, hay dos tipos de planes de marcado: de alcance de servicio y de inquilino (que es para su organización). Se define un plan de marcado de alcance de servicio para cada país o región donde sistema telefónico está disponible. A cada usuario se le asigna automáticamente el plan de marcado del país de servicio que coincide con la ubicación de uso asignada al usuario. No puede cambiar el plan de marcado del país de servicio, pero puede crear planes de marcado de alcance inquilino que aumenten el plan de marcado del país de servicio. A medida que se aprovisionan los clientes, obtienen un "plan de marcado efectivo", que es una combinación del plan de marcado del país de servicio y el plan de marcado inquilino de alcance adecuado. Por lo tanto, no es necesario definir todas las reglas de normalización de los planes de marcado de inquilino ya que es posible que existan en el plan de marcado del país de servicio.

Los planes de marcado de inquilino se pueden dividir en dos ámbitos: alcance de inquilino o ámbito de usuario. Si un inquilino define y asigna un plan de marcado de alcance de usuario, ese usuario recibirá un plan de marcado efectivo del plan de marcado del país de servicio del usuario y el plan de marcado del usuario asignado. Si un inquilino define un plan de marcado de alcance inquilino pero no asigna un plan de marcado de alcance de usuario, ese usuario recibirá un plan de marcado efectivo del plan de marcado del país de servicio del usuario y el plan de marcado inquilino.

El siguiente es el modelo de herencia de planes de marcado en Teams.

![Cómo se heredan los planes de marcado en Teams.](media/b2744f33-ebbd-4c23-bfba-1747312ab178.png)

Los siguientes son los posibles planes de marcado efectivos:

 **País de servicio** Si no se define ningún plan de marcado de alcance de inquilino y no se asigna al usuario un plan de marcado de alcance de usuario inquilino, el usuario recibirá un plan de marcado efectivo asignado al país de servicio asociado con su ubicación de uso.

 **Tenant Global - Service Country** Si se define un plan de marcado de usuario inquilino pero no se asigna a un usuario, el usuario aprovisionado recibirá un plan de marcado efectivo compuesto por un plan de marcado inquilino combinado y el plan de marcado del país de servicio asociado con su ubicación de uso.

 **Usuario inquilino - País de servicio** Si se define y se asigna un plan de marcado de usuario inquilino a un usuario, el usuario aprovisionado recibirá un plan de marcado efectivo compuesto por el plan de marcado de usuario inquilino combinado y el plan de marcado del país de servicio asociado con su ubicación de uso.

Consulte [Crear y administrar planes de marcado](create-and-manage-dial-plans.md) para crear sus planes de marcado inquilino.

> [!NOTE]
> En el escenario en el que no se aplican reglas de normalización del plan de marcado a un número marcado, la cadena marcada sigue normalizada para anteponer "+CC", donde CC es el código de país de la ubicación de uso del usuario de marcación. Esto se aplica a los planes de llamadas, al enrutamiento directo y a los escenarios de llamada entrante y rtc. Además, si una regla de normalización del plan de marcado inquilino da como resultado un número que no empieza con "+", el servicio de llamadas intentará normalizar el número recibido del cliente de Teams en función del plan de marcado inquilino y, si no coincide, en el plan de marcado de región. Para evitar la normalización doble, se recomienda que los clientes de enrutamiento directo normalicen los números para incluir un + y, a continuación, quite el + usando las reglas de traducción troncal. 

## <a name="planning-for-tenant-dial-plans"></a>Diseño de planes de marcado de inquilino

Para planificar los planes de marcado de inquilino siga estos pasos:

- **Paso 1** Decida si se necesita un plan de marcado personalizado para mejorar la experiencia de marcación del usuario. Por lo general, la necesidad de uno sería admitir la marcación no E.164, como las extensiones o el marcado nacional abreviado.

- **Paso 2** Determine si se necesitan planes de marcado de alcance de usuario inquilino o global, o ambos. Los planes de marcado de alcance de usuario son necesarios y los usuarios tienen diferentes requisitos de marcado local.

- **Step 3** Identify valid number patterns for each required dial plan. Only the number patterns that are not defined in the service level country dial plans are required.

- **Step 4** Develop an organization-wide scheme for naming dial plans. Adopting a standard naming scheme assures consistency across an organization and makes maintenance and updates easier.


## <a name="creating-your-new-dial-plan"></a>Crear su nuevo plan de marcado

Al crear un nuevo plan de marcado, debe ingresar la información que se solicita.

### <a name="name-and-simple-name"></a>Nombre y nombre simple

Para los planes de marcado de usuario, debe especificar un nombre descriptivo que identifique a los usuarios a los que se asignará el plan de marcado. El nombre simple del plan de marcado se rellena previamente con una cadena que se deriva del nombre del plan de marcado. El campo Nombre simple se puede editar, y esto le permite crear una convención de denominación más descriptiva para sus planes de marcado. El valor Nombre simple no puede estar en blanco y debe ser único. Es una buena práctica desarrollar una convención de denominación para toda su organización y usarla de manera coherente en todos los sitios y usuarios.

### <a name="description"></a>Descripción

Le recomendamos que escriba el nombre común y reconocible de la ubicación geográfica o el grupo de usuarios a los que se aplica el plan de marcado correspondiente.

### <a name="external-access-prefix"></a>Prefijo de acceso externo
<a name="bkexternalprefix"> </a>

Puede especificar un prefijo de acceso externo de hasta 4 caracteres (#, * y 0-9) si los usuarios deben marcar un dígito adicional o más (por ejemplo, 9) para obtener una línea externa.

> [!NOTE]
> Si especifica un prefijo de acceso externo, no es necesario crear una regla de normalización adicional para incorporar el prefijo.

Consulte [Crear y administrar planes de marcado](create-and-manage-dial-plans.md) para crear sus planes de marcado inquilino.

## <a name="normalization-rules"></a>Reglas de normalización
<a name="bknormalizationrule"> </a>

Normalization rules define how phone numbers expressed in various formats are to be translated. The same number string may be interpreted and translated differently, depending on the locale from which it is dialed. Normalization rules may be necessary if users need to be able to dial abbreviated internal or external numbers.

Se debe asignar una regla de normalización o más al plan de marcado. Las reglas de normalización coinciden de arriba a abajo, por lo que es importante el orden en que aparecen en un plan de marcado inquilino. Por ejemplo, si un plan de marcado inquilino tiene 10 reglas de normalización, se probará la lógica de coincidencia del número marcado a partir de la primera regla de normalización, luego pasará a la segunda, y así sucesivamente. Si se produce una coincidencia, se usará esa regla y no se intentará que coincida con las otras reglas definidas. Puede haber un máximo de 50 reglas de normalización en un plan de marcado inquilino determinado.

### <a name="determining-the-required-normalization-rules"></a>Determinar las reglas de normalización necesarias

Debido a que cualquier plan de marcado inquilino se combina eficazmente con el plan de marcado del país de servicio de un usuario determinado, es probable que las reglas de normalización del plan de marcado del país de servicio deban evaluarse para determinar qué reglas de normalización del plan de marcado inquilino son necesarias. Se puede utilizar efectivamente el cmdlet de **Get-CsEffectiveTenantDialPlan** para este propósito. El cmdlet toma la identidad del usuario como parámetro de entrada y devolverá todas las reglas de normalización aplicables al usuario.

### <a name="creating-normalization-rules"></a>Crear reglas de normalización
<a name="createrule"> </a>

Las reglas de normalización usan expresiones regulares de .NET Framework para especificar patrones de coincidencia numérica que usa el servidor para traducir cadenas de marcado al formato E.164. Las reglas de normalización se pueden crear al especificar la expresión habitual para la coincidencia y la traducción que se debe realizar al encontrarla. Al terminar puede ingresar un número de prueba para verificar que la regla de normalización funcione según lo esperado.

Para obtener más información sobre el uso de expresiones regulares de .NET Framework, consulte [Expresiones regulares de .NET Framework](/dotnet/standard/base-types/regular-expressions).

Consulte [Crear y administrar planes de marcado](create-and-manage-dial-plans.md) para crear y administrar reglas de normalización para los planes de marcado de inquilino.

> [!NOTE]
> Las reglas de normalización con el primer token como opcional no se admiten actualmente en dispositivos 3pip (por ejemplo, el modelo Polycom VVX 601). Si quieres aplicar reglas de normalización con opcionalidad en dispositivos 3pip, debes crear dos reglas de normalización en lugar de una. Por ejemplo, ¿la regla ^0? (999)$ debe sustituirse por las dos normas siguientes: (999)$ (Traducción:$1) y ^0(999)$ (Traducción:$1).


### <a name="sample-normalization-rules"></a>Reglas de normalización de muestra

The following table shows sample normalization rules that are written as .NET Framework regular expressions. The samples are examples only and are not meant to be a prescriptive reference for creating your own normalization rules.

<a name="regularexpression"> </a>
**Reglas de normalización con expresiones regulares de .NET Framework**

| Nombre de la regla<br/> | Descripción<br/> | Patrón de números<br/> | Conversión<br/> | Ejemplo<br/> |
|:-----|:-----|:-----|:-----|:-----|
|4digitExtension  <br/> |Traduce extensiones de 4 dígitos.  <br/> |^(\\d{4})$  <br/> |+1425555$1  <br/> |0100 se traduce a +14255550100  <br/> |
|5digitExtension  <br/> |Traduce extensiones de 5 dígitos.  <br/> |^5(\\d{4})$  <br/> |+1425555$1  <br/> |50100 se traduce a +14255550100  <br/> |
|7digitcallingRedmond  <br/> |Traduce números de 7 dígitos a números locales de Redmond.  <br/> |^(\\d{7})$  <br/> |+1425$1  <br/> |5550100 se traduce a +14255550100  <br/>|
|RedmondOperator  <br/> |Traduce 0 a Operador de Redmond.  <br/> |^0$  <br/> |+14255550100  <br/> |0 se traduce a +14255550100  <br/> |
|RedmondSitePrefix  <br/> |Traduce números con un prefijo de red (6) y el código de sitio de Redmond (222).  <br/> |^6222(\\d{4})$  <br/> |+1425555$1  <br/> |62220100 se traduce a +14255550100  <br/> |
|5digitRange  <br/> |Traduce extensiones de 5 dígitos a partir del rango de dígitos entre 3 y 7 inclusive.  <br/> |^([3-7]\\d{4})$  <br/> |+142555$1 <br/> |54567 se traduce a +14255554567  <br/> |
|Prefijoagregada  <br/> |Añade un prefijo de país delante de un número de 9 dígitos con restricciones en el primer y el tercer dígito.  <br/> |^([2-9]\\d\\d[2-9]\\d{6})$  <br/> |1$1  <br/> |4255554567 se traduce a 14255554567  <br/> |
|NoTranslation  <br/> |Coinciden 5 dígitos pero no hay traducción.  <br/> |^(\\d{5})$  <br/> |$1  <br/> |34567 se traduce a 34567  <br/> |

 **Plan de marcado de Redmond basado en las reglas de normalización que se describen anteriormente.**

 La siguiente tabla ilustra un plan de marcado de muestra para Redmond, Washington, Estados Unidos, basado en las reglas de normalización que se muestran en la tabla anterior.

| Plan de marcado de Redmond<br/> |
|:-----------------------|                                                                                                                      
| 5digitExtension <br/> |                                                                                                                                    
| 7digitcallingRedmond <br/> |
| RedmondSitePrefix <br/> |
| RedmondOperator <br/> |

> [!NOTE]
> Los nombres de las reglas de normalización que se muestran en la tabla anterior no incluyen espacios, pero es una cuestión de elección. Por ejemplo, el primer nombre de la tabla podría haberse escrito como "extensión de 5 dígitos" o "Extensión de 5 dígitos" y ser igualmente válido.

## <a name="related-topics"></a>Temas relacionados

[Crear y administrar planes de marcado](create-and-manage-dial-plans.md)

[Diferentes tipos de números de teléfono que se usan para Planes de llamada](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[Administrar los números de teléfono para su organización](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[Términos y condiciones de las llamadas de emergencia](emergency-calling-terms-and-conditions.md)

[Etiqueta de declinación de responsabilidades de llamadas de emergencia](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
