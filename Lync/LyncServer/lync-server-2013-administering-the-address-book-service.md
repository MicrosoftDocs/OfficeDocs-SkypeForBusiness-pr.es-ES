---
title: 'Lync Server 2013: administración del servicio de libreta de direcciones'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Administering the Address Book Service
ms:assetid: 801e4243-9670-4477-aa2f-88b61ecf5351
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429711(v=OCS.15)
ms:contentKeyID: 48184649
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4ea7a68d77acd7bbaf3de43fce38c0e85c02dad4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037280"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="administering-the-address-book-service-in-lync-server-2013"></a>Administración del servicio de libreta de direcciones en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-02-05_

Como parte de la implementación de Lync Server, Enterprise Edition o Standard Edition Server, el servicio de libreta de direcciones está instalado de forma predeterminada. La base de datos usada por el servicio de libreta de direcciones – RTCab – se crea en SQL Server (para Enterprise Edition, que es el servidor back-end de SQL Server; para el servidor Standard Edition, el servidor SQL Server).

<div>


> [!NOTE]  
> Para obtener información acerca del uso del editor <STRONG>ADSI</STRONG> para editar atributos de objeto de servicios de dominio de Active Directory, consulte <A href="http://go.microsoft.com/fwlink/?linkid=330427">edición de ADSI</A>. Para obtener información sobre una herramienta del kit de recursos específica para el servicio de libreta de direcciones, consulte <A href="http://go.microsoft.com/fwlink/?linkid=330429">las herramientas del kit de recursos de Microsoft Lync Server 2013</A>.



</div>

<div>

## <a name="address-book-server-phone-number-normalization"></a>Normalización del número de teléfono del servidor de libreta de direcciones

Lync Server requiere números de teléfono estándar RFC 3966/E. 164. Para usar números de teléfono que no están estructurados o que tienen un formato incoherente, Lync Server se basa en el servidor de la libreta de direcciones para preprocesar los números de teléfono antes de que se entreguen a las reglas de normalización. Cuando se usa un número de teléfono desde la libreta de direcciones y se aplica la regla de normalización, los clientes, como Lync Phone Edition y Lync Mobile, pueden usar estos números normalizados.

Las reglas de normalización que se usaron en versiones anteriores no funcionen debidamente si no se realizan algunos ajustes. Dado que se quitan los espacios en blanco y los caracteres no obligatorios que preceden a las reglas de normalización, si la expresión regex busca específicamente un guion u otro carácter que se quitó, es posible que la regla de normalización produzca un error. Debe comprobar las reglas de normalización para asegurarse de que no van a buscar estos caracteres que no son obligatorios o de que la regla pueda provocar un error pero continuar en caso de que el carácter no esté presente en el lugar donde la regla prevé que va a estar.

</div>

<div>

## <a name="user-replicator-and-address-book-server"></a>Replicador de usuarios y servidor de libreta de direcciones

El servidor de libreta de direcciones usa datos que aporta el Replicador de usuarios para actualizar la información que obtiene inicialmente de la lista global de direcciones (LDG). El replicador de usuarios escribe los atributos de servicios de dominio de Active Directory para cada usuario, contacto y grupo en la tabla AbUserEntry de la base de datos y el servidor de la libreta de direcciones sincroniza los datos de usuario de la base de datos en archivos del almacén de archivos del servidor de la libreta de direcciones y en la base de datos de la libreta de direcciones RTCab. En el esquema de la tabla AbUserEntry se usan dos columnas, **UserGuid** y **UserData**. **UserGuid** es la columna de índice y contiene el GUID de 16 bytes del objeto de Active Directory. **UserData** es una columna de imagen que contiene todos los atributos de servicios de dominio de Active Directory mencionados anteriormente para ese contacto.

El replicador de usuarios determina qué atributos de Active Directory se deben escribir mediante la lectura de una tabla de configuración ubicada en la misma instancia basada en SQL Server que la tabla AbUserEntry. La tabla ABAttribute contiene tres columnas, **ID**, **Name**, **Flags**y **enable**. La tabla se crea durante la configuración de la base de datos. Si la tabla ABAttribute está vacía, el replicador de usuarios omite su lógica de procesamiento de la tabla AbUserEntry. Los atributos del servidor de libreta de direcciones son dinámicos y se recuperan de la tabla ABAttribute, que inicialmente escribe el servidor de la libreta de direcciones cuando se activa el servidor de la libreta de direcciones.

