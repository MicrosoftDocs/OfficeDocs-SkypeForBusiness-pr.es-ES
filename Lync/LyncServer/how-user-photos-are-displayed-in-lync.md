---
title: Cómo se muestran las fotos de los usuarios en Lync
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
ms.openlocfilehash: 2b2c64d0a147457eb50a778d7909b3ccfbf8fecc
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42180363"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="how-user-photos-are-displayed-in-lync"></a>Cómo se muestran las fotos de los usuarios en Lync

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-08-25_

**Resumen:** Las fotos del usuario que se muestran en el cliente de Lync pueden diferir en función de la característica de Lync que use, como cuando se encuentre en una conferencia o en un chat de mensajería instantánea.

Lync 2010 ha presentado la habilidad de incluir una foto con su perfil de Lync que se muestra a otros usuarios de Lync. También puede elegir si desea mostrar las fotos de sus contactos en el cliente de Lync. En Lync 2013, la compatibilidad con fotos de alta resolución para los usuarios. En este tema se describe cómo el cliente de Lync obtiene y muestra fotos de usuario, dónde se almacenan, las limitaciones para cada origen de imagen y cómo los diferentes servicios de Lync usan las fotos del usuario.

<div>

## <a name="planning-considerations"></a>Consideraciones de planificación

Debe tener en cuenta lo siguiente al planear la implementación de la compatibilidad con fotos de usuario.

  - La compatibilidad con fotos de alta definición requiere que el buzón del usuario esté ubicado en Exchange 2013 y que la cuenta de usuario de Lync esté en el grupo de Lync 2013.

  - Las fotos de usuario de alta definición solo se admiten en un entorno en el que se usan Lync Server 2013 y Exchange 2013.

  - Los usuarios con buzones en Exchange 2010 siempre usarán el atributo **thumbnailPhoto** de AD DS como origen de su foto de usuario.

  - Una foto de usuario almacenada como el atributo **thumbnailPhoto** de AD DS no se mostrará a contactos externos/federados.

  - Si las fotos de los contactos de usuario se almacenan en AD DS, el archivo de imagen usado se limita a 96 × 96 píxeles y no más de 100 KB de tamaño de archivo.

  - Si se pierde la conectividad entre Lync Server y Exchange Server, se muestra la **thumbnailPhoto** de baja resolución del usuario de AD DS y solo a los usuarios internos.

  - Las fotos de usuario de alta resolución se muestran en las reuniones de Lync 2013 cuando un orador activo no tiene el vídeo habilitado. Además, al mover el mouse sobre la foto en miniatura de la galería, se mostrará la foto de alta resolución.

</div>

<div>

## <a name="user-photos-in-lync-2010"></a>Fotos de usuario en Lync 2010

En el cliente de Lync 2010, puede elegir entre dos opciones para mostrar una foto para el perfil, la **imagen corporativa predeterminada** y **Mostrar la imagen de una dirección web**.

<div>

## <a name="default-corporate-picture"></a>Foto corporativa predeterminada

Cuando elige la opción **imagen corporativa predeterminada** , Lync le muestra la foto de los servicios de dominio de Active Directory. La imagen que se usa es la imagen definida como el valor del atributo **thumbnailPhoto** en los servicios de dominio de Active Directory. Se trata del mismo archivo que usa Exchange para mostrar las imágenes en Outlook.

Entre las consideraciones para usar imágenes de los servicios de dominio de Active Directory se incluyen las siguientes:

  - Solo se admiten las imágenes con dimensiones de hasta 96 píxeles por 96 píxeles. El tamaño de archivo de la imagen está limitado a 100 KB.

  - De forma predeterminada, los usuarios pueden cambiar la imagen que se usa para el atributo **thumbnailPhoto** , aunque no directamente a través del cliente de Lync. Puede deshabilitar esto a través de los servicios de dominio de Active Directory.

  - Las imágenes almacenadas en los servicios de dominio de Active Directory no se muestran a los contactos externos a la organización, incluso si son contactos federados.

  - En las organizaciones grandes, el almacenamiento y la recuperación de las imágenes para un gran número de usuarios pueden afectar al tamaño y al rendimiento de la base de datos de servicios de dominio de Active Directory.

  - Las dimensiones de imagen y el tamaño de archivo limitados permiten que solo se usen imágenes de baja resolución.

