---
title: Cómo se muestran las fotos de usuario en Lync
TOCTitle: Cómo se muestran las fotos de usuario en Lync
ms:assetid: b44a364d-a1d2-4d45-b27a-b5f77775e233
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Dn783119(v=OCS.15)
ms:contentKeyID: 62839652
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Cómo se muestran las fotos de usuario en Lync

 

_**Última modificación del tema:** 2016-12-08_

**Resumen:** Las fotos del usuario que se muestran en el cliente de Lync pueden ser distintas en función de qué característica de Lync se está utilizando, por ejemplo si el usuario está en una conferencia o en un chat de MI.

En Lync 2010 se introduce la posibilidad de incluir una foto con el perfil de Lync que se muestra a otros usuarios de Lync. También puede seleccionar si quiere mostrar o no fotos a los contactos del cliente de Lync. En Lync 2013, compatibilidad con las fotos de alta resolución para los usuarios. Este tema describe cómo el cliente de Lync obtiene y muestra fotos de usuario, dónde se almacenan las imágenes, las limitaciones de cada origen de imagen y cómo los distintos servicios de Lync utilizan las fotos de usuario.

## Consideraciones de planificación

Debe tener en cuenta los aspectos siguientes a la hora de planificar la implementación de la compatibilidad con las fotos de usuario.

  - La compatibilidad con las fotos de usuario de alta definición requiere que el buzón del usuario esté ubicado en Exchange 2013 y que la cuenta de usuario de Lync esté en el grupo de Lync 2013.

  - Las fotos de usuario de alta definición únicamente son compatibles en un entorno en el cual se utilizan Lync Server 2013 y Exchange 2013.

  - Los usuarios con buzones en Exchange 2010 siempre utilizarán el atributo **thumbnailPhoto** de AD DS como origen para su foto de usuario.

  - Una foto de usuario almacenada como atributo **thumbnailPhoto** de AD DS no se mostrará a los contactos externos / federados.

  - Si las fotos para los contactos de usuario se almacenan en AD DS, el archivo de imagen utilizado se limita a 96 × 96 píxeles y no puede tener un tamaño de archivo mayor de 100 KB.

  - Si se pierde la conectividad entre Lync Server y Exchange Server, se mostrara el atributo **thumbnailPhoto** de baja resolución del usuario de AD DS, únicamente a los usuarios internos.

  - Las fotos de usuario de alta resolución se muestran en las reuniones de Lync 2013 cuando un orador activo no tiene el vídeo habilitado. Además, al mover el mouse por encima de la foto en miniatura de la galería se mostrará la foto de alta resolución.

## Fotos de usuario en Lync 2010

En el cliente de Lync 2010, puede elegir entre dos posibles opciones para mostrar una foto para su perfil, **Foto corporativa predeterminada** y **Mostrar una foto de una dirección web**.

## Foto corporativa predeterminada

Al elegir la opción **Foto corporativa predeterminada**, Lync obtiene la foto que se muestra en Servicios de dominio de Active Directory. La imagen utilizada es la imagen definida como valor del atributo **thumbnailPhoto** en Servicios de dominio de Active Directory. Es el mismo archivo que utiliza Exchange para mostrar imágenes en Outlook.

Entre los aspectos a tener en cuenta al utilizar imágenes de Servicios de dominio de Active Directory se incluye lo siguiente:

  - Únicamente se admiten las imágenes con dimensiones superiores a 96 x 96 píxeles. El tamaño de archivo para la imagen se limita a 100 KB.

  - De forma predeterminada, los usuarios pueden cambiar la imagen utilizada para el atributo **thumbnailPhoto**, aunque no directamente a través del cliente de Lync. Puede deshabilitarlo a través de Servicios de dominio de Active Directory.

  - Las imágenes almacenadas en Servicios de dominio de Active Directory no se muestran a los contactos externos de la organización, incluso en el caso de que sean contactos federados.

  - En las organizaciones grandes, el almacenamiento y la recuperación de imágenes para un número elevado de usuarios pueden tener un impacto en el rendimiento y el tamaño de la base de datos de Servicios de dominio de Active Directory.

  - Las limitaciones de dimensión de imagen y tamaño de archivo significan que únicamente pueden utilizarse imágenes de baja resolución.

## Cómo los usuarios administran sus fotos de usuario en Servicios de dominio de Active Directory