La activación del servidor de la libreta de direcciones rellena la tabla ABAttribute con los valores que se muestran en la tabla siguiente.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>ID</th>
<th>Nombre</th>
<th>Flags</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1 </p></td>
<td><p>givenName</p></td>
<td><p>0x01400000</p></td>
</tr>
<tr class="even">
<td><p>2 </p></td>
<td><p>Utilidad</p></td>
<td><p>0x02400000</p></td>
</tr>
<tr class="odd">
<td><p>3 </p></td>
<td><p>displayName</p></td>
<td><p>0x03420000</p></td>
</tr>
<tr class="even">
<td><p>4 </p></td>
<td><p>Título</p></td>
<td><p>0x04000000</p></td>
</tr>
<tr class="odd">
<td><p>5 </p></td>
<td><p>mailNickname</p></td>
<td><p>0x05400000</p></td>
</tr>
<tr class="even">
<td><p>6 </p></td>
<td><p>Company</p></td>
<td><p>0x06000000</p></td>
</tr>
<tr class="odd">
<td><p>7 </p></td>
<td><p>physicalDeliveryOfficeName</p></td>
<td><p>0x07000000</p></td>
</tr>
<tr class="even">
<td><p>8 </p></td>
<td><p>msRTCSIP-PrimaryUserAddress</p></td>
<td><p>0x08520C00</p></td>
</tr>
<tr class="odd">
<td><p>9 </p></td>
<td><p>telephoneNumber</p></td>
<td><p>0x09022800</p></td>
</tr>
<tr class="even">
<td><p>10 </p></td>
<td><p>homePhone</p></td>
<td><p>0x0A302800</p></td>
</tr>
<tr class="odd">
<td><p>12</p></td>
<td><p>Mobile</p></td>
<td><p>0x0B622800</p></td>
</tr>
<tr class="even">
<td><p>12</p></td>
<td><p>otherTelephone</p></td>
<td><p>0x0C302000</p></td>
</tr>
<tr class="odd">
<td><p>apartado</p></td>
<td><p>ipPhone</p></td>
<td><p>0x0D302000</p></td>
</tr>
<tr class="even">
<td><p>14 </p></td>
<td><p>Correo</p></td>
<td><p>0x0E500000</p></td>
</tr>
<tr class="odd">
<td><p>15 </p></td>
<td><p>groupType</p></td>
<td><p>0x0F010800</p></td>
</tr>
<tr class="even">
<td><p>16 </p></td>
<td><p>Departamento</p></td>
<td><p>0x10000000</p></td>
</tr>
<tr class="odd">
<td><p>17 </p></td>
<td><p>Descripción</p></td>
<td><p>0x11000100</p></td>
</tr>
<tr class="even">
<td><p>18 </p></td>
<td><p>Manager</p></td>
<td><p>0x12040001</p></td>
</tr>
<tr class="odd">
<td><p>18</p></td>
<td><p>proxyAddress</p></td>
<td><p>0x00500105</p></td>
</tr>
<tr class="even">
<td><p>20</p></td>
<td><p>msExchHideFromAddressLists</p></td>
<td><p>0xFF000003</p></td>
</tr>
<tr class="odd">
<td><p>99</p></td>
<td><p>entryID</p></td>
<td><p>0x99000000</p></td>
</tr>
</tbody>
</table>


