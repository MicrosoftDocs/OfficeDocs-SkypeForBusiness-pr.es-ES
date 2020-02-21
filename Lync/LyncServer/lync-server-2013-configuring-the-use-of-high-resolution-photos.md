---
title: 'Lync Server 2013: configuración del uso de fotos de alta resolución'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the use of high-resolution photos in Lync Server 2013
ms:assetid: 995da78a-dc44-45a3-908d-16fe36cfa0d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688150(v=OCS.15)
ms:contentKeyID: 49733753
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5a49618cd4039163f22d44f358c29a802037b8b8
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42209316"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-the-use-of-high-resolution-photos-in-microsoft-lync-server-2013"></a>Configuración del uso de fotos de alta resolución en Microsoft Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-02-05_

Microsoft Lync Server 2010 proporcionó a los usuarios la posibilidad de ver fotos de sus contactos (y hacer que sus propias fotos estén disponibles para otros usuarios). Normalmente, estas fotos se almacenaban como parte del atributo thumbnailPhoto del usuario en Active Directory. Eso suponía una seria limitación para el tamaño y la resolución de las fotos: el atributo thumbnailPhoto solo puede contener una fotos con un tamaño máximo de 48 píxeles por 48 píxeles.

Sin embargo, en Microsoft Lync Server 2013, las fotos se pueden almacenar en el buzón de correo de Microsoft Exchange Server 2013 de un usuario; que permite tamaños de foto de hasta 648 píxeles por 648 píxeles. Además, Exchange 2013 puede cambiar el tamaño de estas fotos automáticamente para usarlas en diferentes productos según sea necesario. Normalmente, esto significa tres tamaños y resoluciones de foto diferentes:

  - 48 píxeles por 48 píxeles, es el tamaño usado por el atributo thumbnailPhoto de Active Directory. Si carga una foto en Exchange 2013 Exchange creará automáticamente una versión de 48 píxeles por 48 píxeles de dicha foto y actualizará el atributo thumbnailPhoto del usuario. Sin embargo, tenga en cuenta que el valor inverso no es verdadero: Si actualiza manualmente el atributo thumbnailPhoto en Active Directory, la foto en el buzón de Exchange 2013 del usuario no se actualizará automáticamente.

  - 96 píxeles por 96 píxeles, para su uso en Microsoft Outlook 2013 Web App, Microsoft Outlook 2013, Microsoft Lync Web App y Lync 2013.

  - 648 píxeles por 648 píxeles para su uso en Lync 2013 y Microsoft Lync Web App.

<div>


> [!NOTE]  
> Si tiene los recursos, es recomendable que cargue fotos de 648x648, ya que proporcionan la resolución máxima y una calidad de imagen óptima en cualquiera de las aplicaciones de Office 2013. Cada foto JPEG con un tamaño de 648x648 y una profundidad de 24 bits produce un tamaño de archivo de 240 kilobytes aproximadamente. Eso significa que necesitará aproximadamente 1 megabyte de espacio en disco por cada 4 fotos de usuario.



</div>

Las fotos de alta resolución, a las que se tiene acceso a través de los servicios web Exchange, pueden cargarlas los usuarios que ejecutan Outlook 2013 Web App; los usuarios solo pueden actualizar su propia foto. Los administradores, sin embargo, pueden actualizar la foto de cualquier usuario mediante el shell de administración de Exchange y una serie de comandos de Windows PowerShell similares a los siguientes:

    $photo = ([Byte[]] $(Get-Content -Path "C:\Photos\Kenmyer.jpg" -Encoding Byte -ReadCount 0))
    Set-UserPhoto -Identity "Ken Myer" -PictureData $photo -Confirm:$False
    Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False

El primer comando del ejemplo anterior utiliza el cmdlet Get-Content para leer el contenido del archivo C:\\fotos\\kenmyer. jpg y almacenar los datos en una variable llamada $Photo. En el segundo comando, el cmdlet Set-UserPhoto de Exchange se usa para cargar la foto y adjuntarla a la cuenta de usuario de Ken Myer.

<div>


> [!NOTE]  
> En este ejemplo, el nombre para mostrar de Active Directory de Ken Myer se usa como identidad de la cuenta. También puede hacer referencia a una cuenta de usuario usando otros identificadores como la dirección SMTP del usuario o su nombre principal de usuario. Consulte la documentación del cmdlet Set-UserPhoto en <A href="https://go.microsoft.com/fwlink/p/?linkid=268536">https://go.microsoft.com/fwlink/p/?LinkId=268536</A> para obtener más información



</div>

Cargar la fotografía no equivale a asignarla a la cuenta de usuario de Ken Myer. Al cargar la fotografía, el resultado es que se muestra una vista previa de dicha fotografía en la página Opciones de Outlook Web App. Para asignar realmente la fotografía a la cuenta de usuario, debe hacer clic en **Guardar** en la página Opciones o el administrador debe ejecutar el tercer comando del ejemplo. Ese tercer comando usa el parámetro Save para asignar la fotografía a la cuenta de usuario de Ken Myer:

    Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False

Para comprobar que la nueva foto se ha asignado a la cuenta de usuario, Ken Myer puede iniciar sesión en Lync 2013, seleccione **Opciones**y, a continuación, seleccione **mi foto**. La foto recién cargada debe mostrarse como la foto personal de Ken. Otra opción para comprobar la foto de cualquier usuario es que los administradores inicien Internet Explorer y naveguen a una dirección URL similar a esta:

    https://atl-mail-001.litwareinc.com/ews/Exchange.asmx/s/GetUserPhoto?email=kenmyer@litwareinc.com&size=HR648x648

Si el administrador puede ver la foto con Internet Explorer pero el usuario no puede ver su foto en Lync 2013, eso suele indicar un problema de conectividad con los servicios web Exchange o con el servicio Detección automática de Exchange.

Tenga en cuenta que no es necesario realizar ninguna configuración adicional para que esta foto esté disponible en Lync 2013. En su lugar, la foto estará disponible al instante una vez que se haya cargado y se haya ejecutado el cmdlet Set-UserPhoto.

</div>

<span> </span>

</div>

</div>

</div>

