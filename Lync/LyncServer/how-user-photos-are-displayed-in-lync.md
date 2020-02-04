---
title: Cómo se muestran las fotos de usuario en Lync
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: How user photos are displayed in Lync
ms:assetid: b44a364d-a1d2-4d45-b27a-b5f77775e233
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn783119(v=OCS.15)
ms:contentKeyID: 62835297
ms.date: 08/27/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8cd3214c3ada87db6f44f6b99373346d4f0a27d4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730700"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="how-user-photos-are-displayed-in-lync"></a>Cómo se muestran las fotos de usuario en Lync

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-08-25_

**Resumen:** Las fotos del usuario mostradas en el cliente de Lync pueden diferir dependiendo de la característica de Lync que use, como cuando se encuentre en una conferencia o en una conversación de mensajería instantánea.

Lync 2010 presentó la posibilidad de incluir una foto con el perfil de Lync que se muestra a otros usuarios de Lync. También puede elegir si desea mostrar o no las fotos de los contactos en el cliente de Lync. En Lync 2013, soporte técnico para fotos de alta resolución para usuarios. En este tema se describe cómo obtiene y muestra el cliente de Lync las fotos de los usuarios, dónde se almacenan, las limitaciones de cada origen de imagen y cómo usan las fotos de los usuarios diferentes servicios de Lync.

<div>

## <a name="planning-considerations"></a>Consideraciones de planeación

Debe tener en cuenta lo siguiente al planear la implementación de las fotos de los usuarios.

  - La compatibilidad con fotos de usuario de alta definición requiere que el buzón del usuario se encuentre en Exchange 2013 y que la cuenta de usuario de Lync esté en el grupo de Lync 2013.

  - Las fotos de los usuarios de alta definición se admiten únicamente en un entorno en el que se usan Lync Server 2013 y Exchange 2013.

  - Los usuarios con buzones en Exchange 2010 siempre usarán el atributo **thumbnailPhoto** de AD DS como origen de la foto de su usuario.

  - Una foto de usuario almacenada como el atributo **thumbnailPhoto** de AD DS no se mostrará a los contactos externos o federados.

  - Si las fotos de los contactos de los usuarios se almacenan en AD DS, el archivo de imagen usado se limita a 96 x 96 píxeles y no más del tamaño de archivo de 100 KB.

  - Si se pierde la conectividad entre Lync Server y Exchange Server, se mostrará la baja resolución de **thumbnailPhoto** del usuario de AD DS y solo a los usuarios internos.

  - Las fotos de los usuarios de alta resolución se muestran en las reuniones de Lync 2013 cuando un orador activo no tiene el vídeo habilitado. Además, Si mueves el ratón sobre la foto en miniatura de la galería, se mostrará la foto de alta resolución.

</div>

<div>

## <a name="user-photos-in-lync-2010"></a>Fotos de usuario en Lync 2010

En el cliente de Lync 2010, puede elegir entre dos opciones para mostrar una foto de su perfil, una **imagen corporativa predeterminada** y **Mostrar la imagen de una dirección web**.

<div>

## <a name="default-corporate-picture"></a>Imagen corporativa predeterminada

Si elige la opción de **imagen corporativa predeterminada** , Lync le mostrará la foto de los servicios de dominio de Active Directory. La imagen usada es la imagen definida como el valor del atributo **thumbnailPhoto** en servicios de dominio de Active Directory. Este es el mismo archivo que usa Exchange para mostrar imágenes en Outlook.

Entre las consideraciones para usar imágenes de los servicios de dominio de Active Directory se incluyen las siguientes:

  - Solo se admiten las imágenes con dimensiones de hasta 96 píxeles por 96 píxeles. El tamaño de archivo de la imagen está limitado a 100 KB.

  - De forma predeterminada, los usuarios pueden cambiar la imagen que se usa para el atributo **thumbnailPhoto** , aunque no directamente a través del cliente de Lync. Puede deshabilitarlo a través de los servicios de dominio de Active Directory.

  - Las imágenes almacenadas en servicios de dominio de Active Directory no se muestran a los contactos externos a su organización, incluso si son contactos federados.

  - En organizaciones grandes, almacenar y recuperar imágenes para un gran número de usuarios puede repercutir en el tamaño y el rendimiento de la base de datos de los servicios de dominio de Active Directory.

  - Las dimensiones de imagen y el tamaño de archivo limitados indican que solo se pueden usar imágenes de baja resolución.

<div>

## <a name="how-users-manage-their-user-photos-in-active-directory-domain-services"></a>Cómo administran los usuarios las fotos de los usuarios en los servicios de dominio de Active Directory