Los números de la columna **ID** deben ser únicos y nunca se deben volver a usar. Además, mantener los valores de ID en 256 ahorra espacio en los archivos de salida escritos por el servidor de la libreta de direcciones. Sin embargo, el valor de ID máximo es 65535. La columna **nombre** corresponde al nombre de atributo de Active Directory que el replicador de usuarios debe colocar en la tabla AbUserEntry para cada contacto. El valor de la columna **Flags** se usa para definir el tipo de atributo. El replicador de usuarios reconoce los siguientes tipos de atributos del servidor de la libreta de direcciones, indicados por el byte bajo del valor de la columna **indicadores** .


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Atributo</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>0x0</p></td>
<td><p>Un atributo de cadena. El Replicador de usuarios convierte este tipo a UTF-8 antes de almacenarlo en la tabla AbUserEntry.</p></td>
</tr>
<tr class="even">
<td><p>0x1</p></td>
<td><p>Un atributo binario. El Replicador de usuarios lo almacena en el objeto binario grande sin conversión alguna.</p></td>
</tr>
<tr class="odd">
<td><p>0x2</p></td>
<td><p>Un atributo de cadena, pero se incluye solo si el valor del atributo &quot;empieza por&quot;Tel:. Es principalmente para atributos de cadena con varios valores, específicamente <strong>proxyAddresses</strong>. En este caso, el servidor de libreta de direcciones sólo <strong></strong> está interesado en las entradas &quot;de proxyAddresses&quot;que comienzan por Tel:. Por lo tanto, para ahorrar espacio, el replicador de usuarios solo almacena las entradas que &quot;comienzan por&quot;Tel:.</p></td>
</tr>
<tr class="even">
<td><p>0X3</p></td>
<td><p>Un atributo de cadena booleano, que si es TRUE hace que el Replicador de usuarios no incluya este contacto en la tabla AbUserEntry. Si es FALSE, hace que el Replicador de usuarios incluya los atributos de este contacto en la tabla AbUserEntry, pero no el atributo particular con este indicador. Este es otro tipo de caso especial que es básicamente para el atributo <strong>msExchHideFromAddressLists</strong>.</p></td>
</tr>
<tr class="odd">
<td><p>0x4</p></td>
<td><p>Un atributo de cadena, pero se incluye solo si el valor del atributo &quot;empieza por&quot; SMTP: e &quot; @ &quot; incluye el símbolo.</p></td>
</tr>
<tr class="even">
<td><p>0X5</p></td>
<td><p>Un atributo de cadena, pero se incluye solo si el valor del atributo comienza &quot;por Tel&quot; : &quot;o SMTP&quot; : e incluye &quot; @ &quot; el símbolo.</p></td>
</tr>
<tr class="odd">
<td><p>0x100</p></td>
<td><p>Si se ha establecido, es un atributo de varios valores que pueden aparecer más de una vez para cada contacto.</p></td>
</tr>
<tr class="even">
<td><p>0x400</p></td>
<td><p>Si se ha establecido, identifica el atributo del nombre de la cuenta de usuario de correo electrónico para un contacto. El servidor de libreta de direcciones usa este indicador para identificar el valor de atributo que se va a mostrar en la entrada de registro de eventos de normalización del teléfono.</p></td>
</tr>
<tr class="odd">
<td><p>0x800</p></td>
<td><p>Si se ha establecido, identifica un atributo necesario para un contacto. El servidor de libreta de direcciones incluye un usuario en la tabla AbUserEntry únicamente si existe un valor para este atributo en Active Directory. Si hay más de un atributo obligatorio, solamente se requerirá uno de ellos para tener un valor que incluya al usuario en la tabla AbUserEntry.</p></td>
</tr>
<tr class="even">
<td><p>0x1000</p></td>
<td><p>Si se ha establecido, el servidor de libreta de direcciones siempre normaliza el valor de este atributo.</p></td>
</tr>
<tr class="odd">
<td><p>0x2000</p></td>
<td><p>Si se ha establecido, el servidor de libreta de direcciones usa el número normalizado en <strong>proxyAddresses</strong>, en caso de que la configuración del CMS de <strong>UseNormalizationRules</strong> tenga el valor FALSE; de lo contrario, se comporta de la misma forma que cuando el bit del indicador es 0x1000.</p></td>
</tr>
<tr class="even">
<td><p>0x4000</p></td>
<td><p>Si se ha establecido, el servidor de libreta de direcciones no incluye objetos en la tabla AbUserEntry que tengan este valor para el atributo especificado. Por ejemplo, si el atributo <strong>msRTCSIP-PrimaryUserAddress</strong> tiene establecido este bit del indicador, los contactos con este atributo no se escribirán en la base de datos.</p></td>
</tr>
<tr class="odd">
<td><p>0x8000</p></td>
<td><p>Si se ha establecido, el servidor de libreta de direcciones no incluye objetos en la tabla AbUserEntry que no tengan este valor para el atributo especificado. Si los bits del indicador 0x4000 y 0x8000 no se han establecido en un objeto, el atributo con el valor de bit del indicador establecido en 0x4000 tendrá prioridad y el objeto se excluye de la tabla AbUserEntry.</p></td>
</tr>
<tr class="even">
<td><p>0x10000</p></td>
<td><p>Si se ha establecido, representa un objeto de grupo. El Replicador de usuarios se sirve de este bit de indicador para incluir contactos con el atributo <strong>groupType</strong>, cuya presencia indica que se trata de un grupo (por ejemplo, una lista de distribución o un grupo de seguridad).</p></td>
</tr>
<tr class="odd">
<td><p>0x20000</p></td>
<td><p>Si se ha establecido, el Replicador de usuarios se sirve de este bit de indicador para incluir este atributo en archivos de servidor de libreta de direcciones específicas de un dispositivo (es decir, archivos con una extensión .dabs).</p></td>
</tr>
</tbody>
</table>


