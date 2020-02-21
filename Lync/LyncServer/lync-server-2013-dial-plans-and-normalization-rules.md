---
title: 'Lync Server 2013: planes de marcado y reglas de normalización'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Dial plans and normalization rules
ms:assetid: fde45195-6eb4-403c-9094-57df7fc0bd2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413082(v=OCS.15)
ms:contentKeyID: 48185960
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: edd44cbb1e54e811fc646a99362b18a284376953
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213426"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dial-plans-and-normalization-rules-in-lync-server-2013"></a>Planes de marcado y reglas de normalización en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-21_

Un plan de marcado es un conjunto de reglas de normalización especificado por el usuario que convierte números de teléfono para una ubicación especificada por el usuario, un usuario individual o un objeto de contacto a un formato estándar único (E.164) con fines de autorización telefónica y enrutamiento de llamadas.

Las reglas de normalización definen la forma en que los números de teléfono expresados en diversos formatos se van a enrutar en cada ubicación, usuario u objeto de contacto que se haya especificado. La misma cadena de marcado se puede interpretar y convertir de manera diferente, en función de la ubicación desde la que se marque y de la persona o el objeto de contacto que realice la llamada.

<div>

## <a name="dial-plan-scope"></a>Ámbito del plan de marcado

El *ámbito* de un plan de marcado determina el nivel jerárquico en el que se puede aplicar el plan de marcado. En Lync Server, a un usuario se le puede asignar un plan de marcado por usuario específico. Si no se asigna un plan de marcado de usuario, se aplica el plan de marcado de grupo de registrador. Si no hay un plan de marcado de grupo de registrador, se aplica el plan de marcado de sitio. Por último, si no hay otro plan de marcado aplicable al usuario, se aplica el plan de marcado global.

Los clientes obtienen niveles de ámbito del plan de marcado mediante la configuración de aprovisionamiento en banda que se proporciona cuando los usuarios inician sesión en Lync Server. Como administrador, puede administrar y asignar niveles de ámbito del plan de marcado mediante el panel de control de Lync Server.

<div>


> [!NOTE]  
> El plan de marcado de puerta de enlace de red telefónica conmutada (RTC) de nivel de servicio se aplica a las llamadas entrantes de una puerta de enlace concreta.



</div>

Los niveles de ámbito de plan de marcado se definen de la manera siguiente:

  - **Plan de marcado de usuario:** Se puede asignar a usuarios individuales, grupos o a objetos de contacto. Las aplicaciones de voz pueden buscar un plan de marcado por usuario cuando se recibe una llamada con el contexto de teléfono establecido en el predeterminado del usuario. Con el fin de asignar un plan de marcado, un objeto de contacto se considera un usuario individual.

  - **Plan de marcado del Grupo:** Se pueden crear en el nivel de servicio de cualquier puerta de enlace RTC o registrador de la topología. Para definir un plan de marcado de grupo, debe especificarse el servicio (puerta de enlace de RTC o grupo de registrador) en el que se aplica el plan de marcado.

  - **Plan de marcado de sitio:** Se puede crear para un sitio completo, excepto para los usuarios, grupos o objetos de contacto a los que se haya asignado un plan de marcado de grupo o de usuario. Para definir un plan de marcado de sitio, debe especificar el sitio en el que se aplica el plan de marcado.

  - **Plan de marcado global:** El plan de marcado predeterminado instalado con el producto. El plan de marcado global puede editarse, pero no eliminarse. Este plan de marcado se aplica a todos los usuarios, grupos y objetos de contacto de Enterprise Voice en su implementación, a menos que configure y asigne un plan de marcado con un ámbito más específico.

</div>

<div>

## <a name="planning-for-dial-plans"></a>Planeación de planes de marcado

