---
title: Planear el enrutamiento de voz saliente en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Obtenga información sobre el enrutamiento de voz saliente en Skype Empresarial Server Telefonía IP empresarial, incluida la configuración de enrutamiento de llamadas, los planes de marcado, las reglas de normalización, las directivas de voz, los registros de uso de RTC y las rutas de voz.
ms.openlocfilehash: 70681e995068a0999324694a78806421e0f2d129
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101286"
---
# <a name="plan-for-outbound-voice-routing-in-skype-for-business-server"></a>Planear el enrutamiento de voz saliente en Skype Empresarial Server
 
Obtenga información sobre el enrutamiento de voz saliente en Skype Empresarial Server Telefonía IP empresarial, incluida la configuración de enrutamiento de llamadas, los planes de marcado, las reglas de normalización, las directivas de voz, los registros de uso de RTC y las rutas de voz.
  
El enrutamiento de llamadas salientes se aplica Telefonía IP empresarial llamadas que están destinadas a una puerta de enlace de red telefónica conmutada (RTC), un tronco o una central de conmutación privada (PBX). Cuando un usuario de Skype Empresarial hace una llamada, el servidor normaliza el número de teléfono al formato E.164, si es necesario, e intenta hacerlo coincidir con un URI de SIP. Si el servidor no puede establecer la coincidencia, aplicará la lógica de enrutamiento de llamadas realizadas basándose en la cadena de marcado proporcionada. Dicha lógica se define con la configuración de las opciones de servidor que se describe en la siguiente tabla.
  
**Configuración de enrutamiento de llamadas salientes de Skype Empresarial Server**

|**Object**|**Descripción**|
|:-----|:-----|
|Plan de marcado  <br/> |Un plan de marcado es un conjunto de reglas de normalización especificado por el usuario que convierte números de teléfono para una ubicación especificada por el usuario, un usuario individual o un objeto de contacto a un formato estándar único (E.164) con fines de autorización telefónica y enrutamiento de llamadas.  <br/> |
|Regla de normalización  <br/> |Las reglas de normalización definen la forma en que los números de teléfono expresados en diversos formatos se van a enrutar en cada ubicación, usuario u objeto de contacto que se haya especificado. Una misma cadena de marcado se puede interpretar y convertir de manera distinta en función de la ubicación desde la que se marque y la persona o el objeto de contacto que realice la llamada. Un conjunto de reglas de normalización asociado a una ubicación determinada constituye un plan de marcado.  <br/> |
|Directiva de voz  <br/> |Una directiva de voz asocia uno o varios registros de uso de RTC a un usuario o un grupo de usuarios. Además proporciona una lista de características de llamada que se puede habilitar o deshabilitar.  <br/> |
|Registro de uso de RTC  <br/> |Un registro de uso de RTC especifica la clase de llamada (por ejemplo, interna, local o de larga distancia) que pueden realizar los diversos usuarios o grupos de usuarios en una organización.  <br/> |
|Ruta de llamada  <br/> |Una ruta de llamada asocia los números de teléfono de destino a determinados circuitos de enlace y a determinados registros de uso de PSTN. Un circuito de enlace de PSTN se considera una puerta de enlace.  <br/> |
   
## <a name="dial-plans-and-normalization-rules"></a>Planes de marcado y reglas de normalización

Un plan de marcado es un conjunto de reglas de normalización especificado por el usuario que convierte números de teléfono para una ubicación especificada por el usuario, un usuario individual o un objeto de contacto a un formato estándar único (E.164) con fines de autorización telefónica y enrutamiento de llamadas. 
  
Las reglas de normalización definen la forma en que los números de teléfono expresados en diversos formatos se van a enrutar en cada ubicación, usuario u objeto de contacto que se haya especificado. La misma cadena de marcado puede interpretarse y traducirse de forma diferente, según la ubicación desde la que se marca y la persona o el objeto de contacto que realiza la llamada.
  
### <a name="dial-plan-scope"></a>Ámbito del plan de marcado