El usuario no puede cambiar la imagen usada en el perfil de los servicios de dominio de Active Directory directamente a través del cliente de Lync 2010. Puede usar una de las siguientes opciones para hacerlo, si está disponible:

  - ****   Los usuarios de SharePoint Server pueden cargar una foto en ' mi sitio ' en un servidor de SharePoint y, a continuación, [configurar la sincronización de perfiles en SharePoint](http://go.microsoft.com/fwlink/p/?linkid=507466) para sincronizar la foto con el atributo **thumbnailPhoto** en servicios de dominio de Active Directory.

  - **Foto almacenada en la dirección URL**   de acceso público puede configurar su foto de usuario especificando una dirección URL accesible públicamente para la imagen que desea usar. La imagen debe ser públicamente accesible sin una contraseña. La imagen almacenada en la dirección Web especificada se transfiere a otros usuarios a través de la categoría tarjeta de contacto de la información de presencia. Cuando el cliente de Lync necesita mostrar una foto de usuario, recupera la imagen de la dirección Web especificada.

  - **Los cmdlets de Exchange 2010 para administradores de Windows PowerShell**   pueden ejecutar el cmdlet [Import-RecipientDataProperty](http://go.microsoft.com/fwlink/p/?linkid=507468) en el shell de administración de Exchange 2010 en para administrar el atributo **thumbnailPhoto** . Cuando se importan imágenes con cmdlets de Exchange 2010, el tamaño de archivo se limita a 10 KB.

  - **Las herramientas**   de terceros los usuarios pueden cargar solo su propia foto para el atributo **thumbnailPhoto** .

</div>

</div>

<div>

## <a name="show-a-picture-from-a-web-address"></a>Mostrar una imagen de una dirección web

Cuando elige la opción **Mostrar una imagen de una dirección web** , Lync obtiene la imagen en la dirección que escribe y la muestra para la foto de usuario en Lync.

Entre las consideraciones para usar imágenes de una dirección web se incluyen las siguientes:

  - Los límites de tamaño de archivo se determinan mediante el atributo **MaxPhotoSizeKB** en la Directiva de cliente, que se define con el cmdlet [New-ClientPolicy](http://go.microsoft.com/fwlink/p/?linkid=507463) . El límite de tamaño predeterminado es 30 KB. El valor máximo es 100 KB. No hay ninguna restricción en la resolución de la imagen, pero si intenta usar un archivo de imagen que supere el límite de tamaño, no se descargará en los clientes de Lync. Puede establecer el valor en 0 para deshabilitar que todas las fotos de los usuarios se usen en Lync.

  - Los contactos federados externos pueden ver las fotos de los usuarios de una dirección Web.

</div>

<div>

## <a name="managing-users-photo-with-client-policy-cmdlets"></a>Administrar la foto del usuario con cmdlets de directiva de cliente

En Lync Server 2010, la configuración de la Directiva de cliente está configurada con los cmdlets de ClientPolicy. La configuración de la Directiva configurada se envía a los clientes mediante aprovisionamiento en banda. Los dos parámetros de los cmdlets de ClientPolicy que determinan la experiencia de foto del usuario son **DisplayPhoto** y **MaxPhotoSizeKB**. El parámetro de aprovisionamiento dentro de banda correspondiente para **DisplayPhoto** y **MaxPhotoSizeKB** se denomina " **fotousage**". Los valores para el parámetro de **fotouso** se envían a los clientes a través de la **endpointConfiguration** **provisionGroup**. Para obtener más información [, vea información general sobre la configuración y las directivas de cliente](http://go.microsoft.com/fwlink/?linkid=507470) .

El valor del parámetro **DisplayPhoto** determina el origen de la imagen de foto del usuario. En la tabla siguiente se incluyen los valores admitidos.


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
<th>Configuración de cliente de Lync 2010</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>NOPHOTO</p></td>
<td><p>nada</p></td>
<td><p><strong>No mostrar mi foto</strong></p></td>
</tr>
<tr class="even">
<td><p>PhotoFromADOnly</p></td>
<td><p>Active Directory</p></td>
<td><p><strong>Imagen corporativa predeterminada</strong></p></td>
</tr>
<tr class="odd">
<td><p>AllPhotos</p></td>
<td><p>Dirección web</p></td>
<td><p><strong>Mostrar una imagen de una dirección web</strong></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="how-lync-2010-client-gets-photos"></a>Cómo obtiene fotos el cliente de Lync 2010

En Lync 2010, el servicio de libreta de direcciones administra las fotos del usuario en el servidor. El cliente de Lync obtiene las fotos del usuario al consultar primero el servicio de consulta Web de la libreta de direcciones (ABWQ) en el servidor, que se expone a través del servicio Web de expansión de la lista de distribución. El cliente recibe el archivo de imagen y, a continuación, lo copia en la caché del usuario para evitar descargar la imagen cada vez que se debe mostrar. Los valores de atributo devueltos de la consulta también se almacenan en la entrada del servicio de libreta de direcciones en caché para el usuario. El servicio de libreta de direcciones elimina todas las imágenes almacenadas en caché cada 24 horas, lo que significa que puede tardar hasta 24 horas en actualizar las imágenes de usuario nuevas en la memoria caché del servidor. Puede forzar una actualización a la caché mediante el cmdlet [Update-CsAddressBook](https://docs.microsoft.com/powershell/module/skype/Update-CsAddressBook) .

Las fotos del usuario incluidas en el estado de presencia también tienen un valor hash asociado que el cliente de Lync usa para determinar si hay una imagen más reciente disponible. Se notifica automáticamente al cliente los cambios en el archivo de imagen que se usa en el estado de presencia.

<div class=" ">


> [!NOTE]  
> Como las fotos no se almacenan en la base de datos GalContacts. dB, la descarga de fotos del usuario no depende de la configuración de <STRONG>AddressBookAvailability</STRONG> de la Directiva de cliente (<A href="http://go.microsoft.com/fwlink/p/?linkid=507508">set-ClientPolicy</A>).



</div>

La consulta al servicio ABWQ incluye los siguientes atributos:

  - **Fotohash**   el valor hash de los datos de la fotografía binaria y se usa para determinar si la foto actual ha cambiado.

  - **PhotoRelPath**   la ruta de acceso relativa al archivo de imagen almacenado en el servidor.

  - **Tamaño**   tamaño del archivo de imagen, en bytes.

  - **TimeStamp**   la fecha y la hora en las que el archivo de imagen se ha descargado por última vez desde el servidor y se ha copiado en la caché del cliente.

Después, después de recuperar el archivo de imagen, el cliente de Lync 2010 compara los valores de atributo devueltos de la consulta con los valores de atributo recibidos por el cliente de aprovisionamiento en banda para ver si son diferentes. Si los valores son diferentes, el cliente recupera el archivo de imagen del usuario que ha iniciado sesión con una solicitud HTTP GET.

Además, el cliente comprueba el servidor cada 24 horas desde el momento en que se creó la versión en caché del archivo de imagen para comparar el valor del atributo **fotohash** en el servidor con el valor en el cliente. Si los valores son diferentes, el cliente sabe que el archivo de imagen ha cambiado. Para obtener el archivo de imagen actualizado, el cliente consulta nuevamente el servicio ABWQ para actualizar el archivo de imagen en la memoria caché del cliente con el archivo de imagen en el servidor, que también restablece la **marca de hora** en el archivo en la memoria caché del cliente.

La siguiente es una respuesta de ejemplo a una consulta para el servicio ABWQ:
```xml
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
```

</div>

</div>

<div>

## <a name="user-photos-in-lync-2013"></a>Fotos de usuario en Lync 2013

Lync 2013 presentó compatibilidad con imágenes de alta resolución para fotos de usuario. Lync 2013 también incluye compatibilidad para almacenar fotos de usuarios en el buzón del usuario en Exchange 2013, lo que elimina la resolución de imagen y las limitaciones de tamaño presentes en Lync 2010. Las fotos de los usuarios en Lync 2013 pueden tener hasta 648 píxeles por 648 píxeles, con un tamaño de archivo de hasta 20 MB. Las fotos de alta resolución de Lync 2013 deben encontrarse en el buzón del usuario en Exchange 2013, y solo se admiten con el cliente de Lync 2013. Esta integración con Exchange aprovecha el nuevo marco de autorización incluido en las versiones 2013 de Lync, Exchange y SharePoint denominado OAuth.

Si Exchange 2013 no se usa en su implementación, la compatibilidad con las fotos de los usuarios es la misma que con Lync 2010. Sin embargo, las opciones de usuario para elegir la foto que desea usar son diferentes en el cliente de Lync 2013. En el cliente de Lync 2013, los usuarios pueden seleccionar **ocultar mi foto** o **Mostrar mi foto**. La opción **Mostrar una imagen de un sitio web** no está disponible de forma predeterminada, pero se puede habilitar mediante la asignación de una directiva de cliente.

<div>

## <a name="hide-my-picture"></a>Ocultar mi foto

La configuración de las fotos de los usuarios está en el cuadro de diálogo **Opciones** de Lync 2013. Al elegir **ocultar mi**foto, no se muestra ninguna foto de usuario en el cliente de Lync, pero la foto aún se muestra en la tarjeta de contacto y fuera de Lync.

</div>

<div>

## <a name="show-my-picture"></a>Mostrar mi foto

Al elegir la opción **Mostrar mi** foto, la foto del usuario se muestra en el cliente de Lync y en otros usuarios de las conversaciones de Lync. La imagen usada es la que se almacena en AD DS.

</div>

<div>

## <a name="show-a-picture-from-a-website"></a>Mostrar una imagen de un sitio web

La opción **Mostrar imagen de un sitio web** está disponible en Lync 2013 después de establecer una directiva de cliente para habilitarla. La versión del cliente debe ser posterior a 15.0.4535.1002, que se instala con las [actualizaciones acumulativas de Lync: 2013 de noviembre](http://go.microsoft.com/fwlink/p/?linkid=509908). Es posible que los usuarios tengan que cerrar sesión y volver a iniciarla para ver los cambios en el cliente.

Puede establecer la Directiva de cliente para habilitar la **visualización de la imagen de una configuración de sitio web** ejecutando la directiva [set-ClientPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy) en el shell de administración de Lync Server. En los siguientes cmdlets de ejemplo se muestra cómo establecer la Directiva globalmente para todos los usuarios de la implementación:

   ```powershell
    $pe=New-CsClientPolicyEntry -Name EnablePresencePhotoOptions -Value True
   ```

   ```powershell
    $po=Get-CsClientPolicy -Identity Global
   ```

   ```powershell
    $po.PolicyEntry.Add($pe)
   ```

   ```powershell
    Set-CsClientPolicy -Instance $po
   ```


Cuando se carga una imagen en el buzón del usuario, Exchange crea automáticamente una versión de menor resolución de la imagen que se puede usar en las aplicaciones cliente. La foto del usuario también se ha actualizado en AD DS.

<div class=" ">


> [!NOTE]  
> Cuando se actualiza un archivo de imagen en AD DS, se crea una imagen de 48 x 48 de píxeles y se usa para thumbnailPhoto en AD DS. Se reemplaza cualquier imagen existente. Por lo tanto, si agregaste una imagen de 96 x 96 a AD DS, se sobrescribirá con la nueva imagen de 48 x 48. Esto solo es importante: tiene usuarios en su entorno con clientes de Lync 2010, ya que estos clientes obtendrán fotos de usuarios de AD DS. Puede importar imágenes de 96 x 96 pixel para reemplazar las creadas por AD DS si tiene clientes de Lync 2010 en su organización.



</div>

</div>

<div>

## <a name="user-photo-support-in-lync-2013"></a>Compatibilidad con fotos de usuario en Lync 2013

En Lync 2013, se admiten tres resoluciones de imagen para las fotos del usuario, como se describe en la tabla siguiente. La imagen que se usa está determinada por la configuración de directiva de cliente asignada a los usuarios de Lync. Para obtener más información, consulte "administrar la foto del usuario con cmdlets de directivas de cliente" en este tema.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Resolución de imagen (píxeles)</th>
<th>Aplicación</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>48 x 48</p></td>
<td><p>Se usa si no se selecciona ninguna imagen de resolución superior</p></td>
</tr>
<tr class="even">
<td><p>96 x 96</p></td>
<td><p>Se usa en Outlook Web App y Outlook 2013</p></td>
</tr>
<tr class="odd">
<td><p>648 x 648</p></td>
<td><p>Usado en el cliente de escritorio de Lync 2013 y la aplicación Web de Lync 2013</p></td>
</tr>
</tbody>
</table>


Cualquier usuario con un buzón habilitado en Exchange 2013 puede cargar una imagen diferente, incluidas las fotos de alta resolución, a través de las opciones de cliente de Outlook Web Access o Lync 2013. La configuración recomendada para las imágenes que se usan incluye:

  - **Resolución de imagen**   648 por 648 píxeles

  - **Profundidad de color**   de 24 bits

  - **Tamaño de archivo de imagen**   de hasta 20 MB

  - **Formato de archivo**   JPEG

Una imagen de JPEG de 24 bits típica, de 648 píxeles por 648 píxeles, tiene un tamaño de archivo de aproximadamente 240 KB, por lo que se necesita 1 MB de espacio de almacenamiento para cada cuatro fotos de usuario.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

