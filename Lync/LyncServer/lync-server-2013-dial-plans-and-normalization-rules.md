---
title: 'Lync Server 2013: Planes de marcado y reglas de normalización'
TOCTitle: Planes de marcado y reglas de normalización
ms:assetid: fde45195-6eb4-403c-9094-57df7fc0bd2a
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg413082(v=OCS.15)
ms:contentKeyID: 48277272
ms.date: 03/18/2015
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Planes de marcado y reglas de normalización en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

Un plan de marcado es un conjunto de reglas de normalización especificado por el usuario que convierte números de teléfono para una ubicación especificada por el usuario, un usuario individual o un objeto de contacto a un formato estándar único (E.164) con fines de autorización telefónica y enrutamiento de llamadas.

Las reglas de normalización definen la forma en que los números de teléfono expresados en diversos formatos se van a enrutar en cada ubicación, usuario u objeto de contacto que se haya especificado. La misma cadena de marcado se puede interpretar y convertir de manera distinta según la ubicación desde la que se marca y la persona o el objeto de contacto que realiza la llamada.

## Ámbito del plan de marcado

El *ámbito* de un plan de marcado determina el nivel jerárquico en el que se puede aplicar el plan de marcado. En Lync Server, puede asignarse a un usuario un plan de marcado específico para cada usuario. Si no se asigna un plan de marcado de usuario, se aplica el plan de marcado de grupo de registrador. Si no hay un plan de marcado de grupo de registrador, se aplica el plan de marcado de sitio. Por último, si no hay otro plan de marcado aplicable al usuario, se aplica el plan de marcado global.

Los clientes obtienen los niveles de ámbito de plan de marcado mediante la configuración de aprovisionamiento en banda que se proporciona cuando los usuarios inician sesión en Lync Server. El administrador puede controlar y asignar los niveles de ámbito de plan de marcado mediante Panel de control de Lync Server.


> [!NOTE]
> El plan de marcado de puerta de enlace de RTC de nivel de servicio se aplica a las llamadas entrantes de una determinada puerta de enlace.



Los niveles de ámbito de plan de marcado se definen de la manera siguiente:

  - **Plan de marcado de usuario:** se puede asignar a usuarios, grupos u objetos de contacto individuales. Las aplicaciones de voz pueden buscar y usar un plan de marcado por usuario al recibir el valor user-default para el atributo phone-context. Con el fin de asignar un plan de marcado, un objeto de contacto se considera un usuario individual.

  - **Plan de marcado de grupo:** puede crearse en el nivel de servicio para cualquier registrador o puerta de enlace de RTC de la topología. Para definir un plan de marcado de grupo, debe especificarse el servicio (puerta de enlace de RTC o grupo de registrador) en el que se aplica el plan de marcado.

  - **Plan de marcado de sitio:** puede crearse para un sitio en su totalidad, salvo los usuarios, grupos u objetos de contacto que estén asignados a un plan de marcado de grupo o de usuario. Para definir un plan de marcado de sitio, debe especificar el sitio en el que se aplica el plan de marcado.

  - **Plan de marcado global:** el plan de marcado predeterminado que se instala con el producto. El plan de marcado global se puede editar, pero no eliminar. Este plan de marcado se aplica a todos los usuarios, grupos y objetos de contacto de Telefonía IP empresarial incluidos en la implementación, a menos que se configure y asigne un plan de marcado de ámbito más específico.

## Planeación de planes de marcado

Para crear un plan de marcado, siga estos pasos:

  - Elaborar una lista de todas las configuraciones regionales en las que la organización tiene una oficina.
    
    La lista debe ser completa y estar actualizada. Deberá revisarse a medida que evolucione la compañía. En una compañía multinacional grande con numerosas sucursales pequeñas, esta tarea puede requerir mucho tiempo.

  - Identificar modelos de número válidos para cada sitio.
    
    La tarea que más tiempo requiere en el marco de la planeación de los planes de marcado es la identificación de los modelos de número válidos para cada sitio. En algunos casos, se podrán copiar en otros planes de marcado las reglas de normalización escritas para un plan de marcado, sobre todo si los sitios correspondientes están dentro del mismo país o región o incluso en el mismo continente. En otros casos, pequeñas modificaciones en los números de un plan de marcado pueden bastar para usarse en otros planes de marcado.

  - Desarrollar un esquema aplicable a toda la organización para asignar nombres a los planes de marcado.
    
    Adoptar un esquema estándar de asignación de nombres asegura la coherencia en toda la organización y facilita los procesos de mantenimiento y actualización.

  - Decidir si son necesarios varios planes de marcado para una sola ubicación.
    
    Si la organización mantiene un solo plan de marcado para varias ubicaciones, es probable que todavía necesite crear un plan de marcado aparte para los usuarios de Telefonía IP empresarial que migren de un sistema PBX y que necesiten conservar las extensiones actuales.

  - Decidir si son necesarios los planes de marcado por usuario. Por ejemplo, si tiene usuarios en un sitio de sucursal que están registrados en el sitio central o usuarios registrados en un Aplicación de sucursal con funciones de supervivencia, puede considerar escenarios de marcado especiales para esos usuarios mediante planes de marcado y reglas de normalización por usuario. Si desea información detallada, vea [Requisitos de resistencia de sitios de sucursal para Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md).

  - Determinar el ámbito del plan de marcado (como ya se ha explicado antes en este tema).

