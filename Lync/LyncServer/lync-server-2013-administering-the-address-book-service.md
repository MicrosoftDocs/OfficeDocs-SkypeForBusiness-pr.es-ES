---
title: 'Lync Server 2013: administración del servicio de libreta de direcciones'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Administering the Address Book Service
ms:assetid: 801e4243-9670-4477-aa2f-88b61ecf5351
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429711(v=OCS.15)
ms:contentKeyID: 48184649
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8acf59a898f8da14b9c5c4151728206cc501ceaf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842996"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="administering-the-address-book-service-in-lync-server-2013"></a>Administrar el servicio de libreta de direcciones en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-02-05_

Como parte de la implementación de Lync Server, Enterprise Edition o Standard Edition Server, el servicio de libreta de direcciones se instala de forma predeterminada. La base de datos que usa el servicio de libreta de direcciones, RTCab, se crea en el servidor SQL (para Enterprise Edition, que es el servidor SQL Server de servicios de fondo; en el servidor Standard Edition, el servidor SQL Server en el que se proviene).

<div>


> [!NOTE]  
> Para obtener información sobre el uso de <STRONG>ADSI Edit</STRONG> para editar atributos de objetos de Active Directory Domain Services, consulte <A href="http://go.microsoft.com/fwlink/?linkid=330427">ADSI Edit</A>. Para obtener información sobre una herramienta del kit de recursos específicamente para el servicio de libreta de direcciones, consulte <A href="http://go.microsoft.com/fwlink/?linkid=330429">herramientas del kit de recursos de Microsoft Lync Server 2013</A>.



</div>

<div>

## <a name="address-book-server-phone-number-normalization"></a>Normalización del número de teléfono del servidor de libreta de direcciones

Lync Server requiere el estándar RFC 3966/E. 164 números de teléfono. Para usar números de teléfono que no se hayan estructurado o que tengan un formato incoherente, Lync Server depende del servidor de la libreta de direcciones para preprocesar los números de teléfono antes de que se entreguen a las reglas de normalización. Cuando se usa un número de teléfono de la libreta de direcciones y se aplica la regla de normalización, los clientes, como Lync Phone Edition y Lync Mobile, pueden usar estos números normalizados.

Es posible que las reglas de normalización que se usaron en versiones anteriores no funcionen correctamente sin algunos ajustes. Dado que los espacios en blanco y los caracteres no obligatorios se quitan antes de las reglas de normalización, si la expresión de Regex está buscando específicamente un guión u otro carácter que se ha quitado, es posible que la regla de normalización no se realice correctamente. Debe revisar las reglas de normalización para asegurarse de que no busquen estos caracteres no obligatorios o de que la regla puede dar error y continuar en el caso de que el carácter no se presente donde la regla se anticipe.

</div>

<div>

## <a name="user-replicator-and-address-book-server"></a>Duplicador de usuarios y servidor de la libreta de direcciones

El servidor de la libreta de direcciones utiliza los datos proporcionados por el replicador de usuarios para actualizar la información que obtiene inicialmente de la lista global de direcciones (GAL). El replicador de usuarios escribe los atributos de los servicios de dominio de Active Directory para cada usuario, contacto y grupo en la tabla AbUserEntry de la base de datos y el servidor de la libreta de direcciones sincroniza los datos de usuario de la base de datos en los archivos del almacén de archivos del servidor de la libreta de direcciones y en el RTCab de base de datos de la libreta de direcciones. El esquema de la tabla AbUserEntry usa dos columnas: **UserGuid** y **UserData**. **UserGuid** es la columna de índice y contiene el GUID de 16 bytes del objeto de Active Directory. **UserData** es una columna de imagen que contiene todos los atributos de servicios de dominio de Active Directory mencionados anteriormente para ese contacto.