En versiones anteriores de Lync Server, al aplicar un cambio en Active Directory, se necesitaría que el administrador ejecutara los cmdlets **Update-CSUserDatabase** y **Update – CSAddressBook** de Windows PowerShell para conservar el cambio en la base de datos de usuario de Lync Server y la base de datos de RTCab inmediatamente. En Lync Server 2013, el replicador de usuarios de Lync Server tomará los cambios de Active Directory y actualizará la base de datos de usuarios de Lync Server en función de un intervalo configurado. El replicador de usuarios de Lync Server también propagará los cambios rápidamente a la base de datos de RTCab sin que el Administrador tenga que ejecutar Update-CSAddressBook. Si la consulta Web de la libreta de direcciones está habilitada, los clientes de Lync reflejarán los cambios en los resultados de la búsqueda. Los administradores solo tendrán que ejecutar Update-CSAddressBook si está habilitada la descarga del archivo de la libreta de direcciones.

<div>


> [!NOTE]  
> De forma predeterminada, el replicador de usuarios de Lync Server se ejecuta automáticamente cada 5 minutos. Puede configurar este intervalo mediante Set-CSUserReplicatorConfiguration-ReplicationCycleInterval &lt; &gt;.



</div>

</div>

<div>

## <a name="filtering-the-address-book"></a>Filtrado de la libreta de direcciones

Los usuarios rellenados en los archivos del servidor de la libreta de direcciones pueden controlarse en función de determinados atributos de servicios de dominio de Active Directory enumerados en la tabla ABAttribute. Uno de estos atributos que se usa para el filtrado es el atributo **msExchangeHideFromAddressBook**. Se trata de un atributo de usuario que agrega el esquema de Exchange. Si el valor de este atributo es TRUE, Exchange Server lo usa para ocultar el contacto de la lista global de direcciones (LGD) de Outlook. De forma similar, si el valor de este atributo es TRUE, User Replicator no incluye a ese usuario en la tabla AbUserEntry y no estará en los archivos del servidor de libreta de direcciones.

Puede usar ciertos bits de indicador para definir un filtro que se vaya a usar en los atributos del servidor de libreta de direcciones. Por ejemplo, la presencia de ciertos bits de indicador pueden identificar un atributo como un atributo de inclusión o un atributo de exclusión. El Replicador de usuarios deja fuera a los contactos que contienen un atributo de exclusión y a los contactos que no contienen un atributo de inclusión.

<div>


> [!WARNING]  
> Para obtener más información acerca de cómo filtrar la libreta de direcciones, consulte <A href="https://technet.microsoft.com/library/gg415643(v=ocs.15)">cmdlets del servidor de libreta de direcciones en Lync Server 2013</A>y <A href="http://go.microsoft.com/fwlink/?linkid=330430">filtrar la libreta de direcciones de Lync 2013</A>



</div>

