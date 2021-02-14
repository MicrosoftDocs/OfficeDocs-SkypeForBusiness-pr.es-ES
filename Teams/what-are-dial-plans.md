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
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.voice.dialplans.overview
- Calling Plans
description: 'Aprenda qué tipo de planes de llamadas de marcado (planes de marcado de llamadas RTC) están disponibles en Teams y cómo elegir uno para su organización.  '
ms.openlocfilehash: 9e6b9930c5106ec143563e0f69dd61ccb30d550c
ms.sourcegitcommit: 9c1f3a72fb166b49a4b68bcdb9a2868bf86ca680
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/19/2020
ms.locfileid: "49718594"
---
# <a name="what-are-dial-plans"></a>¿Qué son los planes de marcado?

[] Un plan de marcado es un conjunto determinado de reglas de normalización que traducen los números de teléfono marcados por un usuario individual a un formato alternativo (generalmente E.164) para fines de autorización y enrutamiento de llamada.

Un plan de marcado consiste en una o más reglas de normalización que definen cómo los números de teléfono expresados en varios formatos se traducen a un formato alternativo. La misma cadena de marcado se puede interpretar y traducir de diferentes maneras según los planes de marcado, por lo que, dependiendo del plan de marcado asignado a un usuario determinado, el mismo número marcado se puede traducir y enrutar de manera diferente. Puede haber un máximo de 1.000 planes de marcado inquilino.

Vea [Crear y administrar planes de marcado](create-and-manage-dial-plans.md) para crear y administrar planes de marcado de inquilino.

## <a name="tenant-dial-plan-scope"></a>Alcance de un plan de marcado inquilino

El alcance de un plan de marcado determina el nivel jerárquico en el que se puede aplicar. Los clientes obtienen el plan de marcado adecuado mediante la configuración de abastecimiento que se proporciona automáticamente cuando los usuarios inician sesión en Teams. Como administrador, puede administrar y asignar niveles de ámbito del plan de marcado mediante el Centro de administración de Microsoft Teams o PowerShell remoto.

En Teams, hay dos tipos de planes de marcado: de alcance de servicio y de alcance de inquilino (que son para su organización). Un plan de marcado de alcance de servicio se define para cada país o región donde Sistema telefónico está disponible. A cada usuario se le asigna automáticamente el plan de marcado del país de servicio que coincide con la ubicación de uso asignada al usuario. No puede cambiar el plan de marcado del país de servicio, pero puede crear planes de marcado de alcance de inquilino, que aumenten el plan de marcado del país de servicio. A medida que los clientes están aprovisionados, obtienen un "plan de marcado efectivo", que es una combinación del plan de marcado del país de servicio y el plan de marcado inquilino con un alcance adecuado. Por lo tanto, no es necesario definir todas las reglas de normalización de los planes de marcado inquilino ya que es posible que ya existan en el plan de marcado del país de servicio.

Los planes de marcado de inquilino se pueden dividir en dos ámbitos: alcance del inquilino o de usuario. Si un inquilino define y asigna un plan de marcado de alcance de usuario, dicho usuario recibirá un plan de marcado efectivo del plan de marcado del país de servicio del usuario y el plan de marcado del usuario asignado. Si un inquilino define un plan de marcado de alcance de inquilino pero no asigna un plan de marcado de alcance de usuario, ese usuario recibirá un plan de marcado efectivo del plan de marcado del país de servicio del usuario y el plan de marcado inquilino.

El siguiente es el modelo de herencia de los planes de marcado en Teams.

![Cómo se heredan los planes de marcado en Teams](media/b2744f33-ebbd-4c23-bfba-1747312ab178.png)

Los siguientes son los posibles planes de marcado efectivos:

 **País de servicio** Si no se define un plan de marcado de alcance de inquilino y no se asigna al usuario un plan de marcado de alcance de usuario inquilino, el usuario recibirá un plan de marcado efectivo asignado al país de servicio asociado con su ubicación de uso.

 **Inquilino global- País de servicio** Si se define un plan de marcado de usuario inquilino pero no se asigna a un usuario, el usuario aprovisionado recibirá un plan de marcado efectivo compuesto por un plan de marcado inquilino combinado y el plan de marcado del país de servicio asociado con su ubicación de uso.

 **Usuario inquilino - País de servicio** Si se define y se asigna un plan de marcado de usuario inquilino a un usuario, el usuario aprovisionado recibirá un plan de marcado efectivo compuesto por el plan de marcado de usuario inquilino combinado y el plan de marcado del país de servicio asociado con su ubicación de uso.

Vea [Crear y administrar planes de marcado](create-and-manage-dial-plans.md) para crear sus planes de marcado de inquilino.