El replicador de usuarios determina qué atributos de Active Directory se escribirán leyendo una tabla de configuración que se encuentra en la misma instancia basada en SQL Server que la tabla AbUserEntry. La tabla ABAttribute contiene tres columnas: **ID**, **Name**, **Flags**y enable. **** La tabla se crea durante la configuración de la base de datos. Si la tabla ABAttribute está vacía, User Replicator omite su lógica de procesamiento de la tabla AbUserEntry. Los atributos del servidor de la libreta de direcciones son dinámicos y se recuperan de la tabla ABAttribute, que inicialmente escribe el servidor de la libreta de direcciones cuando se activa el servidor de la libreta de direcciones.

La activación del servidor de la libreta de direcciones rellena la tabla abattributes con los valores que se muestran en la tabla siguiente.


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
<th>Marcas</th>
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
<td><p>Utilidad</p></td>
<td><p>0x02400000</p></td>
</tr>
<tr class="odd">
<td><p>3</p></td>
<td><p>Nunca</p></td>
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
<td><p>4,8</p></td>
<td><p>msRTCSIP-PrimaryUserAddress</p></td>
<td><p>0x08520C00</p></td>
</tr>
<tr class="odd">
<td><p>99,999</p></td>
<td><p>NúmeroDeTeléfono</p></td>
<td><p>0x09022800</p></td>
</tr>
<tr class="even">
<td><p>base10</p></td>
<td><p>Teléfono particular</p></td>
<td><p>0x0A302800</p></td>
</tr>
<tr class="odd">
<td><p>once</p></td>
<td><p>Móvil</p></td>
<td><p>0x0B622800</p></td>
</tr>
<tr class="even">
<td><p>2007</p></td>
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
<td><p>Tales</p></td>
<td><p>0x0E500000</p></td>
</tr>
<tr class="odd">
<td><p>4,5</p></td>
<td><p>groupType</p></td>
<td><p>0x0F010800</p></td>
</tr>
<tr class="even">
<td><p>apartado</p></td>
<td><p>Grandes</p></td>
<td><p>0x10000000</p></td>
</tr>
<tr class="odd">
<td><p>apartado</p></td>
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
<td><p>veinte</p></td>
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


