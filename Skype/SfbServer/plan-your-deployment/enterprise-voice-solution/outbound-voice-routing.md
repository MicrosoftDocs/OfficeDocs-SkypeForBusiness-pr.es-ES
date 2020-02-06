---
title: Planear el enrutamiento de voz saliente en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fde45195-6eb4-403c-9094-57df7fc0bd2a
description: Obtenga más información sobre el enrutamiento de voz saliente en Skype empresarial Server Enterprise Voice, como la configuración de enrutamiento de llamadas, los planes de marcado, las reglas de normalización, las directivas de voz, los registros de uso de RTC y las rutas de voz.
ms.openlocfilehash: 26bea8452db00657ae87b5acbdd3f986c637d6fe
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802580"
---
# <a name="plan-for-outbound-voice-routing-in-skype-for-business-server"></a>Planear el enrutamiento de voz saliente en Skype empresarial Server
 
Obtenga más información sobre el enrutamiento de voz saliente en Skype empresarial Server Enterprise Voice, como la configuración de enrutamiento de llamadas, los planes de marcado, las reglas de normalización, las directivas de voz, los registros de uso de RTC y las rutas de voz.
  
El enrutamiento de llamadas salientes se aplica a las llamadas de voz empresariales que están destinadas a una puerta de enlace de red telefónica conmutada (RTC), troncal o central de conmutación (PBX). Cuando un usuario de Skype empresarial realiza una llamada, el servidor normaliza el número de teléfono al formato E. 164, si es necesario, e intenta hacerlo coincidir con el URI del SIP. Si el servidor no puede establecer la coincidencia, aplica la lógica de enrutamiento de llamadas salientes basándose en la cadena de marcado proporcionada. Esta lógica la defines con la configuración de las opciones del servidor que se describe en la siguiente tabla.
  
**Configuración de enrutamiento de llamadas salientes de Skype empresarial Server**

|**Objeto**|**Descripción**|
|:-----|:-----|
|Plan de marcado  <br/> |Un plan de marcado es un conjunto de reglas de normalización especificado por el usuario que convierte números de teléfono para una ubicación especificada por el usuario, un usuario individual o un objeto de contacto a un formato estándar único (E.164) con fines de autorización telefónica y enrutamiento de llamadas.  <br/> |
|Regla de normalización  <br/> |Las reglas de normalización definen la forma en que los números de teléfono expresados en diversos formatos se van a redirigir en cada ubicación, usuario u objeto de contacto que se haya especificado. La misma cadena de marcado se puede interpretar y convertir de manera distinta en función de la ubicación desde la que se marque y la persona o el objeto de contacto que realice la llamada. Un conjunto de reglas de normalización asociado a una ubicación determinada constituye un plan de marcado.  <br/> |
|Directiva de voz  <br/> |Una directiva de voz asocia uno o varios registros de uso de RTC a un usuario o un grupo de usuarios. Además, proporciona una lista de características de llamada que se pueden habilitar o deshabilitar.  <br/> |
|Registro de uso de RTC  <br/> |Un registro de uso de RTC especifica la clase de llamada (por ejemplo, interna, local o de larga distancia) que pueden realizar los diversos usuarios o grupos de usuarios en una organización.  <br/> |
|Ruta de llamada  <br/> |Una ruta de llamada asocia los números de teléfono de destino a determinados troncos y a determinados registros de uso de RTC. Un tronco se considera una puerta de enlace RTC.  <br/> |
   
## <a name="dial-plans-and-normalization-rules"></a>Planes de marcado y reglas de normalización

Un plan de marcado es un conjunto de reglas de normalización especificado por el usuario que convierte números de teléfono para una ubicación especificada por el usuario, un usuario individual o un objeto de contacto a un formato estándar único (E.164) con fines de autorización telefónica y enrutamiento de llamadas. 
  
Las reglas de normalización definen la forma en que los números de teléfono expresados en diversos formatos se van a redirigir en cada ubicación, usuario u objeto de contacto que se haya especificado. La misma cadena de marcado se puede interpretar y convertir de manera distinta en función de la ubicación desde la que se marque y la persona o el objeto de contacto que realice la llamada.
  
