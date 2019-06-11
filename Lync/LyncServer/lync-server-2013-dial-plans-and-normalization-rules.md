---
title: 'Lync Server 2013: planes de marcado y reglas de normalización'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Dial plans and normalization rules
ms:assetid: fde45195-6eb4-403c-9094-57df7fc0bd2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413082(v=OCS.15)
ms:contentKeyID: 48185960
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5d399c49db109a7bac1a1cd3ac430280cb70f665
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835420"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dial-plans-and-normalization-rules-in-lync-server-2013"></a>Planes de marcado y reglas de normalización en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-21_

Un plan de marcado es un conjunto de reglas de normalización especificado por el usuario que convierte números de teléfono para una ubicación especificada por el usuario, un usuario individual o un objeto de contacto a un formato estándar único (E.164) con fines de autorización telefónica y enrutamiento de llamadas.

Las reglas de normalización definen la forma en que los números de teléfono expresados en diversos formatos se van a redirigir en cada ubicación, usuario u objeto de contacto que se haya especificado. La misma cadena de marcado se puede interpretar y convertir de manera distinta en función de la ubicación desde la que se marque y la persona o el objeto de contacto que realice la llamada.

<div>

## <a name="dial-plan-scope"></a>Ámbito del plan de marcado

El *ámbito* de un plan de marcado determina el nivel jerárquico en el que se puede aplicar. En Lync Server, un usuario puede tener asignado un plan de marcado por usuario específico. Si no se asigna un plan de marcado de usuario, se aplica el plan de marcado de la agrupación de registradores. Si no hay ningún plan de marcado del grupo de registradores, se aplica el plan de marcado del sitio. Por último, si no hay otro plan de marcado aplicable al usuario, se aplica el plan de marcado global.

Los clientes obtienen niveles de ámbito del plan de marcado mediante la configuración de aprovisionamiento en banda que se proporciona cuando los usuarios inician sesión en Lync Server. Como administrador, puede administrar y asignar niveles de ámbito de plan de marcado mediante el panel de control de Lync Server.

<div>


> [!NOTE]  
> El plan de marcado de la puerta de enlace de la red telefónica conmutada (RTC) de nivel de servicio se aplica a las llamadas entrantes de una determinada puerta de enlace.



</div>

Los niveles de ámbito del plan de marcado se definen de la manera siguiente:

  - **Plan de marcado del usuario:** Puede asignarse a usuarios individuales, grupos o a objetos de contactos. Las aplicaciones de voz pueden buscar un plan de marcado por usuario cuando una llamada se recibe con el contexto telefónico establecido en el predeterminado para el usuario. Con el fin de asignar un plan de marcado, un objeto de contacto se considera un usuario individual.

  - **Plan de marcado de Grupo:** Se puede crear en el nivel de servicio para cualquier puerta de enlace o registrador RTC de su topología. Para definir un plan de marcado de grupo, necesitas especificar el servicio (puerta de enlace RTC o grupo de registrador) específico en el que se aplica el plan de marcado.

  - **Plan de marcado del sitio:** Puede crearse para un sitio completo, excepto para los usuarios, grupos o objetos de contacto a los que se haya asignado un plan de marcado de grupo o un plan de marcado de usuario. Para definir un plan de marcado de sitio, necesitas especificar el sitio en el que se aplica el plan de marcado.

  - **Plan de marcado global:** El plan de marcado predeterminado instalado con el producto. Puedes editar el plan de marcado global, pero no eliminarlo. Este plan de marcado se aplica a todos los usuarios, grupos y objetos de contacto de Enterprise Voice de su implementación, a menos que configure y asigne un plan de marcado con un ámbito más específico.

</div>

<div>

## <a name="planning-for-dial-plans"></a>Planificar planes de marcado