Para crear un plan de marcado, debe especificar valores en los campos siguientes, según se necesite, mediante el Panel de control de Lync Server o el Shell de administración de Lync Server.

## Nombre y Nombre simple

En los planes de marcado de usuario se debe asignar un nombre descriptivo que identifique a los usuarios, grupos u objetos de contacto a los que se asignará el plan de marcado. En el caso de planes de marcado de sitio, el campo Nombre se rellena previamente con el nombre del sitio y no se puede modificar. En cuanto a los planes de marcado de grupo, el campo Nombre se rellena previamente con la puerta de enlace de RTC o el FQDN de grupo front-end y no se puede modificar.

El plan de marcado de *Nombre simple* se rellena previamente con una cadena de caracteres derivada del nombre del plan de marcado. El campo Nombre simple puede modificarse. Se ha concebido para poder establecer una convención de asignación de nombres más descriptiva para los planes de marcado. El campo *Nombre simple* no puede quedar vacío y debe ser exclusivo. Lo ideal es desarrollar un esquema de asignación de nombres para toda la organización y aplicarlo con coherencia en todos los sitios y usuarios.

## Descripción

Se recomienda escribir el nombre común y reconocible de la ubicación geográfica en la que se aplica el plan de marcado correspondiente. Por ejemplo, si el nombre del plan de marcado es Londres.Contoso.com, la descripción recomendada es Londres.

## Región de conferencia de acceso telefónico local

Si se implementan conferencias de acceso telefónico local, debe especificarse una región de conferencias de acceso telefónico local para asociar números de acceso de conferencias de acceso telefónico local con un plan de marcado.

## Prefijo de acceso externo