Los números de la columna **identificador** deben ser únicos y nunca se deben volver a usar. Además, mantener los valores de identificador en 256 ahorra espacio en los archivos de salida escritos por el servidor de la libreta de direcciones. Sin embargo, el valor del identificador máximo es 65535. La columna **nombre** corresponde al nombre del atributo de Active Directory que el replicador de usuarios debe incluir en la tabla AbUserEntry por cada contacto. El valor de la **** columna flags se usa para definir el tipo de atributo. Los siguientes tipos de atributos del servidor de la libreta de direcciones son reconocidos por el replicador de usuarios, indicado por el byte bajo del valor de la columna **marcas** .


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
<td><p>0X0</p></td>
<td><p>Un atributo de cadena. El replicador de usuarios convierte este tipo en UTF-8 antes de almacenarlo en la tabla AbUserEntry.</p></td>
</tr>
<tr class="even">
<td><p>0x1</p></td>
<td><p>Un atributo binario. El replicador de usuarios almacena este objeto en el BLOB sin ninguna conversión.</p></td>
</tr>
<tr class="odd">
<td><p>0X2</p></td>
<td><p>Un atributo de cadena, pero se incluye solo si el valor del atributo &quot;comienza por&quot;Tel:. Esto se redestina principalmente a los atributos de cadena de valor múltiple, en concreto <strong>proxyAddresses</strong>. En este caso, el servidor de la libreta de direcciones solo está interesado en las &quot;entradas de&quot; <strong>proxyAddresses</strong> que comienzan con Tel:. Por lo tanto, en interés de ahorrar espacio, User Replicator almacena solo las entradas que comienzan &quot;con Tel&quot;:.</p></td>
</tr>
<tr class="even">
<td><p>0X3</p></td>
<td><p>Un atributo de cadena booleana, que si es verdadero hace que el replicador de usuarios no incluya este contacto en la tabla AbUserEntry. Si es falso, hace que el replicador de usuarios incluya los atributos de este contacto en la tabla AbUserEntry, pero no en el atributo concreto con este indicador. Este es otro tipo especial de caso que es principalmente para el atributo <strong>msExchHideFromAddressLists</strong> .</p></td>
</tr>
<tr class="odd">
<td><p>0x4</p></td>
<td><p>Un atributo de cadena, pero se incluye solo si el valor del atributo &quot;comienza por&quot; SMTP: e &quot; @ &quot; incluye el símbolo.</p></td>
</tr>
<tr class="even">
<td><p>0X5</p></td>
<td><p>Un atributo de cadena, pero se incluye solo si el valor del atributo comienza &quot;por Tel&quot; : &quot;o SMTP&quot; : e incluye &quot; @ &quot; el símbolo.</p></td>
</tr>
<tr class="odd">
<td><p>0x100</p></td>
<td><p>Si se establece, se trata de un atributo de valor múltiple que puede aparecer más de una vez para cada contacto.</p></td>
</tr>
<tr class="even">
<td><p>0x400</p></td>
<td><p>Si se establece, se identifica el atributo de nombre de cuenta de usuario de correo electrónico de un contacto. El servidor de la libreta de direcciones usa esta marca para identificar qué valor de atributo se muestra en la entrada del registro de eventos de normalización del teléfono.</p></td>
</tr>
<tr class="odd">
<td><p>0x800</p></td>
<td><p>Si se establece, identifica un atributo obligatorio para un contacto. El servidor de la libreta de direcciones incluye un usuario en la tabla AbUserEntry solo si hay un valor para este atributo en Active Directory. Si hay más de un atributo obligatorio, solo uno de ellos necesita tener un valor para incluir al usuario en la tabla AbUserEntry.</p></td>
</tr>
<tr class="even">
<td><p>ó</p></td>
<td><p>Si se establece, el servidor de la libreta de direcciones siempre normaliza el valor de este atributo.</p></td>
</tr>
<tr class="odd">
<td><p>0x2000</p></td>
<td><p>Si se establece, el servidor de la libreta de direcciones usa el número normalizado de <strong>proxyAddresses</strong>, si la configuración de <strong>USENORMALIZATIONRULES</strong> CMS es falsa. de lo contrario, se comporta igual que cuando el bit de la marca es 0x1000.</p></td>
</tr>
<tr class="even">
<td><p>0x4000</p></td>
<td><p>Si se establece, el servidor de la libreta de direcciones no incluye los objetos de la tabla AbUserEntry que tienen este valor para el atributo especificado. Por ejemplo, si el atributo <strong>msRTCSIP-PrimaryUserAddress</strong> tiene este bit de marca establecido, los contactos que tienen este atributo no se escriben en la base de datos.</p></td>
</tr>
<tr class="odd">
<td><p>0x8000</p></td>
<td><p>Si se establece, el servidor de la libreta de direcciones no incluye los objetos de la tabla AbUserEntry que no tienen este valor para el atributo especificado. Si se establecen los bits de indicador 0x4000 y 0x8000 en un objeto, el atributo con el valor de bit de indicador establecido en 0x4000 tiene prioridad y el objeto se excluye de la tabla AbUserEntry.</p></td>
</tr>
<tr class="even">
<td><p>0x10000</p></td>
<td><p>Si se establece, representa un objeto de grupo. Replicador de usuarios usa este bit de marca para incluir contactos con el atributo <strong>GroupType</strong> cuya presencia indica un grupo (por ejemplo, una lista de distribución o un grupo de seguridad).</p></td>
</tr>
<tr class="odd">
<td><p>0x20000</p></td>
<td><p>Si se establece, User Replicator usa este bit de marca para incluir este atributo en los archivos del servidor de la libreta de direcciones específicos del dispositivo (es decir, los archivos con la extensión. DABS).</p></td>
</tr>
</tbody>
</table>