El ámbito de un plan de marcado determina el nivel jerárquico al que se puede aplicar el plan de marcado. En Skype Empresarial Server, se puede asignar a un usuario un plan de marcado específico por usuario. Si no se asigna un plan de marcado de usuario, se aplica el plan de marcado del grupo de servidores front-end. Si no hay ningún plan de marcado de grupo de servidores front-end, se aplica el plan de marcado de sitio. Por último, si no hay otro plan de marcado aplicable al usuario, se aplica el plan de marcado global.
  
Los clientes obtienen niveles de ámbito del plan de marcado a través de la configuración de aprovisionamiento en banda que se proporciona cuando los usuarios inician sesión en Skype Empresarial. Como administrador, puede administrar y asignar niveles de ámbito del plan de marcado mediante el Panel de control de Skype Empresarial Server.
  
> [!NOTE]
> El plan de marcado de puerta de enlace de red telefónica conmutada (RTC) de nivel de servicio se aplica a las llamadas entrantes de una puerta de enlace determinada. 
  
Los niveles de ámbito de plan de marcado se definen de la manera siguiente:
  
- **Plan de marcado de** usuario: se puede asignar a usuarios individuales, grupos u objetos de contacto. Las aplicaciones de voz pueden buscar un plan de marcado por usuario cuando se recibe una llamada con el contexto de teléfono establecido como predeterminado del usuario. Para asignar un plan de marcado, un objeto de contacto se trata como un usuario individual.
    
- **Plan de marcado de grupo**: puede crearse en el nivel de servicio para cualquier registrador o puerta de enlace de RTC de la topología. Para definir un plan de marcado de grupo, debe especificarse el servicio (puerta de enlace de RTC o grupo de registrador) en el que se aplica el plan de marcado. 
    
- **Plan de marcado** de sitio: se puede crear para todo un sitio, excepto para los usuarios, grupos u objetos de contacto a los que se les asigna un plan de marcado de grupo o un plan de marcado de usuario. Para definir un plan de marcado de sitio, debe especificar el sitio en el que se aplica el plan de marcado.
    
- **Plan de marcado global:** el plan de marcado predeterminado instalado con el producto. El plan de marcado global puede editarse, pero no eliminarse. Este plan de marcado se aplica a todos los Telefonía IP empresarial, grupos y objetos de contacto de la implementación, a menos que configure y asigne un plan de marcado con un ámbito más específico.
    
### <a name="planning-for-dial-plans"></a>Planeación de planes de marcado

Para planear un plan de marcado, siga estos pasos:
  
- Enumerar todas las configuraciones regionales en las que la organización tiene una oficina.
    
    La lista debe estar actualizada y completa. Deberá revisarse a medida que evolucione la compañía. En una gran empresa multinacional con numerosas sucursales pequeñas, esto puede ser una tarea que requiere mucho tiempo.
    
- Identificar patrones de números válidos para cada sitio.
    
    La tarea que más tiempo requiere en el marco de la planeación de los planes de marcado es la identificación de los modelos de número válidos para cada sitio. En algunos casos, se podrán copiar en otros planes de marcado las reglas de normalización escritas para un plan de marcado, sobre todo si los sitios correspondientes están dentro del mismo país o región o incluso en el mismo continente. En otros casos, pequeñas modificaciones en los números de un plan de marcado pueden bastar para usarse en otros planes de marcado.
    
- Desarrollar un esquema para toda la organización para asignar nombres a los planes de marcado.
    
    Adoptar un esquema estándar de asignación de nombres asegura la coherencia en toda la organización y facilita los procesos de mantenimiento y actualización.
    
- Decida si se necesitan varios planes de marcado para una única ubicación. 
    
    Si su organización mantiene un plan de marcado único en varias ubicaciones, es posible que deba crear un plan de marcado independiente para los usuarios de Telefonía IP empresarial que están migrando desde una central de conmutación (PBX) privada y que necesitan conservar sus extensiones existentes.
    
