---
title: "Configuración del uso de fotografías de alta resolución en Microsoft Lync Server 2013"
TOCTitle: "Conf. de l’util. de photos haute résolution dans Microsoft Lync Server 2013"
ms:assetid: 995da78a-dc44-45a3-908d-16fe36cfa0d9
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ688150(v=OCS.15)
ms:contentKeyID: 49889396
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuración del uso de fotografías de alta resolución en Microsoft Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

Microsoft Lync Server 2010 permitía a los usuarios ver las fotos de sus contactos (y hacer que sus propias fotos estuvieran disponibles para los demás). Normalmente, estas fotos se almacenaban como parte del atributo thumbnailPhoto del usuario en Active Directory. Eso suponía una seria limitación para el tamaño y la resolución de las fotos: el atributo thumbnailPhoto solo puede contener una fotos con un tamaño máximo de 48 píxeles por 48 píxeles.

Sin embargo, en Microsoft Lync Server 2013 las fotos se pueden almacenar en un buzón de Microsoft Exchange Server 2013 del usuario, lo que permite tamaños de foto de 648 píxeles por 648 píxeles. Además, Exchange 2013 puede cambiar automáticamente el tamaño de las fotos para usarlas en diferentes productos según se necesiten. Normalmente, esto significa tres tamaños y resoluciones de foto diferentes:

  - 48 píxeles por 48 píxeles, es el tamaño usado por el atributo thumbnailPhoto de Active Directory. Si carga una foto a Exchange 2013, Exchange creará automáticamente una versión de 48 píxeles por 48 píxeles de dicha fotos y actualizará el atributo thumbnailPhoto del usuario. No obstante, tenga en cuenta que lo contrario no es posible: si actualiza manualmente el atributo thumbnailPhoto en Active Directory, la foto del buzón de Exchange 2013 del usuario no se actualizará automáticamente.

  - 96 píxeles por 96 píxeles, para su uso en Microsoft Outlook 2013 Web App, Microsoft Outlook 2013, Microsoft Lync Web App y Lync 2013.

  - 648 píxeles por 648 píxeles, para su uso en Lync 2013 y Microsoft Lync Web App.


> [!NOTE]
> Si tiene los recursos, es recomendable que cargue fotos de 648x648, ya que proporcionan la resolución máxima y una calidad de imagen óptima en cualquiera de las aplicaciones de Office 2013. Cada foto JPEG con un tamaño de 648x648 y una profundidad de 24 bits produce un tamaño de archivo de 240 kilobytes aproximadamente. Eso significa que necesitará aproximadamente 1 megabyte de espacio en disco por cada 4 fotos de usuario.



Los usuarios que utilizan Outlook 2013 Web App pueden cargar fotos de alta resolución, a las que se accede mediante los servicios web de Exchange; los usuarios solo pueden actualizar su propia foto. No obstante, los administradores pueden actualizar la foto de cualquier usuario mediante el Shell de administración de Exchange y una serie de comandos de Windows PowerShell similar a la siguiente:

    $photo = ([Byte[]] $(Get-Content -Path "C:\Photos\Kenmyer.jpg" -Encoding Byte -ReadCount 0))
    Set-UserPhoto -Identity "Ken Myer" -PictureData $photo -Confirm:$False
    Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False

El primer comando del ejemplo anterior usa el cmdlet Get-Content para leer el contenido del archivo C:\\Photos\\Kenmyer.jpg y almacenar dichos datos en una variable denominada $photo. En el segundo comando, se utiliza el cmdlet Set-UserPhoto de Exchange para cargar la foto y adjuntarla a la cuenta de usuario de Ken Myer.


> [!NOTE]
> En este ejemplo, el nombre para mostrar de Active Directory de Ken Myer se usa como identidad de la cuenta. También puede hacer referencia a una cuenta de usuario usando otros identificadores como la dirección SMTP del usuario o su nombre principal de usuario. Consulte la documentación del cmdlet Set-UserPhoto en <A href="http://go.microsoft.com/fwlink/?linkid=268536%26clcid=0xc0a">http://go.microsoft.com/fwlink/?linkid=268536&amp;clcid=0xC0A</A> para obtener más información.



Cargar la fotografía no equivale a asignarla a la cuenta de usuario de Ken Myer. Al cargar la fotografía, el resultado es que se muestra una vista previa de dicha fotografía en la página Opciones de Outlook Web App. Para asignar realmente la fotografía a la cuenta de usuario, debe hacer clic en **Guardar** en la página Opciones o el administrador debe ejecutar el tercer comando del ejemplo. Ese tercer comando usa el parámetro Save para asignar la fotografía a la cuenta de usuario de Ken Myer:

    Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False

Para comprobar que la nueva foto se ha asignado a la cuenta de usuario, Ken Myer puede iniciar sesión en Lync 2013, seleccionar **Opciones** y, después, seleccionar **Mi foto**. La foto recién cargada debe mostrarse como la foto personal de Ken. Otra opción para comprobar la foto de cualquier usuario es que los administradores inicien Internet Explorer y naveguen a una dirección URL similar a esta:

    https://atl-mail-001.litwareinc.com/ews/Exchange.asmx/s/GetUserPhoto?email=kenmyer@litwareinc.com&size=HR648x648

Si el administrador puede ver la foto usando Internet Explorer pero el usuario no puede ver su propia foto en Lync 2013, normalmente es señal de que hay un problema de conectividad con los servicios web de Exchange o con el servicio de detección automática de Exchange.

Observe también que no se requiere ninguna configuración adicional para poner disponible esta fotografía en Lync 2013. Es decir, al cargar la foto y ejecutar el cmdlet Set-UserPhoto, la fotografía queda automátiamente disponible.