En versiones anteriores de Lync Server, al aplicar un cambio a Active Directory, se necesitaba que el administrador ejecutara **Update-CSUserDatabase** y **Update-CSAddressBook** cmdlets de Windows PowerShell para conservar el cambio en el servidor de Lync. base de datos de usuario y base de datos de RTCab inmediatamente. En Lync Server 2013, el replicador de usuarios de Lync Server atenderá los cambios de Active Directory y actualizará la base de datos de usuarios de Lync Server en función de un intervalo configurado. El replicador de usuarios de Lync Server también propagará los cambios a la base de datos de RTCab rápidamente sin que el Administrador tenga que ejecutar Update-CSAddressBook. Si la consulta Web de libreta de direcciones está habilitada, los cambios se reflejarán en los resultados de búsqueda de los clientes de Lync. Los administradores solo tendrán que ejecutar Update-CSAddressBook si está habilitada la descarga del archivo de la libreta de direcciones.

<div>


> [!NOTE]  
> De forma predeterminada, el replicador de usuarios de Lync Server se ejecuta automáticamente cada 5 minutos. Puede configurar este intervalo mediante Set-CSUserReplicatorConfiguration-ReplicationCycleInterval &lt; &gt;.



</div>

</div>

<div>

## <a name="filtering-the-address-book"></a>Filtrar la libreta de direcciones

Los usuarios rellenados en los archivos del servidor de la libreta de direcciones se pueden controlar en función de determinados atributos de servicios de dominio de Active Directory enumerados en la tabla ABAttribute. Un atributo de este tipo utilizado para filtrar es el atributo **msExchangeHideFromAddressBook** . Este es un atributo de usuario agregado por el esquema de Exchange. Si el valor de este atributo es verdadero, Exchange Server usa este atributo para ocultar el contacto de la lista global de direcciones (GAL) de Outlook. De forma similar, si el valor de este atributo es TRUE, User Replicator no incluye a ese usuario en la tabla AbUserEntry y este usuario no estará en los archivos del servidor de la libreta de direcciones.

Puede usar algunos bits de la bandera para definir un filtro que se usará en los atributos del servidor de la libreta de direcciones. Por ejemplo, la presencia de ciertos bits de indicador puede identificar un atributo como un atributo Include o un atributo exclude. El duplicador de usuarios filtra los contactos que contienen un atributo de exclusión y filtra los contiene que no contienen un atributo de inclusión.

<div>


> [!WARNING]  
> Para obtener más información sobre cómo filtrar la libreta de direcciones, consulte cmdlets del <A href="https://technet.microsoft.com/en-us/library/gg415643(v=ocs.15)">servidor de la libreta de direcciones en Lync Server 2013</A>y filtrar la <A href="http://go.microsoft.com/fwlink/?linkid=330430">Libreta de direcciones de Lync 2013</A>



</div>

Actualmente, hay tres filtros diferentes. En la tabla siguiente se enumeran estos filtros.


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
<td><p>Si se establece, identifica un atributo obligatorio para un contacto. Replicador de usuarios usa este bit de marca para filtrar los contactos que no contienen al menos un atributo requerido. El OuPathId es un atributo obligatorio, que siempre se establece. Por lo tanto, se debe establecer al menos uno de los atributos obligatorios. De lo contrario, el valor de Contact (es decir, con el valor de atributo requerido OuPathId) aún no se escribirá en la base de datos. Por ejemplo, si <strong>telephoneNumber</strong> y <strong>teléfono particular</strong> se definen como atributos necesarios, solo los contactos que tengan al menos uno de estos atributos se escribirán en la base de datos.</p></td>
</tr>
<tr class="even">
<td><p>0x4000</p></td>
<td><p>Si se establece, esto identifica un atributo exclude. Replicador de usuarios usa este bit de marca para filtrar los contactos que contienen este atributo. Por ejemplo, si <strong>msRTCSIP-PrimaryUserAddress</strong> se define como un atributo Exclude, los contactos que tienen este atributo no se escriben en la base de datos.</p></td>
</tr>
<tr class="odd">
<td><p>0x8000</p></td>
<td><p>Si se establece, esto identifica un atributo Include. Replicador de usuarios usa este bit de marca para filtrar los contactos que no contienen este atributo. Por ejemplo, si <strong>msRTCSIP-PrimaryUserAddress</strong> se define como un atributo Include, solo los contactos que tienen este atributo se escriben en la base de datos.</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Si se establecen los bits de indicador 0x4000 (atributo Exclude) y 0x8000 (include Attribute), el bit 0x4000 reemplaza el valor de 0x8000 bit y se excluye el contacto.