- Decida si los planes de marcado por usuario son necesarios. Por ejemplo, si tiene usuarios en un sitio de sucursal que están registrados en el sitio central o si tiene usuarios registrados en una aplicación de sucursal con funciones de supervivencia, puede considerar escenarios de marcado especiales para dichos usuarios mediante planes de marcado por usuario y reglas de normalización. Para obtener más información, [vea Plan for Telefonía IP empresarial resiliency in Skype for Business Server](enterprise-voice-resiliency.md).
    
- Determine el ámbito del plan de marcado (como se describió anteriormente en este tema).
    
Para crear un plan de marcado, debe especificar valores en los siguientes campos, según sea necesario, mediante el Panel de control de Skype Empresarial Server o el Shell de administración de Skype Empresarial Server.
  
#### <a name="name-and-simple-name"></a>Nombre y Nombre simple

Para los planes de marcado de usuario, debe especificar un nombre descriptivo que identifique los usuarios, grupos u objetos de contacto a los que se asignará el plan de marcado. Para los planes de marcado de sitio, el campo Nombre se rellena previamente con el nombre del sitio y no se puede cambiar. Para los planes de marcado de grupo, el campo Nombre se rellena previamente con la puerta de enlace RTC o el nombre de dominio completo (FQDN) del grupo de servidores front-end y no se puede cambiar.
  
El plan de marcado Nombre simple se rellena previamente con una cadena derivada del nombre del plan de marcado. El campo Nombre simple es editable, lo que permite crear una convención de nomenclatura más descriptiva para los planes de marcado. El valor de Nombre deSimple no puede estar vacío y debe ser único. Un procedimiento recomendado es desarrollar una convención de nomenclatura para toda la organización y, a continuación, usar esta convención de forma coherente en todos los sitios y usuarios.
  
#### <a name="description"></a>Descripción

Se recomienda escribir el nombre común y reconocible de la ubicación geográfica en la que se aplica el plan de marcado correspondiente. Por ejemplo, si el nombre del plan de marcado es Londres.Contoso.com, la descripción recomendada es Londres. 
  
#### <a name="dial-in-conferencing-region"></a>Región de conferencia de acceso telefónico local

Si se implementan conferencias de acceso telefónico local, debe especificarse una región de conferencias de acceso telefónico local para asociar números de acceso de conferencias de acceso telefónico local con un plan de marcado. 
  
#### <a name="external-access-prefix"></a>Prefijo de acceso externo