> [!NOTE]
> En el caso de que no se apliquen reglas de normalización del plan de marcado a un número marcado, la cadena de marcado seguirá normalizada para anteponer "+CC", donde CC es el código de país de la ubicación de uso del usuario que marca. Esto se aplica a los planes de llamadas, enrutamiento directo y llamadas a conferencias RTC.

## <a name="planning-for-tenant-dial-plans"></a>Diseño de planes de marcado de inquilino

Para planificar los planes de marcado de inquilino siga estos pasos:

- **Paso 1** Decida si necesita un plan de marcado personalizado para mejorar la experiencia de marcado del usuario. Normalmente, sería necesario admitir un marcado que no sea E.164, como extensiones o marcado nacional abreviado.

- **Paso 2** Determine si se necesitan planes de marcado de alcance de usuario inquilino o de inquilino global, o ambos. Los planes de marcado de alcance de usuario son necesarios y los usuarios tienen diferentes requisitos de marcado local.

- **Paso 3** Identificar una cantidad válida de patrones para cada plan de marcado necesario. Únicamente son necesarios los patrones de números que no están definidos en los planes de marcado del país de nivel de servicios.

- **Paso 4** Desarrollar un esquema a nivel de la organización para nombrar los planes de marcado. Al adoptar un esquema de denominación estándar se asegura la coherencia en una organización y se facilita el mantenimiento y las actualizaciones.


## <a name="creating-your-new-tenant-dial-plan"></a>Crear su nuevo plan de marcado de inquilino

Al crear un nuevo plan de marcado, debe ingresar la información que se solicita.

### <a name="name-and-simple-name"></a>Nombre y nombre simple

Para los planes de marcado de usuario, debe especificar un nombre descriptivo que identifique los usuarios a los que se asignará el plan de marcado. El nombre simple del plan de marcado se rellena previamente con una cadena que se deriva del nombre del plan de marcado. El campo Nombre simple se puede editar, y esto le permite crear una convención de denominación más descriptiva para sus planes de marcado. El valor Nombre simple no puede estar en blanco y debe ser único. Es una buena práctica desarrollar una convención de denominación para toda su organización y usarla de manera coherente en todos los sitios y usuarios.

### <a name="description"></a>Descripción

Le recomendamos que escriba el nombre común y reconocible de la ubicación geográfica o el grupo de usuarios a los que se aplica el plan de marcado correspondiente.

### <a name="external-access-prefix"></a>Prefijo de acceso externo
<a name="bkexternalprefix"> </a>