En estos momentos, existen tres tipos diferentes de filtros. En la tabla siguiente se enumeran estos filtros.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Atributo</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>0x800</p></td>
<td><p>Si se ha establecido, identifica un atributo necesario para un contacto. El Replicador de usuarios usa este bit de indicador para dejar fuera los contactos que no contienen al menos uno de los atributos obligatorios. OuPathId es un atributo obligatorio, que está siempre establecido. De forma que se debe establecer al menos uno de los otros atributos obligatorios. De lo contrario, el contacto (es decir, con el valor del atributo OuPathId obligatorio) no se escribirá en la base de datos. Por ejemplo, si <strong>telephoneNumber</strong> y <strong>homePhone</strong> se definen como atributos obligatorios, únicamente los contactos que tengan al menos uno de estos atributos se escribirán en la base de datos.</p></td>
</tr>
<tr class="even">
<td><p>0x4000</p></td>
<td><p>Si se ha establecido, identifica a un atributo de exclusión. El Replicador de usuarios se sirve de este bit de indicador para filtrar contactos que contienen este atributo. Por ejemplo, si se definió <strong>msRTCSIP-PrimaryUserAddress</strong> como un atributo de exclusión, los contactos que tengan este atributo no se escribirán en la base de datos.</p></td>
</tr>
<tr class="odd">
<td><p>0x8000</p></td>
<td><p>Si se ha establecido, identifica a un atributo de inclusión. El Replicador de usuarios se sirve de este bit de indicador para filtrar contactos que no contienen este atributo. Por ejemplo, si se definió <strong>msRTCSIP-PrimaryUserAddress</strong> como un atributo de inclusión, únicamente se escribirán en la base de datos los contactos que tengan este atributo.</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Si se establecieron los bits de indicador 0x4000 (atributo de exclusión) y 0x8000 (atributo de inclusión), el bit 0x4000 sobrescribe el bit 0x8000 y el contacto se excluirá.



</div>

Pese a que puede filtrar la libreta de direcciones para que incluya exclusivamente a ciertos usuarios, cuando se restringen entradas no se limita la capacidad de otros usuarios para ponerse en contacto con los usuarios filtrados o para ver su estado de presencia. los usuarios siempre pueden buscar usuarios y enviar manualmente mensajes instantáneos o iniciar llamadas manualmente a usuarios que no estén en la libreta de direcciones si especifican el nombre de inicio de sesión completo del usuario. Asimismo, la información de contacto para un usuario se puede encontrar en Outlook.

Aunque tener registros de contactos completos en los archivos de la libreta de direcciones permite usar Lync Server para iniciar el correo electrónico, el teléfono o las llamadas de telefonía IP empresarial (es decir, si la telefonía IP empresarial está habilitada en el servidor) con los usuarios que no están configurados para el inicio de sesión Protocol (SIP), algunas organizaciones prefieren incluir sólo usuarios con SIP habilitado en sus entradas del servidor de la libreta de direcciones. Puede filtrar la libreta de direcciones para que incluya solamente a usuarios habilitados para SIP si borra el bit 0x800 en la columna **Indicadores** de los siguientes atributos obligatorios: **mailNickname**, **telephoneNumber**, **homePhone** y **mobile**. También puede filtrar la libreta de direcciones para que incluya solamente a usuarios habilitados para SIP; para ello establezca un bit 0x8000 (atributo de inclusión) en la columna **Indicadores** del atributo **msRTCSIP-PrimaryUserAddress**. Esto sirve también de ayuda para excluir cuentas del servicio de los archivos de la libreta de direcciones.

Una vez haya modificado la tabla AbAttribute, puede actualizar los datos en la tabla AbUserEntry mediante la ejecución del comando**Update-CsUserDatabase** del cmdlet. Cuando se haya completado la replicación, puede actualizar el archivo en el almacén de archivos del servidor de la libreta de direcciones ejecutando manualmente el comando **UpdateCsAddressBook** del cmdlet.

<div>


> [!NOTE]  
> El servidor front-end en el que se coloca el servidor de la libreta de direcciones no se puede configurar de forma administrativa. Uno se elige durante la implementación (normalmente, el primer servidor front-end que se implementó). En caso de error, el servicio de libreta de direcciones se desplazará a otro servidor front-end y no necesitará atención administrativa.



</div>

<div>


> [!IMPORTANT]  
> Si ha consolidado o modificado de otra manera su infraestructura desde una implementación de varios bosques o una implementación principal/secundaria (como la consolidación de la infraestructura antes de pasar a Lync Server), es posible que la descarga del servicio de libreta de direcciones y la consulta Web de la libreta de direcciones no funcionen para algunos usuarios. Cuando se encuentra en una implementación con varios dominios o bosques, el atributo <STRONG>MsRTCSIP-OriginatorSid</STRONG> se rellena en los objetos de usuario que presentan el problema. El atributo <STRONG>MsRTCSIP-OriginatorSid</STRONG> debe establecerse en null en estos objetos para resolver el problema.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