<div>

## <a name="how-users-manage-their-user-photos-in-active-directory-domain-services"></a>Cómo administran los usuarios sus fotos de usuario en servicios de dominio de Active Directory

El usuario no puede cambiar la imagen usada en su perfil de servicios de dominio de Active Directory directamente a través del cliente de Lync 2010. Pueden usar una de las siguientes opciones para hacerlo, si está disponible:

  - ****   Los usuarios de SharePoint Server pueden cargar una foto en ' mi sitio ' en un servidor de SharePoint y, a continuación, [configurar la sincronización de perfiles en SharePoint](https://go.microsoft.com/fwlink/p/?linkid=507466) para sincronizar la foto con el atributo **thumbnailPhoto** en los servicios de dominio de Active Directory.

  - **Foto almacenada en URL**   accesibles públicamente los usuarios pueden configurar su foto de usuario especificando una dirección URL de acceso público para la imagen que desea usar. La imagen debe ser accesible públicamente sin una contraseña. La imagen almacenada en la dirección Web especificada se transfiere a otros usuarios a través de la categoría tarjeta de contacto en la información de presencia. Cuando el cliente de Lync necesita mostrar una foto de usuario, recupera la imagen de la dirección Web especificada.

  - **Los cmdlets de Exchange 2010 para administradores de Windows PowerShell**   pueden ejecutar el cmdlet [Import-RecipientDataProperty](https://go.microsoft.com/fwlink/p/?linkid=507468) en el shell de administración de Exchange 2010 en para administrar el atributo **thumbnailPhoto** . Cuando se importan imágenes con los cmdlets de Exchange 2010, el tamaño del archivo está limitado a 10 KB.

  - **Herramientas de terceros**   los usuarios pueden cargar solo su propia foto para el atributo **thumbnailPhoto** .

</div>

</div>

<div>

## <a name="show-a-picture-from-a-web-address"></a>Mostrar una foto de una dirección web

Cuando elige la opción **Mostrar una imagen de una dirección web** , Lync obtiene la imagen en la dirección que escribió y la muestra para su foto de usuario en Lync.

Entre las consideraciones para usar imágenes de una dirección web se incluyen las siguientes:

  - Los límites de tamaño de archivo los determina el atributo **MaxPhotoSizeKB** de la Directiva de cliente, definido con el cmdlet [New-CsClientPolicy](https://go.microsoft.com/fwlink/p/?linkid=507463) . El límite de tamaño predeterminado es de 30 KB. El valor máximo es 100 KB. No hay ninguna restricción en la resolución de la imagen, pero si intenta usar un archivo de imagen que supera el límite de tamaño, no se descargará a los clientes de Lync. Puede establecer el valor en 0 para deshabilitar el uso de todas las fotos del usuario en Lync.

  - Los contactos federados externos pueden ver las fotos de los usuarios de una dirección Web.

</div>

<div>

## <a name="managing-users-photo-with-client-policy-cmdlets"></a>Administrar la foto del usuario con los cmdlets de la Directiva de cliente

En Lync Server 2010, la configuración de la Directiva de cliente se configura con los cmdlets CsClientPolicy. La configuración de la Directiva configurada se envía a los clientes a través del aprovisionamiento en banda. Los dos parámetros de los cmdlets de CsClientPolicy que determinan la experiencia de foto de usuario son **DisplayPhoto** y **MaxPhotoSizeKB**. El parámetro de aprovisionamiento en banda correspondiente para **DisplayPhoto** y **MaxPhotoSizeKB** se denomina **fotouso**. Los valores para el parámetro de **fotouso** se envían a los clientes a través de la **endpointConfiguration** **provisionGroup**. Para obtener más información [, vea información general sobre la configuración y las directivas de cliente](https://go.microsoft.com/fwlink/?linkid=507470) .

El valor del parámetro **DisplayPhoto** determina el origen de la imagen de foto del usuario. Los valores admitidos se incluyen en la tabla siguiente.


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
<td><p>NoPhoto</p></td>
<td><p>none</p></td>
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


</div>

<div>

## <a name="how-lync-2010-client-gets-photos"></a>Cómo obtiene fotos el cliente 2010 de Lync

En Lync 2010, el servicio de libreta de direcciones administra las fotos del usuario en el servidor. El cliente de Lync obtiene las fotos del usuario consultando primero el servicio de consulta Web de libreta de direcciones (ABWQ) en el servidor, que se expone a través del servicio Web de expansión de lista de distribución. El cliente recibe el archivo de imagen y, a continuación, lo copia en la memoria caché del usuario para evitar descargar la imagen cada vez que debe mostrarse. Los valores de atributo devueltos de la consulta también se almacenan en la entrada del servicio de libreta de direcciones en caché para el usuario. El servicio de libreta de direcciones elimina todas las imágenes en caché cada 24 horas, lo que significa que puede tardar hasta 24 horas en actualizarse las nuevas imágenes de usuario en la memoria caché del servidor. Puede forzar una actualización a la caché mediante el cmdlet [Update-CsAddressBook](https://docs.microsoft.com/powershell/module/skype/Update-CsAddressBook) .

Las fotos del usuario incluidas en el estado de presencia también tienen un valor hash asociado que el cliente de Lync usa para determinar si hay una imagen más reciente disponible. El cliente recibe automáticamente una notificación de los cambios en el archivo de imagen que se usan en el estado de presencia.

<div class=" ">


> [!NOTE]  
> Como las fotos no se almacenan en la base de datos de GalContacts. dB, la descarga de fotos de usuario no depende de la configuración de <STRONG>AddressBookAvailability</STRONG> de la Directiva de cliente (<A href="https://go.microsoft.com/fwlink/p/?linkid=507508">set-CsClientPolicy</A>).



</div>

La consulta al servicio ABWQ incluye los siguientes atributos:

  - **Fotohash**   el valor hash de los datos de la foto binaria y se usa para determinar si la foto actual ha cambiado.

  - **PhotoRelPath**   la ruta de acceso relativa al archivo de imagen almacenado en el servidor.

  - **Tamaño en**bytes del archivo de imagen.   

  - **TimeStamp**   la fecha y la hora en la que el archivo de imagen se descargó del servidor por última vez y se copió a la memoria caché del cliente.

A continuación, después de recuperar el archivo de imagen, Lync 2010 Client compara los valores de atributo devueltos de la consulta con los valores de atributo recibidos por el cliente desde el aprovisionamiento en banda para ver si son diferentes. Si los valores son diferentes, el cliente recupera el archivo de imagen del usuario que ha iniciado sesión con una solicitud HTTP GET.

Además, el cliente comprueba el servidor cada 24 horas desde el momento en que se creó la versión en caché del archivo de imagen para comparar el valor del atributo **Fotohash** del servidor con el valor en el cliente. Si los valores son diferentes, el cliente sabe que el archivo de imagen ha cambiado. Para obtener el archivo de imagen actualizado, el cliente consulta de nuevo el servicio ABWQ para actualizar el archivo de imagen en la memoria caché del cliente con el archivo de imagen en el servidor, que también restablece la **marca de hora** en el archivo en la memoria caché del cliente.

La siguiente es una respuesta de ejemplo a una consulta al servicio ABWQ:
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

Lync 2013 ha incorporado compatibilidad para imágenes de alta resolución para fotos de usuario. Lync 2013 también incluye compatibilidad para almacenar fotos de usuario en el buzón de correo del usuario en Exchange 2013, lo que elimina la resolución de imagen y las limitaciones de tamaño presentes en Lync 2010. Las fotos de los usuarios en Lync 2013 pueden tener hasta 648 píxeles por 648 píxeles con un tamaño de archivo de hasta 20 MB. Las fotos de alta resolución en Lync 2013 deben estar ubicadas en el buzón del usuario en Exchange 2013 y solo son compatibles con el cliente de Lync 2013. Esta integración con Exchange aprovecha el nuevo marco de autorizaci? n que se incluye en las versiones 2013 de Lync, Exchange y SharePoint denominada OAuth.

Si no se usa Exchange 2013 en su implementación, la compatibilidad con fotos de usuario es la misma que con Lync 2010. Sin embargo, las opciones de usuario para elegir la foto que usar son diferentes en el cliente de Lync 2013. En el cliente de Lync 2013, los usuarios pueden seleccionar **ocultar mi foto** o **Mostrar mi foto**. La opción **Mostrar una imagen de un sitio web** no está disponible de forma predeterminada, pero se puede habilitar asignando una directiva de cliente.

<div>

## <a name="hide-my-picture"></a>Ocultar mi foto

La configuración de las fotos del usuario está en el cuadro de diálogo **Opciones** de Lync 2013. Cuando elija **ocultar mi**foto, no se mostrará ninguna foto de usuario en el cliente de Lync, pero la foto seguirá apareciendo en la tarjeta de contacto y fuera de Lync.

</div>

<div>

## <a name="show-my-picture"></a>Mostrar mi foto

Al elegir la opción **Mostrar mi** foto, la foto del usuario se muestra en el cliente de Lync y en los demás usuarios de las conversaciones de Lync. La imagen usada es la que se almacena en AD DS.

</div>

<div>

## <a name="show-a-picture-from-a-website"></a>Mostrar una imagen de un sitio web

La opción **Mostrar imagen de un sitio web** está disponible en Lync 2013 después de configurar una directiva de cliente para habilitarla. La versión de cliente debe ser posterior a 15.0.4535.1002, que se instala con las [actualizaciones acumulativas de Lync: noviembre de 2013](https://go.microsoft.com/fwlink/p/?linkid=509908). Es posible que los usuarios necesiten cerrar sesión y volver a iniciarla para ver los cambios en el cliente.

Puede establecer la Directiva de cliente para habilitar la **visualización de la imagen de una configuración de sitio web** mediante la ejecución de la directiva [set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy) en el shell de administración de Lync Server. Los cmdlets de ejemplo siguientes muestran cómo establecer la Directiva de forma global para todos los usuarios de la implementación:

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


Cuando se carga una imagen en el buzón de correo del usuario, Exchange crea automáticamente una versión de resolución inferior de la imagen que se puede usar en las aplicaciones cliente. La foto del usuario también se actualiza en AD DS.

<div class=" ">


> [!NOTE]  
> Cuando se actualiza un archivo de imagen en AD DS, se crea una imagen de 48 x 48 píxeles y se usa para thumbnailPhoto en AD DS. Se reemplaza cualquier imagen existente. Por lo tanto, si agregó una imagen de 96 x 96 a AD DS, se sobrescribirá con la nueva imagen de 48 x 48. Esto solo es importante si tiene usuarios en su entorno con clientes de Lync 2010, ya que dichos clientes obtendrán fotos de usuario de AD DS. Puede importar imágenes de 96 x 96 píxeles para reemplazar las creadas por AD DS si tiene clientes de Lync 2010 en su organización.



</div>

</div>

<div>

## <a name="user-photo-support-in-lync-2013"></a>Compatibilidad con fotos de usuario en Lync 2013

En Lync 2013, se admiten tres resoluciones de imagen para las fotos de usuario, como se describe en la siguiente tabla. La imagen que se usa está determinada por la configuración de directiva de cliente asignada a los usuarios de Lync. Para obtener más información, vea "administrar la foto del usuario con los cmdlets de la Directiva de cliente" en este tema.


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
<td><p>Se usa en el cliente de escritorio de Lync 2013 y en la aplicación Web de Lync 2013</p></td>
</tr>
</tbody>
</table>


Cualquier usuario con un buzón habilitado en Exchange 2013 puede cargar una imagen diferente, incluidas las fotos de alta resolución, a través de las opciones de cliente de Outlook Web Access o Lync 2013. La configuración recomendada para las imágenes que se usan incluye:

  - **Resolución de imagen**   648 por 648 píxeles

  - **Profundidad de color**   de 24 bits

  - **Tamaño de archivo de imagen**   de hasta 20 MB

  - ****   JPEG de formato de archivo

Una imagen JPEG típica de 24 bits, que es de 648 píxeles por 648 píxeles, tiene un tamaño de archivo de aproximadamente 240 KB, por lo que se necesitan 1 MB de espacio de almacenamiento para cada cuatro fotos de usuario.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