### <a name="dial-plan-scope"></a>Ámbito del plan de marcado

El alcance de un plan de marcado determina el nivel jerárquico en el que se puede aplicar. En Skype empresarial Server, un usuario puede tener asignado un plan de marcado por usuario específico. Si no se asigna un plan de marcado de usuario, se aplica el plan de marcado del grupo de servidores front-end. Si no hay ningún plan de marcado de front end, se aplica el plan de marcado del sitio. Por último, si no hay otro plan de marcado aplicable al usuario, se aplica el plan de marcado global.
  
Los clientes obtienen niveles de ámbito del plan de marcado mediante la configuración de aprovisionamiento en banda que se proporciona cuando los usuarios inician sesión en Skype empresarial. Como administrador, puede administrar y asignar niveles de ámbito de plan de marcado mediante el panel de control de Skype empresarial Server.
  
> [!NOTE]
> El plan de marcado de la puerta de enlace de la red telefónica conmutada (RTC) de nivel de servicio se aplica a las llamadas entrantes de una determinada puerta de enlace. 
  
Los niveles de ámbito del plan de marcado se definen de la manera siguiente:
  
- **Plan de marcado de usuario**: se puede asignar a usuarios, grupos u objetos de contacto individuales. Las aplicaciones de voz pueden buscar un plan de marcado por usuario cuando una llamada se recibe con el contexto telefónico establecido en el predeterminado para el usuario. Con el fin de asignar un plan de marcado, un objeto de contacto se considera un usuario individual.
    
- **Plan de marcado de grupo**: puede crearse en el nivel de servicio para cualquier registrador o puerta de enlace RTC de la topología. Para definir un plan de marcado de grupo, necesitas especificar el servicio (puerta de enlace RTC o grupo de registrador) específico en el que se aplica el plan de marcado. 
    
- **Plan de marcado de sitio**: puede crearse para un sitio en su totalidad, salvo para los usuarios, los grupos o los objetos de contacto que estén asignados a un plan de marcado de grupo o de usuario. Para definir un plan de marcado de sitio, necesitas especificar el sitio en el que se aplica el plan de marcado.
    
- **Plan de marcado global**: el plan de marcado predeterminado que se instala con el producto. Puedes editar el plan de marcado global, pero no eliminarlo. Este plan de marcado se aplica a todos los usuarios, grupos y objetos de contacto de Enterprise Voice de su implementación, a menos que configure y asigne un plan de marcado con un ámbito más específico.
    
### <a name="planning-for-dial-plans"></a>Planificar planes de marcado

Para planificar un plan de marcado, haz lo siguiente:
  
- Haz una lista de todas las configuraciones regionales en las que la organización tiene una oficina.
    
    La lista necesita estar completa y actualizada. Necesitarás revisarla a medida que evolucione la organización de la compañía. En una compañía multinacional con numerosas sucursales pequeñas, esta tarea puede demandar mucho tiempo.
    
- Identifica patrones de números válidos para cada sitio.
    
    La tarea que más tiempo requiere en el marco de la planificación de los planes de marcado es la identificación de los patrones de números válidos para cada sitio. En algunos casos, se podrán copiar las reglas de normalización escritas para un plan de marcado en otros planes de marcado, sobre todo si los sitios correspondientes están dentro del mismo país o de la misma región, o incluso en el mismo continente. En otros casos, pequeñas modificaciones en los números de un plan de marcado pueden bastar para usarse en otros planes de marcado.
    
- Desarrolla un esquema aplicable a toda la organización para asignar nombres a los planes de marcado.
    
    Adoptar un esquema estándar de asignación de nombres asegura la coherencia en toda la organización y facilita los procesos de mantenimiento y actualización.
    
- Decide si son necesarios varios planes de marcado para una sola ubicación. 
    
    Si su organización mantiene un solo plan de marcado en varias ubicaciones, es posible que aún necesite crear un plan de marcado independiente para los usuarios de telefonía IP empresarial que migren desde una central de conmutación (PBX) y tengan que mantener las extensiones existentes.
    