</div>

Aunque puede filtrar la libreta de direcciones para incluir solo algunos usuarios, la limitación de las entradas no limita la capacidad de otros usuarios de ponerse en contacto con los usuarios filtrados ni de ver su estado de presencia. Los usuarios siempre pueden encontrarse, enviar mensajes instantáneos manualmente o iniciar llamadas manualmente a usuarios que no estén en la libreta de direcciones escribiendo el nombre de inicio de sesión completo de un usuario. Además, la información de contacto de un usuario también podría encontrarse en Outlook.

Aunque la opción de registros de contactos completos en los archivos de la libreta de direcciones permite usar Lync Server para iniciar el correo electrónico, el teléfono o las llamadas de telefonía empresariales (es decir, si la telefonía IP empresarial está habilitada en el servidor) con usuarios que no están configurados para iniciar sesión Protocolo (SIP), algunas organizaciones prefieren incluir solo los usuarios con SIP habilitado en las entradas del servidor de la libreta de direcciones. Puede filtrar la libreta de direcciones para incluir solo usuarios habilitados para SIP si desactiva la bit de **** 0x800 en la columna flags de los siguientes atributos obligatorios: **mailNickname**, **telephoneNumber**, **teléfono particular**y **Mobile**. También puede filtrar la libreta de direcciones para incluir solo los usuarios habilitados para SIP mediante la configuración de 0x8000 (include **** Attribute) en la columna Flags del atributo **msRTCSIP-PrimaryUserAddress** . Esto también ayuda a excluir cuentas de servicio de los archivos de la libreta de direcciones.

Después de modificar la tabla ABAttribute, puede actualizar los datos de la tabla AbUserEntry ejecutando el cmdlet **Update-CsUserDatabase** comando. Después de que se complete la replicación de UR, puede actualizar el archivo en el almacén de archivos del servidor de la libreta de direcciones ejecutando manualmente el cmdlet **UpdateCsAddressBook** .

<div>


> [!NOTE]  
> El servidor front-end en el que se encuentra el servidor de la libreta de direcciones no se puede configurar de forma administrativa. Uno se elige durante la implementación (normalmente, el primer servidor front-end implementado). En el caso de que se produzca un error, el servicio de libreta de direcciones se moverá a otro servidor front-end y no requiere ninguna atención administrativa.



</div>

<div>


> [!IMPORTANT]  
> Si ha consolidado o modificado de otra manera su infraestructura desde una implementación de varios bosques o de una implementación de principal/secundario (como consolidar su infraestructura antes de migrar a Lync Server), es posible que descubra que el servicio de libreta de direcciones se ha descargado y el Error en la consulta Web de la libreta de direcciones para algunos usuarios. Cuando se encuentra en una implementación que tiene varios dominios o bosques, el atributo <STRONG>MsRTCSIP-OriginatorSid</STRONG> se rellena en los objetos de usuario que presentan el problema. El atributo <STRONG>MsRTCSIP-OriginatorSid</STRONG> debe establecerse en null en estos objetos para resolver el problema.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