Puede especificar un prefijo de acceso externo de hasta cuatro caracteres (\#, \* y 0-9) si los usuarios necesitan marcar uno o más dígitos iniciales para tener acceso a una línea externa (por ejemplo, 9).


> [!NOTE]
> Si especifica un prefijo de acceso externo, no necesita crear otra regla de normalización para incluir el prefijo.



## Reglas de normalización

Las reglas de normalización definen cómo deben enrutarse los números de teléfono expresados en diversos formatos para la ubicación con nombre. La misma cadena de número se puede interpretar y convertir de manera distinta en función de la configuración regional desde la que se marque. Las reglas de normalización son necesarias para el enrutamiento y la autorización de las llamadas, ya que los usuarios pueden usar (y usan) diversos formatos al escribir los números de teléfono en sus listas de contactos.

La normalización de los números de teléfono proporcionados por los usuarios aporta un formato uniforme que facilita las tareas siguientes:

  - Asociar un número marcado al URI del SIP del destinatario.

  - Aplicar las reglas de autorización de marcado al usuario que realiza la llamada.

Los siguientes campos numéricos están entre los que deben tener en cuenta las reglas de normalización:

  - Plan de marcado

  - Código de país

  - Código de área

  - Longitud de extensión

  - Prefijo de sitio

## Creación de reglas de normalización

Las reglas de normalización usan expresiones regulares de .NET Framework para especificar patrones numéricos coincidentes para convertir las cadenas de marcado a formato E.164 con el fin de realizar búsquedas inversas de números. Las reglas de normalización se crean en el Panel de control de Lync Server ya sea especificando manualmente las expresiones o proporcionando los dígitos iniciales y la longitud de las cadenas de marcado con los que deben coincidir. Asimismo, se permite que el Panel de control de Lync Server genere para el usuario la correspondiente expresión regular. Sea como fuere, al finalizar puede especificarse un número de prueba para comprobar que la regla de normalización funcione según lo previsto.

Para obtener información detallada sobre el uso de las expresiones regulares de .NET Framework, "Expresiones regulares de .NET Framework" en [http://go.microsoft.com/fwlink/p/?linkId=140927](http://go.microsoft.com/fwlink/p/?linkid=140927).

## Reglas de normalización de ejemplo

En la siguiente tabla se muestran ejemplos de reglas de normalización escritas como expresiones regulares de .NET Framework. Son solo ejemplos, no una referencia normativa para crear reglas de normalización.

### Tabla 1. Reglas de normalización que usan expresiones regulares de .NET Framework

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
<th>Traducción</th>
<th>Ejemplo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Extensión_4_dígitos</p></td>
<td><p>Convierte extensiones de 4 dígitos</p></td>
<td><p>^(\d{4})$</p></td>
<td><p>+1425555$1</p></td>
<td><p>0100 se convierte en +14255550100</p></td>
</tr>
<tr class="even">
<td><p>Extensión_5_dígitos</p></td>
<td><p>Convierte extensiones de 5 dígitos</p></td>
<td><p>^5(\d{4})$</p></td>
<td><p>+1425555$1</p></td>
<td><p>50100 se convierte en +14255550100</p></td>
</tr>
<tr class="odd">
<td><p>7_dígitos_a_Redmond</p></td>
<td><p>Convierte números de 7 dígitos en números locales de Redmond</p></td>
<td><p>^(\d{7})$</p></td>
<td><p>+1425$1</p></td>
<td><p>5550100 se convierte en +14255550100</p></td>
</tr>
<tr class="even">
<td><p>7_dígitos_a_Dallas</p></td>
<td><p>Convierte números de 7 dígitos en números locales de Dallas</p></td>
<td><p>^(\d{7})$</p></td>
<td><p>+1972$1</p></td>
<td><p>5550100 se convierte en +19725550100</p></td>
</tr>
<tr class="odd">
<td><p>10_dígitos_a_EEUU</p></td>
<td><p>Convierte números de 10 dígitos en los Estados Unidos</p></td>
<td><p>^(\d{10})$</p></td>
<td><p>+1$1</p></td>
<td><p>2065550100 se convierte en +12065550100</p></td>
</tr>
<tr class="even">
<td><p>LD_a_EEUU</p></td>
<td><p>Convierte los números con prefijos de larga distancia de Estados Unidos</p></td>
<td><p>^1(\d{10})$</p></td>
<td><p>+$1</p></td>
<td><p>12145550100 se convierte en +2145550100</p></td>
</tr>
<tr class="odd">
<td><p>Intl_a_EEUU</p></td>
<td><p>Convierte los números con prefijos internacionales de Estados Unidos</p></td>
<td><p>^011(\d*)$</p></td>
<td><p>+$1</p></td>
<td><p>01191445550100 se convierte en +91445550100</p></td>
</tr>
<tr class="even">
<td><p>Operador_Redmond</p></td>
<td><p>Convierte 0 al operador de Redmond</p></td>
<td><p>^0$</p></td>
<td><p>+14255550100</p></td>
<td><p>0 se convierte en +14255550100</p></td>
</tr>
<tr class="odd">
<td><p>Prefijo_sitio_Redmond</p></td>
<td><p>Convierte los números con prefijo de red (6) y prefijo de sitio de Redmond (222)</p></td>
<td><p>^6222(\d{4})$</p></td>
<td><p>+1425555$1</p></td>
<td><p>62220100 se convierte en +14255550100</p></td>
</tr>
<tr class="even">
<td><p>Prefijo_sitio_NY</p></td>
<td><p>Convierte los números con prefijo de red (6) y prefijo de sitio de Nueva York (333)</p></td>
<td><p>^6333(\d{4})$</p></td>
<td><p>+1202555$1</p></td>
<td><p>63330100 se convierte en +12025550100</p></td>
</tr>
<tr class="odd">
<td><p>Prefijo_sitio_Dallas</p></td>
<td><p>Convierte los números con prefijo de red (6) y prefijo de sitio de Dallas (444)</p></td>
<td><p>^6444(\d{4})$</p></td>
<td><p>+1972555$1</p></td>
<td><p>64440100 se convierte en +19725550100</p></td>
</tr>
</tbody>
</table>


En la tabla siguiente se muestra un plan de marcado de ejemplo para Redmond, Washington, Estados Unidos, basado en las reglas de normalización que se muestran en la tabla anterior.

### Tabla 2. Plan de marcado de Redmond basado en las reglas de normalización mostradas en la tabla 1

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
<td><p>Extensión_5_dígitos</p></td>
</tr>
<tr class="even">
<td><p>7_dígitos_a_Redmond</p></td>
</tr>
<tr class="odd">
<td><p>10_dígitos_a_EEUU</p></td>
</tr>
<tr class="even">
<td><p>Intl_a_EEUU</p></td>
</tr>
<tr class="odd">
<td><p>Prefijo_sitio_Redmond</p></td>
</tr>
<tr class="even">
<td><p>Prefijo_sitio_NY</p></td>
</tr>
<tr class="odd">
<td><p>Prefijo_sitio_Dallas</p></td>
</tr>
<tr class="even">
<td><p>Operador_Redmond</p></td>
</tr>
</tbody>
</table>



> [!NOTE]
> Aunque los nombres de las reglas de normalización que se muestran en la tabla anterior no incluyen espacios, es opcional usarlos. Por ejemplo, el primer nombre de la tabla se podía haber escrito como "Extensión de 5 dígitos" y sería un nombre válido.


