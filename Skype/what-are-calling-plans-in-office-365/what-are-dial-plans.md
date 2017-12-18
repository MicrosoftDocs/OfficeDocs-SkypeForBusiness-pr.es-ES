---
title: "¿Cuáles son los planes de marcado?"
ms.author: tonysmit
author: tonysmit
ms.date: 11/17/2017
ms.audience: Admin
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.custom: Strat_SB_PSTN
ms.assetid: 2f0cfb59-1ca1-4e31-84ce-09d0b1a7ce1b
description: "Learn what type of dial calling plans (PSTN Calling dial plans) are available with Office 365 and how to choose one for your company.  "
---

# ¿Cuáles son los planes de marcado?

> [!IMPORTANT]
> Este artículo se ha traducido con traducción automática; vea la declinación de responsabilidades.  
  
Un plan de marcado es un conjunto determinado de reglas de normalización que traducen los números de teléfono marcados por un usuario individual a un formato alternativo (generalmente E.164) para fines de autorización y enrutamiento de llamada.
  
Un plan de marcado consta de una o más reglas de normalización que definen cómo expresados en varios formatos de números de teléfono se convierten a un formato alternativo. La misma cadena de acceso telefónico se puede interpretar y traducir de forma diferente en otros planes de marcado, para dependiendo de qué plan de marcado está asignada a un usuario determinado, se marca el mismo número puede traducir y se enrutan de forma distinta.
  
Consulte [Crear y administrar planes de marcado](create-and-manage-dial-plans.md) para crear y administrar planes de marcado de inquilinos.
  
## Alcance de un plan de marcado inquilino

Ámbito de un plan de marcado determina el nivel jerárquico en el que se pueden aplicar el plan de marcado. Los ámbitos son diferentes en un Skype empresarial Server 2015 local implementación. Los clientes obtener el plan de marcado adecuado a través de aprovisionamiento de configuración que se proporciona automáticamente cuando los usuarios inician sesión Skype empresarial Online. Como administrador, puede administrar y asignar niveles de ámbito del plan de marcado con PowerShell remoto.
  
En Skype empresarial Online, hay dos tipos de planes de marcado: el ámbito del servicio e inquilino (que es para su organización) ámbito. Un plan de marcado de ámbito de servicio se define para cada país o región donde está disponible el sistema de teléfono de Office 365. Cada usuario se asigna automáticamente el plan de marcado de país de servicio que coincida con la ubicación de uso de Office 365 asignados al usuario. No puede cambiar el plan de marcado de país de servicio, pero puede crear planes de marcado de inquilinos ámbito, que aumentan el plan de marcado de país de servicio. Como los clientes aprovisionados, obtienen un "plan de marcado eficaz", que es una combinación del plan de marcado de país de servicio y el plan de marcado de inquilinos adecuadamente ámbito. Por lo tanto, no es necesario definir todas las reglas de normalización en planes de marcado de inquilinos pueden ya están en el plan de marcado de país de servicio.
  
Los planes de marcado de inquilino se pueden dividir en dos alcances: el alcance de inquilino o el alcance de usuario. Si un inquilino define y asigna un plan de marcado de alcance de usuario, ese usuario recibirá un plan de marcado efectivo del plan de marcado del país de servicio del usuario y el plan de marcado del usuario asignado. Si un inquilino define un plan de marcado de alcance de inquilino pero no asigna un plan de marcado de alcance de usuario, ese usuario recibirá un plan de marcado efectivo del plan de marcado del país de servicio del usuario y el plan de marcado de inquilino.
  
El siguiente es el modelo de herencia de los planes de marcado en Skype Empresarial Online.
  
![How dial plans are inherited in Skype for Business Online.](../images/b2744f33-ebbd-4c23-bfba-1747312ab178.png)
  
Los siguientes son los posibles planes de marcado efectivos:
  
 **País de servicio** Si no se define ningún plan de marcado de inquilinos ámbito y ningún plan de marcado de ámbito de usuario inquilino se asigna al usuario aprovisiona, el usuario recibirá un plan de marcado eficaces asignado al país servicio asociado a su ubicación de uso de Office 365.
  
 **Inquilino Global - país de servicio** Si un plan de marcado de usuario inquilino está definido pero no asignado a un usuario, el usuario aprovisiona recibirá un plan de marcado eficaz formada por un plan de marcado de inquilinos combinadas y el plan de marcado de país de servicio asociada a su ubicación de uso de Office 365.
  
 **Usuario inquilino - país de servicio** Si un plan de marcado de usuario inquilino está definido y asignado a un usuario, el usuario aprovisiona recibirá un plan de marcado eficaz formada por el plan de marcado de usuario inquilino combinadas y el plan de marcado de país de servicio asociada a su ubicación de uso de Office 365.
  
Consulte [Crear y administrar planes de marcado](create-and-manage-dial-plans.md) para crear el inquilino de planes de marcado.
  
## Diseño de planes de marcado de inquilino

Para planificar los planes de marcado de inquilino siga estos pasos:
  
- **Paso 1** Decida si marcado personalizado plan es necesaria para mejorar el marcado experiencia de usuario. Normalmente, la necesidad de uno sería marcado no E.164, como las extensiones de soporte técnico o abrevia marcado nacional.
    
- **Paso 2** Determinar si se necesitan global del inquilino o inquilino planes de marcado de ámbito de usuario o ambos. Planes de marcado de ámbito de usuario son necesarios si los usuarios tienen requisitos distintos marcado local.
    
- **Paso 3** Identificar una cantidad válida de patrones para cada plan de marcado necesario. Únicamente son necesarios los patrones de números que no están definidos en los planes de marcado del país de nivel de servicios.
    
- **Paso 4** Desarrollar un esquema a nivel de la organización para nombrar los planes de marcado. Al adoptar un esquema de denominación estándar se asegura la coherencia en una organización y se facilita el mantenimiento y las actualizaciones.
    
La [FastTrack](https://fasttrack.microsoft.com/microsoft365/capabilities?view=voice) tiene recursos adicionales y planes de marcado de socios que pueden ayudarle con la implementación de inquilinos.
  
## Crear su nuevo plan de marcado de inquilino

Al crear un nuevo plan de marcado, debe ingresar la información que se solicita.
  
### Nombre y nombre simple

Para planes de marcado de usuario, debe especificar se asignará un nombre descriptivo que identifica a los usuarios el plan de marcado. El plan de marcado nombre sencillo es rellenados previamente con una cadena que se deriva el nombre del plan de marcado. El campo nombre sencillo es editable, que le permite crear una convención de nomenclatura más descriptiva para el plan de marcado. El valor de nombre Simple no puede estar vacío y debe ser único. Un procedimiento recomendado es desarrollar una convención de nomenclatura para toda la organización y, a continuación, usar esta convención de forma uniforme en todos los sitios y usuarios.
  
### Descripción

Le recomendamos que escriba el nombre común y reconocible de la ubicación geográfica o el grupo de usuarios a los que se aplica el plan de marcado correspondiente.
  
### Prefijo de acceso externo

> [!CAUTION]
> El prefijo de acceso externo aún no es compatible. 
  
Puede especificar un prefijo de acceso externo de hasta 4 caracteres (#, * y 0-9) si los usuarios deben marcar un dígito adicional o más (por ejemplo, 9) para obtener una línea externa.
  
> [!NOTE]
> Si especifica un prefijo de acceso externo, no es necesario crear una regla de normalización adicional para incorporar el prefijo. 
  
Consulte [Crear y administrar planes de marcado](create-and-manage-dial-plans.md) para crear el inquilino de planes de marcado.
  
## Reglas de normalización

Las reglas de normalización definen cómo se traducen los números expresados en varios formatos. La misma línea de número se puede interpretar y traducir de diferentes maneras, según la ubicación desde la que se marca. Las reglas de normalización pueden ser necesarias y los usuarios deben tener la capacidad de marcar números internos y externos abreviados.
  
Una o más reglas de normalización deben tener asignadas al plan de marcado. Reglas de normalización se comparan de arriba a abajo, por lo que es importante el orden en que aparecen en un plan de marcado de inquilinos. Por ejemplo, si un plan de marcado de inquilinos tiene 10 reglas de normalización, la lógica coincidente número marcada se marcarán comenzando por la primera regla de normalización, si no hay una coincidencia, a continuación, en la segunda etc.. Si se realiza una coincidencia, se utiliza esa regla y no hay ningún esfuerzo para que coincida con las demás reglas que se definen. Puede haber un máximo de 25 reglas de normalización en un plan de marcado de inquilinos determinado.
  
### Determinar las reglas de normalización necesarias

Como todo plan de marcado inquilino se combina efectivamente con un plan de marcado del país de servicio de un usuario dado, es probable que las reglas de normalización del plan de marcado del país de servicio deban ser evaluadas para determinar cuáles de ellas son necesarias por parte del plan de marcado inquilino. Se puede utilizar efectivamente el cmdlet de **Get-CsEffectiveTenantDialPlan** para este propósito. El cmdlet toma la identidad del usuario como parámetro de entrada y devolverá todas las reglas de normalización aplicables al usuario.
  
### Crear reglas de normalización

Las reglas de normalización utilizan expresiones regulares de .NET Framework para especificar los patrones de coincidencia numérica que utiliza el servidor para traducir líneas de marcado a formato E.164 para realizar la búsqueda inversa de número. Las reglas de normalización se pueden crear al especificar la expresión habitual para la coincidencia y la traducción que se debe realizar al encontrarla. Al terminar puede ingresar un número de prueba para verificar que la regla de normalización funcione según lo esperado.
  
Para obtener información detallada sobre el uso de expresiones regulares de .NET Framework, vea [Expresiones regulares de .NET Framework](https://go.microsoft.com/fwlink/p/?linkId=140927).
  
Consulte [Crear y administrar planes de marcado](create-and-manage-dial-plans.md) para crear y administrar normalización reglas de su inquilino de planes de marcado.
  
### Reglas de normalización de muestra

La siguiente tabla muestra reglas de normalización de muestra que se escriben como expresiones regulares de .NET Framework. Las muestras son meramente ejemplos y no sirven como referencia prescriptiva para crear sus propias reglas de normalización.
  
 **Reglas de normalización usando expresiones regulares de .NET Framework**
  
||||||
|:-----|:-----|:-----|:-----|:-----|
|**Nombre de la regla** <br/> |**Descripción** <br/> |**Patrón de números** <br/> |**Traducción** <br/> |**Ejemplo** <br/> |
|Extensión4dígitos  <br/> |Traduce extensiones de 4 dígitos.  <br/> |^(\\d{4})$  <br/> |+1425555$1  <br/> |0100 se traduce a +14255550100  <br/> |
|Extensión5dígitos  <br/> |Traduce extensiones de 5 dígitos.  <br/> |^5(\\d{4})$  <br/> |+1425555$1  <br/> |50100 se traduce a +14255550100  <br/> |
|LlamadaRedmond7dígitos  <br/> |Traduce números de 7 dígitos a números locales de Redmond.  <br/> |^(\\d{7})$  <br/> |+1425$1  <br/> |5550100 se traduce a +14255550100  <br/> |
|OperadorRedmond  <br/> |Traduce 0 a Operador de Redmond.  <br/> |^0$  <br/> |+14255550100  <br/> |0 se traduce a +14255550100  <br/> |
|PrefijoSitioRedmond  <br/> |Traduce números con un prefijo de red (6) y el código de sitio de Redmond (222).  <br/> |^6222(\\d{4})$  <br/> |+1425555$1  <br/> |62220100 se traduce a +14255550100  <br/> |
|Rango5dígitos  <br/> |Traduce extensiones de 5 dígitos a partir del rango de dígitos entre 3 y 7 inclusive.  <br/> |^([3-7]\\d{4})$  <br/> |+142570$1  <br/> |54567 se traduce a +14255554567  <br/> |
|PrefijoAñadido  <br/> |Añade un prefijo de país delante de un número de 9 dígitos con restricciones en el primer y el tercer dígito.  <br/> |^([2-9]\\d\\d[2-9]\\d{6})$  <br/> |1$1  <br/> |4255554567 se traduce a 14255554567  <br/> |
|SinTraducción  <br/> |Coinciden 5 dígitos pero no hay traducción.  <br/> |^(\\d{5})$  <br/> |$1  <br/> |34567 se traduce a 34567  <br/> |
   
 **Plan de marcado de Redmond basado en las reglas de normalización que se describen anteriormente.**
  
La siguiente tabla ilustra un plan de marcado de muestra para Redmond, Washington, Estados Unidos, basado en las reglas de normalización que se muestran en la tabla anterior.
  
||
|:-----|
|**Plan de marcado de Redmond** <br/> |
|Extensión5dígitos  <br/> |
|LlamadaRedmond7dígitos  <br/> |
|PrefijoSitioRedmond  <br/> |
|OperadorRedmond  <br/> |
   
> [!NOTE]
> Los nombres de las reglas de normalización que se muestran en la tabla anterior no incluyen espacios, pero esto es opcional. Por ejemplo, el primer nombre de la tabla podría haberse escrito como "extensión de 5 dígitos" o "Extensión de 5 dígitos" y ser igualmente válido. 
  
## Temas relacionados

[Crear y administrar planes de marcado](create-and-manage-dial-plans.md)
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Declinación de responsabilidades de traducción automática**: Este artículo se ha traducido con un sistema informático sin intervención humana. Microsoft ofrece estas traducciones automáticas para que los hablantes de otros idiomas distintos del inglés puedan disfrutar del contenido sobre los productos, los servicios y las tecnologías de Microsoft. Puesto que este artículo se ha traducido con traducción automática, es posible que contenga errores de vocabulario, sintaxis o gramática. 
  