Para planificar un plan de marcado, haz lo siguiente:

  - Haz una lista de todas las configuraciones regionales en las que la organización tiene una oficina.
    
    La lista necesita estar completa y actualizada. Necesitarás revisarla a medida que evolucione la organización de la compañía. En una compañía multinacional con numerosas sucursales pequeñas, esta tarea puede demandar mucho tiempo.

  - Identifica patrones de números válidos para cada sitio.
    
    La tarea que más tiempo requiere en el marco de la planificación de los planes de marcado es la identificación de los patrones de números válidos para cada sitio. En algunos casos, se podrán copiar las reglas de normalización escritas para un plan de marcado en otros planes de marcado, sobre todo si los sitios correspondientes están dentro del mismo país o de la misma región, o incluso en el mismo continente. En otros casos, pequeñas modificaciones en los números de un plan de marcado pueden bastar para usarse en otros planes de marcado.

  - Desarrolla un esquema aplicable a toda la organización para asignar nombres a los planes de marcado.
    
    Adoptar un esquema estándar de asignación de nombres asegura la coherencia en toda la organización y facilita los procesos de mantenimiento y actualización.

  - Decide si son necesarios varios planes de marcado para una sola ubicación.
    
    Si su organización mantiene un solo plan de marcado en varias ubicaciones, es posible que aún necesite crear un plan de marcado independiente para los usuarios de telefonía IP empresarial que migren desde una central de conmutación (PBX) y tengan que mantener las extensiones existentes.

  - Decide si son necesarios los planes de marcado por usuario. Por ejemplo, si tiene usuarios en un sitio de sucursal que están registrados con el sitio central o tiene usuarios registrados en un dispositivo de sucursal con la supervivencia, puede tener en cuenta escenarios especiales de marcado para esos usuarios usando planes de marcado por usuario y reglas de normalización . Para obtener más información, consulte [requisitos de resistencia de sitio de sucursal para Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md).

  - Determina el ámbito del plan de marcado (como ya se ha explicado antes en este tema).

Para crear un plan de marcado, especifique los valores en los siguientes campos, según sea necesario, mediante el panel de control de Lync Server o el shell de administración de Lync Server.

<div>

## <a name="name-and-simple-name"></a>Nombre y Nombre simple

En los planes de marcado de usuario necesitas asignar un nombre descriptivo que identifique a los usuarios, grupos u objetos de contacto a los que se asignará el plan de marcado. En el caso de los planes de marcado del sitio, el campo nombre se rellena previamente con el nombre del sitio y no se puede cambiar. Para los planes de marcado de grupo, el campo nombre se rellena previamente con el nombre de dominio completo (FQDN) de la puerta de enlace RTC o el grupo de servidores front-end (FQDN) y no se puede cambiar.

El *nombre simple* del plan de marcado se rellena previamente con una cadena que se deriva del nombre del plan de marcado. El campo Nombre simple puede editarse, para que puedas crear una convención de nomenclatura más descriptiva para tus planes de marcado. El campo *Nombre simple* no puede quedar vacío y necesita ser exclusivo. El procedimiento recomendado es desarrollar una convención de nomenclatura para toda la organización y aplicarla con coherencia en todos los sitios y para todos los usuarios.

</div>

<div>

## <a name="description"></a>Descripción

Recomendamos escribir el nombre común y reconocible de la ubicación geográfica en la que se aplica el plan de marcado correspondiente. Por ejemplo, si el nombre del plan de marcado es Londres.Contoso.com, la descripción recomendada sería Londres.

</div>

<div>

## <a name="dial-in-conferencing-region"></a>Región de conferencia de acceso telefónico local

Si implementas conferencias de acceso telefónico local, necesitarás especificar una región de conferencias de acceso telefónico local para asociar números de acceso de conferencias de acceso telefónico local con un plan de marcado.

</div>

<div>

## <a name="external-access-prefix"></a>Prefijo de acceso externo

