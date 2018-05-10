---
título: "Bloque de entrada llamadas en Skype para profesionales en línea" ms.author: tonysmit autor: tonysmit manager: serdars ms.date: 07/05/2018 ms.topic: artículo ms.assetid: ms.tgt.pltfrm: ms.service de nube: ms.collection Skype-de-negocio-en línea: Adm_Skype4B_ Ms.audience Online: administración appliesto: Skype para localization_priority empresarial: f1keywords Normal: ninguno ms.custom: descripción de PowerShell: "Use PowerShell para administrar la entrada llamada de bloqueo de Skype de negocio Online."
---

 # <a name="block-inbound-calls"></a>Bloquear las llamadas entrantes

Skype para Online al llamar a planes de negocios ahora admite el bloqueo de las llamadas entrantes de la red telefónica conmutada (RTC). Esta característica permite una lista global de inquilino de modelos de número debería definirse de forma que el identificador de autor de la llamada de cada RTC entrante llamar al inquilino de se puede comprobar con la lista para una coincidencia. Si se realiza una coincidencia, se rechaza una llamada entrante. 

Esta característica de bloqueo de llamada entrante sólo funciona en las llamadas entrantes que se originan desde la RTC y sólo funciona de forma global inquilino y no está disponible en una base por usuario.

Esta característica aún no está disponible para el enrutamiento directo.

>[Nota] Los autores de llamadas bloqueados pueden experimentar comportamientos ligeramente diferentes cuando se han bloqueado. El comportamiento se basará en cómo portadora del llamador bloqueados controla la notificación de que la llamada no está permitida para completarse correctamente. Algunos ejemplos pueden ser un mensaje de operador que indica la llamada no se puede completar como se marcó, o simplemente eliminarla de la llamada.

## <a name="call-blocking-admin-controls-and-information"></a>Bloqueo de información y los controles de administración de llamadas
Controles de administración para los números de bloqueo se proporcionan con PowerShell sólo. Modelos de bloque número se definen como patrones de expresión regular. El orden de las expresiones es irrelevante – el primer patrón de coincidencia en la lista, se producirá la llamada que se han bloqueado. Un nuevo número o patrón agregado o eliminado en bloqueados lista de autores de llamadas puede tardar hasta 24 horas a para el patrón para activarse.

## <a name="call-blocking-powershell-commands"></a>Bloqueo de comandos de PowerShell de llamadas

*InboundBlockedNumberPattern* Modelos de número se administran a través de los comandos *CsInboundBlockedNumberPattern* **New**, **obtener**, **establecer**y **Quitar**.  

Puede administrar un patrón determinado mediante el uso de estos cmdlets, incluida la capacidad para alternar la activación de un patrón determinado.
- *Get-CsInboundBlockedNumberPattern* Devuelve una lista de todos los modelos de número bloqueados que se agrega a la lista de inquilino incluidos nombre, descripción, Enabled (verdadero/falso) y trama para cada uno.
- *Nueva CsInboundBlockedNumberPattern* Agrega un patrón de número bloqueado a la lista de inquilinos.
- *Remove-CsInboundBlockedNumberPattern* Quita un patrón de número bloqueado de la lista de inquilinos.
- *Set-CsInboundBlockedNumberPattern* Modifica uno o varios parámetros de un patrón de número bloqueado en la lista del inquilino.
- *TenantBlockedCallingNumbers* La visualización y la activación de la característica de bloqueo de toda llamada se administra a través de la CsTenantBlockingCallingNumbers los comandos obtener y establecer. 
- *Get-CsTenantBlockedCallingNumbers* Devuelve los parámetros de la lista global de número bloqueado incluidos habilitado (True/False). No hay una directiva de inquilino global único que no se pueden modificar manualmente distinta para activar la característica completamente activado/desactivado.
- *Set-CsTenantBlockedCallingNumbers* Permite modificar las llamadas del inquilino global bloqueado para activarse o desactivarse en el nivel de inquilino.

### <a name="examples"></a>Ejemplos
#### <a name="blocking-a-number"></a>Bloqueo de un número

En este ejemplo, el - habilitado y - descripción parámetros son opcionales:

`New-CsInboundBlockedNumberPattern -Name “<name>” -Enabled $True -Description “<description>” -Pattern “^[+]?13125550000”`

 Creación de que un nuevo patrón de forma predeterminada agregará siempre es el patrón como habilitada y la descripción y el campo opcional que proporcionan más información. 

Se recomienda que proporcione un nombre descriptivo fácilmente comprender por qué se ha agregado el patrón. En el caso de spam simplemente bloqueo números, que se considera como nombre de la regla de la misma como el patrón de número que se ha de coincidir y agregar información adicional en la descripción según sea necesario.

Se comparan los patrones de uso de expresiones regulares (regex). Permitir tiempo de replicación antes de probar y validar.

#### <a name="allowing-a-number"></a>Permitir un número

En este ejemplo, se requiere el parámetro identity:`Remove-CsInboundBlockedNumberPattern -Identity “<identity>”`
 
Si no se conoce la identidad, use el cmdlet *Get-CsInb undBlockedNumberPattern* para localizar en primer lugar el patrón adecuado y tenga en cuenta la identidad. A continuación, ejecute el cmdlet *Quitar* y pasar el valor de identidad adecuado.

Permitir tiempo de replicación antes de probar y validar.
#### <a name="view-all-number-patterns"></a>Ver todos los patrones de número
Si ejecuta este cmdlet devolverá un números de lista de todos los que ha escrito bloqueado para un inquilino:`Get-CsInboundBlockedNumberPattern`

Uso de PowerShell integrado capacidades de filtrado para analizar los valores devueltos según sea necesario.

#### <a name="a-note-on-regex"></a>Una nota en Regex
Como se indicó anteriormente, la coincidencia de modelos para bloquear los autores de llamadas se realiza mediante el uso de expresiones regulares (regex). En Internet hay varias herramientas disponibles para ayudar a validar una coincidencia de patrón regex. Si no está familiarizado con patrones de regex, se recomienda que se tome algún tiempo a familiarizarse con los conceptos básicos y para obtener los resultados esperados, asegúrese de que use una herramienta para validar las coincidencias de patrón antes de agregar a nuevas coincidencias números bloqueadas a su inquilino. 

## <a name="related-topics"></a>See also
[Configurar el equipo para Skype para la administración en línea de negocio con Windows PowerShell](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell )
