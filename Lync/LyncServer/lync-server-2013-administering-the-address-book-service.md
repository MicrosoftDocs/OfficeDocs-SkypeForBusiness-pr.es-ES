---
title: Administrar el servicio de libreta de direcciones en Lync Server 2013
TOCTitle: Administrar el servicio de libreta de direcciones en Lync Server 2013
ms:assetid: 801e4243-9670-4477-aa2f-88b61ecf5351
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg429711(v=OCS.15)
ms:contentKeyID: 48275826
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Administrar el servicio de libreta de direcciones en Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

La instalación predeterminada del servicio de libreta de direcciones forma parte de la implementación de Lync ServerEnterprise Edition o Servidor Standard Edition. La base de datos que usa el servicio de libreta de direcciones (RTCab) se crea en SQL Server (para Enterprise Edition, es SQL Server back-end y para Servidor Standard Edition, SQL Server combinado).


> [!NOTE]
> Para obtener más información sobre el uso de <STRONG>ADSI Edit</STRONG> para editar atributos de objeto de Servicios de dominio de Active Directory, consulte <A href="http://go.microsoft.com/fwlink/?linkid=330427">ADSI Edit</A>. Para más información sobre una herramienta del kit de recursos específica para el servicio de libreta de direcciones, consulte <A href="http://go.microsoft.com/fwlink/?linkid=330429">Herramientas del kit de recursos de Microsoft Lync Server 2013</A>.



## Normalización del número de teléfono del servidor de libreta de direcciones

Lync Server requiere números de teléfono RFC 3966/E.164 estandarizados. Para usar números de teléfono sin estructura o con un formato incoherente, Lync Serverse basa en el servidor de libreta de direcciones y preprocesa los números de teléfono antes de que se envíen a las reglas de normalización. Cuando se usa un número de teléfono de la libreta de direcciones y se aplica la regla de normalización, los clientes, como por ejemplo, Lync Phone Edition y Lync Mobile, pueden usar estos números normalizados.

Las reglas de normalización que se usaron en versiones anteriores no funcionen debidamente si no se realizan algunos ajustes. Dado que se quitan los espacios en blanco y los caracteres no obligatorios que preceden a las reglas de normalización, si la expresión regex busca específicamente un guion u otro carácter que se quitó, es posible que la regla de normalización produzca un error. Debe comprobar las reglas de normalización para asegurarse de que no van a buscar estos caracteres que no son obligatorios o de que la regla pueda provocar un error pero continuar en caso de que el carácter no esté presente en el lugar donde la regla prevé que va a estar.

## Replicador de usuarios y servidor de libreta de direcciones

El servidor de libreta de direcciones usa datos que aporta el Replicador de usuarios para actualizar la información que obtiene inicialmente de la lista global de direcciones (LDG). El Replicador de usuarios escribe los atributos de Servicios de dominio de Active Directory para cada usuario, contacto y grupo en la tabla AbUserEntry de la base de datos y el servidor de libreta de direcciones sincroniza los datos de usuario de la base de datos en archivos en el almacén de archivos del servidor de libreta de direcciones y en la base de datos RTCab de la libreta de direcciones. En el esquema de la tabla AbUserEntry se usan dos columnas, **UserGuid** y **UserData**. **UserGuid** es la columna de índice y contiene el GUID de 16 bits del objeto de Active Directory. **UserData** es una columna de imagen que contiene todos los atributos de Servicios de dominio de Active Directory previamente mencionados para ese contacto.

User Replicator determina los atributos de Active Directory que se van a escribir; para ello, lee una tabla de configuración ubicada en la misma instancia basada en SQL Server que la tabla AbUserEntry. La tabla AbAttribute contiene tres columnas, **Id.**, **Nombre**, **Indicadores** y **Habilitar**. La tabla se crea durante la configuración de la base de datos. Si la tabla AbAttribute está vacía, User Replicator omite su lógica de procesamiento de la tabla AbUserEntry. los atributos del servidor de libreta de direcciones son dinámicos y se recuperan en la tabla AbAttribute, la cual escribe inicialmente el servidor de libreta de direcciones cuando se activa el servidor de libreta de direcciones.

Con la activación del servidor de libreta de direcciones se rellena la tabla AbAttribute con los valores mostrados en la tabla siguiente.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Id.</th>
<th>Nombre</th>
<th>Indicadores</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1</p></td>
<td><p>givenName</p></td>
<td><p>0x01400000</p></td>
</tr>
<tr class="even">
<td><p>2</p></td>
<td><p>Sn</p></td>
<td><p>0x02400000</p></td>
</tr>
<tr class="odd">
<td><p>3</p></td>
<td><p>displayName</p></td>
<td><p>0x03420000</p></td>
</tr>
<tr class="even">
<td><p>4</p></td>
<td><p>Título</p></td>
<td><p>0x04000000</p></td>
</tr>
<tr class="odd">
<td><p>5</p></td>
<td><p>mailNickname</p></td>
<td><p>0x05400000</p></td>
</tr>
<tr class="even">
<td><p>6</p></td>
<td><p>Compañía</p></td>
<td><p>0x06000000</p></td>
</tr>
<tr class="odd">
<td><p>7</p></td>
<td><p>physicalDeliveryOfficeName</p></td>
<td><p>0x07000000</p></td>
</tr>
<tr class="even">
<td><p>8</p></td>
<td><p>msRTCSIP-PrimaryUserAddress</p></td>
<td><p>0x08520C00</p></td>
</tr>
<tr class="odd">
<td><p>9</p></td>
<td><p>telephoneNumber</p></td>
<td><p>0x09022800</p></td>
</tr>
<tr class="even">
<td><p>10</p></td>
<td><p>homePhone</p></td>
<td><p>0x0A302800</p></td>
</tr>
<tr class="odd">
<td><p>11</p></td>
<td><p>Móvil</p></td>
<td><p>0x0B622800</p></td>
</tr>
<tr class="even">
<td><p>12</p></td>
<td><p>otherTelephone</p></td>
<td><p>0x0C302000</p></td>
</tr>
<tr class="odd">
<td><p>13</p></td>
<td><p>ipPhone</p></td>
<td><p>0x0D302000</p></td>
</tr>
<tr class="even">
<td><p>14</p></td>
<td><p>Correo</p></td>
<td><p>0x0E500000</p></td>
</tr>
<tr class="odd">
<td><p>15</p></td>
<td><p>groupType</p></td>
<td><p>0x0F010800</p></td>
</tr>
<tr class="even">
<td><p>16</p></td>
<td><p>Departamento</p></td>
<td><p>0x10000000</p></td>
</tr>
<tr class="odd">
<td><p>17</p></td>
<td><p>Descripción</p></td>
<td><p>0x11000100</p></td>
</tr>
<tr class="even">
<td><p>18</p></td>
<td><p>Administrador</p></td>
<td><p>0x12040001</p></td>
</tr>
<tr class="odd">
<td><p>19</p></td>
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


los números en la columna **Id.** deben ser únicos y no se pueden volver a usar. Asimismo, si los valores de Id. se mantienen por debajo de 256, se ahorra espacio en los archivos de resultados que escribe el servidor de libreta de direcciones. Sin embargo, el valor de Id. máximo es 65535. La columna **Nombre** corresponde al nombre de atributo de Active Directory que debe poner User Replicator en la tabla AbUserEntry para cada contacto. El valor en la columna **Indicadores** se usa para definir el tipo de atributo. User Replicator reconoce los siguientes tipos de atributo de servidor de libreta de direcciones, lo cual se indica mediante el byte inferior del valor en la columna **Indicadores**.


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
<td><p>Un atributo de cadena, pero se incluye solo si el valor del atributo comienza con &quot;tel:&quot;. Es principalmente para atributos de cadena con varios valores, específicamente <strong>proxyAddresses</strong>. En este caso, el servidor de libreta de direcciones solo se interesará por entradas <strong>proxyAddresses</strong> que comiencen con &quot;tel:&quot;. Por tanto, para ahorrar espacio, el Replicador de usuarios almacena solamente las entradas que comienzan con &quot;tel:&quot;.</p></td>
</tr>
<tr class="even">
<td><p>0x3</p></td>
<td><p>Un atributo de cadena booleano, que si es TRUE hace que el Replicador de usuarios no incluya este contacto en la tabla AbUserEntry. Si es FALSE, hace que el Replicador de usuarios incluya los atributos de este contacto en la tabla AbUserEntry, pero no el atributo particular con este indicador. Este es otro tipo de caso especial que es básicamente para el atributo <strong>msExchHideFromAddressLists</strong>.</p></td>
</tr>
<tr class="odd">
<td><p>0x4</p></td>
<td><p>Un atributo de cadena, pero se incluye solo si el valor del atributo comienza con &quot;smtp:&quot; e incluye el símbolo &quot;@&quot;.</p></td>
</tr>
<tr class="even">
<td><p>0x5</p></td>
<td><p>Un atributo de cadena, pero se incluye solo si el valor del atributo comienza con &quot;tel:&quot; o &quot;smtp:&quot; e incluye el símbolo &quot;@&quot;.</p></td>
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


En versiones anteriores de Lync Server, cuando se aplica un cambio al Active Directory, el administrador debía ejecutar los cmdlets **Update -CSUserDatabase** y **Update –CSAddressBook**Windows PowerShell para resistir el cambio a la base de usuario Lync Server y la base de datos RTCab inmediatamente. En Lync Server 2013, User Replicator Lync Server recibirá los cambios de Active Directory y actualizará la base de datos de usuarios de Lync Server según un intervalo configurado. User Replicator Lync Server también propagará rápidamente los cambios a la base de datos RTCab sin que el administrador tenga que ejecutar el Update-CSAddressBook. Si se habilita la consulta a la web de Libreta de direcciones, los cambios se reflejarán en los resultados de búsqueda de los clientes Lync. los administradores solo deberán ejecutar Update -CSAddressBook si está habilitada la descarga del archivo de la Libreta de direcciones.