Para planear un plan de marcado, siga estos pasos:

  - Enumera todas las configuraciones regionales en las que la organización tiene una oficina.
    
    La lista debe estar actualizada y completa. Deberá revisarse a medida que evolucione la compañía. En una gran empresa multinacional con numerosas pequeñas sucursales, esta tarea puede llevar mucho tiempo.

  - Identificar patrones de números válidos para cada sitio.
    
    La tarea que más tiempo requiere en el marco de la planeación de los planes de marcado es la identificación de los modelos de número válidos para cada sitio. En algunos casos, se podrán copiar en otros planes de marcado las reglas de normalización escritas para un plan de marcado, sobre todo si los sitios correspondientes están dentro del mismo país o región o incluso en el mismo continente. En otros casos, pequeñas modificaciones en los números de un plan de marcado pueden bastar para usarse en otros planes de marcado.

  - Desarrollar un esquema de organización para la asignación de nombres a los planes de marcado.
    
    Adoptar un esquema estándar de asignación de nombres asegura la coherencia en toda la organización y facilita los procesos de mantenimiento y actualización.

  - Decida si se requieren varios planes de marcado para una sola ubicación.
    
    Si su organización mantiene un solo plan de marcado en varias ubicaciones, es posible que tenga que crear un plan de marcado independiente para los usuarios de Enterprise Voice que migren desde una central de conmutación (PBX) y que necesiten mantener sus extensiones existentes.

  - Decida si los planes de marcado por usuario son necesarios. Por ejemplo, si tiene usuarios en un sitio de sucursal que están registrados en el sitio central o si tiene usuarios registrados en una aplicación de sucursal con funciones de supervivencia, puede considerar escenarios especiales de marcado para los usuarios con planes de marcado y reglas de normalización por usuario. . Para obtener información detallada, consulte [Branch-site Resiliency Requirements for Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md).

  - Determine el ámbito del plan de marcado (como se describió anteriormente en este tema).

Para crear un plan de marcado, especifique valores en los campos siguientes, según sea necesario, mediante el panel de control de Lync Server o el shell de administración de Lync Server.

<div>

## <a name="name-and-simple-name"></a>Nombre y Nombre simple

Para los planes de marcado de los usuarios, debe especificar un nombre descriptivo que identifique los usuarios, los grupos o los objetos de contacto a los que se asignará el plan de marcado. En el caso de planes de marcado de sitio, el campo Nombre se rellena previamente con el nombre del sitio y no se puede modificar. Para los planes de marcado de grupo, el campo nombre se rellena previamente con el nombre de dominio completo (FQDN) del grupo de servidores front-end o la puerta de enlace RTC, y no se puede cambiar.

El *nombre simple* del plan de marcado se rellena previamente con una cadena que se deriva del nombre del plan de marcado. El campo nombre simple es editable, lo que le permite crear una Convención de nomenclatura más descriptiva para los planes de marcado. El valor del *nombre simple* no puede estar vacío y debe ser único. Un procedimiento recomendado es desarrollar una Convención de nomenclatura para toda la organización y, a continuación, usar esta Convención de forma coherente en todos los sitios y usuarios.

</div>

<div>

## <a name="description"></a>Descripción

Se recomienda escribir el nombre común y reconocible de la ubicación geográfica en la que se aplica el plan de marcado correspondiente. Por ejemplo, si el nombre del plan de marcado es Londres.Contoso.com, la descripción recomendada es Londres.

</div>

<div>

## <a name="dial-in-conferencing-region"></a>Región de conferencia de acceso telefónico local

Si se implementan conferencias de acceso telefónico local, debe especificarse una región de conferencias de acceso telefónico local para asociar números de acceso de conferencias de acceso telefónico local con un plan de marcado.

</div>

<div>

## <a name="external-access-prefix"></a>Prefijo de acceso externo