- Decide si son necesarios los planes de marcado por usuario. Por ejemplo, si tiene usuarios en un sitio de sucursal que están registrados con el sitio central o tiene usuarios registrados en un dispositivo de sucursal con la supervivencia, puede tener en cuenta escenarios especiales de marcado para esos usuarios usando planes de marcado por usuario y reglas de normalización . Para obtener más detalles, mira [Plan for Enterprise Voice resiliency in Skype for Business Server](enterprise-voice-resiliency.md).
    
- Determina el ámbito del plan de marcado (como ya se ha explicado antes en este tema).
    
Para crear un plan de marcado, especifique los valores en los siguientes campos, según sea necesario, mediante el panel de control de Skype empresarial Server o el shell de administración de Skype empresarial.
  
#### <a name="name-and-simple-name"></a>Nombre y Nombre simple

En los planes de marcado de usuario necesitas asignar un nombre descriptivo que identifique a los usuarios, grupos u objetos de contacto a los que se asignará el plan de marcado. En el caso de planes de marcado de sitio, el campo Nombre se rellena previamente con el nombre del sitio y no se puede modificar. Para los planes de marcado de grupo, el campo nombre se rellenó previamente con la puerta de enlace RTC o el nombre de dominio completo del grupo de servidores front-end (FQDN) y no se puede cambiar.
  
El nombre simple del plan de marcado se ha rellenado previamente con una cadena que se deriva del nombre del plan de marcado. El campo Nombre simple se puede editar, y esto le permite crear una convención de denominación más descriptiva para sus planes de marcado. El valor de nombre simple no puede estar vacío y debe ser único. El procedimiento recomendado es desarrollar una convención de nomenclatura para toda la organización y aplicarla con coherencia en todos los sitios y para todos los usuarios.
  
#### <a name="description"></a>Descripción

Recomendamos escribir el nombre común y reconocible de la ubicación geográfica en la que se aplica el plan de marcado correspondiente. Por ejemplo, si el nombre del plan de marcado es Londres.Contoso.com, la descripción recomendada sería Londres. 
  
#### <a name="dial-in-conferencing-region"></a>Región de conferencia de acceso telefónico local

Si implementas conferencias de acceso telefónico local, necesitarás especificar una región de conferencias de acceso telefónico local para asociar números de acceso de conferencias de acceso telefónico local con un plan de marcado. 
  
#### <a name="external-access-prefix"></a>Prefijo de acceso externo