Puede especificar un prefijo de acceso externo de hasta cuatro caracteres (#, y 0-9) si los usuarios necesitan marcar uno o más dígitos iniciales \* adicionales (por ejemplo, 9) para obtener una línea externa.
  
> [!NOTE]
> Si especifica un prefijo de acceso externo, no necesita crear otra regla de normalización para incluir el prefijo. 
  
### <a name="normalization-rules"></a>Reglas de normalización

Las reglas de normalización definen cómo deben enrutarse los números de teléfono expresados en diversos formatos para la ubicación con nombre. La misma cadena de número puede interpretarse y traducirse de forma diferente, según la configuración regional desde la que se marca. Las reglas de normalización son necesarias para el enrutamiento y la autorización de las llamadas, ya que los usuarios pueden usar (y usan) diversos formatos al escribir los números de teléfono en sus listas de contactos.
  
La normalización de números de teléfono proporcionados por el usuario proporciona un formato coherente que facilita las siguientes tareas:
  
- Coincide con un número marcado con el URI DE SIP del destinatario previsto.
    
- Aplicar reglas de autorización de marcado al usuario que realiza la llamada.
    
Los siguientes campos numéricos están entre los que deben tener en cuenta las reglas de normalización:
  
- Plan de marcado
    
- Código de país
    
- Código de área
    
- Longitud de extensión
    
- Prefijo de sitio
    
#### <a name="creating-normalization-rules"></a>Creación de reglas de normalización

Las reglas de normalización usan .NET Framework expresiones regulares para especificar patrones numéricos de coincidencia que el servidor usa para traducir cadenas de marcado al formato E.164 con el fin de realizar búsquedas de números inversos. Para crear reglas de normalización en el Panel de control de Skype Empresarial Server, escriba las expresiones manualmente o escriba los dígitos iniciales y la longitud de las cadenas de marcado que deben coincidir y permitir que el Panel de control de Skype Empresarial Server genere la expresión regular correspondiente. De cualquier manera, cuando termine, puede escribir un número de prueba para comprobar que la regla de normalización funciona según lo esperado.
  
Para obtener más información sobre .NET Framework expresiones regulares, vea [".NET Framework Regular Expressions"](/dotnet/standard/base-types/regular-expressions).
  
#### <a name="sample-normalization-rules"></a>Reglas de normalización de ejemplo
<a name="BKMK_SampleNormalizationRules"> </a>

En la siguiente tabla se muestran ejemplos de reglas de normalización escritas como expresiones regulares de .NET Framework. Son solo ejemplos, no una referencia normativa para crear reglas de normalización.
  
**Tabla 1. Reglas de normalización que usan expresiones regulares de .NET Framework**

|**Nombre de regla**|**Descripción**|**Patrón de número**|**Conversión**|**Ejemplo**|
|:-----|:-----|:-----|:-----|:-----|
|4digitExtension  <br/> |Convierte extensiones de 4 dígitos  <br/> |^(\d {4} )$  <br/> |+1425555$1  <br/> |0100 se convierte en +14255550100  <br/> |
|5digitExtension  <br/> |Convierte extensiones de 5 dígitos  <br/> |^5(\d {4} )$  <br/> |+1425555$1  <br/> |50100 se convierte en +14255550100  <br/> |
|7digitcallingRedmond  <br/> |Convierte números de 7 dígitos en números locales de Redmond  <br/> |^(\d {7} )$  <br/> |+1425$1  <br/> |5550100 se convierte en +14255550100  <br/> |
|7digitcallingDallas  <br/> |Convierte números de 7 dígitos en números locales de Dallas  <br/> |^(\d {7} )$  <br/> |+1972$1  <br/> |5550100 se convierte en +19725550100  <br/> |
|10digitcallingUS  <br/> |Convierte números de 10 dígitos en los Estados Unidos  <br/> |^(\d {10} )$  <br/> |+1$1  <br/> |2065550100 se convierte en +12065550100  <br/> |
|LDCallingUS  <br/> |Convierte los números con prefijos de larga distancia de Estados Unidos  <br/> |^1(\d {10} )$  <br/> |+$1  <br/> |12145550100 se convierte en +2145550100  <br/> |
|IntlCallingUS  <br/> |Convierte los números con prefijos internacionales de Estados Unidos  <br/> |^011(\d \* )$  <br/> |+$1  <br/> |01191445550100 se convierte en +91445550100  <br/> |
|RedmondOperator  <br/> |Convierte 0 al operador de Redmond  <br/> |^0$  <br/> |+14255550100  <br/> |0 se convierte en +14255550100  <br/> |
|RedmondSitePrefix  <br/> |Convierte los números con prefijo de red (6) y prefijo de sitio de Redmond (222)  <br/> |^6222(\d {4} )$  <br/> |+1425555$1  <br/> |62220100 se convierte en +14255550100  <br/> |
|NYSitePrefix  <br/> |Convierte los números con prefijo de red (6) y prefijo de sitio de Nueva York (333)  <br/> |^6333(\d {4} )$  <br/> |+1202555$1  <br/> |63330100 se convierte en +12025550100  <br/> |
|DallasSitePrefix  <br/> |Convierte los números con prefijo de red (6) y prefijo de sitio de Dallas (444)  <br/> |^6444(\d {4} )$  <br/> |+1972555$1  <br/> |64440100 se convierte en +19725550100  <br/> |
   
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

Las directivas de voz de Skype Empresarial Server definen lo siguiente para cada usuario, sitio u organización que tiene asignada la directiva:
  
- Un conjunto de características de llamada que se pueden habilitar o deshabilitar para determinar la Telefonía IP empresarial funcionalidad disponible para los usuarios.
    
- Un conjunto de registros de uso de la red telefónica conmutada (RTC) que definen qué tipo de llamadas están autorizadas. 
    
Los siguientes pasos le ayudarán a planear las directivas de voz que necesitará para su Telefonía IP empresarial implementación:
  
- Determine cómo configurará la directiva de voz global (la directiva de voz predeterminada que se instala con el producto). Esta directiva se aplicará a todos Telefonía IP empresarial usuarios a los que no se haya asignado explícitamente una directiva de nivel de sitio o por usuario.
    
- Identifique cualquier directiva de voz de nivel de sitio que pueda necesitar.
    
- Identifique cualquier directiva de voz por usuario que pueda necesitar.
    
- Decida qué características de llamada desea habilitar para cada directiva de voz.
    
- Determine qué registros de uso de RTC desea configurar para cada directiva de voz.
    
### <a name="voice-policy-scope"></a>Ámbito de directiva de voz

El ámbito de directiva de voz determina el nivel jerárquico en el que se puede aplicar la directiva. En Skype Empresarial Server, puede configurar directivas de voz con los siguientes niveles de ámbito (enumerados de los más específicos a los más generales).
  
- La **directiva de voz de usuario** se puede asignar a usuarios, grupos u objetos de contacto individuales. Es la directiva de nivel más bajo. Las directivas de voz de usuario se pueden implementar para habilitar características para usuarios y grupos determinados en un sitio, pero no para otros en el mismo sitio. Por ejemplo, puede deshabilitar las llamadas de larga distancia para algunos empleados. Con el fin de asignar una directiva de voz, un objeto de contacto se considera un usuario individual.
    
    > [!NOTE]
    > Se recomienda implementar una directiva de voz de usuario para usuarios de sucursal Telefonía IP empresarial que estén registrados con la implementación del sitio central o usuarios registrados en una aplicación de sucursal con funciones de supervivencia. 
  
- La **directiva de voz de sitio** se aplica a todo un sitio, excepto para los usuarios, grupos u objetos de contacto a los que se ha asignado una directiva de voz de usuario. Para definir una directiva de voz de sitio, debe especificar el sitio al que se aplica la directiva. Si no se asignó una directiva de voz de usuario, se usa la directiva de voz de sitio.
    
- La **directiva de voz global** es la directiva de voz predeterminada que se instala con el producto. Puede modificar la directiva de voz global para cumplir las necesidades específicas de su organización, pero no puede cambiar su nombre ni eliminarla. Esta directiva de voz se aplica a todos los Telefonía IP empresarial, grupos y objetos de contacto de la implementación a menos que configure y asigne una directiva de voz con un ámbito más específico. Si desea deshabilitar esta directiva en su totalidad, compruebe que todos los sitios y usuarios tengan asignadas directivas personalizadas.
    
### <a name="call-features"></a>Características de llamada

Puede habilitar o deshabilitar las siguientes características de llamada para cada directiva de voz:
  
- El **desvío de llamadas** permite que los usuarios desvíen llamadas a otros teléfonos y dispositivos de cliente. Habilitado de forma predeterminada.
    
- La **delegación** permite a los usuarios especificar otros usuarios para que realicen y reciban llamadas en su nombre. Habilitada de forma predeterminada.
    
- La **transferencia de llamadas** permite a los usuarios transferir llamadas a otros usuarios. Habilitada de forma predeterminada.
    
- El **estacionamiento de llamadas** permite a los usuarios estacionar llamadas y atenderlas en otro teléfono o cliente. Deshabilitado de forma predeterminada.
    
- La característica de **llamadas simultáneas** permite que las llamadas entrantes suenen en un teléfono adicional (por ejemplo, un móvil) u otros dispositivos de extremo. Habilitada de forma predeterminada.
    
- La **llamada de equipo** permite a los usuarios de un equipo determinado responder llamadas por otros miembros del equipo. Habilitada de forma predeterminada.
    
- El **nuevo enrutamiento RTC** permite que las llamadas realizadas por usuarios que tienen asignada esta directiva a otros usuarios de la empresa se puedan volver a enrutar en la red telefónica conmutada (RTC) si la red WAN está saturada o no disponible. Habilitado de forma predeterminada.
    
- El **reemplazo de directiva de ancho de banda** permite a los administradores reemplazar las decisiones de la directiva de control de admisión de llamadas para un usuario concreto. Deshabilitado de forma predeterminada.
    
- **El seguimiento de llamadas** malintencionadas permite a los usuarios notificar llamadas malintencionadas mediante el cliente de Skype Empresarial y, a continuación, marca dichas llamadas en los registros de detalles de llamadas. Deshabilitado de forma predeterminada.
    
- **El escape** de correo de voz evita que las llamadas se enrutan inmediatamente al sistema de correo de voz del teléfono móvil del usuario cuando se configura la llamada simultánea y el teléfono está apagado, sin batería o fuera de intervalo, y se basa en un valor de temporizador. Esta opción habilita y deshabilita el temporizador, y establece su valor. Solo se puede configurar mediante el Shell de administración de Skype Empresarial Server. Deshabilitado de forma predeterminada.
    
- El reenvío de llamadas y los usos de RTC de llamadas simultáneas permiten a los administradores especificar el mismo uso de RTC que la directiva de voz para el reenvío de llamadas y llamadas simultáneas, restringir el reenvío de llamadas y las llamadas **simultáneas** solo a usuarios internos de Skype Empresarial o especificar un uso de RTC personalizado que sea diferente del uso de RTC de la directiva de voz. La opción predeterminada es usar el mismo uso de RTC que la directiva de voz para el desvío de llamadas y las llamadas simultáneas.
    
### <a name="pstn-usage-records"></a>Registros de uso de RTC

Cada directiva de voz debe tener uno o más registros de uso de RTC asociados. Los usos de RTC se pueden asociar a una directiva de voz únicamente para las llamadas simultáneas y el desvío de llamadas. 
  
> [!NOTE]
> El orden de los usos de RTC es fundamental ya que, al asociar usuarios a rutas, la función de enrutamiento saliente compara los usos de RTC desde el principio hasta el final. Si el primer uso coincide con la ruta de la llamada, se usa la ruta. En caso contrario, la función de enrutamiento saliente pasa al siguiente uso de RTC de la lista y sigue así hasta que encuentra alguna coincidencia. De hecho, los usos de RTC siguientes se usan a modo de reserva si el primero de la lista no está disponible. 
  
## <a name="pstn-usage-records"></a>Registros de uso de RTC

La planeación de registros de uso de RTC consiste principalmente en enumerar todos los permisos de llamadas que están actualmente en vigor en su organización, desde el director ejecutivo hasta los trabajadores temporales, los consultores y el personal contingente. Este proceso también ofrece la oportunidad de volver a examinar los permisos de llamadas existentes y revisarlos. Solo puede crear registros de uso de RTC para los permisos de llamada que se aplican a los usuarios de Telefonía IP empresarial previstos, pero una mejor solución de largo alcance podría ser crear registros de uso de RTC para todos los permisos de llamada, independientemente de si algunos no se pueden aplicar actualmente al grupo de usuarios que se habilitarán para Telefonía IP empresarial. Si cambian los permisos de llamadas o se agregan nuevos usuarios con permisos de llamada diferentes, ya habrá creado los registros de uso de RTC necesarios.
  
En la tabla siguiente se muestra una tabla de uso típica de RTC.
  
**Registros de uso de RTC**

|**Atributo Phone**|**Descripción**|
|:-----|:-----|
|Local  <br/> |Llamadas locales  <br/> |
|Long-Distance  <br/> |Llamadas de larga distancia  <br/> |
|International  <br/> |Llamadas internacionales  <br/> |
|Delhi  <br/> |Empleados a tiempo completo de Delhi  <br/> |
|Redmond  <br/> |Empleados a tiempo completo de Redmond  <br/> |
|RedmondTemps  <br/> |Empleados temporales de Redmond  <br/> |
|Zúrich  <br/> |Empleados a tiempo completo de Zúrich  <br/> |
   
Por sí mismos, los registros de uso de RTC no hacen nada. Para que funcionen, debe asociarlos con lo siguiente:
  
- Directivas de voz, que se asignan a los usuarios.
    
- Rutas, que se asignan a números de teléfono.
    
## <a name="voice-routes"></a>Rutas de voz

Las rutas de llamada especifican cómo Skype Empresarial Server controla las llamadas salientes realizadas por Telefonía IP empresarial usuarios. Cuando un usuario marca un número, el servidor front-end normaliza la cadena de marcado al formato E.164, si es necesario, e intenta hacerlo coincidir con un URI de SIP. Si el servidor no puede hacer la coincidencia, aplica la lógica de enrutamiento de llamadas salientes en función del número. El último paso para definir esa lógica es crear una ruta de llamada con nombre independiente para cada conjunto de números de teléfono de destino que se enumeran en cada plan de marcado.
  
Antes de definir rutas de llamadas salientes, debe completar los siguientes pasos:
  
- Implemente uno o varios troncos.
    
- Cree planes de marcado según sea necesario para sitios, personas y objetos Contact.
    
- Crear registros de uso de la red telefónica conmutada (RTC).
    
Además, para habilitar el enrutamiento de llamadas salientes, debe crear y asignar una o más directivas de voz. Puede hacerlo antes o después de definir rutas de llamadas salientes.
  
Para cada ruta, debe especificar:
  
- Nombre por el que se puede identificar fácilmente la ruta.
    
- Una descripción opcional en los casos en los que el nombre solo puede no ser suficiente para describir la ruta.
    
- Patrón de coincidencia de expresiones regulares que identifica los números de teléfono de destino a los que se aplica la ruta, junto con excepciones a las que no se va a aplicar el patrón de coincidencia.
    
- Uno o varios troncos que desea asignar a la ruta.
    
- Los registros de uso de RTC que los usuarios deben tener para llamar a números que coincidan con la expresión regular del número de teléfono de destino.
    
Puede especificar rutas de llamada en el Panel de control de Skype Empresarial Server. Estas rutas de llamada rellenan la tabla de enrutamiento del servidor, que Skype Empresarial Server usa para enrutar las llamadas destinadas a la RTC.
  
### <a name="mn-trunk-support"></a>Compatibilidad con troncos M:N

Skype Empresarial Server proporciona flexibilidad en la forma en que se enrutan las llamadas a la RTC. Una ruta de voz especifica un conjunto de troncos a la RTC que se pueden usar para una llamada de voz determinada. Un tronco asocia un servidor de mediación y un número de puerto con una puerta de enlace RTC y un número de puerto de escucha. Esta asociación lógica permite que un servidor de mediación esté asociado a varias puertas de enlace y tenga varias conexiones a la misma puerta de enlace. Al definir una ruta de llamada, se especifican los troncos asociados a esa ruta, pero no se especifica qué servidores de mediación están asociados a la ruta. Para crear troncos definiendo las relaciones entre servidores de mediación y puertas de enlace RTC, IP-PBX y controladores de borde de sesión (SBC), use el Generador de topologías.
  
### <a name="least-cost-routing"></a>Least-Cost enrutamiento

La capacidad de especificar los troncos a los que se enrutan varios números permite determinar qué rutas conllevan los costos más bajos e implementarlas en consecuencia. La regla general al seleccionar troncos es elegir el tronco con la puerta de enlace más cercana a la ubicación del número de destino para minimizar los cargos de larga distancia. Por ejemplo, si está en Nueva York y llama a un número en Roma, llevará la llamada a través de la red IP al tronco con la puerta de enlace en su oficina de Roma, lo que conlleva un cargo solo para una llamada local.
  
Para obtener un ejemplo de cómo se puede usar el enrutamiento de menor costo, tenga en cuenta lo siguiente: Fabrikam decide permitir que los usuarios alemanes marquen números de Estados Unidos mediante el tronco de Estados Unidos. Fabrikam también desea configurar el sistema para que todas las llamadas de los usuarios de Skype Empresarial Server a Alemania y países o regiones adyacentes finalicen en el tronco con la puerta de enlace en Alemania. Este enrutamiento ahorrará dinero, ya que una llamada de Alemania a Austria, por ejemplo, es menos costosa que una llamada de Estados Unidos a Austria.
  
### <a name="translating-outbound-dial-strings"></a>Traducción de cadenas de marcado salientes

Skype Empresarial Server requiere que todas las cadenas de marcado se normalizan al formato E.164 con el fin de realizar una búsqueda inversa de números (RNL). Para los troncos con puertas de enlace o centrales de conexas privadas (PBX) que requieren números traducidos en formatos de marcado local, Skype Empresarial Server permite crear una o más reglas que ayudan a manipular el número llamado (es decir, solicitar URI) antes de enrutarlo al tronco. Por ejemplo, podría escribir una regla para quitar +44 del jefe de una cadena de marcado y reemplazarla por 0144.
  
Con Skype Empresarial Server, es posible crear una o más reglas que ayuden a manipular el número de llamada antes de enrutarlo al tronco.
  
Al planear los troncos que asocian pares gateway:port con pares de servidor de mediación:puerto, puede resultar útil agrupar troncos con requisitos de marcado locales similares y, por lo tanto, reducir el número de reglas de traducción necesarias y el tiempo necesario para escribirlas.
  
### <a name="configuring-caller-id"></a>Configuración del identificador de autor de la llamada

Skype Empresarial Server proporciona una forma de manipular el identificador de autor de la llamada para las llamadas salientes. Por ejemplo, si una organización quiere enmascarar las extensiones de marcado directo de los empleados y reemplazarlas por el número corporativo o departamental genérico, un administrador puede hacerlo mediante el Panel de control de Skype Empresarial Server para suprimir el identificador de autor de la llamada y reemplazarlo por un identificador de llamador alternativo especificado. Al planear la lógica de enrutamiento, tenga en cuenta para qué personas, grupos, sitios deseará esta opción, tal vez, incluso para todos los empleados.
  
> [!NOTE]
> En el caso de las llamadas que se reenrutan a través de la RTC, se mostrará el identificador de autor de la llamada genérico en lugar del identificador de autor de la llamada original. Esto puede hacer que la llamada omita la configuración de privacidad o No molestar que haya configurado el destinatario de la llamada. 
  
### <a name="additional-routing-logic"></a>Lógica de enrutamiento adicional

Al crear rutas de llamadas salientes, debe tener en cuenta los siguientes factores que pueden afectar a la lógica de enrutamiento:
  
- Cuando se establece una llamada sobre un límite federado, la parte de dominio del URI se usa para enrutar la llamada a la empresa responsable de aplicar la lógica de enrutamiento saliente.
    
- Si la parte de dominio del URI de solicitud no contiene un dominio admitido para la empresa, el componente de enrutamiento saliente del servidor no procesa la llamada.
    
- Si un usuario no está habilitado para Telefonía IP empresarial, el servidor aplica otra lógica de enrutamiento, según corresponda.
    
- Si una llamada se enruta a una puerta de enlace totalmente ocupada (todas las líneas troncales están ocupadas), la puerta de enlace rechaza la llamada y la lógica de enrutamiento saliente redirige la llamada a la ruta de menor costo. Tenga en cuenta esto detenidamente, ya que una puerta de enlace de tamaño de una pequeña oficina en el extranjero (por ejemplo, Zúrich) puede llevar realmente una cantidad significativa de tráfico no local para llamadas internacionales a Suiza. Si la puerta de enlace no tiene el tamaño correcto para este tráfico adicional, las llamadas a Suiza se pueden enrutar a través de una puerta de enlace en Alemania, lo que resulta en cargos de pago más grandes.