Un usuario no puede cambiar la imagen que utiliza en su perfil de Servicios de dominio de Active Directory directamente a través del cliente de Lync 2010. El usuario únicamente puede utilizar una de las opciones siguientes para hacerlo, si está disponible:

  - **SharePoint Server** Los usuarios pueden cargar una foto en ‘Mi sitio’ en SharePoint Server y posteriormente [configurar la sincronización de perfiles en SharePoint](http://go.microsoft.com/fwlink/p/?linkid=507466) para sincronizar la foto con el atributo **thumbnailPhoto** en Servicios de dominio de Active Directory.

  - **Fotos almacenadas en direcciones URL de acceso público** Los usuarios pueden configurar su foto de usuario especificando una dirección URL de acceso público para la imagen que desean utilizar. La imagen debe ser de acceso público sin contraseña. La imagen almacenada en la dirección web especificada se transfiere a otros usuarios a través de la categoría de la tarjeta de contacto en la información de presencia. Cuando el cliente de Lync tiene que mostrar una foto de usuario, recupera la imagen de la dirección web especificada.

  - **Cmdlets de Exchange 2010 para Windows PowerShell** Los administradores pueden ejecutar el cmdlet [Import-RecipientDataProperty](http://go.microsoft.com/fwlink/p/?linkid=507468) del Shell de administración de Exchange 2010 para administrar el atributo **thumbnailPhoto**. Cuando las imágenes se importan con cmdlets de Exchange 2010, el tamaño de archivo se limita a 10 KB.

  - **Herramientas de terceros** Los usuarios pueden cargar únicamente su propia foto para el atributo **thumbnailPhoto**.

## Mostrar una foto de una dirección web

Al elegir la opción **Mostrar una foto de una dirección web**, Lync obtiene la imagen de la dirección introducida y la muestra como foto de usuario en Lync.

Entre los aspectos a tener en cuenta a la hora de utilizar imágenes de una dirección web se incluye lo siguiente:

  - Las limitaciones de tamaño de archivo las determina el atributo **MaxPhotoSizeKB** de la directiva de cliente, que se define con el cmdlet [New-CsClientPolicy](http://go.microsoft.com/fwlink/p/?linkid=507463). El límite de tamaño predeterminado es 30 KB. El valor máximo es 100 KB. No existe ninguna restricción acerca de la resolución de la imagen, pero si intenta utilizar un archivo de imagen que supere el límite de tamaño, no se descargará en los clientes de Lync. Puede establecer el valor en 0 para deshabilitar la utilización de todas las fotos de usuario en Lync.

  - Los contactos federados externos pueden ver las fotos de usuario de una dirección web.

## Administración de fotos de usuario con cmdlets de directiva de cliente

En Lync Server 2010, las opciones de directiva de cliente se configuran con los cmdlets CsClientPolicy. Las opciones de directiva configuradas se envían a los clientes a través del aprovisionamiento dentro de banda. Los dos parámetros de los cmdlets CsClientPolicy que determinan la experiencia de foto de usuario son **DisplayPhoto** y **MaxPhotoSizeKB**. El parámetro de aprovisionamiento dentro de banda correspondiente para **DisplayPhoto** y **MaxPhotoSizeKB** se denomina **PhotoUsage**. Los valores para el parámetro **PhotoUsage** se envían a los clientes a través de **endpointConfigurationprovisionGroup**. Consulte la [introducción a la configuración y las directivas de cliente](http://go.microsoft.com/fwlink/?linkid=507470) para obtener más información.

El valor del parámetro **DisplayPhoto** determina el origen de la imagen de foto de usuario. Los valores admitidos se incluyen en la tabla siguiente.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Valor del parámetro DisplayPhoto</th>
<th>Origen de la imagen</th>
<th>Configuración del cliente de Lync 2010</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>NoPhoto</p></td>
<td><p>Ninguno</p></td>
<td><p><strong>No mostrar mi foto</strong></p></td>
</tr>
<tr class="even">
<td><p>PhotoFromADOnly</p></td>
<td><p>Active Directory</p></td>
<td><p><strong>Foto corporativa predeterminada</strong></p></td>
</tr>
<tr class="odd">
<td><p>AllPhotos</p></td>
<td><p>Dirección web</p></td>
<td><p><strong>Mostrar una foto de una dirección web</strong></p></td>
</tr>
</tbody>
</table>


## Cómo obtiene fotos el cliente de Lync 2010

En Lync 2010, el servicio de libreta de direcciones administra las fotos de usuario en el servidor. El cliente de Lync obtiene las fotos de usuario consultando primero el servicio de consulta web de la libreta de direcciones (ABWQ) en el servidor, que se expone a través del servicio web de expansión de lista de distribución. El cliente recibe el archivo de imagen y posteriormente lo copia en la memoria caché del usuario para evitar la descarga de la imagen cada vez que tenga que mostrarse. Los valores del atributo devueltos por la consulta también se almacenan en la entrada del servicio de libreta de direcciones para el usuario. El servicio de libreta de direcciones elimina todas las imágenes almacenadas en la memoria caché cada 24 horas, lo cual significa que pueden transcurrir 24 horas para que las imágenes nuevas se actualicen en la memoria caché del servidor. Puede forzar una actualización de la memoria caché utilizando el cmdlet [Update-CsAddressBook](https://docs.microsoft.com/en-us/powershell/module/skype/Update-CsAddressBook).

Las fotos de usuario incluidas en el estado de presencia también tienen un valor hash asociado que el cliente de Lync utiliza para determinar si existe alguna imagen más reciente disponible. Los cambios en el archivo de imagen utilizado en el estado de presencia se notifican automáticamente al cliente.


> [!NOTE]
> Dado que las fotos no se almacenan en la base de datos GalContacts.db, la descarga de fotos de usuario no depende de la configuración de <STRONG>AddressBookAvailability</STRONG> en la directiva de cliente (<A href="http://go.microsoft.com/fwlink/p/?linkid=507508">Set-CsClientPolicy</A>).



La consulta al servicio ABWQ incluye los atributos siguientes:

  - **PhotoHash** El valor hash de los datos de foto binarios; se utiliza para determinar si la foto actual ha cambiado.

  - **PhotoRelPath** La ruta de acceso relativa al archivo de imagen almacenado en el servidor.

  - **PhotoSize** El tamaño del archivo de imagen, en bytes.

  - **TimeStamp** La fecha y la hora en que el archivo de imagen se ha descargado del servidor y se ha copiado en la memoria caché del cliente por última vez.

Posteriormente, tras recuperar el archivo de imagen, el cliente de Lync 2010 compara los valores de atributo devueltos por la consulta con los valores de atributo recibidos por el cliente desde el aprovisionamiento dentro de banda, para ver si son distintos. Si los valores son distintos, el cliente recupera el archivo de imagen del usuario que ha iniciado la sesión con una solicitud HTTP GET.

Además, el cliente realiza una comprobación cada 24 horas en el servidor, a partir de la hora de creación de la versión almacenada en caché, para comparar el valor del atributo **PhotoHash** en el servidor con el valor en el cliente. Si los valores son distintos, el cliente sabe que el archivo de imagen ha cambiado. Para obtener el archivo de imagen actualizado, el cliente vuelve a consultar el servicio ABWQ para actualizar el archivo de imagen en la memoria caché del cliente con el archivo de imagen en el servidor, lo cual también restablece el atributo **TimeStamp** en el archivo de la memoria caché del cliente.

A continuación se muestra una respuesta de ejemplo a una consulta realizada al servicio ABWQ:

    <Attribute>
              <Name>PhotoRelPath</Name>
              <Value>efa6096aed2746cb9ab2037f7dbdde9d.f2eeeb5946db54a7aa607ecd3ae09d
              95.photo</Value>
              <Values xmlns:d6p1="http://schemas.microsoft.com/2003/10/Serialization/Arrays" i:nil="true" />
    </Attribute>
    <Attribute>
              <Name>PhotoHash</Name>
              <Value>f2eeeb5946db54a7aa607ecd3ae09d95</Value>
              <Values xmlns:d6p1="http://schemas.microsoft.com/2003/10/Serialization/Arrays" i:nil="true" />
    </Attribute>
    <Attribute>
         <Name>PhotoSize</Name>
         <Value>4620</Value>
         <Valuesxmlns:d6p1="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
    i:nil="true" />
    </Attribute>

## Fotos de usuario en Lync 2013

En Lync 2013 se introduce la compatibilidad de las imágenes de alta resolución para las fotos de usuario. Lync 2013 también incluye compatibilidad para almacenar fotos de usuario en el buzón del usuario en Exchange 2013, lo cual acaba con las limitaciones de tamaño y resolución de imagen que existían en Lync 2010. Las fotos de usuario en Lync 2013 pueden ser de hasta 648 x 648 píxeles, con un tamaño de archivo de hasta 20 MB. Las fotos de alta resolución en Lync 2013 deben estar ubicadas en el buzón del usuario en Exchange 2013 y únicamente son compatibles con el cliente de Lync 2013. Esta integración con Exchange aprovecha el nuevo marco de autorización incluido con las versiones 2013 de Lync, Exchange y SharePoint, bajo el nombre Oauth.

Si Exchange 2013 no se utiliza en su implementación, la compatibilidad con las fotos de usuario es la misma que con Lync 2010. No obstante, las opciones del usuario para elegir la foto son distintas en el cliente de Lync 2013. En el cliente de Lync 2013, los usuarios pueden seleccionar **Ocultar mi foto** o **Mostrar mi foto**. La opción **Mostrar una foto de una dirección web** no está disponible de forma predeterminada, pero puede habilitarse asignando una directiva de cliente.

## Ocultar mi foto

La configuración para las fotos de usuario está en el diálogo **Opciones** de Lync 2013. Al elegir **Ocultar mi foto**, no se le mostrará ninguna foto de usuario en su cliente de Lync, pero su foto seguirá apareciendo en la tarjeta de contacto y fuera de Lync.

## Mostrar mi foto

Al elegir la opción **Mostrar mi foto**, su foto de usuario se mostrará en su cliente de Lync y a los otros usuarios de las conversaciones en Lync. La imagen utilizada es la que está almacenada en AD DS.

## Mostrar una foto de una dirección web

La opción **Mostrar una foto de una dirección web** pasa a estar disponible en Lync 2013 cuando una directiva de cliente está establecida para habilitarla. La versión del cliente debe ser posterior a 15.0.4535.1002, que es la versión instalada con [Actualizaciones acumulativas para Lync: noviembre de 2013](http://go.microsoft.com/fwlink/p/?linkid=509908). Es posible que los usuarios tengan que cerrar la sesión y volver a iniciarla para ver los cambios en el cliente.

Puede establecer la directiva de cliente para habilitar la configuración de **Mostrar una foto de una dirección web** ejecutando la directiva [Set-CsClientPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClientPolicy) del Shell de administración de Lync Server. Los cmdlets de ejemplo siguientes demuestran cómo se establece la directiva globalmente para todos los usuarios de la implementación:

  ```
  $pe=New-CsClientPolicyEntry -Name EnablePresencePhotoOptions -Value True
  ```
  ```
  $po=Get-CsClientPolicy -Identity Global
  ```
  ```
  $po.PolicyEntry.Add($pe)
  ```
  ```
  Set-CsClientPolicy -Instance $po
  ```

Cuando se carga una imagen en el buzón del usuario, Exchange crea automáticamente una versión de menor resolución de la imagen, que puede utilizarse en las aplicaciones cliente. La foto de usuario también se actualiza en AD DS.


> [!NOTE]
> Cuando se actualiza una imagen en AD DS, se crea y se utiliza una imagen de 48 x 48 píxeles para el atributo thumbnailPhoto de AD DS. Se sustituyen todas las imágenes existentes. Por lo tanto, si agrega una imagen de 96 x 96 píxeles a AD DS, quedará sobrescrita por la nueva imagen de 48 x 48 píxeles. Esto únicamente resulta importante si usuarios de su entorno utilizan clientes de Lync 2010, ya que dichos clientes obtendrán las fotos de usuario de AD DS. Puede importar imágenes de 96 x 96 píxeles para sustituir las imágenes creadas por AD DS si tiene clientes de Lync 2010 en su organización.



## Compatibilidad con la foto de usuario en Lync 2013

En Lync 2013 se admiten tres resoluciones de imagen para las fotos de usuario, como se describe en la tabla siguiente. La imagen que se utiliza la determina la configuración de la directiva de cliente asignada a los usuarios de Lync. Consulte “Administración de fotos de usuario con cmdlets de directiva de cliente”, en este mismo tema, para obtener más información.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Resolución de imagen (píxeles)</th>
<th>Application</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>48 × 48</p></td>
<td><p>Se utiliza si no se ha seleccionado una imagen de resolución superior</p></td>
</tr>
<tr class="even">
<td><p>96 × 96</p></td>
<td><p>Se utiliza en Outlook Web App y Outlook 2013</p></td>
</tr>
<tr class="odd">
<td><p>648 × 648</p></td>
<td><p>Se utiliza en el cliente para equipo de escritorio de Lync 2013 y en Lync 2013 Web App</p></td>
</tr>
</tbody>
</table>


Cualquier usuario con un buzón habilitado en Exchange 2013 puede cargar una imagen distinta, incluyendo fotos de alta resolución, a través de opciones del cliente de Lync 2013 u Outlook Web Access. La configuración recomendada para las imágenes utilizadas incluye:

  - **Resolución de imagen**   648 x 648 píxeles

  - **Profundidad de color** 24 bits

  - **Tamaño del archivo de imagen** 20 MB máximo

  - **Formato de archivo** JPEG

Una imagen JPEG típica de 24 bits con una resolución de 648 x 648 píxeles tiene un tamaño de archivo de unos 240 KB, por lo que se necesita 1 MB de espacio de almacenamiento para cada 4 fotos de usuario.