Puede especificar un prefijo de acceso externo de hasta 4 caracteres (#, * y 0-9) si los usuarios deben marcar un dígito adicional o más (por ejemplo, 9) para obtener una línea externa.

> [!NOTE]
> Si especifica un prefijo de acceso externo, no es necesario crear una regla de normalización adicional para incorporar el prefijo.

Vea [Crear y administrar planes de marcado](create-and-manage-dial-plans.md) para crear sus planes de marcado de inquilino.

## <a name="normalization-rules"></a>Reglas de normalización
<a name="bknormalizationrule"> </a>

Las reglas de normalización definen cómo se traducen los números expresados en varios formatos. La misma línea de número se puede interpretar y traducir de diferentes maneras, según la ubicación desde la que se marca. Las reglas de normalización pueden ser necesarias y los usuarios deben tener la capacidad de marcar números internos y externos abreviados.

Se debe asignar una regla de normalización o más al plan de marcado. Las reglas de normalización coinciden de arriba a abajo, por lo que el orden en que aparecen en un plan de marcado inquilino es importante. Por ejemplo, si un plan de marcado inquilino tiene 10 reglas de normalización, se probará la lógica de coincidencia del número marcado a partir de la primera regla de normalización, luego pasará a la segunda, y así sucesivamente. Si se produce una coincidencia, se usará esa regla y no se intentará que coincida con las otras reglas definidas. Puede haber un máximo de 50 reglas de normalización en un plan de marcado inquilino determinado.

### <a name="determining-the-required-normalization-rules"></a>Determinar las reglas de normalización necesarias

Como todo plan de marcado inquilino se combina efectivamente con el plan de marcado del país de servicio de un usuario dado, es probable que las reglas de normalización del plan de marcado del país de servicio deban evaluarse a fin de determinar qué reglas de normalización del plan de marcado inquilino son necesarias. Se puede utilizar efectivamente el cmdlet de **Get-CsEffectiveTenantDialPlan** para este propósito. El cmdlet toma la identidad del usuario como parámetro de entrada y devolverá todas las reglas de normalización aplicables al usuario.

### <a name="creating-normalization-rules"></a>Crear reglas de normalización
<a name="createrule"> </a>

Las reglas de normalización usan expresiones regulares de .NET Framework para especificar patrones de coincidencia numérica que utiliza el servidor para traducir cadenas de marcado al formato E.164. Las reglas de normalización se pueden crear al especificar la expresión habitual para la coincidencia y la traducción que se debe realizar al encontrarla. Al terminar puede ingresar un número de prueba para verificar que la regla de normalización funcione según lo esperado.

Para obtener más información sobre el uso de expresiones regulares de .NET Framework, vea [Expresiones regulares de .NET Framework.](https://go.microsoft.com/fwlink/p/?linkId=140927)

Vea [Crear y administrar planes de marcado para](create-and-manage-dial-plans.md) crear y administrar reglas de normalización para sus planes de marcado inquilino.

> [!NOTE]
> Actualmente, las reglas de normalización con el primer token opcional no son compatibles con los dispositivos 3pip (por ejemplo, el modelo Polycom VVX 601). Si desea aplicar reglas de normalización con opcionalidad en dispositivos 3pip, debe crear dos reglas de normalización en lugar de una. Por ejemplo, la regla ^0? (999)$ debe sustituirse por las dos reglas siguientes: (999)$ (Traducción:$1) y ^0(999)$ (Traducción:$1).


### <a name="sample-normalization-rules"></a>Reglas de normalización de muestra

La siguiente tabla muestra reglas de normalización de muestra que se escriben como expresiones regulares de .NET Framework. Las muestras son meramente ejemplos y no sirven como referencia prescriptiva para crear sus propias reglas de normalización.

<a name="regularexpression"> </a> 
 **Reglas de normalización con expresiones regulares de .NET Framework**

| Nombre de la regla<br/> | Descripción<br/> | Patrón de números<br/> | Conversión<br/> | Ejemplo<br/> |
|:-----|:-----|:-----|:-----|:-----|
|4digitExtension  <br/> |Traduce extensiones de 4 dígitos.  <br/> |^(\\d{4})$  <br/> |+1425555$1  <br/> |0100 se traduce a +14255550100  <br/> |
|5digitExtension  <br/> |Traduce extensiones de 5 dígitos.  <br/> |^5(\\d{4})$  <br/> |+1425555$1  <br/> |50100 se traduce a +14255550100  <br/> |
|7digitcallingRedmond  <br/> |Traduce números de 7 dígitos a números locales de Redmond.  <br/> |^(\\d{7})$  <br/> |+1425$1  <br/> |5550100 se traduce a +14255550100  <br/>|
|RedmondOperator  <br/> |Traduce 0 a Operador de Redmond.  <br/> |^0$  <br/> |+14255550100  <br/> |0 se traduce a +14255550100  <br/> |
|RedmondSitePrefix  <br/> |Traduce números con un prefijo de red (6) y el código de sitio de Redmond (222).  <br/> |^6222(\\d{4})$  <br/> |+1425555$1  <br/> |62220100 se traduce a +14255550100  <br/> |
|Rango5dígit  <br/> |Traduce extensiones de 5 dígitos a partir del rango de dígitos entre 3 y 7 inclusive.  <br/> |^([3-7]\\d{4})$  <br/> |+142555$1 <br/> |54567 se traduce a +14255554567  <br/> |
|PrefixAdded  <br/> |Añade un prefijo de país delante de un número de 9 dígitos con restricciones en el primer y el tercer dígito.  <br/> |^([2-9]\\d\\d[2-9]\\d{6})$  <br/> |1$1  <br/> |4255554567 se traduce a 14255554567  <br/> |
|SinTraducción  <br/> |Coinciden 5 dígitos pero no hay traducción.  <br/> |^(\\d{5})$  <br/> |$1  <br/> |34567 se traduce a 34567  <br/> |

 **Plan de marcado de Redmond basado en las reglas de normalización que se describen anteriormente.**

 La siguiente tabla ilustra un plan de marcado de muestra para Redmond, Washington, Estados Unidos, basado en las reglas de normalización que se muestran en la tabla anterior.

| Plan de marcado de Redmond<br/> |
|:-----------------------|                                                                                                                      
| 5digitExtension <br/> |                                                                                                                                    
| 7digitcallingRedmond <br/> |
| RedmondSitePrefix <br/> |
| RedmondOperator <br/> |

> [!NOTE]
> Los nombres de las reglas de normalización que se muestran en la tabla anterior no incluyen espacios, pero esto es una elección. Por ejemplo, el primer nombre de la tabla podría haberse escrito como "extensión de 5 dígitos" o "Extensión de 5 dígitos" y ser igualmente válido.

## <a name="related-topics"></a>Temas relacionados

[Crear y administrar planes de marcado](create-and-manage-dial-plans.md)

[Diferentes tipos de números de teléfono que se usan para Planes de llamada](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[Administrar los números de teléfono para su organización](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[Términos y condiciones de las llamadas de emergencia](emergency-calling-terms-and-conditions.md)

[Etiqueta de declinación de responsabilidades en llamadas de emergencia](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