Puede especificar un prefijo de acceso externo de hasta cuatro caracteres (\#, \*y 0-9) si los usuarios necesitan marcar uno o más dígitos iniciales adicionales (por ejemplo, 9) para obtener una línea externa.

<div>


> [!NOTE]  
> Si especifica un prefijo de acceso externo, no necesita crear otra regla de normalización para incluir el prefijo.



</div>

</div>

</div>

<div>

## <a name="normalization-rules"></a>Reglas de normalización

Las reglas de normalización definen cómo deben enrutarse los números de teléfono expresados en diversos formatos para la ubicación con nombre. La misma cadena de números puede interpretarse y traducirse de forma diferente, dependiendo de la configuración regional desde la que se marque. Las reglas de normalización son necesarias para el enrutamiento y la autorización de las llamadas, ya que los usuarios pueden usar (y usan) diversos formatos al escribir los números de teléfono en sus listas de contactos.

La normalización de los números de teléfono proporcionados por el usuario proporciona un formato coherente que facilita las tareas siguientes:

  - Hacer coincidir un número marcado con el SIP-URI del destinatario correspondiente.

  - Aplicar reglas de autorización de marcado al usuario que realiza la llamada.

Los siguientes campos numéricos están entre los que deben tener en cuenta las reglas de normalización:

  - Plan de marcado

  - Código de país

  - Código de área

  - Longitud de extensión

  - Prefijo de sitio

<div>

## <a name="creating-normalization-rules"></a>Creación de reglas de normalización

Las reglas de normalización utilizan expresiones regulares de .NET Framework para especificar patrones de coincidencia numérica que el servidor usa para traducir cadenas de marcado al formato E. 164 con el fin de realizar la búsqueda inversa de números. Puede crear reglas de normalización en el panel de control de Lync Server si escribe las expresiones manualmente o si escribe los dígitos iniciales y la longitud de las cadenas de marcado para coincidir y permite que el panel de control de Lync Server genere el correspondiente. expresión regular para usted. En cualquier caso, cuando termine, puede escribir un número de prueba para comprobar que la regla de normalización funciona según lo esperado.

Para obtener información detallada sobre el uso de expresiones regulares de .NET Framework, vea "expresiones [https://go.microsoft.com/fwlink/p/?linkId=140927](https://go.microsoft.com/fwlink/p/?linkid=140927)regulares de .NET Framework" en.

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
<th>Nombre de regla</th>
<th>Descripción</th>
<th>Modelo de número</th>
<th>Translation</th>
<th>Ejemplo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>4digitExtension</p></td>
<td><p>Convierte extensiones de 4 dígitos</p></td>
<td><p>^ (\d{4}) $</p></td>
<td><p>+ 1425555 $1</p></td>
<td><p>0100 se convierte en +14255550100</p></td>
</tr>
<tr class="even">
<td><p>5digitExtension</p></td>
<td><p>Convierte extensiones de 5 dígitos</p></td>
<td><p>^ 5 (\d{4}) $</p></td>
<td><p>+ 1425555 $1</p></td>
<td><p>50100 se convierte en +14255550100</p></td>
</tr>
<tr class="odd">
<td><p>7digitcallingRedmond</p></td>
<td><p>Convierte números de 7 dígitos en números locales de Redmond</p></td>
<td><p>^ (\d{7}) $</p></td>
<td><p>+ 1425 $1</p></td>
<td><p>5550100 se convierte en +14255550100</p></td>
</tr>
<tr class="even">
<td><p>7digitcallingDallas</p></td>
<td><p>Convierte números de 7 dígitos en números locales de Dallas</p></td>
<td><p>^ (\d{7}) $</p></td>
<td><p>+ 1972 $1</p></td>
<td><p>5550100 se convierte en +19725550100</p></td>
</tr>
<tr class="odd">
<td><p>10digitcallingUS</p></td>
<td><p>Convierte números de 10 dígitos en los Estados Unidos</p></td>
<td><p>^ (\d{10}) $</p></td>
<td><p>+ 1 $1</p></td>
<td><p>2065550100 se convierte en +12065550100</p></td>
</tr>
<tr class="even">
<td><p>LDCallingUS</p></td>
<td><p>Convierte los números con prefijos de larga distancia de Estados Unidos</p></td>
<td><p>^ 1 (\d{10}) $</p></td>
<td><p>+ $1</p></td>
<td><p>12145550100 se convierte en +2145550100</p></td>
</tr>
<tr class="odd">
<td><p>IntlCallingUS</p></td>
<td><p>Convierte los números con prefijos internacionales de Estados Unidos</p></td>
<td><p>^ 011 (\d *) $</p></td>
<td><p>+ $1</p></td>
<td><p>01191445550100 se convierte en +91445550100</p></td>
</tr>
<tr class="even">
<td><p>RedmondOperator</p></td>
<td><p>Convierte 0 al operador de Redmond</p></td>
<td><p>^ $0</p></td>
<td><p>+ 14255550100</p></td>
<td><p>0 se convierte en +14255550100</p></td>
</tr>
<tr class="odd">
<td><p>RedmondSitePrefix</p></td>
<td><p>Convierte los números con prefijo de red (6) y prefijo de sitio de Redmond (222)</p></td>
<td><p>^ 6222 (\d{4}) $</p></td>
<td><p>+ 1425555 $1</p></td>
<td><p>62220100 se convierte en +14255550100</p></td>
</tr>
<tr class="even">
<td><p>NYSitePrefix</p></td>
<td><p>Convierte los números con prefijo de red (6) y prefijo de sitio de Nueva York (333)</p></td>
<td><p>^ 6333 (\d{4}) $</p></td>
<td><p>+ 1202555 $1</p></td>
<td><p>63330100 se convierte en +12025550100</p></td>
</tr>
<tr class="odd">
<td><p>DallasSitePrefix</p></td>
<td><p>Convierte los números con prefijo de red (6) y prefijo de sitio de Dallas (444)</p></td>
<td><p>^ 6444 (\d{4}) $</p></td>
<td><p>+ 1972555 $1</p></td>
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
<th>Redmond. forestFQDN</th>
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
> Aunque los nombres de las reglas de normalización que se muestran en la tabla anterior no incluyen espacios, es opcional usarlos. Por ejemplo, el primer nombre de la tabla se podía haber escrito como "Extensión de 5 dígitos" y sería un nombre válido.



</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