Puede especificar un prefijo de acceso externo de hasta cuatro caracteres (#, \*, y 0-9) si los usuarios necesitan marcar uno o varios dígitos iniciales adicionales (por ejemplo, 9) para obtener una línea externa.
  
> [!NOTE]
> Si especificas un prefijo de acceso externo, no necesitas crear una regla de normalización adicional para incluir el prefijo. 
  
### <a name="normalization-rules"></a>Reglas de normalización

Las reglas de normalización definen cómo es el enrutamiento necesario de los números de teléfono expresados en diversos formatos para la ubicación específica. La misma cadena de número se puede interpretar y convertir de manera distinta en función de la configuración regional desde la que se marque. Las reglas de normalización son necesarias para el enrutamiento de las llamadas, ya que los usuarios pueden usar (y usan) diversos formatos al escribir los números de teléfono en sus listas de contactos.
  
La normalización de los números de teléfono proporcionados por los usuarios aporta un formato uniforme que facilita las tareas siguientes:
  
- Hacer coincidir un número marcado con el URI SIP del destinatario correspondiente.
    
- Aplicar las reglas de autorización de marcado al usuario que realiza la llamada.
    
Los siguientes campos numéricos se incluyen entre los que necesitan considerar las reglas de normalización:
  
- Plan de marcado
    
- Código de país
    
- Código de área
    
- Longitud de extensión
    
- Prefijo de sitio
    
#### <a name="creating-normalization-rules"></a>Crear reglas de normalización

Las reglas de normalización usan expresiones regulares de .NET Framework para especificar patrones numéricos coincidentes que el servidor utiliza para convertir las cadenas de marcado a formato E.164 con el fin de realizar búsquedas inversas de números. Puede crear reglas de normalización en el panel de control de Skype empresarial Server, ya sea introduciendo las expresiones de forma manual, o bien introduciendo los dígitos iniciales y la longitud de las cadenas de marcado para que coincidan con el panel de control de Skype empresarial Server. generar la expresión regular correspondiente para usted. Sea como fuere, al finalizar puedes especificar un número de prueba para comprobar que la regla de normalización funciona según lo previsto.
  
Para obtener información detallada sobre el uso de expresiones regulares de .NET Framework, vea ["expresiones regulares de .NET Framework"](https://go.microsoft.com/fwlink/p/?linkId=140927).
  
#### <a name="sample-normalization-rules"></a>Reglas de normalización de ejemplo
<a name="BKMK_SampleNormalizationRules"> </a>

La siguiente tabla muestra reglas de normalización de muestra que se escriben como expresiones regulares de .NET Framework. Las muestras son meramente ejemplos y no sirven como referencia prescriptiva para crear sus propias reglas de normalización.
  
**Tabla 1. Reglas de normalización que usan expresiones regulares de .NET Framework**

|**Nombre de la regla**|**Descripción**|**Patrón de números**|**Traducción**|**Ejemplo**|
|:-----|:-----|:-----|:-----|:-----|
|4digitExtension  <br/> |Convierte extensiones de 4 dígitos  <br/> |^ (\d{4}) $  <br/> |+1425555$1  <br/> |0100 se traduce a +14255550100  <br/> |
|5digitExtension  <br/> |Convierte extensiones de 5 dígitos  <br/> |^ 5 (\d{4}) $  <br/> |+1425555$1  <br/> |50100 se traduce a +14255550100  <br/> |
|7digitcallingRedmond  <br/> |Convierte números de 7 dígitos en números locales de Redmond  <br/> |^ (\d{7}) $  <br/> |+1425$1  <br/> |5550100 se convierte en +14255550100  <br/> |
|7digitcallingDallas  <br/> |Convierte números de 7 dígitos en números locales de Dallas  <br/> |^ (\d{7}) $  <br/> |+1972$1  <br/> |5550100 se convierte en +19725550100  <br/> |
|10digitcallingUS  <br/> |Convierte números de 10 dígitos de Estados Unidos  <br/> |^ (\d{10}) $  <br/> |+1$1  <br/> |2065550100 se convierte en +12065550100  <br/> |
|LDCallingUS  <br/> |Convierte los números con prefijos de larga distancia de Estados Unidos  <br/> |^ 1 (\d{10}) $  <br/> |+$1  <br/> |12145550100 se convierte en +2145550100  <br/> |
|IntlCallingUS  <br/> |Convierte los números con prefijos internacionales de Estados Unidos  <br/> |^ 011 (\d\*) $  <br/> |+$1  <br/> |01191445550100 se convierte en +91445550100  <br/> |
|RedmondOperator  <br/> |Convierte 0 al operador de Redmond  <br/> |^0$  <br/> |+14255550100  <br/> |0 se traduce a +14255550100  <br/> |
|RedmondSitePrefix  <br/> |Convierte los números con prefijo de red (6) y prefijo de sitio de Redmond (222)  <br/> |^ 6222 (\d{4}) $  <br/> |+1425555$1  <br/> |62220100 se convierte en +14255550100  <br/> |
|NYSitePrefix  <br/> |Convierte los números con prefijo de red (6) y prefijo de sitio de Nueva York (333)  <br/> |^ 6333 (\d{4}) $  <br/> |+1202555$1  <br/> |63330100 se convierte en +12025550100  <br/> |
|DallasSitePrefix  <br/> |Convierte los números con prefijo de red (6) y prefijo de sitio de Dallas (444)  <br/> |^ 6444 (\d{4}) $  <br/> |+1972555$1  <br/> |64440100 se convierte en +19725550100  <br/> |
   
En la tabla siguiente se muestra un plan de marcado de ejemplo para Redmond, Washington, Estados Unidos, basado en las reglas de normalización que se muestran en la tabla anterior.
  
**Tabla 2. Plan de marcado de Redmond basado en las reglas de normalización mostradas en la tabla 1**

|**Redmond.forestFQDN**|
|:-----|
|5digitExtension  <br/> |
|7digitcallingRedmond  <br/> |
|10digitcallingUS  <br/> |
|IntlCallingUS  <br/> |
|RedmondSitePrefix  <br/> |
|NYSitePrefix  <br/> |
|DallasSitePrefix  <br/> |
|RedmondOperator  <br/> |
   
> [!NOTE]
> Aunque los nombres de las reglas de normalización que se muestran en la tabla anterior no incluyen espacios, es opcional usarlos. Por ejemplo, el primer nombre de la tabla se podía haber escrito como "Extensión de 5 dígitos" y sería un nombre válido. 
  
## <a name="voice-policies"></a>Directivas de voz

Las directivas de voz de Skype empresarial Server definen lo siguiente para cada usuario, sitio u organización que tiene asignada la Directiva:
  
- Un conjunto de características de llamadas que se pueden habilitar o deshabilitar para determinar la funcionalidad de telefonía IP empresarial disponible para los usuarios.
    
- Un conjunto de registros de uso de la red telefónica conmutada (RTC) que definen qué tipo de llamadas están autorizadas. 
    
Los pasos siguientes le ayudarán a planear las directivas de voz que necesitará para su implementación de telefonía IP empresarial:
  
- Determina cómo configurarás la directiva de voz global (la directiva de voz predeterminada que se instala con el producto). Esta Directiva se aplicará a todos los usuarios de telefonía de telefonía empresarial a los que no se les haya asignado explícitamente una directiva de sitio o usuario.
    
- Identifica cualquier directiva de voz de sitio que puedas necesitar.
    
- Identifica cualquier directiva de voz de usuario que puedas necesitar.
    
- Decide qué características de llamada deseas habilitar para cada directiva de voz.
    
- Determina qué registros de uso de RTC deseas configurar para cada directiva de voz.
    
### <a name="voice-policy-scope"></a>Ámbito de directiva de voz

El ámbito de directiva de voz determina el nivel jerárquico en el que se puede aplicar la directiva. En Skype empresarial Server, puede configurar directivas de voz con los siguientes niveles de ámbito (enumerados de la más específica a la más general).
  
- La **directiva de voz de usuario** se puede asignar a usuarios, grupos u objetos de contacto individuales. Es la directiva de nivel más bajo. Las directivas de voz de usuario se pueden implementar para habilitar características para usuarios y grupos determinados en un sitio, pero no para otros en el mismo sitio. Por ejemplo, puedes deshabilitar las llamadas de larga distancia para algunos empleados. Con el fin de asignar una directiva de voz, un objeto de contacto se considera un usuario individual.
    
    > [!NOTE]
    > Le recomendamos que implemente una directiva de voz de usuario para los usuarios de la empresa de voz de un sitio de sucursal que estén registrados en la implementación de sitio central o los usuarios que estén registrados en un dispositivo de sucursal con la supervivencia. 
  
- La **directiva de voz de sitio** se aplica a todo un sitio, excepto para los usuarios, grupos u objetos de contacto a los que se ha asignado una directiva de voz de usuario. Para definir una directiva de voz de sitio, necesitas especificar el sitio al que se aplica la directiva. Si no se asignó una directiva de voz de usuario, se usa la directiva de voz de sitio.
    
- La **directiva de voz global** es la directiva de voz predeterminada que se instala con el producto. Puedes editar la directiva de voz global para cumplir las necesidades específicas de tu organización, pero no puedes cambiar su nombre ni eliminarla. Esta directiva de voz se aplica a todos los usuarios, grupos y objetos de contacto de Enterprise Voice de su implementación, a menos que configure y asigne una directiva de voz con un ámbito más específico. Si deseas deshabilitar esta directiva en su totalidad, asegúrate de que todos los sitios y todos los usuarios tengan asignadas directivas personalizadas.
    
### <a name="call-features"></a>Características de llamada

Puedes habilitar o deshabilitar las siguientes características de llamada para cada directiva de voz:
  
- El **desvío de llamadas** permite que los usuarios desvíen llamadas a otros teléfonos y dispositivos de cliente. Está habilitado de forma predeterminada.
    
- La **delegación** permite a los usuarios especificar otros usuarios para que realicen y reciban llamadas en su nombre. Está habilitada de forma predeterminada.
    
- La **transferencia de llamadas** permite a los usuarios transferir llamadas a otros usuarios. Está habilitada de forma predeterminada.
    
- El **estacionamiento de llamadas** permite a los usuarios estacionar llamadas y atenderlas en otro teléfono o cliente. Está deshabilitado de forma predeterminada.
    
- La característica de **llamadas simultáneas** permite que las llamadas entrantes suenen en un teléfono adicional (por ejemplo, un móvil) u otros dispositivos de extremo. Está habilitada de forma predeterminada.
    
- La **llamada de equipo** permite a los usuarios de un equipo determinado responder llamadas por otros miembros del equipo. Está habilitada de forma predeterminada.
    
- El **desvío de RTC** permite que las llamadas realizadas por usuarios que tienen asignada esta directiva a otros usuarios de la empresa se puedan desviar en la red telefónica conmutada (RTC) si la red WAN está saturada o no disponible. Está habilitado de forma predeterminada.
    
- El **reemplazo de directiva de ancho de banda** permite a los administradores cambiar las decisiones de la directiva del servicio de control de admisión de llamadas para un usuario en concreto. Está deshabilitado de forma predeterminada.
    
- El **seguimiento de llamadas malintencionadas** permite a los usuarios denunciar llamadas malintencionadas con el cliente de Skype empresarial y, a continuación, marca dichas llamadas en los registros de detalles de llamadas. Está deshabilitado de forma predeterminada.
    
- El **buzón de voz** evita que las llamadas se enruten inmediatamente al sistema de buzón de voz del teléfono móvil del usuario cuando se configura el tono de llamada simultánea y el teléfono está apagado, fuera de la batería o fuera de intervalo, y se basa en un valor del temporizador. Esta configuración habilita y deshabilita el temporizador, y establece su valor. Solo se puede configurar mediante el shell de administración de Skype empresarial Server. Está deshabilitado de forma predeterminada.
    
- El **desvío de llamadas y los usos de RTC de llamadas simultáneas** permite a los administradores especificar el mismo uso de la RTC que la Directiva de voz para el desvío de llamadas y las llamadas simultáneas, restringir el desvío de llamadas y las llamadas simultáneas a usuarios internos de Skype empresarial, o especificar un uso de RTC personalizado que sea diferente del uso de RTC de la Directiva de voz. La opción predeterminada es usar el mismo uso de RTC que la directiva de voz para el desvío de llamadas y las llamadas simultáneas.
    
### <a name="pstn-usage-records"></a>Registros de uso de RTC

Cada directiva de voz necesita tener uno o más registros de uso de RTC asociados. Los usos de RTC se pueden asociar a una directiva de voz únicamente para las llamadas simultáneas y el desvío de llamadas. 
  
> [!NOTE]
> El orden de los usos de RTC es fundamental ya que, al asociar usuarios a rutas, la función de enrutamiento saliente compara los usos de RTC desde el principio hasta el final. Si el primer uso coincide con la ruta de la llamada, se usa la ruta. En caso contrario, la función de enrutamiento saliente pasa al siguiente uso de RTC de la lista y sigue así hasta que encuentra alguna coincidencia. De hecho, los usos de RTC siguientes se usan a modo de copia de seguridad si el primero de la lista no está disponible. 
  
## <a name="pstn-usage-records"></a>Registros de uso de RTC

Planificar los registros de uso de RTC consiste principalmente en elaborar una lista de todos los permisos de llamada vigentes actualmente en la organización, desde los permisos del presidente hasta los de los empleados temporales, consultores y personal contingente. Este proceso también brinda la oportunidad de volver a examinar los permisos de llamada existentes y modificarlos. Puede crear registros de uso de RTC solo para los permisos de llamada que se aplican a los usuarios de voz de empresa previstos, pero una mejor solución de larga duración podría ser crear registros de uso de RTC para todos los permisos de llamadas, independientemente de si algunos usuarios no pueden aplicar al grupo de usuarios que desea habilitar para la telefonía IP empresarial. Si cambian los permisos de llamada o se agregan usuarios nuevos con permisos de llamada diferentes, ya estarán creados los registros de uso de RTC necesarios.
  
A continuación se muestra una tabla del uso de RTC típico.
  
**Registros de uso de RTC**

|**Atributo de teléfono**|**Descripción**|
|:-----|:-----|
|Local  <br/> |Llamadas locales  <br/> |
|Long-Distance  <br/> |Llamadas de larga distancia  <br/> |
|International  <br/> |Llamadas internacionales  <br/> |
|Delhi  <br/> |Empleados de jornada completa de Delhi  <br/> |
|Redmond  <br/> |Empleados de jornada completa de Redmond  <br/> |
|RedmondTemps  <br/> |Empleados temporales de Redmond  <br/> |
|Zurich  <br/> |Empleados de jornada completa de Zúrich  <br/> |
   
Por sí mismos, los registros de uso de RTC no hacen nada. Para que funcionen, hay que asociarlos a:
  
- Directivas de voz, que se asignan a los usuarios.
    
- Rutas, que se asignan a los números de teléfono.
    
## <a name="voice-routes"></a>Rutas de voz

Las rutas de llamadas especifican cómo administra Skype empresarial Server las llamadas salientes que hacen los usuarios de telefonía IP. Cuando un usuario marca un número, el servidor front-end normaliza la cadena de marcado al formato E. 164, si es necesario, e intenta hacerlo coincidir con el URI del SIP. Si el servidor no puede establecer esa coincidencia, aplicará la lógica de enrutamiento de llamadas salientes basándose en el número. El paso final para definir la lógica consiste en crear una ruta de llamada con nombre independiente para cada conjunto de números de teléfono de destino indicados en cada plan de marcado.
  
Antes de definir las rutas de llamadas salientes, necesitas completar los pasos siguientes:
  
- Implementa uno o más troncos.
    
- Crea planes de marcado, según sea necesario, para sitios, usuarios individuales y objetos de contacto.
    
- Crea registros de uso de la red telefónica conmutada (RTC).
    
Además, para habilitar el enrutamiento de llamadas salientes, necesitas crear y asignar una o más directivas de voz. Puedes hacerlo antes o después de definir las rutas de llamadas salientes.
  
Para cada ruta, necesitas especificar:
  
- Un nombre con el que se pueda identificar fácilmente la ruta.
    
- Una descripción opcional en los casos en que el nombre no sea suficiente para describir la ruta.
    
- El patrón coincidente de la expresión regular que identifica los números de teléfono de destino a los que se aplica la ruta, junto con excepciones a las que no se necesita aplicar el patrón coincidente.
    
- Uno o más troncos que deseas asignar a la ruta.
    
- Los registros de uso de RTC que los usuarios necesitan tener para llamar a los números que coincidan con la expresión regular del número de teléfono de destino.
    
Puede especificar rutas de llamadas en el panel de control de Skype empresarial Server. Estas rutas de llamadas rellenan la tabla de enrutamiento del servidor, que usa Skype empresarial Server para enrutar las llamadas destinadas a la RTC.
  
### <a name="mn-trunk-support"></a>Compatibilidad con troncos M:N

Skype empresarial Server proporciona flexibilidad a la hora de enrutar llamadas a la RTC. Una ruta de voz especifica a la RTC un conjunto de troncos que pueden usarse para una llamada de voz concreta. Un tronco asocia un servidor de mediación y un número de puerto con una puerta de enlace RTC y un número de puerto de escucha. Esta asociación lógica permite asociar un servidor de mediación con varias puertas de enlace y tener varias conexiones a la misma puerta de enlace. Al definir una ruta de llamada, especifica los troncos asociados a esa ruta, pero no especifica qué servidores de mediación están asociados a la ruta. Para crear troncos definiendo las relaciones entre los servidores de mediación y las puertas de enlace RTC, IP-PBX y los controladores de borde de sesión (SBCs), use el generador de topología.
  
### <a name="least-cost-routing"></a>Enrutamiento de menor coste

La capacidad para especificar los troncos a los que se redirigen varios números te permite determinar e implementar las rutas de menor coste. La regla general para seleccionar troncos es elegir el que tenga la puerta de enlace más cercana a la ubicación del número de destino a fin de minimizar los gastos de larga distancia. Por ejemplo, si te encontraras en Nueva York y llamaras a Roma, llevarías la llamada a través de la red IP hasta el tronco con la puerta de enlace más cercana a la oficina de Roma, por lo que solo necesitarías pagar el precio de una llamada local.
  
Para obtener un ejemplo de cómo se puede usar el enrutamiento de menor costo, considere lo siguiente: fabrikam decide permitir que los usuarios de alemán llamen a números de Estados Unidos con el tronco de Estados Unidos. Fabrikam también desea configurar el sistema para que todas las llamadas de los usuarios de Skype empresarial Server de Estados Unidos a Alemania y países o regiones adyacentes terminen en el tronco con el gateway de Alemania. Este enrutamiento ahorrará dinero, porque una llamada de Alemania a Austria, por ejemplo, es menos costosa que una llamada de Estados Unidos a Austria.
  
### <a name="translating-outbound-dial-strings"></a>Convertir cadenas de marcado salientes

Skype empresarial Server requiere normalizar todas las cadenas de marcado al formato E. 164 con el fin de realizar la búsqueda de números inversos (RNL). Para los troncos con puertas de enlace o las sucursales privadas (PBX) que requieren números traducidos en formatos de marcado locales, Skype empresarial Server le permite crear una o más reglas que ayuden a manipular el número llamado (es decir, URI de solicitud) antes del enrutamiento. en el tronco. Por ejemplo, podrías escribir una regla para quitar +44 del encabezado de la cadena de marcado y cambiarlo por 0144.
  
Con Skype empresarial Server es posible crear una o más reglas que ayuden a manipular el número de llamada antes de enrutarlo al tronco.
  
En la planeación de los troncos que asocian la puerta de enlace: pares de puertos con el servidor de mediación: pares de puertos, puede ser útil agrupar los troncos con requisitos de marcado local similares y, por lo tanto, reducir el número de reglas de traducción necesarias y el tiempo que se tarda en escribirlas.
  
### <a name="configuring-caller-id"></a>Configurar el identificador de llamada

Skype empresarial Server permite manipular la identificación de llamadas para las llamadas salientes. Por ejemplo, si una organización desea enmascarar las extensiones de marcado directo de los empleados y reemplazarlas con el número de departamento o corporativo genérico, un administrador puede hacerlo con el panel de control de Skype empresarial Server para suprimir el identificador de llamada y reemplazarlo. con un identificador de llamada alternativo especificado. En el planeamiento de la lógica de enrutamiento, piense en qué personas, grupos y sitios deseará esta opción, tal vez incluso para todos los empleados.
  
> [!NOTE]
> En el caso de las llamadas que se desvían a través de la RTC, se presentará el identificador de llamada genérico en lugar del identificador de llamada original. Esto puede hacer que la llamada omita la configuración de privacidad o de No molestar que pueda haber establecido el destinatario de la llamada. 
  
### <a name="additional-routing-logic"></a>Lógica de enrutamiento adicional

Al crear rutas de llamadas salientes, necesitas tener en cuenta los siguientes factores que pueden afectar a la lógica de enrutamiento:
  
- Si se establece una llamada a través de un límite federado, la parte correspondiente al dominio en el URI se usa para redirigir la llamada a la empresa responsable de aplicar la lógica de enrutamiento saliente.
    
- Si la parte correspondiente al dominio en el URI de la solicitud no contiene un dominio compatible para la empresa, el componente de enrutamiento saliente en el servidor no procesará la llamada.
    
- Si un usuario no está habilitado para Enterprise Voice, el servidor aplicará otra lógica de enrutamiento, según corresponda.
    
- Si se redirige una llamada a una puerta de enlace totalmente ocupada (todas las principales líneas de conexión están ocupadas), la puerta de enlace rechaza la llamada y la lógica de enrutamiento saliente redirige la llamada a la siguiente ruta de menor coste. Esto necesita analizarse minuciosamente, ya que una puerta de enlace con un tamaño adecuado para una oficina pequeña internacional (por ejemplo, de Zúrich), podría transportar una cantidad importante de tráfico no local para las llamadas internacionales a Suiza. Si el tamaño de la puerta de enlace no se diseñara correctamente para este tráfico adicional, las llamadas a Suiza podrían redirigirse a través de una puerta de enlace de Alemania, lo que daría lugar a tarifas más altas.
    