> [!NOTE]
> De forma predeterminada, User Replicator Lync Server se ejecuta automáticamente cada 5 minutos. Puede configurar este intervalo usando Set -CSUserReplicatorConfiguration -ReplicationCycleInterval &lt;&gt;.



## Filtrado de la libreta de direcciones

los usuarios que se han incluido en los archivos del servidor de libreta de direcciones se pueden controlar según ciertos atributos de Servicios de dominio de Active Directory que aparecen en la tabla AbAttribute. Uno de estos atributos que se usa para el filtrado es el atributo **msExchangeHideFromAddressBook**. Se trata de un atributo de usuario que agrega el esquema de Exchange. Si el valor de este atributo es TRUE, Exchange Server lo usa para ocultar el contacto de la lista global de direcciones (LGD) de Outlook. De forma similar, si el valor de este atributo es TRUE, User Replicator no incluye a ese usuario en la tabla AbUserEntry y no estará en los archivos del servidor de libreta de direcciones.

Puede usar ciertos bits de indicador para definir un filtro que se vaya a usar en los atributos del servidor de libreta de direcciones. Por ejemplo, la presencia de ciertos bits de indicador pueden identificar un atributo como un atributo de inclusión o un atributo de exclusión. El Replicador de usuarios deja fuera a los contactos que contienen un atributo de exclusión y a los contactos que no contienen un atributo de inclusión.

> [!WARNING]  
> Para obtener más información sobre cómo filtrar la libreta de direcciones, consulte <a href="https://technet.microsoft.com/en-us/library/gg415643(v=ocs.15)">Cmdlets de servidor de libreta de direcciones</a> y <a href="http://go.microsoft.com/fwlink/?linkid=330430">Filtrar la libreta de direcciones de Lync 2013</a>


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



> [!NOTE]
> Si se establecieron los bits de indicador 0x4000 (atributo de exclusión) y 0x8000 (atributo de inclusión), el bit 0x4000 sobrescribe el bit 0x8000 y el contacto se excluirá.



Pese a que puede filtrar la libreta de direcciones para que incluya exclusivamente a ciertos usuarios, cuando se restringen entradas no se limita la capacidad de otros usuarios para ponerse en contacto con los usuarios filtrados o para ver su estado de presencia. los usuarios siempre pueden buscar usuarios y enviar manualmente mensajes instantáneos o iniciar llamadas manualmente a usuarios que no estén en la libreta de direcciones si especifican el nombre de inicio de sesión completo del usuario. Asimismo, la información de contacto para un usuario se puede encontrar en Outlook.

Aunque al disponer de registros de contactos íntegros en los archivos de la libreta de direcciones se puede usar Lync Server para iniciar correos electrónicos, llamadas telefónicas o de Enterprise Voice (es decir, si Enterprise Voice se ha habilitado en el servidor) con los usuarios que no se han configurado para el Protocolo de inicio de sesión (SIP), algunas organizaciones prefieren incluir únicamente a usuarios habilitados para SIP en sus entradas del servidor de libreta de direcciones. Puede filtrar la libreta de direcciones para que incluya solamente a usuarios habilitados para SIP si borra el bit 0x800 en la columna **Indicadores** de los siguientes atributos obligatorios: **mailNickname** , **telephoneNumber** , **homePhone** y **mobile** . También puede filtrar la libreta de direcciones para que incluya solamente a usuarios habilitados para SIP; para ello establezca un bit 0x8000 (atributo de inclusión) en la columna **Indicadores** del atributo **msRTCSIP-PrimaryUserAddress** . Esto sirve también de ayuda para excluir cuentas del servicio de los archivos de la libreta de direcciones.

Una vez haya modificado la tabla AbAttribute, puede actualizar los datos en la tabla AbUserEntry mediante la ejecución del comando**Update-CsUserDatabase** del cmdlet. Cuando se haya completado la replicación, puede actualizar el archivo en el almacén de archivos del servidor de la libreta de direcciones ejecutando manualmente el comando **UpdateCsAddressBook** del cmdlet.


> [!NOTE]
> El Servidor front-end donde está el servidor de libreta de direcciones no se puede configurar de forma administrativa. Se elige uno durante la implementación, por lo general el primer Servidor front-end que se implementa. En caso de error, el servicio de libreta de direcciones se transferirá a otro Servidor front-end y no requiere atención administrativa.



> [!IMPORTANT]  
> Si ha consolidado o modificado de alguna otra forma la infraestructura a partir de una implementación de varios bosques o de una implementación de miembro principal/secundario (como la consolidación de su infraestructura antes de transferirse a Lync Server), es posible que experimente errores para algunos usuarios con la descarga del servicio de libreta de direcciones y del servicio de consulta web de la libreta de direcciones. Cuando en una implementación que tenía varios dominios o bosques, se incluye el atributo <strong>MsRTCSIP-OriginatorSid</strong> se rellena en los objetos de usuario que muestran el problema, el atributo <strong>MsRTCSIP-OriginatorSid</strong> debe establecerse en NULL en estos objetos para resolver el problema.