Puede especificar un prefijo de acceso externo de hasta cuatro caracteres (\#, \*y 0-9) si los usuarios necesitan marcar uno o varios dígitos iniciales adicionales (por ejemplo, 9) para obtener una línea externa.

<div>


> [!NOTE]  
> Si especificas un prefijo de acceso externo, no necesitas crear una regla de normalización adicional para incluir el prefijo.



</div>

</div>

</div>

<div>

## <a name="normalization-rules"></a>Reglas de normalización

Las reglas de normalización definen cómo es el enrutamiento necesario de los números de teléfono expresados en diversos formatos para la ubicación específica. La misma cadena de número se puede interpretar y convertir de manera distinta en función de la configuración regional desde la que se marque. Las reglas de normalización son necesarias para el enrutamiento de las llamadas, ya que los usuarios pueden usar (y usan) diversos formatos al escribir los números de teléfono en sus listas de contactos.

La normalización de los números de teléfono proporcionados por los usuarios aporta un formato uniforme que facilita las tareas siguientes:

  - Asociar un número marcado al URI del SIP del destinatario.

  - Aplicar las reglas de autorización de marcado al usuario que realiza la llamada.

Los siguientes campos numéricos se incluyen entre los que necesitan considerar las reglas de normalización:

  - Plan de marcado

  - Código de país

  - Código de área

  - Longitud de extensión

  - Prefijo de sitio

<div>

## <a name="creating-normalization-rules"></a>Crear reglas de normalización

Las reglas de normalización usan expresiones regulares de .NET Framework para especificar patrones numéricos coincidentes que el servidor utiliza para convertir las cadenas de marcado a formato E.164 con el fin de realizar búsquedas inversas de números. Puede crear reglas de normalización en el panel de control de Lync Server, ya sea introduciendo las expresiones manualmente, o bien especificando los dígitos iniciales y la longitud de las cadenas de marcado que deben coincidir y que el panel de control de Lync Server genere el correspondiente expresión regular para usted. Sea como fuere, al finalizar puedes especificar un número de prueba para comprobar que la regla de normalización funciona según lo previsto.

Para obtener información detallada sobre el uso de expresiones regulares de .NET Framework, vea "expresiones [http://go.microsoft.com/fwlink/p/?linkId=140927](http://go.microsoft.com/fwlink/p/?linkid=140927)regulares de .NET Framework" en.

</div>

<span id="BKMK_SampleNormalizationRules"></span>

<div>

## <a name="sample-normalization-rules"></a>Reglas de normalización de ejemplo

En la siguiente tabla se muestran ejemplos de reglas de normalización escritas como expresiones regulares de .NET Framework. Son solo ejemplos, no una referencia normativa para crear reglas de normalización.

### <a name="table-1normalization-rules-using-net-framework-regular-expressions"></a>Tabla 1. Reglas de normalización que usan expresiones regulares de .NET Framework

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>Nombre de la regla</th>
<th>Descripción</th>
<th>Patrón de números</th>
<th>Conversión</th>
<th>Ejemplo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>4digitExtension</p></td>
<td><p>Convierte extensiones de 4 dígitos</p></td>
<td><p>^ (\d{4}) $</p></td>
<td><p>+1425555$1</p></td>
<td><p>0100 se traduce a +14255550100</p></td>
</tr>
<tr class="even">
<td><p>5digitExtension</p></td>
<td><p>Convierte extensiones de 5 dígitos</p></td>
<td><p>^ 5 (\d{4}) $</p></td>
<td><p>+1425555$1</p></td>
<td><p>50100 se traduce a +14255550100</p></td>
</tr>
<tr class="odd">
<td><p>7digitcallingRedmond</p></td>
<td><p>Convierte números de 7 dígitos en números locales de Redmond</p></td>
<td><p>^ (\d{7}) $</p></td>
<td><p>+1425$1</p></td>
<td><p>5550100 se convierte en +14255550100</p></td>
</tr>
<tr class="even">
<td><p>7digitcallingDallas</p></td>
<td><p>Convierte números de 7 dígitos en números locales de Dallas</p></td>
<td><p>^ (\d{7}) $</p></td>
<td><p>+1972$1</p></td>
<td><p>5550100 se convierte en +19725550100</p></td>
</tr>
<tr class="odd">
<td><p>10digitcallingUS</p></td>
<td><p>Convierte números de 10 dígitos de Estados Unidos</p></td>
<td><p>^ (\d{10}) $</p></td>
<td><p>+1$1</p></td>
<td><p>2065550100 se convierte en +12065550100</p></td>
</tr>
<tr class="even">
<td><p>LDCallingUS</p></td>
<td><p>Convierte los números con prefijos de larga distancia de Estados Unidos</p></td>
<td><p>^ 1 (\d{10}) $</p></td>
<td><p>+$1</p></td>
<td><p>12145550100 se convierte en +2145550100</p></td>
</tr>
<tr class="odd">
<td><p>IntlCallingUS</p></td>
<td><p>Convierte los números con prefijos internacionales de Estados Unidos</p></td>
<td><p>^011(\d*)$</p></td>
<td><p>+$1</p></td>
<td><p>01191445550100 se convierte en +91445550100</p></td>
</tr>
<tr class="even">
<td><p>RedmondOperator</p></td>
<td><p>Convierte 0 al operador de Redmond</p></td>
<td><p>^0$</p></td>
<td><p>+14255550100</p></td>
<td><p>0 se traduce a +14255550100</p></td>
</tr>
<tr class="odd">
<td><p>RedmondSitePrefix</p></td>
<td><p>Convierte los números con prefijo de red (6) y prefijo de sitio de Redmond (222)</p></td>
<td><p>^ 6222 (\d{4}) $</p></td>
<td><p>+1425555$1</p></td>
<td><p>62220100 se convierte en +14255550100</p></td>
</tr>
<tr class="even">
<td><p>NYSitePrefix</p></td>
<td><p>Convierte los números con prefijo de red (6) y prefijo de sitio de Nueva York (333)</p></td>
<td><p>^ 6333 (\d{4}) $</p></td>
<td><p>+1202555$1</p></td>
<td><p>63330100 se convierte en +12025550100</p></td>
</tr>
<tr class="odd">
<td><p>DallasSitePrefix</p></td>
<td><p>Convierte los números con prefijo de red (6) y prefijo de sitio de Dallas (444)</p></td>
<td><p>^ 6444 (\d{4}) $</p></td>
<td><p>+1972555$1</p></td>
<td><p>64440100 se convierte en +19725550100</p></td>
</tr>
</tbody>
</table>


En la tabla siguiente se muestra un plan de marcado de ejemplo para Redmond, Washington, Estados Unidos, basado en las reglas de normalización que se muestran en la tabla anterior.

### <a name="table-2-redmond-dial-plan-based-on-normalization-rules-shown-in-table-1"></a>Tabla 2. Plan de marcado de Redmond basado en las reglas de normalización mostradas en la tabla 1

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th>Redmond.forestFQDN</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>5digitExtension</p></td>
</tr>
<tr class="even">
<td><p>7digitcallingRedmond</p></td>
</tr>
<tr class="odd">
<td><p>10digitcallingUS</p></td>
</tr>
<tr class="even">
<td><p>IntlCallingUS</p></td>
</tr>
<tr class="odd">
<td><p>RedmondSitePrefix</p></td>
</tr>
<tr class="even">
<td><p>NYSitePrefix</p></td>
</tr>
<tr class="odd">
<td><p>DallasSitePrefix</p></td>
</tr>
<tr class="even">
<td><p>RedmondOperator</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Los nombres de las reglas de normalización que se muestran en la tabla anterior no incluyen espacios, pero esto es opcional. Por ejemplo, el primer nombre de la tabla podría haberse escrito como "extensión de 5 dígitos" o "Extensión de 5 dígitos" y ser igualmente válido.



</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

